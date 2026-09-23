# Task 1: Refactoring

## 1. Getting a person's credit score

The related arguments are a Data Clumps smell. Namely, `personFirstName`,
`personLastName`, `personSSN`, and `personAdddress` all describe the same person,
but the method receives them separately. This causes an unnecessarily long
parameter list, making the call is harder to read and maintain, and making it easy to
accidentally swap arguments with the same type. 

I would group these values in a `Person` object and change `getCreditScore` to
accept that object:

```java
// Before
int score = cA.getCreditScore(personFirstName, personLastName,
                            personSSN, personAdddress);

// After: person contains the identity and address information needed by cA.
int score = cA.getCreditScore(person);
```

This gives the related information a single home and makes the relationship
between the arguments explicit. It also lets the object own any shared validation
instead of duplicating it across callers.

## 2. The `Person` class

The smell is Primitive Obsession, with an occurrence in each of `fullName`,
`mailingAddress`, and `email`. Each field represents a domain concept, but all
three are stored as general-purpose strings. Although Java's `String` is a class,
using strings in place of meaningful domain types still falls under this smell.

I would introduce dedicated types:

```java
public class Person {
    private PersonName fullName;
    private MailingAddress mailingAddress;
    private EmailAddress email;

    // Constructor and methods use these domain types.
}
```

- `PersonName` would own the name representation and any name-formatting rules
  the application needs.
- `MailingAddress` would hold the address components required by the application
  and own their validation and formatting.
- `EmailAddress` would wrap the email value and enforce the application's email
  validation rules when it is created.

These classes can still use strings internally, but the improvement is that the
meaning and relevant behavior are encapsulated in distinct types. For example,
an `EmailAddress` cannot accidentally be passed where a `MailingAddress` is
expected. I would move existing validation and formatting into these types and
update callers while preserving the application's existing behavior. The amount
of structure in each type should follow actual domain requirements.
