# STM8_headers + PlatformIO 

This is an example project which includes a copy of https://github.com/gicking/STM8_headers by Georg Icking-Konert. 

The library is included via copying it in the `lib/` folder, adding a small `library.json` to it and referencing it in the `platformio.ini` via `lib_deps`. The code from the original example project (`blink_noInterrupt`) is slightly adapted regarding the relative include paths and some verbosity via `#warning` pragmas for the selected pin mapping.

The `platformio.ini` contains 3 environments for the STM8S-DISCOVERY, the NUCLEO-8S207K8 and the NUCLEO-8S208RB boards. Select the correct environment [per docs](https://docs.platformio.org/en/latest/integration/ide/vscode.html#project-tasks). The latter two board definitions are work in progress (see [issues](https://github.com/platformio/platform-ststm8/issues/34)) and pulled in from [a modified platform](https://github.com/maxgerhardt/platform-ststm8/tree/gdb_debugging/boards).  

Compilation should work fine for all environments, but uploading and confirming that the firmware executes correctly has not been done, as I lack the hardware for that. 

```
Environment           Status    Duration
--------------------  --------  ------------
stm8sblue_stm8s103f3  SUCCESS   00:00:01.918
stm8sdisco            SUCCESS   00:00:01.877
nucleo_8s207k8        SUCCESS   00:00:01.890
nucleo_8s208rb        SUCCESS   00:00:01.874
```

## Debugging

Thanks to new code in the modified platform, debugging via OpenOCD is enabled by default for all boards. 

Tested for an STM8S103F3 board and confirmed working.