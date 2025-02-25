---
title: How to Commit
sidebar_position: 2
---

# How to Commit

## 0. Preface
Apache InLong uses github's Pull Request (PR) to receive contributed code. This document will introduce the process of code commit in detail.

- InLong code base：https://github.com/apache/incubator-inlong

- InLong website base：https://github.com/apache/incubator-inlong-website

## 1. Fork the repository

Open [apache/incubator-inlong](https://github.com/apache/incubator-inlong) 's github page, clicking on the `fork` button at the top right to fork.

## 2. Configure git and commit changes

### 2.1 Clone your fork to your local machine

```shell
git clone https://github.com/<your_github_name>/incubator-inlong.git
```

After clone is completed, `origin` will linked to the remote fork address on github by default.

### 2.2 Add apache/incubator-inlong to local repository's remote branch upstream

```shell
cd  incubator-inlong
git remote add upstream https://github.com/apache/incubator-inlong.git
```

### 2.3 Check remote repository settings
              
```shell
git remote -v
origin    https://github.com/<your_github_name>/incubator-inlong.git (fetch)
origin    https://github.com/<your_github_name>/incubator-inlong.git(push)
upstream  https://github.com/apache/incubator-inlong.git (fetch)
upstream  https://github.com/apache/incubator-inlong.git (push)
```

There will be two repositories: `origin` (own repository) and `upstream` (official repository).

### 2.4 Fetch code from upstream and update the local master branch code to the latest

```shell
git fetch upstream
git pull upstream master
```

### 2.5 Create a new branch
> Generally, issue id is used as the branch name, such as: INLONG-123

```shell
git checkout -b INLONG-123
```

**Make sure that the branch `INLONG-123` is building successfully on the latest code of the official master branch**

After the branch is created, you can start coding.

### 2.6 Commit code to remote branch
> The format of the commit message must be consistent with the issue title and start with `[issue id]`, such as `[INLONG-123] xxx`:
```shell
git commit -a -m "[INLONG-123] xxx"
git push origin INLONG-123
```

## 3. Open a Pull Request
### 3.1 Open your github repository page
   `https://github.com/<your_github_name>/incubator-inlong`
### 3.2. Switch branch
   Switch to committed branch `INLONG-123`
### 3.3. New pull request
   Click `New pull request` or `Compare & pull request`
### 3.4. Click `Create pull request` button to open a PR
   Considerations when opening a pull request:
      1. The title of PR must start with issue id, which is better consistent with the commit message
      2. You can fill in some description information or not
      3. If a code conflict is prompted after clicking `Create pull request` , please synchronize the code of the `INLONG-123` branch with the master branch and commit it

## 4. Code Review
After creating PR, everyone can review your code and may discuss some implementation details with you, and you may need to modify them further.

**Generally, the PR can be formally merged into the code base only after more than 2 PPMC/Committer reply + 1.**

Finally, congratulations on becoming an official contributor to InLong!