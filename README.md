### RustDesk | Your Remote Desktop Software

The best open source remote desktop software written with Rust.

[**BINARY DOWNLOAD**](https://github.com/rustdesk/rustdesk/releases)

## Dependence

Desktop versions use [sciter](https://sciter.com/) for GUI, please download sciter dynamic library yourself.

[Windows](https://github.com/c-smile/sciter-sdk/blob/dc65744b66389cd5a0ff6bdb7c63a8b7b05a708b/bin.win/x64/sciter.dll)
[Linux](https://github.com/c-smile/sciter-sdk/raw/dc65744b66389cd5a0ff6bdb7c63a8b7b05a708b/bin.lnx/x64/libsciter-gtk.so)
[Osx](https://github.com/c-smile/sciter-sdk/raw/dc65744b66389cd5a0ff6bdb7c63a8b7b05a708b/bin.osx/sciter-osx-64.dylib)

## How To Build

* Prepare your Rust development env and C++ build env

* Install [vcpkg](https://github.com/microsoft/vcpkg), and set VCPKG_ROOT env variable correctly

   - Windows: vcpkg install libvpx:x64-windows-static libyuv:x64-windows-static opus:x64-windows-static
   - Linux/Osx: vcpkg install libvpx libyuv opus
   
* cargo run

## File Structure

- **[libs/hbb_common](https://github.com/rustdesk/rustdesk/tree/master/libs/hbb_common)**: video codec, config, tcp/udp wrapper, protobuf, fs functions for file transfer, and some other utility functions
- **[libs/scrap](https://github.com/rustdesk/rustdesk/tree/master/libs/scrap)**: screen capture
- **[libs/enigo](https://github.com/rustdesk/rustdesk/tree/master/libs/enigo)**: platform specific keyboard/mouse control
- **[src/ui](https://github.com/rustdesk/rustdesk/tree/master/src/ui)**: GUI
- **[src/server](https://github.com/rustdesk/rustdesk/tree/master/src/server)**: audio/clipboard/input/video services, and network connections
- **[src/client.rs](https://github.com/rustdesk/rustdesk/tree/master/src/client.rs)**: start a peer connection
- **[src/rendezvous_mediator.rs](https://github.com/rustdesk/rustdesk/tree/master/src/rendezvous_mediator.rs)**: Communicate with [rustdesk-server](https://github.com/rustdesk/rustdesk-server), wait for remote direct (TCP hole punching) or relayed connection
- **[src/platform](https://github.com/rustdesk/rustdesk/tree/master/src/platform)**: platform specific code