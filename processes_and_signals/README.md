# processes_and_signals

This project is part of the `alu-shell` repository. It covers inspecting
running processes and sending/trapping Unix signals from Bash.

## Environment

* Written and tested for Ubuntu 20.04 LTS.
* All scripts start with `#!/usr/bin/env bash`.
* The second line of every script is a comment describing what it does.
* All scripts are executable (`chmod +x`).
* All files end with a new line.

## Files

| File | Description |
| --- | --- |
| `0-what-is-my-pid` | Displays its own PID (`$$`) |
| `1-list_your_processes` | Lists every process, every user, with hierarchy (`ps aux --forest`) |
| `2-show_your_bash_pid` | Filters the process list for lines containing `bash` (uses `grep`, not `pgrep`) |
| `3-show_your_bash_pid_made_easy` | Same idea, but with `pgrep -l bash` (no `ps`) |
| `4-to_infinity_and_beyond` | Prints `To infinity and beyond` forever, 2s apart |
| `5-dont_stop_me_now` | Stops `4-to_infinity_and_beyond` using `kill` |
| `6-stop_me_if_you_can` | Stops `4-to_infinity_and_beyond` without `kill`/`killall` (`pkill`) |
| `7-highlander` | Like task 4, but traps `SIGTERM` and refuses to die (`I am invincible!!!`) |
| `67-stop_me_if_you_can` | Copy of task 6, retargeted at `7-highlander` |
| `8-beheaded_process` | Actually kills `7-highlander` by sending `SIGKILL`, which can't be trapped |
| `10-process_and_pid_file` | Writes a PID file, runs forever, reacts differently to `SIGTERM`/`SIGINT`/`SIGQUIT` |
| `manage_my_process` | Daemon: writes `I am alive!` to `/tmp/my_process` every 2s, forever |
| `11-manage_my_process` | Init-style script: `start` / `stop` / `restart` for `manage_my_process`, tracks PID in `/var/run/my_process.pid` |

## Notes

* Tasks that write to `/var/run/` (`10-process_and_pid_file`, `11-manage_my_process`)
  need to be run with `sudo`, since regular users can't write there.
* `11-manage_my_process` calls `./manage_my_process` relative to its own
  location, so keep both files in the same directory.
* Scripts were checked by hand against `shellcheck` conventions (quoted
  variables, no unquoted command substitution, `# shellcheck disable=SC2009`
  exactly on line 3 of `2-show_your_bash_pid` as required). If you have
  `shellcheck` installed, run e.g. `shellcheck 0-what-is-my-pid` to confirm
  before submitting.
