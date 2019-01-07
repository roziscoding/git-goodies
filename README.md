# git-goodies
Set of git custom commands to make life easier

- [git-goodies](#git-goodies)
  - [Installing](#installing)
  - [Commands](#commands)
    - [git bump](#git-bump)
    - [git bugfix](#git-bugfix)
    - [git feature](#git-feature)
    - [git hotfix](#git-hotfix)
    - [git pop](#git-pop)
    - [git publish](#git-publish)

## Installing
1. Clone this:
   ```sh
   git clone git@github.com:rjmunhoz/git-goodies.git
   ```
2. Enter the newly created folder
   ```sh
   cd git-goodies
   ```
3. Give the execute permissions to the all of the -git files
   ```sh
   chmod +x git-*
   ```
4. Add the full path of the git-goodies folder to your PATH environment variable

## Commands

### git bump

**Syntax**
```sh
git bump version_type [message]
```

**Params**

- vesrion_type:
  - Description: version type to be used with `npm version version_type`
  - Required: yes
- message:
  - Description: commit message to be used along with the new version in the format of `vx.x.x - message`
  - Required: no
  - Default: no message. Commit will only contain the version number

**Usage**

This calls npm with the passed version type and commits it with the optional message and the new version.

### git bugfix

**Syntax**
```sh
git bugfix bugfix_name
```

**Params**

- bugfix_name
  - Description: The git-compliant name for the new branch
  - Required: yes

**Usage**

This command performs a series of actions to ensure it creates an updated bugfix branch. These are the steps:
- Checks `release` out and pulls its changes
- Checks `master` out and pulls its changes
- Checks `release` out and merges `master` into `release`
- Pushes `release`
- Creates a new branch called `bugfix/bugfix_name`

### git feature

> This follows the exact same steps, syntax and usage as the [git bugfix](#git-bugfix) command, except everything is called `feature`, and not `bugfix`

### git hotfix

**Syntax**
```sh
git hotfix hotfix_name
```

**Params**
- hotfix_name
  - Description: The git-compliant name for the hotfix branch
  - Required: yes

**Usage**

This command performs a series of actions to ensure it creates an updated bugfix branch. These are the steps:
- Checks `master` out and pulls its changes
- Creates a new branch called `hotfix/hotfix_name`

### git pop

### git publish