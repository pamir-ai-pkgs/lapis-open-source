# Lapis One system software rk3576-v0.4.0: sources

Source code and license notices for the open-source components in the Lapis One system image `rk3576-v0.4.0`.

## Components

| Group | Contents | License | Materials |
| --- | --- | --- | --- |
| Linux kernel | Linux 6.1.172 with Rockchip and Pamir changes | GPL-2.0-only; Linux-syscall-note on the files whose SPDX line names it | Full source tree, configuration, build scripts, build notes and a list of changed files |
| U-Boot | U-Boot 2017.09 with Rockchip and Pamir changes | GPL-2.0-or-later | Full source tree, build scripts, build notes and a list of changed files |
| Debian packages | 486 source packages from Debian 13 (trixie) and its security, updates and backports suites, unmodified | Per package | Each Debian source package as Debian publishes it: the `.dsc`, the upstream source and Debian's changes |
| Packages built by Pamir | android-adbd (development images only), bluez, chromium, ffmpeg, gstreamer-webrtc, gstreamer1.0-rga, gstreamer1.0-rockchip, libdrm-cursor, librga, libv4l-rkmpp, mpp, rauc, rockchip-update-engine, umtp-responder, v4l-utils | Per package | Source with the Pamir changes and the packaging used to build it |
| Nix packages | The packages in the Nix store under the GPL, LGPL, MPL or similar licenses | Per package | Upstream source, the patches nixpkgs applies, and the license text of every Nix package on the image |
| Rockchip boot binaries | rkbin: the loader, trust and tool binaries the U-Boot and kernel image builds use | Rockchip's rkbin license | The binaries as Rockchip distributes them, with one settings file changed |
| Rust crate | serialport 4.10.0 | MPL-2.0 | The unmodified crates.io release |
| MPL modules in Nix programs | option-ext 0.2.0 in the Google Workspace CLI, go-version 1.9.0 in gh | MPL-2.0 | The unmodified releases, under `nix/sources/vendored/` in the Nix archive |

`open-source.json` lists all 613 components with version, license and archive. Each component also has its path inside the archive and its SHA-256 hash, except the 106 Nix packages: their entries list their files under `nix/sources/`, and the `SHA256SUMS` file in the Nix archive holds those hashes.

In `open-source.json`, `modified` means changed by Pamir. Debian and nixpkgs apply their own patches to the packages they build, and those patches ship in the archives: in each Debian source package, and under `nix/sources/patches/` in the Nix archive. A component that only Debian or nixpkgs patched has `modified` set to `false`.

In the kernel and U-Boot sources, each file that differs from the base named in `CHANGES-pamir.txt` carries a one-line comment near the top that says it was modified and gives the dates of the changes. Files that cannot take a comment without a risk to their format are listed instead in `MODIFIED-FILES.txt` at the root of the source archive, and `CHANGES-pamir.txt` lists every changed file. The RAUC source has a fourth patch that adds the same comments to the files the Pamir patches change; it changes comments only and was not part of the build of the shipped package. These comment lines were added for this release, so they are not in the git commits named in the `BUILD.md` files. The U-Boot source also differs from its commit in one documentation file, `board/rockchip/lapis_rk3576/lcd_assets/README.md`: the new version drops a path on a developer's computer and states that the Avicenna font was made by Pamir. Nothing is built from that file.

## Applicable versions

Lapis One system image `rk3576-v0.4.0`.

## Downloads

Download the attached files under **Assets**:

| File | Contents |
| --- | --- |
| `lapis-rk3576-v0.4.0-kernel.tar` | Kernel source, configuration, build notes and list of changed files |
| `lapis-rk3576-v0.4.0-u-boot.tar` | U-Boot source, build notes and list of changed files |
| `lapis-rk3576-v0.4.0-rkbin.tar` | Rockchip's boot binaries and tools |
| `lapis-rk3576-v0.4.0-build-scripts.tar` | The scripts that build the kernel and U-Boot images |
| `lapis-rk3576-v0.4.0-debian-1.tar`, `lapis-rk3576-v0.4.0-debian-2.tar` | Debian source packages, names a to k and l to z, with build notes and a table that maps each installed package to its source |
| `lapis-rk3576-v0.4.0-pool.tar` | The packages built by Pamir |
| `lapis-rk3576-v0.4.0-nix.tar` | Nix package sources, patches and license texts |
| `lapis-rk3576-v0.4.0-first-party-deps.tar` | The serialport crate |
| `open-source.json` | Every component with its version, license and archive, and its path inside the archive and hash (for a Nix package, its files under `nix/sources/`) |
| `SHA256SUMS` | Checksums for the files above. Check them with `sha256sum -c SHA256SUMS` |

Each archive unpacks into a directory with a `SHA256SUMS` file for its contents. Both Debian archives unpack into `debian/`; its `SHA256SUMS` comes in `lapis-rk3576-v0.4.0-debian-1.tar` and covers the source packages of both.

GitHub's automatically generated **Source code (zip/tar.gz)** files contain the repository index, not the component sources.

## Scope

This release covers the components listed in `open-source.json`. It includes Pamir's changes to those components: the Linux kernel, U-Boot, RAUC and the other packages built by Pamir. It does not include Pamir's own independent programs, which are proprietary, or the device firmware and libraries that other companies supply in binary form under their own terms, apart from the Rockchip boot binaries listed above. It is a source release, not a system image or an update.
