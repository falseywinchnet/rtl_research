# Technical Notes

The repository contains two subfolders:

- `rtlcanary` – the upstream rtl_433 project at release 25.02 (Feb 2025).
- `rtlmarco` – a custom Windows plugin for SDRSharp that wraps a `rtl_433.dll`.

The plugin calls functions from `rtl_433.dll` via P/Invoke (`NativeMethods.cs`).
The binary in `rtlmarco/install` is built from rtl_433 release 24.10 (Oct 2024).

Porting new device support requires rebuilding `rtl_433.dll` from the
`rtlcanary` sources while preserving the exported functions used by the plugin.
Be aware that the C structures and exported names must stay compatible so that
`NativeMethods.cs` continues to work without changes.

The plugin expects data through callbacks that match `R_deviceToPlugin` and
other structures defined in the C code.  Any change in these definitions can
break the plugin interface.  Also note that some data files such as
`devices.txt` are loaded by the plugin at runtime.

The build system for rtl_433 uses CMake.  When compiling for Windows you must
enable the `-DBUILD_DLL=ON` option and target both x86 and x64 as needed.
The resulting `rtl_433.dll` files should replace the ones shipped under
`rtlmarco/install/`.
