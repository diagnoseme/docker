# Docker Shell Wrapper

  A wrapper that executes an interactive shell on the container chosen from a list.

## Description

  The script asks for the:

  - Container number (from a list)
  - If to connect as a root
    - The root is hardcoded together with the group as `root:root` 
    - A `DOCKER_USER_AND_GROUP` environment variable can be used to override the host's user and group
      - It can contain only the user's name or their id, e.g. `user` or `1000`
      - It can also contain the user's group or its id, e.g. `user:group` or `1000:1000`
    - Otherwise, the user and group are detected automatically from the host's system

  The `bash` shell is used if it is available in the container otherwise the `sh`.

## Usage

  Run it with the command:

    $ ./bin/docker-shell-wrapper [filter]

## Parameters

### Filter

  Filter is a non required parameter.

  It filters the list based on names, identifiers and labels.

  If no filter is set the list contains all the running containers.
