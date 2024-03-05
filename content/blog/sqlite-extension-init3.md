+++
title = "SQLITE_EXTENSION_INIT3"
date = "2024-03-05T10:25:19+05:30"
tags = ["sqlite", "extensions"]
+++

We use [sqlean extensions](https://github.com/nalgeon/sqlean) at [Turso](https://turso.tech/). I was debugging something, and I was looking at sqlean's source code. One thing that caught my attention was the usage of `SQLITE_EXTENSION_INIT3`.

Google or SQLite documentation returned nothing. The only usage I could find was in [SQLite's source code](https://github.com/sqlite/sqlite/blob/1828149/src/sqlite3ext.h#L709,L710). It has no comments, and my noob ass couldn't figure out what it does in C.

Fornutately, I found [this comment](https://github.com/rusqlite/rusqlite/issues/524#issuecomment-507787350) by jrandall in rusqlite's GitHub issue, which explains what it is for:

> The `SQLITE_EXTENSION_INIT3` macro is an alternative to `SQLITE_EXTENSION_INIT2` (i.e. you use one or the other but not both). It is used when you have code that needs to talk to sqlite from within an extension (i.e. linked into an extension), but which does not itself include the extension entrypoint (i.e. because it is compiled into a separate object or library file).
>
> In `sqlite3ext.h` this is defined as:
>
> ```c
> # define SQLITE_EXTENSION_INIT3     \
>    extern const sqlite3_api_routines *sqlite3_api;
> ```
>
> The idea is that the code that calls `SQLITE_EXTENSION_INIT3` is embedded within (i.e. linked into) a sqlite extension, and so the sqlite3_api global is an extern that is expected to be provided by the extension itself (which will have called `SQLITE_EXTENSION_INIT2` when it is initialized).

Other than this one comment, there are no other explanations on the entire internet.

Looking at the `math` extension source code [1](https://github.com/nalgeon/sqlean/blob/ffa39c3/src/sqlite3-math.c), [2](https://github.com/nalgeon/sqlean/blob/ffa39c3/src/math/extension.c) confirms the usage.

