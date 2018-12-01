# Standalone conrod Examples

[conrod](https://github.com/PistonDevelopers/conrod) is a 2D GUI library for [Rust](https://www.rust-lang.org).  It took me longer than I care to admit to get my first conrod project off the ground, despite conrod having some bundled examples that are easy to get running alongside the conrod library.  There are basically two issues with the way the examples are currently distributed currently:
  1. They don't show (as far as I noticed, at least) how to make your cargo application depend on conrod with the appropriate `features` set.
  2. Within the `examples` directory of cargo, some generic code is hidden away in an examples module, which IMHO defeats some of the purpose of an example...

This repo simply extracts those examples in to their own cargo applications, so building and running one should be as simple as:

  1. Clone repository
  2. cd to one of the `examples` subdirectories.
  3. `cargo run`
  
The secret sauce is mostly in the line of your Cargo.toml file, which lists the conrod dependency:

```
[dependencies]
conrod = {version = "0.61", features = ["glium", "winit"]}
glium = "0.22.0"
winit = "0.18.0"
```
