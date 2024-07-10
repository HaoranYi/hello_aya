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

```
$ RUST_LOG=info cargo xtask run -- --iface bond0
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.02s
     Running `target/debug/xtask run -- --iface bond0`
    Finished `dev` profile [optimized] target(s) in 0.10s
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.07s
[2024-07-09T21:12:47Z INFO  myapp] Waiting for Ctrl-C...
[2024-07-09T21:12:48Z INFO  myapp] received a packet
[2024-07-09T21:12:48Z INFO  myapp] received a packet
[2024-07-09T21:12:48Z INFO  myapp] received a packet
[2024-07-09T21:12:48Z INFO  myapp] received a packet
...
```

## TODO
- learn to use map/array shared between eBPF/user program
  [PerCpuArray](https://medium.com/@stevelatif/aya-rust-tutorial-part-5-using-maps-4d26c4a2fff8)
  [bpf map](https://github.com/vadorovsky/aya-btf-maps-experiments/blob/main/ebpf/aya/src/main.rs)
  - PID_MAP, DUMMY_MAP hooks between eBPF/user program
  - tracepoint(name="fork")
- learn to hook to perf event
    - [perf event](https://www.infoq.com/articles/benchmark-profile-ebpf-code/)
