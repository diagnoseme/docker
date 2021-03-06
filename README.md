# Docker tools

---

## Connect to container 🤝

  A wrapper that executes an interactive shell on the container chosen from a list.

### Description

  The script asks for the:

  - Container number (from a list)
  - If to connect as a root
    - The root is hardcoded together with the group as `root:root` 
    - A `DOCKER_USER_AND_GROUP` environment variable can be used to override the host's user and group
      - It can contain only the user's name or their id, e.g. `user` or `1000`
      - It can also contain the user's group or its id, e.g. `user:group` or `1000:1000`
    - Otherwise, the user and group are detected automatically from the host's system

  The `bash` shell is used if it is available in the container otherwise the `sh`.

### Usage

  Run it with the command:

    $ ./bin/connect-to-container [filter]

- **`filter`** :  
  - not required
  - filter names, identifiers and labels  
  - if empty, shows all running containers

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
