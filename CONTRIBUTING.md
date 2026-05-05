# Contributing

Development, issues, and pull requests happen on [Forgejo](https://git.barrettruth.com/barrettruth/sioyek-dev).

## Scope

sioyek-dev is an AUR PKGBUILD for the development build of Sioyek. It is not the upstream Sioyek application, a general PDF viewer fork, or an Arch packaging framework.

## Pull Requests

Bug fixes, documentation fixes, and packaging fixes are welcome. AI-generated contributions are not accepted.

For new behavior, open an issue first unless the change is small and already fits the repository's scope.

Package changes should update `PKGBUILD` and `README.md` when appropriate.

## Development

This repository is maintained as an Arch PKGBUILD. Package work should be tested with `makepkg`.

## Checks

Run the package source verification before opening a pull request:

```sh
makepkg --verifysource
```
