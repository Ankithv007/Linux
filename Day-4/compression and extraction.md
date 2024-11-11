# Linux Compression and Extraction Commands

This document provides a reference for commonly used Linux commands to compress and extract files, including `tar`, `gzip`, and `zip`. It also includes instructions for using `unzip` to extract `.zip` archives.

---

## 1. **Tar** (Tape Archive)

`tar` is primarily used for archiving multiple files and directories into a single file, known as a tarball.

### Syntax
```bash
tar [options] archive_name.tar file_or_directory
```
- -c: Create a new archive 
- -x: Extract files from an archive
- -v: Verbose, shows files being processed
- -f: Specify the archive file name
- -z: Compress with gzip
- -j: Compress with bzip2
- -J: Compress with xz


## Gzip
gzip is used for compressing individual files. It replaces the original file with a compressed version.

- Syntax
```
gzip [options] file
```
- -d: Decompress a file
- -k: Keep the original file after compression

## Zip
zip is commonly used for creating compressed archives in .zip format, especially for cross-platform compatibility.
```
zip [options] archive_name.zip file_or_directory

```
   - Common Options
- -r: Recursively zip directories
- -d: Delete entries from a zip archive
- -e: Encrypt the archive with a password

## Unzip
unzip is used to extract files from .zip archives.

```
unzip [options] archive_name.zip
```
   - Common Options
- -d: Extract files to a specific directory.
- -l: List the contents of the .zip archive without extracting.
- -o: Overwrite existing files without prompting.
- -v: Display verbose output, showing details of the files being extracted.   

   - example
 ```
 Extract files from a .zip archive:
 ```

 ### Comparison of Tar, Gzip, and Zip
 ## Comparison of Tar, Gzip, and Zip

| Tool | Primary Use                                            | Compression | Encryption |
|------|--------------------------------------------------------|-------------|------------|
| Tar  | Archiving (usually combined with `gzip` or `bzip2`)    | No          | No         |
| Gzip | Compressing individual files                           | Yes         | No         |
| Zip  | Compressing and archiving with cross-platform support  | Yes         | Yes        |
  


