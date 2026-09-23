## Git Commands Used:

```text
(base) Ethan@MacBook-Pro-7 oose-hw6 % mkdir task2
(base) Ethan@MacBook-Pro-7 oose-hw6 % cd task2
(base) Ethan@MacBook-Pro-7 task2 % git init -b main
Initialized empty Git repository in /Users/Ethan/Desktop/JHU/JHU F26/OOSE_F26/oose-hw6/task2/.git/
(base) Ethan@MacBook-Pro-7 task2 % git rev-parse --show-toplevel
/Users/Ethan/Desktop/JHU/JHU F26/OOSE_F26/oose-hw6/task2
(base) Ethan@MacBook-Pro-7 task2 % git config --local push.default simple
(base) Ethan@MacBook-Pro-7 task2 % git config --local push.autoSetupRemote false
(base) Ethan@MacBook-Pro-7 task2 % printf 'This is a readme file!\n' > README.md
(base) Ethan@MacBook-Pro-7 task2 % git add README.md
(base) Ethan@MacBook-Pro-7 task2 % git commit -m "Add initial README"
[main (root-commit) bf7158d] Add initial README
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch main
nothing to commit, working tree clean
(base) Ethan@MacBook-Pro-7 task2 % git remote add origin git@github.com:ethanbabel/oose-hw6-task2.git
(base) Ethan@MacBook-Pro-7 task2 % git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 241 bytes | 241.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:ethanbabel/oose-hw6-task2.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
(base) Ethan@MacBook-Pro-7 task2 % printf 'This is a local readme file!\n' > README.md
(base) Ethan@MacBook-Pro-7 task2 % git add README.md
(base) Ethan@MacBook-Pro-7 task2 % git commit -m "Update README locally"
[main 0a21952] Update README locally
 1 file changed, 1 insertion(+), 1 deletion(-)
(base) Ethan@MacBook-Pro-7 task2 % git push
To github.com:ethanbabel/oose-hw6-task2.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:ethanbabel/oose-hw6-task2.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) Ethan@MacBook-Pro-7 task2 % git fetch origin
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 925 bytes | 231.00 KiB/s, done.
From github.com:ethanbabel/oose-hw6-task2
   bf7158d..ea3aec2  main       -> origin/main
(base) Ethan@MacBook-Pro-7 task2 % git merge origin/main
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
(base) Ethan@MacBook-Pro-7 task2 % printf 'This is a readme file!\n' > README.md
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Ethan@MacBook-Pro-7 task2 % git add README.md
(base) Ethan@MacBook-Pro-7 task2 % git commit -m "Resolve README conflict with required final text"
[main 5c3c963] Resolve README conflict with required final text
(base) Ethan@MacBook-Pro-7 task2 % git push
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 11 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 489 bytes | 489.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:ethanbabel/oose-hw6-task2.git
   ea3aec2..5c3c963  main -> main
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Ethan@MacBook-Pro-7 task2 % git switch -c feature1
Switched to a new branch 'feature1'
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch feature1
nothing to commit, working tree clean
(base) Ethan@MacBook-Pro-7 task2 % printf 'This is feature 1!\n' > FEATURE1.md
(base) Ethan@MacBook-Pro-7 task2 % git add FEATURE1.md
(base) Ethan@MacBook-Pro-7 task2 % git commit -m "Add feature 1"              
[feature1 517ef63] Add feature 1
 1 file changed, 1 insertion(+)
 create mode 100644 FEATURE1.md
(base) Ethan@MacBook-Pro-7 task2 % git push
fatal: The current branch feature1 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature1

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

(base) Ethan@MacBook-Pro-7 task2 % git push -u origin feature1
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 11 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 290 bytes | 290.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'feature1' on GitHub by visiting:
remote:      https://github.com/ethanbabel/oose-hw6-task2/pull/new/feature1
remote: 
To github.com:ethanbabel/oose-hw6-task2.git
 * [new branch]      feature1 -> feature1
branch 'feature1' set up to track 'origin/feature1'.
(base) Ethan@MacBook-Pro-7 task2 % git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Ethan@MacBook-Pro-7 task2 % git pull --ff-only origin main
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 897 bytes | 299.00 KiB/s, done.
From github.com:ethanbabel/oose-hw6-task2
 * branch            main       -> FETCH_HEAD
   5c3c963..c2175c9  main       -> origin/main
Updating 5c3c963..c2175c9
Fast-forward
 FEATURE1.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 FEATURE1.md
(base) Ethan@MacBook-Pro-7 task2 % git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Ethan@MacBook-Pro-7 task2 % cat README.md
This is a readme file!
(base) Ethan@MacBook-Pro-7 task2 % cat FEATURE1.md
This is feature 1!
```

## Link to task2 repo:
[task2](https://github.com/ethanbabel/oose-hw6-task2)
