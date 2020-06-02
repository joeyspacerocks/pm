# teenypm
A teeny, tiny CLI project manager.

Suitable for solo development projects; stores data in a local SQLite file.

## Install

`pip install teenypm`

Once installed you can execute it using:

`pm`

## Usage

When run `pm` will create a small sqlite file in your current working directory named `pm.db`.

* `pm` - show open issues
* `pm -h` - show help
* `pm <command> -h` show help for command

Subcommands:

* `pm show [-a] [tags]` - show issues, optionally including closed and/or filtering by tags
* `pm tags` - show a summary of all tags with issue counts
* `pm add [-e] <tags> <title> [points]` - add an issue with optional complexity points (defaults to 1), optionally opening an editor for multiline text
* `pm edit <id>` - open an editor to edit issue text
* `pm rm <id>` - remove an issue
* `pm start <id>` - mark issue as in-progress
* `pm backlog <id>` - places issue back in the backlog
* `pm end <id>` - mark issue as completed
* `pm commit <id>` - mark issue as completed and commit changes to git using issue text for message
* `pm tag [-r] <tag> <id>` - add/remove a tag to/from an issue
* `pm feature [-r] <tag>` - flags/unflags a tag as a feature (used to group issues in list display)
* `pm plan [tag]` - open an editor for entering multiple issues, optionally tagged with `<tag>`

*Experimental*

* `pm burn` - show a burndown chart with estimated finish time

*Planned*

* `pm start random` - start a random backlog issue
* `pm start <id> <timeframe>` - start an issue and promise to finish it within a timeframe

## Configuration

The editor used for the `addx`, `edit` and `plan` commands defaults to `vim`.

You can specify an alternative by setting the `EDITOR` environment variable.

For example, to use VS Code:

`export EDITOR="code --wait --new-window"`

(Assumes that the `code` command has been installed from VS Code - see https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line.)
