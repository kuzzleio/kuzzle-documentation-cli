# kuzdoc

## Dummy release 2.0 (for test purposes)

The CLI that helps build the Kuzzle Docs.

This is an internal tool used by the Kuzzle team to build the documentation of all the Kuzzle.io projects.

[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![Version](https://img.shields.io/npm/v/kdoc.svg)](https://npmjs.org/package/kdoc)
[![Downloads/week](https://img.shields.io/npm/dw/kdoc.svg)](https://npmjs.org/package/kdoc)
[![License](https://img.shields.io/npm/l/kdoc.svg)](https://github.com/kuzzleio/kdoc/blob/master/package.json)

<!-- toc -->
* [kuzdoc](#kuzdoc)
* [Usage](#usage)
* [Commands](#commands)
<!-- tocstop -->

# Usage

<!-- usage -->
```sh-session
$ npm install -g kuzdoc
$ kuzdoc COMMAND
running command...
$ kuzdoc (-v|--version|version)
kuzdoc/2.0.0 darwin-x64 node-v12.18.3
$ kuzdoc --help [COMMAND]
USAGE
  $ kuzdoc COMMAND
...
```
<!-- usagestop -->

# Commands

<!-- commands -->
* [`kuzdoc build-and-deploy [FILE]`](#kuzdoc-build-and-deploy-file)
* [`kuzdoc help [COMMAND]`](#kuzdoc-help-command)
* [`kuzdoc install`](#kuzdoc-install)

## `kuzdoc build-and-deploy [FILE]`

describe the command here

```
USAGE
  $ kuzdoc build-and-deploy [FILE]

OPTIONS
  -f, --force
  -h, --help       show CLI help
  -n, --name=name  name to print
```

_See code: [src/commands/build-and-deploy.ts](https://github.com/kuzzleio/kuzdoc/blob/v2.0.0/src/commands/build-and-deploy.ts)_

## `kuzdoc help [COMMAND]`

display help for kuzdoc

```
USAGE
  $ kuzdoc help [COMMAND]

ARGUMENTS
  COMMAND  command to show help for

OPTIONS
  --all  see all commands in CLI
```

_See code: [@oclif/plugin-help](https://github.com/oclif/plugin-help/blob/v3.2.1/src/commands/help.ts)_

## `kuzdoc install`

Installs one or multiple repos in the framework meta-repo.

```
USAGE
  $ kuzdoc install

OPTIONS
  -h, --help               show CLI help

  --localPath=localPath    Installs the repo from a local path instead of cloning it from Github. Handy for testing
                           locally developed features.
                           This option is valid if only 1 repo is specified. Overrides --repoBranch.

                           Environment variable: $KUZDOC_LOCAL_PATH

  --repo=repo              The list of repositories to install, or the value __ALL__ to install all repos.
                           If not specified, kuzdoc will ask a prompt.

                           Environment variable: $KUZDOC_REPO

  --repoBranch=repoBranch  The branch to checkout from the repo to install.
                           This option is valid if only 1 repo is specified.

                           Environment variable: $KUZDOC_REPO_BRANCH

  --stage=stable|dev       The branch type to checkout.
                           If this option is not specified, kuzdoc will try to infer it based on the current branch of
                           the framework meta-repo.

                           Environment variable: $KUZDOC_STAGE

DESCRIPTION
  NOTE: This command must be executed from the root of the framework meta-repo.

  This command will install one or multiple repos, listed in the repositories.yml file, within the .repos directory of 
  the documentation framework.
  Repositories will be either cloned from Github or symlink-ed from the local filesystem (--local-path flag).
  The repositories.yml file will be fetched from the local instance of the documentation framework.
  Repositories are either specified via the --repo flag, or the KUZDOC_REPO: if no value is specified, kuzdoc will ask 
  it via a prompt.
  Kuzdoc will not overwrite existing repositories. If a folder with the same name of a selected repository is already 
  present, the selected repository will be skipped and the folder will be left untouched.
```

_See code: [src/commands/install.ts](https://github.com/kuzzleio/kuzdoc/blob/v2.0.0/src/commands/install.ts)_
<!-- commandsstop -->
