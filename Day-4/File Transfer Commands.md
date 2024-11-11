# Linux  File Transfer Commands

---

## File Transfer and Synchronization Commands

### 1. **SCP** (Secure Copy Protocol)

`scp` is used to securely transfer files and directories between hosts over SSH.

#### Syntax
```bash
scp [options] source_file user@host:destination_path
   - Common Options
- -r: Recursively copy directories
- -P: Specify the SSH port
- -i: Specify an SSH private key file   

- Examples
- Copy a file to a remote server
 ```
 scp file.txt user@remote_host:/remote/directory
 ```
 - Copy a directory to a remote server:
``` 
scp -r /local/directory user@remote_host:/remote/directory

```

- Copy a file from a remote server to the local machine:
```
scp user@remote_host:/remote/file.txt /local/directory

```

### Rsync (Remote Sync)
 rsync is a powerful tool for efficient file synchronization between local and remote systems. It can perform incremental file transfers, transferring only the changed parts of files, saving bandwidth and time.

 - Syntax
 ```
 rsync [options] source destination
```
- options
- -r: Recursively copy directories
- -a: Archive mode (preserves permissions, timestamps, etc.)
- -z: Compress data during transfer
- -v: Verbose output
- --delete: Delete files in the destination that don’t exist in the source

- Sync a local directory to a remote server:
```
rsync -avz /local/directory/ user@remote_host:/remote/directory
```
- Sync a remote directory to the local machine
```
rsync -avz user@remote_host:/remote/directory/ /local/directory
```
- Sync and delete files in the destination not present in the source:
```
rsync -avz --delete /local/directory/ user@remote_host:/remote/directory
```



