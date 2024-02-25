+++
title = "SwissTable"
date = "2024-02-25T21:52:31+05:30"
tags = ["hashmap",]
+++

SwissTable is an hash map implementation which is faster but takes significantly less memory. It was developed by Google and released in 2016. This is so good that [Rust standard library](https://github.com/rust-lang/hashbrown) has it by default. There is an [ongoing effort](https://github.com/golang/go/issues/54766) to put that in Go too.

Go's std library has open hashing scheme, the hashed keys are put in a bucket. SwissTable uses closed hashing scheme, it puts the data in an array, finds the spot by probing the array.

Links:
- Announcement blog post - (link)[https://abseil.io/blog/20180927-swisstables]
- [Designing a Fast, Efficient, Cache-friendly Hash Table, Step by Step](https://youtu.be/ncHmEUmJZf4) - This is an intro video, which shows a how a typical hash table is built in languages, then step by step it discards and builds SwissTable from scratch.
- Two years later, they released one more video with the updates - [Abseil's Open Source Hashtables: 2 Years In](https://www.youtube.com/watch?v=JZE3_0qvrMg)
- DoltHub ported this to Go, called [SwissMap](https://www.dolthub.com/blog/2023-03-28-swiss-map/)