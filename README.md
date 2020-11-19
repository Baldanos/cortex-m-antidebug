# Anti debugging tips for Cortex-M devices

This repository contains the source code and slides from my [GreHack presentation](https://grehack.fr/2020/program#enodebug)

The project is a simple STM32CubeMX project built for a STM32F103 (like the blue pill)

## Building

Simply clone the repo, `cd source` and run `make`. This will build all the examples.

## Examples

### DHCSR detection

Detects a debugger by looking at the `C_DEBUGEN` bit in `DHCSR`

Source is in `source/Core/Src/main.dhcsr.c` and compiles into `source/build/main.dhcsr.elf`

### FPB enable

Detects if the FPB is enabled, meaning that a hardware breakpoint might be set.

Source is in `source/Core/Src/main.fpb.c` and compiles into `source/build/main.fpb.elf`

### FPB remap

This shows how to use the FPB remap capabilities by switching called function at runtime.

Source is in `source/Core/Src/main.remap.c` and compiles into `source/build/main.remap.elf`


### Hardfault handler

This example shows how to use a custom hardfault handler to detect a `bkpt` instruction with no debugger attached.

Source is in `source/Core/Src/main.hardfault.c` and compiles into `source/build/main.hardfault.elf`
