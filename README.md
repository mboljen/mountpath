# mountpath

This bash script looks up the mountpoint for the given path in `/etc/fstab` and mounts the corresponding device if currently unmounted.

## Installation

Use the following command to install this software:

```bash
$ make
$ make install
```

The default `PREFIX` is set to `/usr/local`.  In order to succesfully complete the installation, you need to have write permissions for the installation location.

## Usage

The following command will find the corresponding device for `path` and mount it unless already mounted.

```bash
$ mountpath [-options] path
```

### Options

+ `-l` Lookup mountpoint in `/etc/fstab` for the given path
+ `-c` Check if corresponding device is mounted (skips mount operation)
+ `-u` Unmount the corresponding device safely
+ `-t` Set sleep time in seconds between unmount trials (default: `5`)
+ `-m` Set the maximum number of unmount trials (default: `10`)
+ `-h` Show this help message

### Exit codes

+ `0` operation successful
+ `1` operation failed, device is already mounted
+ `2` operation failed, no mountpoint found in `/etc/fstab`
+ `3` operation failed, command `mount` failed
+ `4` operation failed, command `umount` failed
+ `5` operation failed, insufficient pre-requisites
+ `6` operation failed, invalid syntax

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
