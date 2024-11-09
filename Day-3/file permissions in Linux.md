# Understanding `chmod` and File Permissions in Linux

Linux file permissions are controlled by the `chmod` command, which can modify access permissions using binary and octal (numerical) values. Each file or directory in Linux has permissions for three types of users:
1. **Owner**: The user who owns the file.
2. **Group**: Other users who belong to the file's group.
3. **Others**: All other users.

Each of these user types can have three types of permissions:
- **Read (`r`)**: Permission to read the file (binary `100`, octal `4`).
- **Write (`w`)**: Permission to modify the file (binary `010`, octal `2`).
- **Execute (`x`)**: Permission to execute the file (binary `001`, octal `1`).

The permissions are represented in a **3-bit binary format** for each user category, creating an octal number when converted.

## How `chmod` Permissions Work in Binary

### Binary Representation of Permissions

| Permission | Binary | Octal |
|------------|--------|-------|
| ---        | `000`  | 0     |
| --x        | `001`  | 1     |
| -w-        | `010`  | 2     |
| -wx        | `011`  | 3     |
| r--        | `100`  | 4     |
| r-x        | `101`  | 5     |
| rw-        | `110`  | 6     |
| rwx        | `111`  | 7     |

For example:
- **`7` (binary `111`)** means **read, write, and execute** permissions.
- **`6` (binary `110`)** means **read and write** permissions.
- **`5` (binary `101`)** means **read and execute** permissions.
- **`4` (binary `100`)** means **read-only** permission.

### Structure of `chmod` Permission Syntax

The `chmod` command uses three digits to specify permissions for **Owner**, **Group**, and **Others** in that order. For instance, `chmod 755 filename` sets permissions as follows:
1. **7** (Owner) = `111` in binary = `rwx`
2. **5** (Group) = `101` in binary = `r-x`
3. **5** (Others) = `101` in binary = `r-x`

### Example Permissions Using `chmod`

1. **`chmod 777 filename`**: Full permissions for everyone.
   - Owner: `rwx` (7) = read, write, execute
   - Group: `rwx` (7) = read, write, execute
   - Others: `rwx` (7) = read, write, execute

2. **`chmod 644 filename`**: Common permission for files.
   - Owner: `rw-` (6) = read, write
   - Group: `r--` (4) = read-only
   - Others: `r--` (4) = read-only

3. **`chmod 755 filename`**: Common permission for executable files.
   - Owner: `rwx` (7) = read, write, execute
   - Group: `r-x` (5) = read, execute
   - Others: `r-x` (5) = read, execute

## Using Binary to Understand `chmod`

Each permission digit represents a **binary sum** of `r`, `w`, and `x`:

- `7` = `4 + 2 + 1` = `rwx`
- `6` = `4 + 2` = `rw-`
- `5` = `4 + 1` = `r-x`
- `4` = `4` = `r--`

### Summary of `chmod` Syntax with Binary

To set permissions:
1. Convert the desired permissions for each user type (Owner, Group, Others) to binary or octal.
2. Use `chmod XYZ filename`, where **X** is for Owner, **Y** for Group, and **Z** for Others.

### Example Command

```bash
chmod 750 example.sh
