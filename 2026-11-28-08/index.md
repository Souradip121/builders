---
title: "Learn Linux in 2 weeks: the order + every free link"
---

# Learn Linux in 2 weeks: the order + every free link

The idea: stop watching long courses and get your hands on a real terminal from day 1. Everything below is free. Checked on the official pages on 27 Nov 2026.

## Days 1-2: get a Linux
- **Windows: WSL** (https://learn.microsoft.com/en-us/windows/wsl/install). Needs Windows 10 version 2004+ (build 19041+) or Windows 11. Open PowerShell as administrator, run `wsl --install`, restart. It installs **Ubuntu** by default and sets up WSL 2.
- **Mac:** the built-in Terminal is Unix-like and fine for most of this. **Or** dual boot, or use the free in-browser terminals on Linux Journey.

## Days 3-5: the basics
- **Linux Journey** (https://labex.io/linuxjourney, the old linuxjourney.com redirects here): free, no sign-up. Lessons on the command line, text editing, users and permissions, processes, package managers, then filesystem, boot, networking.
- **The Linux Command Line** by William Shotts (https://linuxcommand.org/tlcl.php): a full book, free PDF under a CC BY-NC-ND licence (Seventh Internet Edition). Use it as the reference when a lesson feels thin.

## Days 6-8: MIT Missing Semester
- https://missing.csail.mit.edu/ , the 2026 edition: shell, command-line environment, dev tools, debugging and profiling, version control and Git, packaging code, and more. Lecture videos are linked on the site (YouTube playlist). Do the exercises, not just the videos.

## Days 9-11: OverTheWire Bandit
- https://overthewire.org/wargames/bandit/ : a command-line wargame "aimed at absolute beginners".
- Start: `ssh bandit0@bandit.labs.overthewire.org -p 2220`, password `bandit0`. Each level hides the password for the next one. Aim for level 10+.

## Days 12-14: run a real server
- **Linux Upskill Challenge** (https://linuxupskillchallenge.org/): free and open source, 21 lessons, about 1-2 hours a day. It restarts on the **first Monday of each month** (next: 7 Dec 2026). You need your own internet-facing server; the course explains free and low-cost ways to get one.
- **Mini project:** write `backup.sh` that tars your `~/projects` folder into `~/backups` with the date in the filename, then schedule it with `crontab -e`. Push it to GitHub with a README.

## 20 commands to know
`pwd` `ls` `cd` `mkdir` `cp` `mv` `rm` `cat` `less` `grep` `find` `chmod` `chown` `ps` `kill` `top` `ssh` `tar` `curl` `man`
Bonus: pipes (`|`), redirection (`>`, `>>`), `sudo`, `apt` (Ubuntu's package manager).

## Sources (checked 27 Nov 2026)
- https://learn.microsoft.com/en-us/windows/wsl/install
- https://labex.io/linuxjourney
- https://linuxcommand.org/tlcl.php
- https://missing.csail.mit.edu/
- https://overthewire.org/wargames/bandit/bandit0.html
- https://linuxupskillchallenge.org/

---

Found this useful? Follow [@souradip.sh](https://www.instagram.com/souradip.sh/) for one builder tool a day.
