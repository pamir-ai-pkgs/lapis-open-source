# Lapis One system software rk3576-v0.4.0: sources

Source code and license notices for the open-source components in the Lapis One system image `rk3576-v0.4.0`.

## Components

| Group | Contents | License | Materials |
| --- | --- | --- | --- |
| Linux kernel | Linux 6.1.172 with Rockchip and Pamir changes | GPL-2.0 | Full source tree, configuration, build scripts, build notes and a list of changed files |
| U-Boot | U-Boot 2017.09 with Rockchip and Pamir changes | GPL-2.0-or-later | Full source tree, build scripts, build notes and a list of changed files |
| Debian packages | 486 source packages from Debian 13 (trixie) and its security, updates and backports suites, unmodified | Per package | Each Debian source package as Debian publishes it: the `.dsc`, the upstream source and Debian's changes |
| Packages built by Pamir | bluez, chromium, ffmpeg, gstreamer-webrtc, gstreamer1.0-rga, gstreamer1.0-rockchip, libdrm-cursor, librga, libv4l-rkmpp, mpp, rauc, umtp-responder, v4l-utils | Per package | Source with the Pamir changes and the packaging used to build it |
| Nix packages | The packages in the Nix store under the GPL, LGPL, MPL or similar licenses | Per package | Upstream source, the patches nixpkgs applies, and the license text of every Nix package on the image |
| Rockchip boot binaries | rkbin: the loader, trust and tool binaries the U-Boot and kernel image builds use | Rockchip's rkbin license | The binaries as Rockchip distributes them, with one settings file changed |
| Rust crate | serialport 4.10.0 | MPL-2.0 | The unmodified crates.io release |

`open-source.json` lists all 611 components with version, license, archive and SHA-256 hash.

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
| `open-source.json` | Every component with its version, license, archive, path inside the archive and hash |
| `SHA256SUMS` | Checksums for the files above. Check them with `sha256sum -c SHA256SUMS` |

Each archive unpacks into its own directory with a `SHA256SUMS` file for its contents.

GitHub's automatically generated **Source code (zip/tar.gz)** files contain the repository index, not the component sources.

## Scope

This release covers the components listed in `open-source.json`. It does not include Pamir's own software, or the device firmware and libraries that other companies supply in binary form under their own terms, apart from the Rockchip boot binaries listed above. It is a source release, not a system image or an update.
