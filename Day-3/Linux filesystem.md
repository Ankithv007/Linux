# Linux Filesystem Architecture

The Linux filesystem follows the **Filesystem Hierarchy Standard (FHS)**, organizing files and directories in a hierarchical, tree-like structure. This guide provides a tree view of the Linux filesystem architecture with brief descriptions for each main directory.

```plaintext
/
├── bin               # Essential command binaries (e.g., ls, cp, mv)
├── boot              # Boot loader files (e.g., kernel, initrd)
├── dev               # Device files (e.g., /dev/sda for disk devices)
├── etc               # Configuration files for system and applications
│   ├── passwd        # User account information
│   ├── fstab         # Filesystem mount table
│   └── ssh/          # SSH configuration files
├── home              # User home directories
│   ├── user1         # Home directory for user1
│   └── user2         # Home directory for user2
├── lib               # Essential shared libraries and kernel modules
├── lib64             # 64-bit libraries (on some systems)
├── media             # Mount points for removable media (e.g., USB drives)
│   ├── cdrom         # CD-ROM mount point
│   └── usb           # USB mount point
├── mnt               # Temporary mount points for filesystems
├── opt               # Optional application software packages
├── proc              # Virtual filesystem for system information
│   ├── 1             # Information for process with PID 1
│   └── cpuinfo       # CPU information
├── root              # Home directory for the root user
├── run               # Runtime variable data (e.g., process IDs, sockets)
├── sbin              # Essential system binaries (e.g., init, ip, mount)
├── srv               # Data for services provided by the system
├── sys               # Virtual filesystem for system hardware information
├── tmp               # Temporary files
├── usr               # Secondary hierarchy for user data
│   ├── bin           # User command binaries (e.g., gcc, make)
│   ├── include       # Header files
│   ├── lib           # Libraries for user applications
│   ├── local         # Locally installed software
│   └── share         # Shared data (e.g., man pages, docs)
└── var               # Variable data (logs, spool files, etc.)
    ├── cache         # Application cache data
    ├── log           # Log files (e.g., system logs, error logs)
    ├── mail          # Mail storage
    ├── spool         # Spool directory for tasks (e.g., printing jobs)
    └── tmp           # Temporary files preserved between reboots
```
### Key Directory Descriptions

```
/bin: Stores essential command binaries used by all users (e.g., ls, cp, mv).
/boot: Contains files needed to boot the system, such as the kernel and initrd images.
/dev: Holds device files representing hardware devices (e.g., disks, terminals).
/etc: Configuration files for the system and applications.
/home: The default location for user home directories.
/lib and /lib64: Libraries essential for running binaries in /bin and /sbin.
/media and /mnt: Used for mounting filesystems like USB drives and external disks.
/opt: Stores optional, additional software packages.
/proc: A virtual filesystem providing system and process information.
/root: The home directory of the root (admin) user.
/sbin: Contains system binaries primarily used by the system administrator.
/sys: A virtual filesystem with kernel and device information.
/tmp: Temporary files created by applications and processes.
/usr: Contains user applications, libraries, and documentation.
/var: Stores variable data like logs, spools, and cache files.

```

