**CPEN 221 / Fall 2020 / Lab 4A**

# Git Branching and Merging

One important aspect of using a source code control system is to manage simultaneous updates to the code base and to merge the changes. To familiarize yourselves with this aspect of `git`, read [A Hacker’s Guide to Git](http://wildlyinaccurate.com/a-hackers-guide-to-git/).

## Resolving Conflicts

To understand how one can resolve conflicts, follow these steps. This task is set up so that one person can complete all the steps (including creating the conflict) although conflicts are more common when multiple people are contributing to a project. This is not the only way to resolve a conflict but it is intended to be a start.

- **Clone your assigned Github repository**: `git clone <https://github.com/CPEN-221-2020/><your-repo> lab4a` which will clone the repo in a local directory `lab4a`.
- Change to the `lab4a` directory and create a new branch `b1` and switch to it: `git branch b1` followed by `git checkout b1`
- Add an empty file named `README.txt` in the `lab4a` directory and push to Github:

```
git add README.txt
git commit -m "Added README"
git push origin b1
```

- Now, from the parent directory for `lab4a`, clone branch `b1` of your repository using the command: `git clone -b b1 <https://github.com/CPEN-221-2020/><your-repo> lab4a1` which will clone the repo in a local directory `lab4a1`. (This would allow the two cloned repositories to be on the same machine, if necessary.)
- In the `lab4a1` directory, add the following line to `README.txt`: `Hello from Lab4a1`. Then commit and push the change to Github.
- In the `lab4a` directory, add the following line to `README.txt`: `Hello from Lab4a.` Commit this change and execute a `pull`: `git pull`
- Git will indicate that there is a merge conflict.
- Edit `README.txt` in `lab4a` to have the two lines in the correct order (`Lab4a` before `Lab4a1`). You will remove the conflict indicators placed by Git.
- Add, commit and push `README.txt` from `lab4a1`.

## Merging Branches

- In `lab4a`, switch to the `master` branch:

   ```java
   git checkout master
   ```

- You should not see `README.txt` in your directory for now.

- Now add any new file to this directory, then add, and commit this file to the repository.

- Now, merge the `master` branch with the `b1` branch:

```java
git merge b1
```

- At this point you should see `README.txt` and the new file that you added. The two branches have been merged and you can keep working on the `master` branch.