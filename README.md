# Holder SDK

Ready-to-use builds of Holder's core library, libholder, for Linux, macOS and Windows. Use them to build your own tools, integrations and language bindings on top of Holder, without building core and its dependencies yourself.

Everything here is built from the public source in [HolderTeam/holder](https://github.com/HolderTeam/holder) by that repository's CI. Nothing is built or run in this repository; it only holds releases.

## What's in a release

- An SDK archive for each platform and configuration: headers, static libraries, the CMake package (`find_package(holder CONFIG REQUIRED)`, then link `Holder::Core`), the C API (`holder/holder.h`), and core's schema and resources. The Windows SDK also bundles core's third-party dependencies; on Linux and macOS, install them from the system or Homebrew.
- `sdk-index.json`, listing every archive with its platform, configuration, size and SHA-256 checksum, and the commit it was built from.

## Which release to use

- **`holder-v<version>`**: the SDK that shipped with that Holder release. Use these for anything you distribute.
- **`core-<tree>`**: development snapshots, one for each change to core on `main`, named after core's source tree. They're pruned over time.

## Verifying a download

Check each archive's size and SHA-256 checksum against `sdk-index.json`, and the manifest inside the archive (`libholder-manifest.json`) against the commit you expect. `core/scripts/core-sdk.py` in HolderTeam/holder does both.

## Licence

libholder is free software under the GNU General Public License, version 3 ([LICENSE](LICENSE), also included in each archive). The source for every build is the commit named in its `sdk-index.json`, in HolderTeam/holder. Each archive also includes the licences of the third-party libraries it bundles.

The libraries are static, so a program that links libholder is a combined work under the GPL: your project's licence needs to be compatible with GPLv3.

## Questions and bugs

Please open issues in [HolderTeam/holder](https://github.com/HolderTeam/holder/issues). This repository only holds builds.
