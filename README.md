# rsync-script

This repository contains a collection of shell scripts for using `rsync` to perform efficient file transfers and backups across multiple machines.

## Usage

This repository contains several useful shell scripts for performing various rsync tasks. Here are the list of the scripts and their purposes:

- `rsync-android`: This script performs a backup of android internal storage data to external drive.
- `rsync-termux`: This script performs a backup of android internal storage data to external drive using `termux` in Android device.

## Prerequisites

To use these scripts, you will need:

- A Unix-like operating system, such as Linux, macOS, or FreeBSD
- The `rsync` utility, which is pre-installed on most Unix-like systems.
- Basic familiarity with the terminal.

## Scripts and config variables

1) `rsync-android` : 
A shell script to backup android internal storage data to external drive.
uses [`'Android File Transfer For Linux'`](https://whoozle.github.io/android-file-transfer-linux/) to mount Android internal storage as mtp. Make sure to configure it first.

Before executing the script, Replace the config variables as per your needs:

`mtpDIR`   : mtp mount directory

`ExtDrive` : Path of External Drive

`DESTINATIONDIR` : Destination path in External Drive

`EXCLUDES` : excludes file.  [`rsync_excludes.txt`](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-android/rsync_excludes.txt)- this contains a wildcard pattern per line of files to be excluded.

`BackupDirFile` : [BackupDir.txt file](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-android/BackupDir.txt) - this contains per line of directories to be backed up.


2) `rsync-termux` : A shell script to backup android internal storage data to external drive via `termux`.
- Install [termux](https://github.com/termux/termux-app/releases) app.
- Install `rsync` package by excuting:
    ```sh
    pkg install rsync
    ```
- Install `rsync-termux` script
    ```sh
    mkdir -pv ~/home/local/bin
    cd ~/home/local/bin
    curl https://raw.githubusercontent.com/dhacommas/rsync-script/main/rsync-termux > rsync-termux

Before executing the script, Replace the config variables as per your needs:

`configDIR` : config directory in sdcard path which contains BackupDir.txt and rsync_excludes.txt

`ExtDrive` : Path of External Drive

`DESTINATIONDIR` : Destination path in External Drive

`EXCLUDES` : excludes file. [`rsync_excludes.txt`](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-termux/rsync_excludes.txt)- this contains a wildcard pattern per line of files to be excluded.

`BackupDirFile` : [`BackupDir.txt file`](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-termux/BackupDir.txt) - this contains per line of directories to be backed up.

3) `rsync-linux` : 
A shell script to backup linux machine data to external drive.

Before executing the script, Replace the config variables as per your needs:

`ExtDrive` : Path of External Drive

`DESTINATIONDIR` : Destination path in External Drive

`EXCLUDES` : excludes file.  [`rsync_excludes.txt`](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-linux/rsync_excludes.txt)- this contains a wildcard pattern per line of files to be excluded.

`BackupDirFile` : [BackupDir.txt file](https://github.com/dhacommas/rsync-script/blob/main/script/rsync-linux/BackupDir.txt) - this contains per line of directories to be backed up.
    
## Installation

To install these scripts, simply clone the repository:
```sh
git clone https://github.com/dhacommas/rsync-script.git
```
ssh:
```sh
git clone git@github.com:dhacommas/rsync-script.git
```
`Be sure to replace the config variables as per your needs before executing the script.`

To use any of these scripts, simply navigate to the directory containing the script and run it. For example:
```sh
cd rsync-script
chmod +x rsync-android
./rsync-android
```
Add the script path to `PATH` to execute from anywhere. (.bashrc)


termux:
```sh
cd ~/home/local/bin #location of `rsync-termux` script
chmod +x rsync-termux
./rsync-termux
```
or
Add the script path to `PATH` to execute from anywhere. (bash.bashrc)


## Contributing

If you find a bug or have a suggestion for a new feature, please open an issue or create a pull request.

## License

This repository is licensed under the [GNU General Public License v3.0](https://github.com/dhacommas/rsync-script/blob/main/LICENSE)

`@dhacommas`

`@EphemeralG`
