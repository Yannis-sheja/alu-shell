# loops_conditions_and_parsing

This project is part of the `alu-shell` repository. It groups a series of
Bash scripts that practice loops (`for`, `while`, `until`), conditionals
(`if`/`elif`/`else`, `case`), and basic log/text parsing.

## Environment

* Written and tested for Ubuntu 20.04 LTS.
* All scripts start with `#!/usr/bin/env bash`.
* The second line of every script is a comment describing what it does.
* All scripts are executable (`chmod +x`).
* All files end with a new line.

## Files

| File | Description |
| --- | --- |
| `1-for_best_school` | Prints `Best School` 10 times with a `for` loop |
| `2-while_best_school` | Prints `Best School` 10 times with a `while` loop |
| `3-until_best_school` | Prints `Best School` 10 times with an `until` loop |
| `4-if_9_say_hi` | `while` + `if`, prints `Hi` after the 9th `Best School` |
| `5-4_bad_luck_8_is_your_chance` | `while` + `if`/`elif`/`else`, special messages on 4 and 8 |
| `6-superstitious_numbers` | `while` + `case`, prints numbers 1-20 with superstition messages |
| `7-clock` | Nested `while` loops, prints hours 0-12 and minutes 1-59 |
| `8-for_ls` | `for` loop over the current directory, strips everything up to the first dash |
| `9-to_file_or_not_to_file` | `if`/`else` checks on a file named `school` |
| `10-fizzbuzz` | Prints 1-100, replacing multiples of 3/5/15 with Fizz/Buzz/FizzBuzz |
| `11-read_and_cut` | `while` + `read` with `IFS`, prints username/uid/home from `/etc/passwd` |
| `12-tell_the_story_of_passwd` | `while` + `read` with `IFS`, tells a short story for every user in `/etc/passwd` |
| `13-lets_parse_apache_logs` | `awk` one-liner extracting `IP HTTP_CODE` from `apache-access.log` |
| `14-dig_the-data` | `awk` + `sort`/`uniq` grouping visitors by IP and status code, sorted by occurrence count |
| `apache-access.log` | Sample log file used to test tasks 13 and 14 |

## Notes

* For tasks 0-12, `awk` is intentionally **not** used, per the project
  rules. Tasks 13 and 14 are the documented exception: their own
  instructions explicitly require `awk` and forbid `while`/`for`/`until`/`cut`.
* `apache-access.log` included here is only a small sample so the scripts
  can be tested end-to-end. Replace it with the full log file provided by
  the course before submitting, since the real grading log is much larger
  and produces the occurrence counts shown in the project examples.
* Scripts were checked by hand against `shellcheck` conventions (quoted
  variables, `$()` instead of backticks, POSIX `[ ]` test syntax). If you
  have `shellcheck` installed, run e.g. `shellcheck 1-for_best_school` to
  confirm before submitting.
