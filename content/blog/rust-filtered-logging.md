+++
title = "Filtered (selective) logging in Rust"
date = "2024-03-30T14:19:32+05:30"

tags = ["rust", "logging"] 
+++

I absolutely like the way Rust lets us filter logs.

```bash
RUST_LOG="warn,mod1::foo=info,mod2::foo::bar=debug"
```

This will set:
- `warn` level for entire project, including dependencies
- except `mod1::foo` at `info` and `mod2::foo::bar` at `debug`

In my current project, I was using [`tracing`](https://docs.rs/tracing/latest/tracing/) package. My code had several `trace` logs and so did the dependencies. I wanted to print only the logs from my code, so here is what I did:

```rust
    let filter = EnvFilter::try_from_default_env()
        .unwrap_or_else(|_| EnvFilter::new("batman=trace"));
    tracing::subscriber::set_global_default(
        FmtSubscriber::builder().with_env_filter(filter).finish(),
    )
    .expect("setting default subscriber failed");
```

This is self explanatory. My code's cargo package name was `batman`. Above code sets the trace log by default if no env `RUST_LOG` was found.

Note that of your cargo package name has dashes, change them to underscore. For e.g. I had to set `RUST_LOG="libsql_storage_server=trace"` for cargo package `libsql-storage-server`.

Rust nursery on [logging](https://rust-lang-nursery.github.io/rust-cookbook/development_tools/debugging/config_log.html) has more tricks.