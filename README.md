# Daylist

A small daily task widget for the Linux terminal. It uses only Python's standard library and stores tasks by local date.

## Download and install

Daylist is a single Python script. It needs Python 3 with the standard `curses` module; there are no pip dependencies. Install Python if it is not already available:

| Distribution | Command |
| --- | --- |
| Arch Linux, Manjaro, EndeavourOS | `sudo pacman -S python` |
| Ubuntu, Debian, Linux Mint, Pop!_OS | `sudo apt update && sudo apt install python3` |
| Fedora | `sudo dnf install python3` |
| Other Linux distributions | Install your distribution's Python 3 package. |

To download Daylist, open the [daylist script on GitHub](https://github.com/parthmunjal07/daylist/blob/master/daylist), choose **Raw** or **Download**, and save it as `daylist` in your Downloads folder. You can also [download the project archive](https://github.com/parthmunjal07/daylist/archive/refs/heads/master.zip), extract it, and use the `daylist` script inside.

Install the downloaded script for your user account:

```sh
mkdir -p ~/.local/bin
install -m 755 ~/Downloads/daylist ~/.local/bin/daylist
daylist
```

If you already have the source folder locally, run `install -m 755 daylist ~/.local/bin/daylist` from the folder containing this README. The same command updates an existing installation.

If your shell says `daylist: command not found`, add `~/.local/bin` to your `PATH` in your shell profile, then open a new terminal. You can also run `~/.local/bin/daylist` directly.

## Use

Run `daylist` to open the interactive dashboard. Press `?` or `h` to view all commands inside the widget. Use the arrow keys or `j`/`k` to choose a task, then press Space or Enter to check it off. Press `a` to add, `e` to edit, `x` to delete, and `q` to quit. The “Add another task” row also opens the add prompt.

Other terminal commands:

```text
daylist add Buy groceries
daylist done 1
daylist undo 1
daylist remove 1
daylist list
daylist commands
daylist --help
```

`daylist commands` prints every terminal command and widget shortcut. The commands view inside the widget scrolls with the arrow keys and closes with `?`, `h`, Enter, or Esc.

Yesterday's bar shows the portion of yesterday's tasks completed. Daily average is the mean completion rate across all saved days that contain tasks, including today. Days with no tasks are excluded.

Data is saved to `~/.local/share/daylist/tasks.json` by default. Set `XDG_DATA_HOME` or `DAYLIST_DATA_FILE` to change the location.
