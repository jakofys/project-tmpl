# Readme-Ex

Readme `Context` and explain about technology.
Motivation about the project.

## Introduction

Explain the project bravely, without missing to details project boundaries.

## Requirement

- [Exemple service](https://exemple.com) version -> maj.min.release

## Installation

Installation process is the more complexe operation you can find. </br>
Just complete `profile-env.yaml` and replacing respective field or let default interaction.

> Be careful about `(Optional)` comment to let it by default, otherwise, you have to complete with valid information. </br>
> If information are not valid, the current process interupt itself, undo all previous operations and remove used cache

Before install workspace, make sure you're enable to run it.
Execute:

```shell
make configure
```

This command permit to verify all configuration, and return you `configuration: OK`, else list instructions have to do for create the right configuration environment. And then run again this command until is `OK` .

And finally, just typed:

``` bash
make install
```

To install all environment to have all missing dependancies.

> For more information about configuration and installation command, go to [installation](documents/commands/INSTALLING.md) documentation.

### Reference environment profile

> Consider all interpolation key (%interpolation_key%) as case sensitive. </br>
> All path included respect path basic syntax with source project as root

- `%ssh_key_gen_file%` is the location path of your ssh public key </br> (by default, it user `HOME` environment variable on Linux and MacOS, and `...` on Windows).

> For more information about `profile-env.yaml` reference about, go to [profile environment](documents/configuration/PROFILE_ENV.md) documentation.

## Running

For running the entier application, just make `make run`, but if you want to specify a particular service, simply complete it as

```bash
make run-service SERVICE_NAME=%service_name%
```

> Notice, each service have it own configuration, this command use it to configure service's environment and run the corresponding service.

You can also specify type of `run mode` with make flag `RUN_MODE=%run_mode%` and lot more flag:

``` bash
make run RUN_MODE=%run_mode%
```

You can do the same thing about `environment` execution with `ENV` flag (e.g. `make run ENV=development`).

> For more information about running command, go to [running](documents/commands/RUNNING.md) documentation

## Test

Just run `make test` command will run all type of test. </br>
You can specify which test you want to execute with flag command `TESTS_MODE=%tests_mode%` where `tests_mode` should be a list of string separate by coma:

``` bash
make test TESTS_MODE=unit,function,secure,perf
```

| Testing type        | Keyword    | Must be blocking |
| ------------------- | ---------- | ---------------- |
| Unit testing        | `unit`     | yes              |
| Functional testing  | `function` | yes              |
| Regression testing  | `regress`  | yes              |
| Performance testing | `perf`     | no               |
| Security testing    | `secure`   | yes              |
| Ent-To-End testing  | `e2e`      | yes              |
| Lint evaluation     | `lint`     | no               |
| Coverage evaluation | `cover`    | no               |

Use the `make` command on root to know all existing commands. </br>
For testing, it is assumed that services implements tests, and configuration to be launchable via the `make` command.

> For more information about test command, go to [testing](documents/commands/TESTING.md) documentation

## Available command

Can use `make` command to know which command available about:
- [Documents name](./documents/commands/type.md)

## References

- [Reference's name](https://www.example.com) (SHORT) brieve explaination
