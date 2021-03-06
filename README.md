# Spring 2020 Computer and Network Administration — Assignment 2

* **Do not edit this file.**
* **Do not start this project until you have read these instructions carefully.**

---

## Before You Begin
1. Log in to GitHub.
2. Fork this repo(sitory). See [this video](http://code-warrior.github.io/tutorials/git/github/forking-and-cloning-at-the-github-web-site/) on how to carry out this step and step `3`.
3. Clone your fork, using either the web site or the GitHub Desktop client.
4. Checkout your personalized branch, the one with your name and GitHub user handle.

---

## Directions
All your answers must be included in the fenced region marked by back ticks and the word `bash`.

---

## Due Date
⏰ **Thursday, 2 April 2020, at 10:00 AM. At that time, the repo will be closed and will not accept any more submissions. 🚫 _No late work will be accepted._**

---

## Submission
Issue a pull request back into the original repo, the one from which your forked was created, before the deadline. [Look at these videos](http://code-warrior.github.io/tutorials/git/github/) for help on how to do so.

**Note**: This assignment may *only* be submitted via GitHub. 🚫 **_No other form of submission will be accepted_**.

---

## /1 Create a Global Pre Commit Hook
Write a global pre-commit hook that reports whether a commit is the first or subsequent commit to the repo, and also checks for un-necessary whitespace in a file, such as trailing whitespace on a line and extra newlines. You will need to modify `pre-commit.sample`, which is available under `.git/hooks` in every basic Git repo on your machine. (**50pts**)

A new commit should generate the following output:

```
pre-commit: About to create the first commit...
pre-commit: Testing for whitespace errors 😨
pre-commit: No whitespace errors 😀
[master (root-commit) f683f23] Initial commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 file.txt
```

```bash
```

Every subsequent commit should generate the following output:

```
pre-commit: About to create a new commit...
pre-commit: Testing for whitespace errors 😨
pre-commit: No whitespace errors 😀
[master 79e878d] Add content to file.txt
 1 file changed, 1 insertion(+)
```

```bash
```

Trailing whitespace on a line and extra newlines should generate the following output:

```
pre-commit: About to create a new commit...
pre-commit: Testing for whitespace errors 😨
file.txt:4: trailing whitespace.
+
file.txt:2: new blank line at EOF.
pre-commit: Aborting commit due to whitespace errors ☹️
```

```bash
```

When you’re done, do the following:

A. Copy the contents of your global Git config settings and paste it below. Use the following command to do so: `git config --global | pbcopy`. (This assumes you’ve installed the environment profile from our class’ examples folder.)

```bash
```

B. Place the entire contents of your pre commit hook in the included file `pre-commit`.

## /2 Flush and Backup a File
Write a script that backups the `/var/log/kern.log` file to a file called `kern.log.backup`, then resets its contents to an empty file. Your script in this case should return 0. If `/var/log/kern.log` is empty, do nothing and return an exit status of `1`. Echo the status of each event in the script. For example, before copying the log file, indicate that the script is about to copy the file. Make the interaction with the script as informative as possible. Add the contents of your finished script to the included `kernel-log-backup.sh`. (**50pts**)
