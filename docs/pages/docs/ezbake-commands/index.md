---
title: ezbake Commands Reference
---

Execute `ezbake --help` to see the list of valid commands.

You may also execute `ezbake <command> --help` to see the list of options per command.

All of these commands are to be executed at the root of a project.

# ezbake plug

## Description

This command is intended to add `ezbake` support to a project. This will create an `.ezbake` folder in the current working directory.  This command is primarily used by authors who want to enable `ezbake` templating for their users.

## Options

n/a

### Sample

`ezbake plug`

# ezbake unplug

## Description

This command will remove the `.ezbake` folder from a project that is using it.

## Options

n/a

## Sample

`ezbake unplug`

# ezbake prepare [options]

## Description

This command is intended to scaffold a project from a given Git URL source.  If it is not provided in the command line, you are prompted for it.

## Options

**Note**: You will be prompted for these if you don't pass them in as arguments

* `-r`: The full URL of the Git repo to use a source
* `-b`: The branch to clone from the Git repo source
* `-o`: The full URL of the Git repo to use as the origin for the created ezbake scaffold. It should be a completely empty repository

## Sample

`ezbake prepare -r https://github.com/ericnograles/ads-baseline-madlibs.git -b ezbake-branch`

# ezbake menu

## Description

This command lists the available recipes in an existing `ezbake` project.

## Options

n/a

## Sample

`ezbake menu`

# ezbake cook [options]

## Description

This command is to be used within a project that has been created using `ezbake prepare`.  This is the command which will cook a recipe for the user. Recipes are defined under `.ezbakes/recipes` or can be seen with `ezbake menu`.

## Options

* `-r`: The name of the recipe to cook. These are the recipes defined in the `.ezbake/recipes` folder.

## Sample

`ezbake cook -r Query`

# ezbake sync [options]

## Description

This command allows a user to resynchronize their `.ezbake` folder with the latest published by the author.

As an escape hatch, a user can also manually specify another Git source and branch from which to pull the syncing operation.

**Note**: This is a destructive action and will remove your project's recipes and replace them with whatever recipes are defined from the Git repo you specify at the time of execution.

## Options

**Note**: You will be prompted for these if you don't pass them in as arguments

* `-r`: (Optional) The full URL of a Git repo to use a source.
* `-b`: (Optional) Only to be used in addition to the `-r` branch, the branch to clone from the Git repo source
