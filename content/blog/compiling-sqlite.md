+++
title = "Compiling SQLite"
date = "2024-02-25T17:08:22+05:30"
tags = ["sqlite"]
+++

Compiling SQLite is super easy.

1. Get the source from Github mirror or download it from the official page:

	```shell
	git clone git@github.com:sqlite/sqlite.git

	# or

	wget https://www.sqlite.org/2024/sqlite-src-3450100.zip
	```

2. Build the header file and the library:

	```shell
	 ./configure
	 make sqlite3.c 
	```

3. Compile the shell to access

	```shell
	gcc shell.c sqlite3.c -lpthread -ldl -lm -o sqlite3
	```