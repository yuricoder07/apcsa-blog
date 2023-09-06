---
toc: true
comments: false
layout: post
title: Linux & Bash
description: xx
type: tangibles
courses: { csa: {week: 1} }
permalink: /linux-and-bash
---

> Setting up Linux and using Bash to check tools

### Student View
> Come up with your own student view of this procedure to show your tools are installed.

```
(base) yuri@Yuris-MacBook-Air ~ % >....                                         
echo "Using conditional statement to create a project directory and project"

cd ~    # start in home directory

# Conditional block to make a project directory
if [ ! -d $project_dir ]
then
    echo "Directory $project_dir does not exists... makinng directory $project_dir"
    mkdir -p $project_dir
fi
echo "Directory $project_dir exists."

# Conditional block to git clone a project from project_repo
if [ ! -d $project ]
then
    echo "Directory $project does not exists... cloning $project_repo"
    cd $project_dir
    git clone $project_repo
    cd ~
fi
echo "Directory $project exists."

fg: no current job
zsh: command not found: #
Using conditional statement to create a project directory and project
cd: too many arguments
zsh: command not found: #
Directory /Users/yuri/vscode exists.
zsh: command not found: #
Directory /Users/yuri/vscode/teacher exists.
(base) yuri@Yuris-MacBook-Air ~ % 
```

### Frequent Linux Commands
> Name and create notes on some Linux commands you will use frequently.


1. **ls**: List files and directories in the current directory.
   - Example: `ls -l` (long format), `ls -a` (including hidden files), `ls -lh` (long format with human-readable file sizes).

2. **cd**: Change the current directory.
   - Example: `cd /path/to/directory`.

3. **pwd**: Print the current working directory.

4. **mkdir**: Create a new directory.
   - Example: `mkdir new_folder`.

5. **rm**: Remove files or directories.
   - Example: `rm file.txt` (remove a file), `rm -r directory` (remove a directory recursively), `rm -rf directory` (forcefully remove a directory and its contents).

6. **cp**: Copy files or directories.
   - Example: `cp file.txt /path/to/destination`, `cp -r source_dir/ destination_dir/`.

7. **mv**: Move (rename) files or directories.
   - Example: `mv old_file.txt new_file.txt`, `mv file.txt /new/directory`.

8. **touch**: Create an empty file.
   - Example: `touch new_file.txt`.

9. **cat**: Display the contents of a file.
   - Example: `cat file.txt`.

10. **nano** or **vim**: Text editors for creating or editing files from the terminal.
    - Example (nano): `nano file.txt`, exit with `Ctrl + X`.
    - Example (vim): `vim file.txt`, exit with `:wq`.

11. **grep**: Search for text patterns in files.
    - Example: `grep "pattern" file.txt`.

12. **chmod**: Change file permissions.
    - Example: `chmod +x script.sh` (add executable permission), `chmod 644 file.txt` (set specific permission mode).

13. **chown**: Change file ownership.
    - Example: `chown user:group file.txt`.

14. **ps**: Display information about running processes.
    - Example: `ps aux`.

15. **top** or **htop**: Display real-time system resource usage and process information.
    - Example (top): `top`, exit with `q`.
    - Example (htop): `htop`, exit with `F10`.

16. **df**: Display disk space usage.
    - Example: `df -h` (human-readable sizes).

17. **du**: Display file/directory disk usage.
    - Example: `du -h file.txt` (human-readable size), `du -sh directory` (summary).

18. **wget**: Download files from the internet.
    - Example: `wget URL`.

19. **tar**: Create or extract compressed archive files.
    - Example (create): `tar -czvf archive.tar.gz files/`.
    - Example (extract): `tar -xzvf archive.tar.gz`.

20. **ssh**: Securely log into a remote server.
    - Example: `ssh username@remote_server`.

### Version Checking
> Is there anything we use to verify tools we install? Review versions checks.

We can either use `which`, `pwd`, `tool -v`, or variables such as `$tool` to verify tools we install.

### Verify WSL and Anaconda
> Is there anything we could verify with Anaconda? or WSL?

Yes, in our Powershell we can run `wsl --v` to verify our WSL. Same syntax applies to Anaconda.

### Updating Repositories With Bash
> How would you update a repository? Could you do that in script above?

You can update a repository with Linux using Git commands:

``` bash
cd /path/to/your/repository
git fetch origin
git pull origin master
git commit -m "msg" -a
git push
```