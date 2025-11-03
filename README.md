# rust-sandbox

Sandbox is a personal playground for experimenting with Rust techniques that do
not yet deserve their own repository. The `rust-sandbox` repo collects tiny
binaries, prototype-friendly workflows, and notes that help future-me remember
what worked (or failed).


## What You Will Find

- `sandbox/`: a crate with many small binaries exploring Tokio, channels,
  synchronization primitives, and lifetime experiments (`cargo run --bin
  tokio_channel --package sandbox`, etc.).
- `sample/ffi/`: minimal Rust FFI samples used to test build scripts and cross
  compilation setups.
- `Makefile`: helpers for formatting, linting, and compiling against
  `x86_64-unknown-linux-musl`.

Everything is intentionally scrappy—code may be experimental, undocumented, or
half-finished.


## Getting Started

1. Install the latest stable Rust toolchain (`rustup install stable`).
2. Clone the repository and run `cargo build` to make sure dependencies compile.
3. Pick an experiment and run it, for example:

   ```bash
   cargo run --package sandbox --bin tokio_channel
   ```

   Swap the binary name to explore other topics such as `closure`, `std_drop`,
   or `tokio_asyncwrite`.


## Workflow Tips

- `cargo fmt` and `cargo clippy` keep experiments tidy; both run automatically
  via `make prebuild`.
- `cargo test` exists but many experiments are integration-style binaries—feel
  free to add tests when an experiment graduates from a quick spike.
- Cross-compiling? The Makefile already wires up `OPENSSL_STATIC` for Musl
  builds; set `PKG` before invoking `make debug` or `make run`.


### License

<sup>
Licensed under either of <a href="LICENSE-APACHE">Apache License, Version 2.0</a> or <a href="LICENSE-MIT">MIT license</a> at your option.
</sup>

<br>

<sub>
Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.
</sub>
