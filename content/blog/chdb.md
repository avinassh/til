+++
title = "chDB"
date = "2024-03-17T10:48:48+05:30"

tags = ["embedded", "duckdb", "chdb", "clickhouse"]
+++

I find the entire story of chDB fascinating.

chDB is an embedded ClickHouse. ClickHouse comes with a binary called ClickHouse Local, which chDB wraps around and makes it super easy to run ClickHouse locally.

![image4](https://github.com/avinassh/dump/assets/640792/ae8dc0af-f68a-4cb7-9a9a-ab2d674313ef)

The author Auxten wanted to do some data analysis in Jupyter Notebook, so he created chDB. It was launched last year, February 2023.

The project became super popular in an year, deservingly so.

Now, Auxten has joined ClickHouse to work on chDB full time!

This is a beautiful story of open source, and databases.

1. [The birth of chDB](https://auxten.com/the-birth-of-chdb/)
2. [chDB is joining ClickHouse](https://auxten.com/chdb-is-joining-clickhouse/) and [Welcome, chDB](https://clickhouse.com/blog/welcome-chdb-to-clickhouse) 