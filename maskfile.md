# Maskfile

## stow_all

> Stows every package in the ./dotfiles directory

```sh
cd stow
stow --verbose --target=$HOME */
```

## stow_package (package)

> Stows a single package

```sh
cd stow
stow --verbose --target=$HOME $package
```
