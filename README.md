# Dotfiles Management with GNU Stow

This repository contains my personal dotfiles, managed and symlinked to the home directory using **GNU Stow**.

## 🚀 Quick Start

To apply all dotfiles configurations from this directory, run the following command in the root of this repository:

```zsh
stow --verbose=2 --target=$HOME */
```

### 🔍 Command Breakdown

- `stow`: The GNU Stow utility used to manage symlinks.
- `--verbose=2`: Enables a high level of verbosity so you can see exactly which symlinks are being created, skipped, or updated.
- `--target=$HOME`: Specifies the target directory where the symlinks should be placed (your user home folder).
- `*/`: Tells Stow to process all subdirectories within the current folder as individual Stow packages.

---

## 🛠️ Essential Operations

### 1. Preview Changes (Dry Run)

It is highly recommended to run a dry run first to see exactly what symlinks Stow will create, without making any actual changes to your filesystem:

```zsh
stow --no --verbose=2 --target=$HOME */
```

_(Alternatively, you can use the shorthand `-n` flag instead of `--no`)_

### 2. Apply Configuration (Link)

Once you are happy with the preview, link your dotfiles to your home directory:

```zsh
stow --verbose=2 --target=$HOME */
```

### 3. Remove Configuration (Unstow)

If you want to safely remove the symlinks created by Stow (leaving your actual config files in this repository completely untouched), run the unstow command:

```zsh
stow -D --verbose=2 --target=$HOME */
```

💡 **Pro Tip**: If a file already exists in your target directory (e.g., a default `~/.zshrc` created by your OS), Stow will refuse to overwrite it. You must backup and delete the existing file before running the Stow command.
