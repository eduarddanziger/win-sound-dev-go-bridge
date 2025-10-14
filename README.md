# win-sound-dev-go-bridge

Go + cgo bridge to `SoundAgentApiDll.dll` for monitoring/querying Windows default audio devices.

## Build (cmd.exe)
Prereqs: CGO enabled and a GCC-style toolchain (MinGW-w64 gcc or LLVM-mingw clang). MSVC `cl.exe` is not supported by cgo.

```bat
set CGO_ENABLED=1

go build .
```
Place `SoundAgentApiDll.dll` next to the built `.exe` (or on `PATH`).

## Run
```bat
win-sound-dev-go-bridge.exe
```

## External module
- github.com/eduarddanziger/sound-win-scanner/v4 (pkg/soundlibwrap): cgo wrapper around SoundAgentApi, see [soundlibwrap documentation](https://pkg.go.dev/github.com/eduarddanziger/sound-win-scanner/v4/pkg/soundlibwrap)

## Advanced (tiny)
Use clang instead of gcc:
```bat
set CC=x86_64-w64-mingw32-clang
set CXX=x86_64-w64-mingw32-clang++
```
