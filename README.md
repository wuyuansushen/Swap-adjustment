# Swap-adjustment

### Removing Swap File

0. Show swap situation
```
swapon --show
```

1. Deactivate swap file

```
swapoff -v <swapFile>
```

2. Remove the entry line from file system table (`/etc/fstab`)


3. Delete swap file

```
rm -f <swapFile>
```

### Create Swap

1. Create swap file
```
dd if=/dev/zero of=<swapFile> count=<countNum> bs=<sizeNum>MiB
```

2. Change permission
```
chmod 0600 <swapFile>
```

3. Make swap file system
```
mkswap <swapFile>
```

4. Activate swap file
```
swapon -v <swapFile>
```

5. Add entry line to `/etc/fstab` file
```
<swapFile>	swap	swap	defaults	0	0
```
