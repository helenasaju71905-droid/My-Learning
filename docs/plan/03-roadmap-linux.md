# Linux Roadmap

Learned mostly **by doing** (running the stack surfaces most of it), backed by curated reference material rather than a course. Two depth tiers.

## Helena — Intermediate

Primary: [Linux Journey](https://linuxjourney.com/) (structured, browser-based). Reference: [The Linux Command Line (Shotts, free)](https://linuxcommand.org/tlcl.php).

Skills (surface naturally from the project):

```
Navigation    pwd  ls -la  cd  tree
Files         touch  mkdir -p  cp  mv  rm -rf  cat  less  head  tail -f
Search        grep -r  find  which  history | grep
Pipes         |  >  >>  2>&1  wc -l  sort  uniq -c
Permissions   chmod +x  ls -l reading (rwx, 644 vs 755)
Processes     ps aux  top  kill -9  lsof -i :3000
Env           export  echo $PATH  env  ~/.bashrc
Packages      apt update  apt install
Editor        nano (survival vim: i, Esc, :wq, :q!)
```

Drills: find which process holds port 3000 and kill it; tail a log and grep it for `ERROR`; make a shell script executable and run it.

## Thomas — Advanced

Everything above **plus** deliberate study (a web app won't surface these on its own):

- [MIT Missing Semester](https://missing.csail.mit.edu/) — shell scripting, tooling, the command line ecosystem.
- [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/) — CLI mastery + security drills, level by level.

Advanced topics:

```
Networking    ss -tlnp  curl -i  tcpdump basics  DNS/ports
Processes     signals, jobs, nohup, systemd unit basics
Scripting     bash functions, args, exit codes, set -euo pipefail
Containers    namespaces/cgroups intuition, docker internals
Performance   top/htop, iostat, reading load
```

Drill: write a bash script that backs up the Postgres volume (`pg_dump`) and rotates old dumps.

## Gate contribution

Linux is validated as part of the Phase 1 assessment via a **skills checklist demonstrated live** (see [`../tracker/rubric.md`](../tracker/rubric.md)) — Helena to intermediate depth, Thomas to advanced.
