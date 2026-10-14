# FIX Ray downloads

FIX Ray is a desktop workspace for exploring FIX messages. Open logs or paste messages, follow orders, inspect fields and validation results, and query your data with SQL.

[Visit the FIX Ray website](https://petrokarpiuk.github.io/fix-ray/)

## Download

Current version: **1.0.0**.

| Platform | Requirements | Download | Checksum |
| --- | --- | --- | --- |
| macOS, Apple Silicon (arm64) | macOS **27.0.1 or newer** | [macOS ZIP, about 39 MB](https://github.com/petrokarpiuk/fix-ray-releases/raw/refs/heads/main/downloads/v1.0.0/fix-ray-1.0.0-macos-arm64.zip) | [SHA-256](https://github.com/petrokarpiuk/fix-ray-releases/raw/refs/heads/main/downloads/v1.0.0/fix-ray-1.0.0-macos-arm64.zip.sha256) |
| Linux, x86_64 | Ubuntu **24.04+**, or a desktop with **glibc 2.39+** | [Linux tar.gz, about 62 MB](https://github.com/petrokarpiuk/fix-ray-releases/raw/refs/heads/main/downloads/v1.0.0/fix-ray-1.0.0-linux-x86_64.tar.gz) | [SHA-256](https://github.com/petrokarpiuk/fix-ray-releases/raw/refs/heads/main/downloads/v1.0.0/fix-ray-1.0.0-linux-x86_64.tar.gz.sha256) |

## Install on macOS

1. Download the macOS ZIP and double-click it to extract **FIX Ray.app**.
2. Move **FIX Ray.app** into **Applications**.
3. Open the app.

This build is ad hoc signed, with no Apple Developer ID signature or notarization. If macOS blocks opening it, attempt to launch it first, then open **System Settings → Privacy & Security**, choose **Open Anyway**, and confirm opening FIX Ray. 

This package runs on Apple Silicon Macs with macOS **27.0.1 or newer**. The minimum version comes from the packaged binary's build metadata.

## Run on Linux

Extract the archive and run the launcher:

```sh
tar -xzf fix-ray-1.0.0-linux-x86_64.tar.gz
cd fix-ray-1.0.0-linux-x86_64
./fix-ray
```

Keep the extracted directory together: its launchers depend on the bundled `bin/`, `lib/`, and `share/` directories. No administrator install is needed. X11 and Wayland plugins are included; your desktop supplies glibc, fonts, and OpenGL/EGL graphics drivers.

The baseline is **Ubuntu 24.04 LTS / glibc 2.39 / x86_64**. Ubuntu 22.04, Debian 12, and Alpine Linux are outside this package's compatibility baseline.

The Linux package also includes the command-line importer:

```sh
./fix-ray-import input.fix analysis.duckdb input.spool
```

Choose a new spool path for each import. Run `./fix-ray-import --help` for available options.

## Verify a download

Download the archive and its matching `.sha256` file into the same directory. On macOS:

```sh
shasum -a 256 -c fix-ray-1.0.0-macos-arm64.zip.sha256
```

On Linux:

```sh
sha256sum -c fix-ray-1.0.0-linux-x86_64.tar.gz.sha256
```

The command should report `OK`. Each package includes build information and third-party license notices.

