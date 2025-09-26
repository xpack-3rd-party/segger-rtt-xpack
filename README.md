# An xpm/npm package with the SEGGER RTT library

This project offers a convenient method for integrating the
[SEGGER RTT](https://github.com/SEGGERMicro/RTT) library
into the xpm/npm ecosystem, enabling installation as a package dependency.

The open-source project is hosted on GitHub at
[xpack-3rd-party/segger-rtt-xpack](https://github.com/xpack-3rd-party/segger-rtt-xpack).

In addition to the original SEGGER project, this fork provides
a `package.json` with npm/xpm metadata and a `CMakeLists.txt` for
seamless CMake integration.

The current version is based on **v8.56a**, dated **5 August 2025**.

Changes:

- the `Config/SEGGER_RTT_Conf.h` file was copied as
`include/SEGGER_RTT_ConfDefaults.h` and slightly updated
- `RTT/SEGGER_RTT.h` was edited to include it
- warnings were silenced in `RTT/SEGGER_RTT.c`
- the `templates/include/SEGGER_RTT_Conf.h` was added; copy it to your project.

## How to use

### Install

The easiest method to install the library into a project is via `xpm`:

```sh
xpm install github:xpack-3rd-party/segger-rtt-xpack#v8.56.1-2
```

### Template files

In the `templates` folder there is a header file;
copy them into the project, and possibly update it.

### CMake

If the project uses CMake, include the `CMakeLists.txt` and the
`segger::rtt` to the build.

### Other builders

Otherwise manually add the include folders and the source files mentioned in
the `CMakeLists.txt` to the build configuration.

---

The original README content is provided below.

---

RTT
===

SEGGER RTT Sources

https://www.segger.com/products/debug-probes/j-link/technology/about-real-time-transfer
https://wiki.segger.com/RTT

## Included files

  * `RTT/`
    * `SEGGER_RTT.c`               - Main module for RTT.
    * `SEGGER_RTT.h`               - Main header for RTT.
    * `SEGGER_RTT_ASM_ARMv7M.S`    - Assembly-optimized implementation of RTT functions for ARMv7M processors.
    * `SEGGER_RTT_Printf.c`        - Simple implementation of printf (`SEGGER_RTT_Printf()`) to write formatted strings via RTT.
  * `Syscalls/`
    * `SEGGER_RTT_Syscalls_*.c`    - Low-level syscalls to retarget `printf()` to RTT with different toolchains.
  * `Config/`
    * `SEGGER_RTT_Conf.h`          - RTT configuration file.
  * `Examples/`
    * `Main_RTT_InputEchoApp.c`    - Example application which echoes input on Channel 0.
    * `Main_RTT_MenuApp.c`         - Example application to demonstrate RTT bi-directional functionality.
    * `Main_RTT_PrintfTest.c`      - Example application to test RTT's simple printf implementation.
    * `Main_RTT_SpeedTestApp.c`    - Example application to measure RTT performance. (Requires embOS)
