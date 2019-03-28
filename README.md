# Orderly

**orderly** is tool that provides ordered and controlled start, stop,
restart and cleanup of a group of processes. It aims to be a building
block for reliable servers/services/containers.

orderly draws inspiration from erlang supervisor trees, It provides
mechanisms to build a tree of supervised processes, and failure can
propagrate when process restarts rate exceeds a specified limit.

If this interests you, you can read the manual [here](man/orderly.1.md).

## Example

``` 
$ orderly -max-restart-tokens 2 -restart-tokens-per-second 0.1 -- \
  -name redis   -run ./run-redis -wait-started ./wait-redis  -- \
  -name website -run ./run-website -check ./health-check-website -cleanup ./website-cleanup 
```

## Building from source

[![builds.sr.ht
status](https://builds.sr.ht/~ach/orderly.svg)](https://builds.sr.ht/~ach/orderly?)

Orderly is a rust project, so running `cargo build` is sufficient for
most people after cloning the git repository.

## Installation

Binary packages are not yet provided.

# Contact

Try the [mailing list](https://lists.sr.ht/~ach/orderly-dev)

Or create a [github
issue](https://github.com/andrewchambers/orderly/issues)

# Sponsors

This project was sponsored by [backupbox.io](https://backupbox.io)
