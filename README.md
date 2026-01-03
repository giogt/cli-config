# cli-config

My config for CLI tools such as zsh, nvim, terminal emulators, etc.

## Install CLI config for all supported tools 

Clone this repo under `~/.cli-config`:

```sh
git clone https://github.com/giogt/cli-config.git ~/.cli-config
```

Either delete the current cli tools config, or keep it as a backup.
Some examples:

```sh
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.zshrc ~/.zshrc.bak
mv ~/.zprofile ~/.zprofile.bak
mv ~/.config/ghostty ~/.config/ghostty.bak
mv ~/.config/yazi ~/.config/yazi.bak
mv ~/.config/alacritty.toml ~/.config/alacritty.toml.bak
mv ~/.config/wezterm ~/.config/wezterm.bak
mv ~/.config/kitty ~/.config/kitty.bak
mv ~/.config/neomutt ~/.config/neomutt.bak
mv ~/.ideavimrc ~/.ideavimrc.bak
```

Clean up your `nvim` state and caches:

```sh
rm -rf ~/.local/share/nvim
rm -rf ~/.local/state/nvim
```

I'm not sure if there are any other caches to clean. Please double check.

Create all the symlinks needed to use the config from the cloned repo.
Some examples:

```sh
ln -s ~/.cli-config/.config/nvim ~/.config
ln -s ~/.cli-config/.zshrc ~
ln -s ~/.cli-config/.zprofile ~
ln -s ~/.cli-config/.config/ghostty ~/.config
ln -s ~/.cli-config/.config/yazi ~/.config
ln -s ~/.cli-config/.config/alacritty.toml ~/.config
ln -s ~/.cli-config/.config/wezterm ~/.config
ln -s ~/.cli-config/.config/kitty ~/.config
ln -s ~/.cli-config/.config/neomutt ~/.config
ln -s ~/.cli-config/.ideavimrc ~
```

You're done!

Note to self: try to keep this up to date and synchronised across my devices :)

## Brewfile for Homebrew bundle

Homebrew provides a `bundle` command to dump all the installed packages to a `Brewfile`, so that
they can be synced at any time on any machine that has access to the file.
See [this web page](https://docs.brew.sh/Brew-Bundle-and-Brewfile) for details.

I am using `brew bundle -g` (or `--global`), which expects the `Brewfile` to be located at
`~/.Brewfile`.

To use the `Brewfile` in this repo:

```sh
rm ~/.Brewfile
ln -s ~/.cli-config/.Brewfile ~
```

**IMPORTANT**: before installing the packages, review the content of `.Brewfile`.
There are some bugs causing the bundle functionality to dump to the file additional package
types that were not installed via Homebrew, such as `vscode` and `cargo`.
Please consider keeping only packages of type `brew` and `cask`, and remove all the others.

You can then install the packages in the Bundlefile by running:

```sh
brew bundle -g
```