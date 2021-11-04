# Docker Shell Wrapper

  A wrapper that executes an interactive shell on the container chosen from a list.

## Description

  The script asks for the:

  - Container number (from a list)
  - User type (root or the host's user)

  The `bash` shell is used if it is available in the container otherwise the `sh`.

## Usage

  Run it with the command:

    $ ./bin/docker-shell-wrapper [filter]

## Parameters

### Filter

  Filter is a non required parameter.

  It filters the list based on names, identifiers and labels.

  If no filter is set the list contains all the running containers.
