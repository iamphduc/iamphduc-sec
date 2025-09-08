---
title: "OverTheWire - Bandit Level 4 -> Level 5"
date: 2025-09-08 11:30:00 +0700
categories: [OverTheWire, Bandit]
tags: [overthewire, bandit, linux]
author: iamphduc
---

### Task
Link: [https://overthewire.org/wargames/bandit/bandit5.html](https://overthewire.org/wargames/bandit/bandit5.html)
SSH: `ssh bandit4@bandit.labs.overthewire.org -p 2220` 

No further explanation since the task is already clear.

### Solution
```bash
$ cd inhere
$ ls -a
```

As the problem said: "the only human-readable file", all we need is using the command `file` to check whether that file is human readable.

But we see all files start with a hyphen (-) at the beginning of their name. Dealing with files that start with a hyphen is tricky because many commands
interpret arguments starting with a hyphen as options.

We can use double dash `--` to signal our terminal this is the end of command options

or

We add prefixing `./` which means current directory and follow up with `*` meaning everything in this directory.

```bash
$ file ./*

./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
```

```bash
$ cat ./-file07

4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

### Note
Dealing with files that start with a hyphen, we can use either double dash `--` method or `./` current directory method
