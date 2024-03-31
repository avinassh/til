+++
title = "git rebase with `--exec`"
date = "2024-03-31T09:19:51+05:30"

tags = ["git"]
+++

While rebasing, you can pass a cmd to run and rebase stops if the command fails. For e.g. you can run tests with the rebase and find out a broken commit.

```bash
git rebase --exec "cmd.sh"
```

An equivalent would be, do git rebase without exec, then run git bisect if the tests fail. So, depending on the workflow, you may choose either of options.

There are some more tricks here - [git as debugging tool
](https://lucasoshiro.github.io/posts-en/2023-02-13-git-debug/)