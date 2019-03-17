# Connect

[![IRC][IRC Badge]][IRC]

###### [Usage](#usage) | [Documentation](#commands) | [Contributing](CONTRIBUTING)

> [Kakoune] extension to connect a program to the current client.

[![asciicast](https://asciinema.org/a/234186.svg)](https://asciinema.org/a/234186)

## Installation

### [Pathogen]

``` kak
pathogen-infect /home/user/repositories/github.com/alexherbo2/connect.kak
```

## Usage

Create a new terminal with `:connect` and edit a file with say, a file explorer.

The file will be opened in the client from where `:connect` was executed by using `EDITOR`.

You can also use the `[e]dit` and `[b]uffer` shell commands available in `PATH`.

### Examples

**Example** – [lf] integration:

``` kak
def lf %(connect lf)
```

**Example** – [fzf] integration:

``` kak
def fzf-files %(connect edit $(fzf))
```

``` kak
def fzf-buffers %(connect buffer $(buffer | fzf))
```

## Commands

- `connect-shell [program] [arguments]`: Run a shell with `[e]dit`, `[b]uffer` and `EDITOR` connected to the current client
- `connect-terminal [program] [arguments]`: Create a new terminal with `[e]dit`, `[b]uffer` and `EDITOR` connected to the current client

## Aliases

- `connect` → `connect-terminal`

## Options

- `connect_shell`: Shell program to be used as default entry-point (Default: `SHELL`)

[Kakoune]: https://kakoune.org
[IRC]: https://webchat.freenode.net?channels=kakoune
[IRC Badge]: https://img.shields.io/badge/IRC-%23kakoune-blue.svg
[Pathogen]: https://github.com/alexherbo2/pathogen.kak
[lf]: https://github.com/gokcehan/lf
[fzf]: https://github.com/junegunn/fzf
