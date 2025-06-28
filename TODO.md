# Porting Tasks

1. **Compile latest rtl_433**
   - From the `rtlcanary` folder run CMake with `-DBUILD_DLL=ON`.
   - Build 32‑bit and 64‑bit versions of `rtl_433.dll`.
   - Keep the exported function list identical to the one used by `NativeMethods.cs`.

2. **Update plugin binaries**
   - Replace the old DLLs in `rtlmarco/install` with the freshly built ones.
   - Update the zip archives if distributing prebuilt packages.

3. **Refresh device data**
   - Copy new `conf/*.conf` files and any updated `devices.txt` from `rtlcanary`.
   - Verify that `ClassInterfaceWithRtl433` still parses the device list correctly.

4. **Check structure compatibility**
   - Review `R_deviceToPlugin` and related structs in both repos.
   - If upstream changed fields, adjust the C# definitions accordingly.

5. **Retest the plugin**
   - Build the plugin solution under `rtlmarco`.
   - Validate that new devices from release 25.02 decode correctly within SDRSharp.
