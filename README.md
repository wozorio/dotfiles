# Dotfiles

macOS configuration managed with [GNU Stow](https://www.gnu.org/software/stow/) and [Homebrew](https://brew.sh/).

## GNU Stow

Run from the repository root:

```zsh
# Dry run (preview only)
stow -n --verbose=2 --target=$HOME */

# Link all packages
stow --verbose=2 --target=$HOME */

# Unlink all packages
stow -D --verbose=2 --target=$HOME */
```

> **Note:** Stow won't overwrite existing files (e.g., `~/.zshrc`). Back up or delete conflicts first.

## Homebrew

```zsh
# Install packages from Brewfile
brew bundle install

# Update Brewfile from installed packages
brew bundle dump --no-describe --force
```
