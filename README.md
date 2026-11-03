# Codex configuration

Shared Codex CLI preferences with automatic approval review, Vim input mode,
and a status line showing model/reasoning, current directory, Git branch,
remaining context, the 5-hour limit, and the weekly limit.

Install Git and Codex CLI separately. This repository works independently on
Windows, macOS, and Linux.

## Setup

Clone the repository and copy the shared profile into your Codex configuration
directory. The commands below respect `CODEX_HOME` when set and otherwise use
the default `.codex` directory under your home directory. They copy only
`dotfiles.config.toml`; your local `config.toml` remains separate.

### macOS and Linux

```sh
git clone https://github.com/TenofHearts/codex-config.git "$HOME/codex-config"
codex_config_dir="${CODEX_HOME:-$HOME/.codex}"
mkdir -p "$codex_config_dir"
cp "$HOME/codex-config/dotfiles.config.toml" "$codex_config_dir/dotfiles.config.toml"
```

### Windows (PowerShell)

```powershell
git clone https://github.com/TenofHearts/codex-config.git "$HOME/codex-config"
$codexConfigDir = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME ".codex" }
New-Item -ItemType Directory -Force -Path $codexConfigDir | Out-Null
Copy-Item "$HOME/codex-config/dotfiles.config.toml" (Join-Path $codexConfigDir "dotfiles.config.toml")
```

## Usage

Start Codex with the profile on any platform:

```sh
codex --profile dotfiles
```

The profile overrides matching values in your machine's `config.toml`.
Keep machine-specific settings such as project trust, providers, and local paths
in that file. Run `codex` without the profile flag to use your usual defaults.

## Updates

Run `git pull` inside the clone, then repeat your platform's copy command to
refresh the installed profile. Restart Codex to load the updated settings.
To share changes, edit `dotfiles.config.toml` in the clone, commit, and push.
