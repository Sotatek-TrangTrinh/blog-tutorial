<h1 align="center">TERMINAL</h1>

### CONFIG SSH COMMAND

Create .ssh folder

```bash
mkdir -p ~/.ssh && chmod 700 ~/.ssh
```

Create config file

```bash
touch ~/.ssh/config
chmod 600 ~/.ssh/config
```

Edit Config file

```bash
nano ~/.ssh/config
```

The SSH Config file following structure:

```
Host ignition
  HostName dev.example.com
  User sotatek
```

Access to dev.example.com

```bash
ssh ignition
```

### PERMISSION IN LINUX

```bash
ls -l
```

The result will look something like this:

```bash
drwxr-xr-x 10 sotatek sotatek  4096 Thg 5  29 10:18 Desktop
```

The information is as follows:

- `d` : directory
- `rwx` : owner permission
- `r-x` : group permission
- `r-x` : other users permission
- `10` : number of links
- `sotatek` : owner name
- `sotatek` : group name
- `4096` : directory size (number of bytes)
- `Thg 5  29 10:18` : time when the directory was modified
- `Desktop` : folder name

### CHMOD COMMAND

Changing permission

```bash
chmod g+w Desktop
chmod o-rwx
```

- u = user, g = group, o = other, a = all and uoa = all
- `+` = add permission, `-` = remove permission
- r = read, w= write, x = execute
- `Desktop`: folder name

Changing permissions in numeric code

The command above will give read, write and execute permissions for everyone

```bash
chmod 777 Desktop
```

Using number instate of `r`, `w`, `e`

- 0 = no permission
- 1 = execute
- 2 = write
- 4 = read

So, permission numbers are:

- 0 = ---
- 1 = --x
- 2 = -w-
- 3 = -wx
- 4 = r-
- 5 = r-x
- 6 = rw-
- 7 = rwx
