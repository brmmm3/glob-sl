glob-sl
=======

Support for matching file paths against Unix shell style patterns.

[![Build Status](https://dev.azure.com/rust-lang/glob/_apis/build/status/rust-lang-nursery.glob?branchName=master)](https://dev.azure.com/rust-lang/glob/_build/latest?definitionId=20&branchName=master)

[Documentation](https://docs.rs/glob-sl)

## Usage

To use `glob-sl`, add this to your `Cargo.toml`:

```toml
[dependencies]
glob = "0.4.0"
```

And add this to your crate root:

```rust
extern crate glob_sl;
```

## Examples

Print all jpg files in /media/ and all of its subdirectories.

```rust
use glob_sl::glob;

for entry in glob("/media/**/*.jpg").expect("Failed to read glob pattern") {
    match entry {
        Ok(path) => println!("{:?}", path.display()),
        Err(e) => println!("{:?}", e),
    }
}
```
