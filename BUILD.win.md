# Build Instructions for Zed `v0.202.0-dev-win` (Windows)

This document describes the exact environment and steps used to build the `zed.exe` binary for release `v0.202.0-dev`. 

## Environment

- **OS**: Windows 11 Pro 22H2 (x64)
- **Shell**: PowerShell 7.5.2
- **Rust Toolchain**:
  - rustc `1.89.0`
  - cargo `1.89.0`
  - Target: `x86_64-pc-windows-msvc`
- **Compiler Backend**:
  - Visual Studio 2022 Community Edition
  - Windows SDK for Windows 11 (10.0.26100.4654)
- **Compression Tools**:
  - UPX `5.0.2`
- **Strip Tool**:
  - strip `2.44`

## Build Steps

### Clone
```powershell
git clone https://github.com/baz14/zed.git
cd zed
git checkout release/v0.202.0-dev-win
```

### Build the Executable
```powershell
cargo build --release
```

### Compress
```powershell
upx target\release\zed.exe
```

### Strip Debug Symbols
```powershell
strip target\release\zed.exe
```
