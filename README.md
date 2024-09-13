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