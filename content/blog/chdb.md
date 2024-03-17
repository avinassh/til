+++
title = "chDB"
date = "2024-03-17T10:48:48+05:30"

tags = ["embedded", "duckdb", "chdb", "clickhouse"]
+++

I find the entire story of chDB fascinating.

chDB is an embedded ClickHouse. ClickHouse comes with a binary called ClickHouse Local, which chDB wraps around and makes it super easy to run ClickHouse locally.

![image4](https://private-user-images.githubusercontent.com/640792/313447640-ae8dc0af-f68a-4cb7-9a9a-ab2d674313ef.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTA2NTQwNTksIm5iZiI6MTcxMDY1Mzc1OSwicGF0aCI6Ii82NDA3OTIvMzEzNDQ3NjQwLWFlOGRjMGFmLWY2OGEtNGNiNy05YTlhLWFiMmQ2NzQzMTNlZi5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMzE3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDMxN1QwNTM1NTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wYmY4ZWM2MjY5ZDcwYWVjZDJkMGM4MzE0NjY2YWY4ZWZmOWM0MjkxZTY5NTZjOGNmOTEwZTM1YjIwZTM2OTRlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.EVvyzik3pW7g-ZfQr73dhUYhvGtwHVcq4c91R-N59wg)

The author Auxten wanted to do some data analysis in Jupyter Notebook, so he created chDB. It was launched last year, February 2023.

The project became super popular in an year, deservingly so.

Now, Auxten has joined ClickHouse to work on chDB full time!

This is a beautiful story of open source, and databases.

1. [The birth of chDB](https://auxten.com/the-birth-of-chdb/)
2. [chDB is joining ClickHouse](https://auxten.com/chdb-is-joining-clickhouse/) and [Welcome, chDB](https://clickhouse.com/blog/welcome-chdb-to-clickhouse) 