# tmux

| `tmux new -s [session-name]`          | Create new session        |
| `tmux ls`                             | List existing sessions    |
| `tmux attach -t [session-name]`       | Attach to a session       |
| `tmux kill-session -t [session-name]` | Kill specific session     |
| `tmux kill-server`                    | Kill all sessions         |

## Quick commands

Always `ctrl-b` plus:

### Sessions

| `$` | Rename session  |
| `s` | List sessions   |
| `d` | Detach          |

### Windows

| `c` | Create new          |
| `,` | Rename window       |
| `w` | List windows        |
| `%` | Split horizontally  |
| `"` | Split vertically    |
| `n` | Next window         |
| `"` | Previous window     |

### Panes

| `%` | Create horizontal pane  |
| `"` | Create vertical pane    |
| `o` | Toggle between panes    |
| `x` | Kill current pane       |


## Components' intentions

 - **Session**: Overall theme (e.g. sysadmin)
 - **Window**: Project within a theme (e.g. logs)
 - **Pane**: View within a project (e.g. syslog, errlog)


# tmuxinator

[Github link](https://github.com/tmuxinator/tmuxinator)

## Commands

| `tmuxinator new [project]`                | Create or edit project                |
| `tmuxinator start [project]`              | Start a project                       |
| `tmuxinator start [project] -n [name]`    | Start a project with a custom name    |
| `tmuxinator copy [project] [new]`         | Duplicate a project                   |
| `tmuxinator list`                         | List all projects                     |

## Simple config

```
name: session-name
root: /path/to/wd

startup_window: window-name

windows:
    - project-name:
        root: /wd/of/project
        panes:
          - command1 arg1 arg2
          - command2
```