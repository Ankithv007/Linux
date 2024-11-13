# File Test Operators in Shell Scripting

In shell scripting, file test operators are used to check properties of files and directories, such as existence, type, permissions, and size. They are commonly used in `if` statements to make conditional decisions based on file properties.

## Common File Test Operators

| Operator | Description                                | Example                                   |
|----------|--------------------------------------------|-------------------------------------------|
| `-e`     | Checks if a file or directory exists       | `if [ -e file.txt ]; then`                |
| `-f`     | Checks if it is a regular file             | `if [ -f file.txt ]; then`                |
| `-d`     | Checks if it is a directory                | `if [ -d myfolder ]; then`                |
| `-r`     | Checks if it has read permission           | `if [ -r file.txt ]; then`                |
| `-w`     | Checks if it has write permission          | `if [ -w file.txt ]; then`                |
| `-x`     | Checks if it has execute permission        | `if [ -x script.sh ]; then`               |
| `-s`     | Checks if the file is non-empty            | `if [ -s file.txt ]; then`                |
| `-L`     | Checks if it is a symbolic link            | `if [ -L symlink ]; then`                 |
| `-c`     | Checks if it is a character device file    | `if [ -c device ]; then`                  |
| `-b`     | Checks if it is a block device file        | `if [ -b device ]; then`                  |
| `-p`     | Checks if it is a named pipe (FIFO)        | `if [ -p pipefile ]; then`                |
| `-h`     | Checks if it is a symbolic link (alternative to `-L`) | `if [ -h link ]; then` |
| `-N`     | Checks if it was modified since last read  | `if [ -N file.txt ]; then`                |
| `-O`     | Checks if the file is owned by the user    | `if [ -O file.txt ]; then`                |
| `-G`     | Checks if the file's group matches the user’s group | `if [ -G file.txt ]; then`  |

## Examples

### 1. Check if a File Exists

```bash
if [ -e file.txt ]; then
  echo "file.txt exists."
else
  echo "file.txt does not exist."
fi
```
2. Check if a Directory Exists
```bash
if [ -d myfolder ]; then
  echo "Directory myfolder exists."
else
  echo "Directory myfolder does not exist."
fi

```
3. Check if a File is Readable, Writable, and Executable
```bash
if [ -r file.txt ] && [ -w file.txt ] && [ -x file.txt ]; then
  echo "file.txt has read, write, and execute permissions."
else
  echo "file.txt does not have the necessary permissions."
fi

```
4. Check if a File is a Symbolic Link

```bash
if [ -L symlink ]; then
  echo "symlink is a symbolic link."
else
  echo "symlink is not a symbolic link."
fi
```
5. Check if a File is Empty or Non-Empty

```bash
if [ -s file.txt ]; then
  echo "file.txt is not empty."
else
  echo "file.txt is empty."
fi
```
6. Check if a File is a Block or Character Device
```bash
if [ -b /dev/sda ]; then
  echo "/dev/sda is a block device."
fi

if [ -c /dev/tty ]; then
  echo "/dev/tty is a character device."
fi

```
7. Check if a File is Owned by the Current User
```bash
if [ -O file.txt ]; then
  echo "file.txt is owned by the current user."
else
  echo "file.txt is not owned by the current user."
fi

```
8. Check if a File's Group Matches the User's Group
```bash
if [ -G file.txt ]; then
  echo "file.txt belongs to the user's group."
else
  echo "file.txt does not belong to the user's group."
fi

```
9. Check if a File has been Modified Since Last Read
```bash
if [ -N file.txt ]; then
  echo "file.txt has been modified since it was last read."
else
  echo "file.txt has not been modified since last read."
fi

```
10. Check for a Named Pipe (FIFO)
```bash
if [ -p mypipe ]; then
  echo "mypipe is a named pipe (FIFO)."
else
  echo "mypipe is not a named pipe."
fi
```
- File test operators enable you to perform condition checks on files and directories effectively in shell scripts. They are essential for creating robust scripts that can validate and manipulate files based on their properties.






















