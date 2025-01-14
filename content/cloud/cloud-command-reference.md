title = "Cloud Command Reference"
date = "2023-06-07T22:41:02.478752Z"
template = "cloud_main"
enable_shortcodes = true
[extra]
url = "https://github.com/fermyon/developer/blob/main/content/cloud/cloud-command-reference.md"

---
- [Spin Cloud Command](#spin-cloud-command)
- [spin cloud](#spin-cloud)
- [spin cloud deploy](#spin-cloud-deploy)
- [spin cloud help](#spin-cloud-help)
- [spin cloud login](#spin-cloud-login)
- [spin cloud variables](#spin-cloud-variables)
- [spin cloud variables delete](#spin-cloud-variables-delete)
- [spin cloud variables help](#spin-cloud-variables-help)
- [spin cloud variables list](#spin-cloud-variables-list)
- [spin cloud variables set](#spin-cloud-variables-set)
- [Subcommand Stability Table](#subcommand-stability-table)

## Spin Cloud Command

Fermyon provides a [`cloud` plugin](https://github.com/fermyon/cloud-plugin) for the [Spin CLI](./cli-reference.md) for you to manage Spin applications in Fermyon Cloud. This page documents the `spin cloud` command. Specifically, all of the available options and subcommands. For more information on subcommand stability, see the [subcommands stability table](#subcommand-stability-table). You can reproduce the Spin Cloud command documentation on your machine by using the `--help` flag. For example:

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->

```console
$ spin cloud --help

cloud-plugin 0.1.1
Fermyon Engineering <engineering@fermyon.com>

USAGE:
    cloud <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    deploy       Package and upload an application to the Fermyon Cloud
    help         Print this message or the help of the given subcommand(s)
    login        Login to Fermyon Cloud
    variables    Manage Spin application variables
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud deploy

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud deploy --help

cloud-deploy 0.1.1
Package and upload an application to the Fermyon Cloud

USAGE:
    cloud deploy [OPTIONS]

OPTIONS:
        --buildinfo <BUILDINFO>
            Build metadata to append to the bindle version

    -d, --staging-dir <STAGING_DIR>
            Path to assemble the bindle before pushing (defaults to a temporary directory)

    -e, --deploy-existing-bindle
            Deploy existing bindle if it already exists on bindle server

        --environment-name <environment-name>
            Deploy to the Fermyon instance saved under the specified name. If omitted, Spin deploys
            to the default unnamed instance [env: FERMYON_DEPLOYMENT_ENVIRONMENT=]

    -f, --from <APP_MANIFEST_FILE>
            The application to deploy. This may be a manifest (spin.toml) file, or a directory
            containing a spin.toml file. If omitted, it defaults to "spin.toml" [default: spin.toml]

    -h, --help
            Print help information

        --key-value <KEY_VALUES>
            Set a key/value pair (key=value) in the deployed application's default store. Any
            existing value will be overwritten. Can be used multiple times

        --no-buildinfo
            Disable attaching buildinfo [env: SPIN_DEPLOY_NO_BUILDINFO=]

        --readiness-timeout <READINESS_TIMEOUT_SECS>
            How long in seconds to wait for a deployed HTTP application to become ready. The default
            is 60 seconds. Set it to 0 to skip waiting for readiness [default: 60]

    -V, --version
            Print version information

        --variable <VARIABLES>
            Set a variable pair (variable=value) in the deployed application. Any existing value
            will be overwritten. Can be used multiple times
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud help

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

<!-- @selectiveCpy -->
```console
$ spin cloud help

cloud-plugin 0.1.1
Fermyon Engineering <engineering@fermyon.com>

USAGE:
    cloud <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    deploy       Package and upload an application to the Fermyon Cloud
    help         Print this message or the help of the given subcommand(s)
    login        Login to Fermyon Cloud
    variables    Manage Spin application variables
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud login

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud login --help

cloud-login 0.1.1
Login to Fermyon Cloud

USAGE:
    cloud login [OPTIONS]

OPTIONS:
        --auth-method <auth-method>
            [env: AUTH_METHOD=] [possible values: github, token]

        --environment-name <environment-name>
            Save the login details under the specified name instead of making them the default. Use
            named environments with `spin deploy --environment-name <name>` [env:
            FERMYON_DEPLOYMENT_ENVIRONMENT=]

    -h, --help
            Print help information

    -k, --insecure
            Ignore server certificate errors

        --list
            List saved logins

        --status
            Display login status

        --token <TOKEN>
            Auth Token [env: SPIN_AUTH_TOKEN=]

        --url <CLOUD_SERVER_URL>
            URL of Fermyon Cloud Instance [env: CLOUD_URL=] [default: https://cloud.fermyon.com/]

    -V, --version
            Print version information
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud variables

{{ tabs "cloud-plugin-version" }} 

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud variables --help

cloud-variables 0.1.1
Manage Spin application variables

USAGE:
    cloud variables <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    delete    Delete variable pairs
    help      Print this message or the help of the given subcommand(s)
    list      List all variables of an application
    set       Set variable pairs
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud variables delete

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud variables delete --help

cloud-variables-delete 0.1.1
Delete variables

USAGE:
    cloud variables delete [OPTIONS] --app <app> [VARIABLES_TO_DELETE]...

ARGS:
    <VARIABLES_TO_DELETE>...    Variable pair to set

OPTIONS:
        --app <app>
            Name of Spin app

        --environment-name <environment-name>
            Deploy to the Fermyon instance saved under the specified name. If omitted, Spin deploys
            to the default unnamed instance [env: FERMYON_DEPLOYMENT_ENVIRONMENT=]

    -h, --help
            Print help information

    -V, --version
            Print version information
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud variables help

{{ tabs "cloud-plugin-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->

```console
$ spin cloud variables help

cloud-variables 0.1.1
Manage Spin application variables

USAGE:
    cloud variables <SUBCOMMAND>

OPTIONS:
    -h, --help       Print help information
    -V, --version    Print version information

SUBCOMMANDS:
    delete    Delete variables
    help      Print this message or the help of the given subcommand(s)
    list      List all variables of an application
    set       Set variables
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud variables list

{{ tabs "cloud-plugin-version" }} 

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud variables list --help

cloud-variables-list 0.1.1
List all variables of an application

USAGE:
    cloud variables list [OPTIONS] --app <app>

OPTIONS:
        --app <app>
            Name of Spin app

        --environment-name <environment-name>
            Deploy to the Fermyon instance saved under the specified name. If omitted, Spin deploys
            to the default unnamed instance [env: FERMYON_DEPLOYMENT_ENVIRONMENT=]

    -h, --help
            Print help information

    -V, --version
            Print version information
```

{{ blockEnd }}

{{ blockEnd }}

<!-- markdownlint-disable-next-line titlecase-rule -->
## spin cloud variables set

{{ tabs "cloud-plugin-version" }} 

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

<!-- @selectiveCpy -->
```console
$ spin cloud variables set --help

cloud-variables-set 0.1.1
Set variables

USAGE:
    cloud variables set [OPTIONS] --app <app> [VARIABLES_TO_SET]...

ARGS:
    <VARIABLES_TO_SET>...    Variable pair to set

OPTIONS:
        --app <app>
            Name of Spin app

        --environment-name <environment-name>
            Deploy to the Fermyon instance saved under the specified name. If omitted, Spin deploys
            to the default unnamed instance [env: FERMYON_DEPLOYMENT_ENVIRONMENT=]

    -h, --help
            Print help information

    -V, --version
            Print version information
```

{{ blockEnd }}

{{ blockEnd }}

## Subcommand Stability Table

CLI commands have four phases that indicate levels of stability:

- `Experimental`: These commands are experiments and may or may not be available in later versions of the CLI.
- `Stabilizing`: These commands have moved out of the `experimental` phase and we are now in the active process of stabilizing them. This includes updating flags, command output, errors, and more.
- `Stable`: These commands have moved out of the `stablizing` phase and will not change in backwards incompatible ways until the next major version release.
- `Deprecated`: Support for these commands will be removed in a future release.

{{ tabs "command-version" }}

{{ startTab "v0.1.1"}}

Spin compatibility: `>= v1.3`

| Command                                                    | Stability   |
| ---------------------------------------------------------- | ----------- |
| <code>cloud deploy</code>                                  | Stabilizing |
| <code>cloud login</code>                                   | Stabilizing |
| <code>cloud variables</code>                               | Stabilizing |

{{ blockEnd }}

{{ blockEnd }}
