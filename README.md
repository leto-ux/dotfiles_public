# denial of time files (I wasted so much time on this D:)

## Dependencies

For ease of use, I combine GNU Stow with Mask. You can be normal and just
install them, but I provide both as submodules ready to be combined with
the following commands if need be:

1. GNU Stow

I have no fucking clue why this fails, autoreconf just ain't working with me:

```sh
cd stow && \
autoreconf -iv && \
./configure && sudo make install
```

Alternativly, you can just curl it (NOTE: current maintainer of Stow is Adam
Spiers, if this changes, you'd have to look for the public pgp key of the new
maintainer):

```sh
curl https://keybase.io/adamspiers/pgp_keys.asc | gpg --import
curl -O https://ftp.gnu.org/gnu/stow/stow-latest.tar.gz
curl -O https://ftp.gnu.org/gnu/stow/stow-latest.tar.gz.sig
gpg --verify stow-latest.tar.gz.sig
```

If the output says "Good signature [...]", you're good to go.

```sh
tar -xf stow-latest.tar.gz
cd stow-<version>
./configure && sudo make install
```

Et voila!

2. Mask

Thankfully this one is a lot easier, either get the binary from [here](https://github.com/jacobdeichert/mask/releases),
or using the submodule do the following:

```sh
cd mask
cargo build --release
sudo cp target/release/mask /usr/bin
```

You can obviously just copy the binary into any other binary path you have
configured, that doesn't need sudo privilages, e.g. `~/.local/bin`

## Usage

One can either manually stow/copy/link all the packages they need, or use the
provided maskfile.md file to automate a bunch of the nonsense out of it.
The arguments for mask are specified in the maskfile. The argument is the second
heading, i.e. "\#\# stow_all" means that stow_all is an argument of mask.

```sh
mask <arg>
```

## Enjoy the worst dotfiles experience this side of the pacific.
