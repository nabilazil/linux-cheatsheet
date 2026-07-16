# linux-cheatsheet 🐧
My Linux commands reference for cybersecurity learning

## Shell Operators & Redirection
| Symbol | Name | Purpose | Example |
|--------|------|---------|---------|
| `&` | Background Operator | Run command in background | `sleep 10 &` |
| `&&` | Logical AND Operator | Run second command only if first succeeds | `mkdir test && cd test` |
| `>` | Output Redirection (Overwrite) | Write output to file (erase old content) | `ls > list.txt` |
| `>>` | Output Redirection (Append) | Add output to end of file (keep old) | `echo "new" >> log.txt` |


## Navigation
| Command | Purpose | Example |
|---------|---------|---------|
| `pwd` | Show current path | `pwd` → `/home/user` |
| `cd` | Change directory | `cd folder1`, `cd ..` |
| `ls` | List files (non-hidden only) | `ls` |
| `ls -a` | List ALL files (including hidden) | `ls -a` |
| `ls -la` | List all files with details (permissions, size, date) | `ls -la` |
| `ls -lh` | List files in human-readable format | `ls -lh` |


## File Operations
| Command | Purpose | Example |
|---------|---------|---------|
| `cat` | View file content | `cat notes.txt` |
| `./` | Explicit current directory reference / Bypass special names | `cat ./-`, `./script.sh` |


## File Information & Analysis
| Command | Purpose | Example |
|---------|---------|---------|
| `file` | Identify file type (text, binary, script) | `file ./*` |


## Search & Filter
| Command | Purpose | Example |
|---------|---------|---------|
| `grep` | Search for text in files | `grep "THM" access.log` |
| `find` | Search for files/directories by name, type, size, etc. | `find /home -name "file.txt"`, `find . -type f -size +10M` |
| `find` | Search files with multiple conditions | `find ./dir -type f -size 1033c ! -executable` |
| `find ./dir -name "*.txt"` | Search by name pattern | `find / -name "passwd"` |
| `find ./dir -mtime -7` | Find files modified in last 7 days | `find . -mtime +30` |
| `find / -user [name]` | Find files owned by specific user | `find / -user bandit7` |
| `find / -group [name]` | Find files by group | `find / -group bandit6` |


## Text Processing
| Command | Purpose | Example |
|---------|---------|---------|
| `sort` | Sort lines alphabetically | `sort file.txt` |
| `uniq` | Remove/flag duplicate lines | `uniq file.txt` |
| `uniq -u` | Show ONLY unique lines (occur once) | `sort file.txt \| uniq -u` |
| `uniq -c` | Count occurrences of each line | `sort file.txt \| uniq -c` |
| `strings` | Extract text from binary files | `strings data.txt` |
| `strings \| grep "pattern"` | Find text patterns in binary | `strings data.txt \| grep "=="` |


## Remote Access (SSH)
| Command | Purpose | Example |
|---------|---------|---------|
| `ssh user@host` | Connect to remote server (default port 22) | `ssh kali@192.168.1.10` |
| `ssh user@host -p port` | Connect to custom port | `ssh bandit0@bandit.labs.overthewire.org -p 2220` |
| `ssh -i key.pem user@host` | Connect with SSH key | `ssh -i aws-key.pem ubuntu@ec2-xx-xx.com` |
**Key Points:**
- Default SSH port: `22`
- Custom port: use `-p [port_number]`
- Password typing: **invisible** (no characters shown)
- SSH = Secure Shell ← encrypted remote access to Linux servers
 
