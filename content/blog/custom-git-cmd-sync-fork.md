+++
title = "Custom git command to sync a fork"
date = "2024-02-27T13:30:57+05:30"
tags = ["git",]
+++

Just added a short git custom command to sync my forks with the source.

Add a new file called `git-sync` and make it available in your path. You can keep this file anywhere. I have kept it in `~/git-scripts/git-sync`. You need [`gh` CLI](https://cli.github.com/) installed and make sure to use your github name:

```bash
# copied from oh-my-zsh/lib/git.zsh
function git_current_branch() {
  local ref
  ref=$(__git_prompt_git symbolic-ref --quiet HEAD 2> /dev/null)
  local ret=$?
  if [[ $ret != 0 ]]; then
    [[ $ret == 128 ]] && return  # no git repo.
    ref=$(__git_prompt_git rev-parse --short HEAD 2> /dev/null) || return
  fi
  echo ${ref#refs/heads/}
}

gh repo sync avinassh/$(basename "$(pwd)")
git pull origin "$(git_current_branch)"
```

Set the file permission to allow execution and then you can run `git sync`:

```shell
$ chmod +x ~/git-scripts/git-sync

$ git sync
✓ Synced the "avinassh:main" branch from "tursodatabase:main"
From github.com:avinassh/libsql
 * branch            HEAD       -> FETCH_HEAD
Already up to date.
```