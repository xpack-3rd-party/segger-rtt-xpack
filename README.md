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
