# Holder SDK

Ready-to-use builds of Holder's components, for building your own tools, integrations and language bindings on top of Holder without building Holder yourself.

Each build is made once and shared, by you, other developers and Holder's own CI alike, which saves everyone the time, and the electricity, of building the same thing again.

Everything here is built from the public source in [HolderTeam/holder](https://github.com/HolderTeam/holder) by that repository's CI. Nothing is built or run in this repository; it only holds releases.

## Releases

- **`holder-v<version>`**: the components that shipped with that Holder release. Use these for anything you distribute.
- **`<component>-<id>`**: development builds, for example `core-<tree>` for each change to core on `main`, named after core's source tree. They're pruned over time.

Each release has an index (for core, `sdk-index.json`) listing every archive with its platform, configuration, size and SHA-256 checksum, and the commit it was built from.

## Components

### Core (libholder)

Holder's core library, for Linux, macOS and Windows. Each archive holds the headers, static libraries, the CMake package (`find_package(holder CONFIG REQUIRED)`, then link `Holder::Core`), the C API (`holder/holder.h`), and core's schema and resources. The Windows archive also bundles core's third-party dependencies; on Linux and macOS, install them from the system or Homebrew.

To check a download, compare its size and SHA-256 checksum with `sdk-index.json`, and the manifest inside the archive (`libholder-manifest.json`) with the commit you expect. `core/scripts/core-sdk.py` in HolderTeam/holder does both.

## Licence

Holder is free software under the GNU General Public License, version 3 ([LICENSE](LICENSE), also included in each archive). The source for every build is the commit named in its index, in HolderTeam/holder. Archives also include the licences of the third-party libraries they bundle.

A program that links a Holder library (core's libraries are static) is a combined work under the GPL, so your project's licence needs to be compatible with GPLv3.

## Questions and bugs

Please open issues in [HolderTeam/holder](https://github.com/HolderTeam/holder/issues). This repository only holds builds.
