# Local Aliases

## Overview

Sometime you need to create one or more aliases for a specific project,
but you don't want to add them to your global aliases file.

This plugin allows you to create a local aliases file in your project

## Installation

Copy the lal file into /usr/bin or /usr/local/bin,
to make it available system-wide.

## Synopsis

    lal [ALIAS [PARENT_DIR_DEPTH]]

    ALIAS: The alias to be called

    PARENT_DIR_DEPTH: The number of parent directories to search for the
                      local aliases file. Default is 0

## Usage

1. `lal` needs a file called `local_aliases.yaml` or `.local_aliases.yaml`,
    which contains the aliases you want to create.

    This file can be created manually, or using the `lal` command with no arguments.

2.  The newly created file can be filled with aliases, like this:

    **Path:** 
    
    local_aliases.yaml
    
    **Content:**
    
    hello: echo "Hello World"
    
    compile: make all

3.  These aliases can be called, like this:

    `lal hello`
    
    `lal compile`

4.  Since the project might be an abundance of nested directories, 
    you can specify if `lal` should also look for the local aliases file in the parent directories.
    By default, `lal` will look for the file **only** in the current directory.

    `lal hello 0` ... will only look for the file in the current directory

    `lal hello 1` ... will look for the file in the current directory and in the parent directories

    `lal hello 2` ... will look for the file in the current directory, 
                      in the parent directory and in the parent of the parent directory