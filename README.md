# cli-config

My config for CLI tools such as zsh, nvim, terminal emulators, etc.

## How to use

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
```

You're done!

Note to self: try to keep this up to date and synchronised across my devices :)