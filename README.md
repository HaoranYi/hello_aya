# myapp

## generated from `aya-template`
```bash
cargo generate https://github.com/aya-rs/aya-template
# or
cargo generate --name myapp -d program_type=xdp https://github.com/aya-rs/aya-template
```

See [aya-book](https://aya-rs.dev/book/start/development/#starting-out) for
more details.


## Prerequisites

1. Install bpf-linker: `cargo install bpf-linker`

## Build eBPF

```bash
cargo xtask build-ebpf
```

To perform a release build you can use the `--release` flag.
You may also change the target architecture with the `--target` flag.

## Build Userspace

```bash
cargo build
```

## Build eBPF and Userspace

```bash
cargo xtask build
```

## Run

```bash
RUST_LOG=info cargo xtask run
```
