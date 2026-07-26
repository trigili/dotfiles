# Dotfiles

Personal configuration managed with [chezmoi](https://www.chezmoi.io/).

## New machine

Install chezmoi, then initialize this repository:

```sh
chezmoi init --apply git@github.com:trigili/dotfiles.git
```

For a one-line bootstrap on Linux or macOS:

```sh
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply git@github.com:trigili/dotfiles.git
```

The shell configuration works without optional tools, but the full setup uses:

- zsh and Oh My Zsh
- Powerlevel10k
- tmux and TPM
- Vim
- keychain
- Rust/Cargo and NVM, when installed

## Routine workflow

```sh
chezmoi diff
chezmoi add ~/.zshrc
chezmoi cd
git add .
git commit -m "Update shell configuration"
git push
```

On another machine:

```sh
chezmoi update
```

Do not add shell histories, SSH or GPG private keys, tokens, password stores,
or application state unless they are intentionally encrypted first.
