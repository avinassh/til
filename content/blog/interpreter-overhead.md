+++
title = "Interpreter overhead"
date = "2024-03-10T17:50:58+05:30"
tags = ["compiler", "interpreter"]
+++

How much overhead do interpreted languages like Python and Ruby add? 

I found this nicely made video ["The size of your variables matter"](https://www.youtube.com/watch?v=hwyRnHA54lI). In languages like Python and JavaScript, we don't specify the size of the variable, so the interpreter might allocate significantly more memory than required. This increases memory usage and CPU workload since it may now have to read more data from the RAM.

```python
a = 5
```
The value of `a` can be anything, from an unsigned 8-bit integer (u8) to a 64-bit integer (i64). (It's a different matter than being able to assign a string or anything else too.)

```rust
a: u8 = 5;
```
Here, the Rust compiler allocates only one byte for the variable `a`. Interpreted languages also need to keep track of the type information, so along with a large memory block for the value, they allocate extra memory just to store the type information.

Note: the same channel has two more videos explaining [Stack](https://www.youtube.com/watch?v=N3o5yHYLviQ) and [Heap](https://www.youtube.com/watch?v=ioJkA7Mw2-U&t=930s) 