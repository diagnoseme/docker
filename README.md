# Docker tools

---

## Connect to container 🤝

  An interactive TUI for shelling into a running Docker container.

### Description

  - **Type to search** — filter containers in real time as you type
  - **Arrow keys** — navigate the filtered list
  - **`Backspace`** — delete the last search character
  - **`Ctrl+U`** — clear the search
  - **`Enter`** — connect to the selected container

  After selecting a container, choose to connect as your current host user or as root.

  - A `DOCKER_USER_AND_GROUP` environment variable overrides the detected host user/group
    - Accepts a name or id, e.g. `user` or `1000`
    - Accepts user and group, e.g. `user:group` or `1000:1000`
  - `bash` is used if available in the container, otherwise `sh`

### Usage

```shell
# show all running containers
$ ./bin/connect-to-container

# open with a pre-filled search
$ ./bin/connect-to-container [query]
```

---

## Mutagen sync to VM (especially for OSX users)

Handy shortcut to sync actual folder to VM.   
Idea behind this tool is:
- sync actual state to VM via rsync
- create [mutagen.io](https://mutagen.io/) session aftewards for changes sync
- if folder to sync contains `.mutagen` file this command will take it as [mutagen configuration file](https://mutagen.io/documentation/introduction/configuration#configuration-files)

### Requirements

- environment variable `DOCKER_VM_HOST` must be set (e.g. Parallels local VM IP address)
- environment variable `DOCKER_VM_USER` must be set (e.g. VM default user "ubuntu")
- connection to VM for that ENVs must be via certificate (without password, test it with command 
```shell ssh $DOCKER_VM_USER@$DOCKER_VM_HOST`)```

### Usage
```shell
$ cd <some folder to sync>

# create a sync session
$ ./bin/mutagen-sync

# drop sync session
$ ./bin/mutagen-sync d
```
