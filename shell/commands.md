Here’s a **straight, no-BS cheat sheet** for `rm`, `rm -rf *`, and `cd`. I’ll give you the commands **and** call out the foot-guns so you don’t nuke your system like an amateur.

---

## `cd` (change directory)

### Basics

```bash
cd dir_name        # go into dir_name
cd ..              # go up one level
cd ../..           # go up two levels
cd /               # go to filesystem root
cd ~               # go to your home directory
cd                 # same as cd ~
```

### Useful shortcuts

```bash
cd -               # switch to previous directory
cd ~/projects      # absolute path from home
cd /var/log        # absolute path from root
```

### Reality check

* `cd` **does nothing dangerous by itself**
* But where you `cd` **determines how dangerous your next rm is**

---

## `rm` (remove files)

### Safe-ish usage

```bash
rm file.txt              # delete a single file
rm file1 file2           # delete multiple files
rm *.log                 # delete all .log files
rm -i file.txt           # interactive (asks before deleting)
```

### Directories

```bash
rm -r folder/            # delete folder and contents
rm -ri folder/           # recursive + interactive (smart)
```

---

## `rm -rf` (the nuclear option)

### What the flags mean

* `-r` → recursive (directories + contents)
* `-f` → force (no prompts, no mercy)

### Common patterns

```bash
rm -rf folder/           # delete folder completely
rm -rf folder1 folder2   # delete multiple folders
```

---

## `rm -rf *` (THIS IS THE DANGEROUS ONE)

```bash
rm -rf *
```

### What it does

* Deletes **everything in the current directory**
* Does **NOT** delete hidden files (`.git`, `.env`) unless globbing is extended

### Variants that are even worse

```bash
rm -rf .* *      # deletes hidden files too (can brick your system)
rm -rf /         # goodbye OS
rm -rf ~         # wipes your home directory
```

### Hard truth

If you run `rm -rf *` in the wrong directory:

* There is **no undo**
* No recycle bin
* No “oops” recovery unless you had backups

---

## Safer alternatives (use these unless you enjoy pain)

```bash
ls                      # ALWAYS check first
pwd                     # confirm where you are
rm -ri *                # asks before deleting each item
rm -rf ./folder/*       # limit the blast radius
```

### Pro move

```bash
set -o noclobber        # prevents some destructive overwrites
alias rm='rm -i'       # forces confirmation by default
```

---

## Survival checklist before `rm -rf *`

1. Run `pwd`
2. Run `ls`
3. Ask yourself: *“Am I okay losing ALL of this forever?”*
4. If hesitation exists → **don’t run it**

---



