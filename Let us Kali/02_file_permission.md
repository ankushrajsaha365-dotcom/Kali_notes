# Day 2: Files, Permissions, sudo, and Packages

> All testing was done on my own Kali Linux install and an isolated lab.

## Goal
Learn to read, copy, move, search, and protect files, and install software using `apt`.

## Commands Learned

### Reading files
| Command | Use | Why it matters | Example |
|---|---|---|---|
| `cat` | Prints a whole file | Quick look at configs and notes | `cat notes.txt` |
| `less` | Scrollable viewer (q to quit) | Good for long files | `less /etc/passwd` |
| `head` | First lines of a file | Peek at the start | `head -n 5 file` |
| `tail` | Last lines (`-f` follows live) | Watching logs | `tail -f file` |

### Managing files
| Command | Use | Example |
|---|---|---|
| `cp` | Copy | `cp a.txt b.txt` |
| `mv` | Move or rename | `mv b.txt c.txt` |
| `rm` | Delete (permanent, no recycle bin) | `rm c.txt`, `rm -r folder` |

### Writing and searching
| Command | Use | Why it matters | Example |
|---|---|---|---|
| `echo` | Prints text | Create content fast | `echo "hello"` |
| `>` | Overwrite a file with output | Save command output | `echo "hello" > a.txt` |
| `>>` | Append to a file | Add without erasing | `echo "more" >> a.txt` |
| `grep` | Search text inside files | Find one line in thousands | `grep -i "hello" a.txt` |
| `grep -r` | Search through folders | Hunt through configs | `grep -r "pass" /etc` |
| `find` | Locate files by name | Find a file anywhere | `find / -name "notes.txt" 2>/dev/null` |

`2>/dev/null` hides the "permission denied" error messages.

## Permissions

Run `ls -l` and read something like `-rwxr-xr--`:

| Symbol | Meaning | Number |
|---|---|---|
| `r` | read | 4 |
| `w` | write | 2 |
| `x` | execute | 1 |

The three groups are **owner**, **group**, and **others**.

```bash
chmod +x script.sh     # make executable
chmod 755 file         # owner: rwx, group: r-x, others: r-x
chmod 644 file         # owner: rw-, others: r--
```

Why: scripts and tools will not run without the `x` permission.

## sudo
- Runs **one** command as root (admin).
- Needed for installing software and editing system files.
- Do not stay logged in as root: one typo can break the system.

```bash
sudo apt update
```

## apt (package manager)

```bash
sudo apt update            # refresh package list
sudo apt upgrade           # update installed software
sudo apt install tree      # install a package
apt search nmap            # search for packages
sudo apt remove tree       # uninstall
```


## What I Learned
- `>` overwrites, `>>` appends. Mixing them up can erase a file.
- `rm` is permanent, so double-check before running it.
- Permission numbers add up: 7 = 4+2+1, 5 = 4+1, 4 = read only.
- `sudo` is for single commands, not for working as root all day.

