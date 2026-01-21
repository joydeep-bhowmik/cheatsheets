

# SHELL COMMAND CHEATSHEET

## NAVIGATION

```sh
pwd                     # print current directory
ls                      # list files
ls -l                   # long listing
ls -a                   # include hidden files
ls -lh                  # human-readable sizes
cd /path/to/dir         # change directory
cd ..                   # go up one directory
cd ~                    # go home
cd -                    # previous directory
```

---

## FILE OPERATIONS

```sh
touch file.txt          # create empty file
cat file.txt            # view file
less file.txt           # scrollable view
head file.txt           # first 10 lines
tail file.txt           # last 10 lines
tail -f file.txt        # follow live updates
```

---

## DIRECTORY OPERATIONS

```sh
mkdir dir               # create directory
mkdir -p path/to/dir    # create parent dirs as needed
rmdir dir               # remove empty directory
rm -r dir               # delete directory recursively
rm -rf dir              # force delete directory (dangerous)
```

---

## DELETE FILES

```sh
rm file.txt             # delete file
rm -i file.txt          # interactive delete
rm -f file.txt          # force delete
rm *                    # delete all files in current dir
rm -r *                 # delete all files and directories
rm -rf *                # delete everything without prompt (high risk)
rm *.txt                # delete all .txt files
rm .* *                 # delete hidden + normal files (very risky)
```

---

## COPY / MOVE / RENAME

```sh
cp src.txt dest.txt             # copy file
cp -r dir1 dir2                 # copy directory recursively
cp -a src dest                  # archive copy (preserve attrs)
mv old.txt new.txt              # rename or move file
mv file.txt /path/to/dir/       # move file
mv dir1 dir2                    # rename directory
```

---

## SEARCH & FIND

```sh
find . -name "file.txt"         # find file by name
grep "text" file.txt            # search text in file
grep -r "text" .                # recursive search
```

---

## PERMISSIONS

```sh
ls -l                           # view permissions
chmod 644 file.txt               # set permissions
chmod +x script.sh               # make executable
chown user:group file.txt        # change ownership (sudo if needed)
```

---

## DISK USAGE

```sh
df -h                           # disk space usage
du -sh dir                       # directory size
```

---

## ARCHIVES

```sh
tar -czf archive.tar.gz dir       # create tar.gz
tar -xzf archive.tar.gz           # extract tar.gz
zip -r archive.zip dir            # create zip
unzip archive.zip                 # extract zip
```

---

## PROCESSES

```sh
ps                              # list processes
ps aux                          # full list
top                             # live process monitor
kill PID                        # terminate process
kill -9 PID                     # force kill
```

---

## SUPERUSER

```sh
sudo command                     # run command as root
su -                             # switch to root
```

---

## REDIRECTION & PIPES

```sh
command > file.txt               # overwrite output
command >> file.txt              # append output
command < file.txt               # input from file
command1 | command2              # pipe output
ps aux | grep python             # example
```

---

## WILDCARDS / GLOBBING

```sh
*       # all files (not hidden)
?.txt   # any single char followed by .txt
[abc]*  # starts with a, b, or c
*.log   # all .log files
```

---

## SAFETY TIPS

* Always `ls` before destructive commands
* Use `-i` for interactive deletes
* `echo rm *` for dry-run
* Never `rm -rf /` or blindly use wildcards in sensitive dirs

---

