# Day 1: Terminal Basics

> All testing was done on my own Kali Linux install and an isolated lab.

## Goal
Learn how to find my way around the Kali terminal: where I am, what is around me, and how to create files and folders.

## Environment
- OS: Kali Linux (dual boot, installed on my own device)
- Tool: default terminal
- Check version: `cat /etc/os-release`

## Commands Learned

| Command | Use | Why it matters | Example |
|---|---|---|---|
| `pwd` | Shows the current folder | Always know where you are before acting | `pwd` → `/home/kali` |
| `ls` | Lists files and folders | See what is around you | `ls`, `ls -l`, `ls -a`, `ls -la` |
| `cd` | Moves between folders | Tools and files live in different places | `cd Desktop`, `cd ..`, `cd ~`, `cd /` |
| `whoami` | Shows the current user | Permissions depend on the user (normal vs root) | `whoami` → `kali` |
| `mkdir` | Creates a folder | Organize practice work | `mkdir practice` |
| `touch` | Creates an empty file | Quickly make files to work with | `touch notes.txt` |
| `clear` | Cleans the screen | Keeps the terminal readable | `clear` or Ctrl+L |

## Useful Flags
- `ls -l`: long format (permissions, owner, size, date)
- `ls -a`: shows hidden files (names starting with `.`)
- `ls -la`: both together

## Shortcuts
- **Tab**: autocomplete file and command names
- **Up arrow**: repeat previous commands
- **Ctrl+L**: clear the screen
- **Ctrl+C**: stop a running command


## What I Learned
- Everything in Kali revolves around the terminal.
- `pwd` and `ls` are the first commands to run when I'm lost.
- `cd ..` goes up one level; `cd ~` always returns home.
- Hidden files only show up with `ls -a`.
