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
