+++
title = "User defined order in SQL"
date = "2024-03-10T15:35:01+05:30"
tags = ["sqlite","database","sql"]
+++

Imagine you are building a to-do list app where users maintain a list: 

```
┌─────────────────────┬─────┐
│        task         │ pos │
├─────────────────────┼─────┤
│ share TIL           │   1 │
│ walk                │   2 │
│ milk                │   3 │
│ github issue #12    │   4 │
└─────────────────────┴─────┘
```

If the priority of some item changes or a new item is added, all the items need to be reordered! 

```
┌─────────────────────┬─────┐
│        task         │ pos │
├─────────────────────┼─────┤
│ share TIL           │   1 │
│ movie               │   2 │  ←
│ walk                │   3 │  ↓
│ milk                │   4 │  ↓
│ github issue #12    │   5 │  ↓
└─────────────────────┴─────┘
```

If you were storing this in a database, you would essentially have to execute multiple operations (one new insert and several updates). How do you handle this efficiently? 

I would probably use Sorted Sets in Redis, and consider the problem solved. However, what if your dataset is so massive that you cannot use Redis and need to store the data on disk?

1. [How to rerank one row in a big set of rows?](https://sqlite.org/forum/forumpost/e08e13bf2c06d4bf?t=h)
2. [User-defined Order in SQL](https://begriffs.com/posts/2018-03-20-user-defined-order.html)