# sioyek-dev

Arch Linux PKGBUILD for Sioyek that "just works."

> [!NOTE]
> Due to GitHub's historic unreliability, active development is hosted on
> [Forgejo](https://git.barrettruth.com/barrettruth/sioyek-dev).
> GitHub is maintained as a read-only mirror.

- Tracks upstream Sioyek's `development` branch
- Builds the matching upstream `mupdf` submodule instead of linking Arch's `libmupdf`
- Supports X11/Wayland

## Why This Package Exists

This package is intentionally different from the other Sioyek AUR packages:

| Package | Source | MuPDF strategy | Best fit |
| --- | --- | --- | --- |
| `sioyek` | Stable release | Arch `libmupdf` | Released Sioyek builds |
| `sioyek-git` | Upstream `development` branch | Arch `libmupdf` | Development branch with system libraries |
| `sioyek-dev` | Upstream `development` branch | Bundled upstream `mupdf` submodule | Development branch with matching MuPDF sources |

The main reason to use `sioyek-dev` is to avoid crashes or build/runtime
breakage from Sioyek being compiled against one MuPDF version and run against
another. If `sioyek-git` works well for your system, it is also a valid package.

## Installation

```sh
makepkg -si
```
