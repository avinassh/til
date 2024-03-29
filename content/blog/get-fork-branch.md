+++
title = "Getting a branch from fork or a pull request"
date = "2024-03-29T12:48:15+05:30"

tags = ["git", "github", "pull request"] 
+++

Sometimes you get a patch or a pull request from an external contributor, this is how you get those changes locally.

1. I wanted to get this branch locally: https://github.com/penberg/libsql/tree/durable-wal

the git command is:

```
# git fetch git://repo-address target-branch:my-branch
git fetch git@github.com:penberg/libsql.git durable-wal:wal
```

2. If you want to pull a branch from a pull request from Github:

```
# git pull origin pull/<pull request number>/head
# to get https://github.com/tursodatabase/libsql/pull/1170

git checkout -b test-pr
git pull origin pull/1170/head
```