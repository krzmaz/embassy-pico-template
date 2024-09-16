# Embassy Raspberry Pi Pico W template
This repo is intended to be a template for future projects now that Embassy is published to crates.io

The `cyw43-firmware` folder is copied from https://github.com/embassy-rs/embassy/tree/3d6a270f30c45eaf394c8eb8bf182dd1a7ec2d7b/cyw43-firmware

## Prerequisites
```
rustup target add thumbv6m-none-eabi
```

## Runner
You will need to use [probe-rs](https://probe.rs/), [picotool](https://github.com/raspberrypi/picotool) or [elf2uf2-rs](https://github.com/JoNil/elf2uf2-rs) to flash the compiled binary onto your pico.  
Choose whichever you want and set the runner in `.cargo/config.toml` accordingly

`picotool` seems like the most beginner friendly, but feel free to explore your options. Note that probe-rs will require more wiring, but will allow you to see your debug logs.

On MacOS and Linux you can install `picotool` with [brew](https://brew.sh/):

```sh
brew install picotool
```

## CI [![Cargo Build & Release](https://github.com/krzmaz/embassy-pico-template/actions/workflows/ci.yml/badge.svg)](https://github.com/krzmaz/embassy-pico-template/actions/workflows/ci.yml)
This repository has a very simplistic CI setup that builds the main branch after each push and uploads the resulting binaries in UF2 format for ease of retesting older builds (the artifacts are stored for 90 days after the CI run)

If there was a new tag pushed, it will also be build and the artifacts will be uploaded and available in the Releases section.