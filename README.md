# sioyek-dev

Arch Linux PKGBUILD for Sioyek that "just works."

- Tracks upstream Sioyek's `development` branch
- Builds the matching upstream `mupdf` submodule instead of linking Arch's `libmupdf`
- Supports X11 and defaults to XWayland in Wayland sessions

## Why This Package Exists

This package is intentionally different from the other Sioyek AUR packages:

| Package | Source | MuPDF strategy | Best fit |
| --- | --- | --- | --- |
| [`sioyek`](https://aur.archlinux.org/packages/sioyek) | Stable release | Arch `libmupdf` | Released Sioyek builds |
| [`sioyek-git`](https://aur.archlinux.org/packages/sioyek-git) | Upstream `development` branch | Arch `libmupdf` | Development branch with system libraries |
| [`sioyek-dev`](https://aur.archlinux.org/packages/sioyek-dev) | Upstream `development` branch | Bundled upstream `mupdf` submodule | Development branch with matching MuPDF sources |

The main reason to use `sioyek-dev` is to avoid crashes or build/runtime
breakage from Sioyek being compiled against one MuPDF version and run against
another. If `sioyek-git` works well for your system, it is also a valid package.

## Installation

```sh
makepkg -si
```

## Display Backend

In a Wayland session, the launcher defaults to XWayland when `QT_QPA_PLATFORM`
is unset or empty. For native Wayland, install `qt6-wayland` and run:

```sh
QT_QPA_PLATFORM=wayland sioyek
```

For desktop launches, copy `/usr/share/applications/sioyek.desktop` to
`$XDG_DATA_HOME/applications/` (default: `~/.local/share/applications/`).
Set `Exec` under `[Desktop Entry]`:

```ini
Exec=env QT_QPA_PLATFORM=wayland sioyek %f
```

If you [have problems with Wayland](https://github.com/ahrm/sioyek/issues/1660),
replace `wayland` with `xcb` for XWayland. Restart Sioyek after changing backends.
