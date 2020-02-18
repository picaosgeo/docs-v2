---
title: Use InfluxDB templates
description: >
  Use the `influx pkg` command to view and install templates from your local
  filesystem or from URLs.
menu:
  v2_0:
    parent: InfluxDB templates
    name: Use templates
weight: 101
v2.0/tags: [templates]
---

Use the `influx pkg` command to summarize, validate, and install templates from
your local filesystem and from URLs.

- [View a template summary](#view-a-template-summary)
- [Validate a template](#validate-a-template)
- [Install templates](#install-templates)
<<<<<<< HEAD
- [Use InfluxDB community templates](#use-influxdb-community-templates)
=======
- [Use an InfluxDB community template](#use-influxdb-community-templates)
>>>>>>> influx-templates

## View a template summary
To view a summary of what's included in a template before installing the template,
use the [`influx pkg summary` command](/v2.0/reference/cli/influx/pkg/summary/).
<<<<<<< HEAD
Summarize templates stored in your local filesystem or from a URL.
=======
View a summary of a template stored in your local filesystem or from a URL.
>>>>>>> influx-templates

{{% code-tabs-wrapper %}}
{{% code-tabs %}}
[From a file](#)
[From a URL](#)
{{% /code-tabs %}}
{{% code-tab-content %}}
```sh
# Syntax
influx pkg summary -f <template-file-path>

# Example
influx pkg summary -f /path/to/template.yml
```
{{% /code-tab-content %}}
{{% code-tab-content %}}
```sh
# Syntax
influx pkg summary -u <template-url>

# Example
influx pkg summary -u https://raw.githubusercontent.com/influxdata/community-templates/master/linux_system/linux_system.yml
```
{{% /code-tab-content %}}
{{% /code-tabs-wrapper %}}

## Validate a template
<<<<<<< HEAD
To validate a template before installing it or for troubleshooting purposes, use
the [`influx pkg validate` command](/v2.0/reference/cli/influx/pkg/validate/).
Validate templates stored in your local filesystem or from a URL.
=======
To validate a template before your install it or troubleshooting a template, use
the [`influx pkg validate` command](/v2.0/reference/cli/influx/pkg/validate/).
Validate a template stored in your local filesystem or from a URL.
>>>>>>> influx-templates

{{% code-tabs-wrapper %}}
{{% code-tabs %}}
[From a file](#)
[From a URL](#)
{{% /code-tabs %}}
{{% code-tab-content %}}
```sh
# Syntax
influx pkg validate -f <template-file-path>

# Example
influx pkg validate -f /path/to/template.yml
```
{{% /code-tab-content %}}
{{% code-tab-content %}}
```sh
# Syntax
influx pkg validate -u <template-url>

# Example
influx pkg validate -u https://raw.githubusercontent.com/influxdata/community-templates/master/linux_system/linux_system.yml
```
{{% /code-tab-content %}}
{{% /code-tabs-wrapper %}}

## Install templates
Use the [`influx pkg` command](/v2.0/reference/cli/influx/pkg/) to install templates
from your local filesystem or from URLs.

<<<<<<< HEAD
- [Install templates from files](#install-templates-from-files)
- [Install templates from URLs](#install-templates-from-urls)
- [Install templates from both files and URLs](#install-templates-from-both-files-and-urls)
- [Include secrets when installing a template](#include-secrets-when-installing-a-template)

### Install templates from files
=======
- [Install a template from a file](#install-a-template-from-a-file)
- [Install all templates in a directory](#install-all-templates-in-a-directory)
- [Install a template from a URL](#install-a-template-from-a-url)
- [Install templates from both files and URLs](#install-templates-from-both-files-and-urls)
- [Include a secret when installing a template](#include-a-secret-when-installing-a-template)

### Install a template from a file
>>>>>>> influx-templates
To install templates stored on your local machine, use the `-f` or `--file` flag
to provide the **file path** of the template manifest.

```sh
# Syntax
influx pkg -f <template-file-path>

# Examples
# Install a single template
influx pkg -f /path/to/template.yml

# Install multiple templates
influx pkg \
  -f /path/to/this/template.yml \
  -f /path/to/that/template.yml
```

<<<<<<< HEAD
#### Install all templates in a directory
=======
### Install all templates in a directory
>>>>>>> influx-templates
To install all templates in a directory, use the `-f` or `--file` flag to provide
the **directory path** of the directory where template manifests are stored.
By default, this only installs templates stored in the specified directory.
To install all templates stored in the specified directory and its subdirectories,
include the `--recurse` flag.

```sh
# Syntax
influx pkg -f <template-directory-path>

# Examples
# Install all templates in a directory
influx pkg -f /path/to/template/dir/

# Install all templates in a directory and its subdirectories
influx pkg -f /path/to/template/dir/ --recurse
```

<<<<<<< HEAD
### Install templates from URLs
=======
### Install a template from a URL
>>>>>>> influx-templates
To install templates from a URL, use the `-u` or `--url` flag to provide the URL
of the template manifest.

```sh
# Syntax
influx pkg -u <template-url>

# Examples
# Install a single template from a URL
influx pkg -u https://mydomain.com/templates/template.yml

# Install multiple templates from URLs
influx pkg \
  -u https://mydomain.com/templates/template1.yml \
  -u https://mydomain.com/templates/template2.yml
```

### Install templates from both files and URLs
To install templates from both files and URLs in a single command, include multiple
file or directory paths and URLs, each with the appropriate `-f` or `-u` flag.

```sh
# Syntax
influx pkg -u <template-url> -f <template-path>

# Example
influx pkg \
  -u https://mydomain.com/templates/template1.yml \
  -u https://mydomain.com/templates/template2.yml \
  -f ~/templates/custom-template.yml \
  -f ~/templates/iot/home/ \
  --recurse
```

<<<<<<< HEAD
### Include secrets when installing a template
=======
### Include a secret when installing a template
>>>>>>> influx-templates
Some templates use [secrets](/v2.0/security/secrets/) in queries.
Secret values are not included in templates.
To define secret values when installing a template, include the `--secret` flag
with the secret key-value pair.

```sh
# Syntax
influx pkg -f <template-file-path> --secret=<secret-key>=<secret-value>

# Examples
# Define a single secret when installing a template
influx pkg -f /path/to/template.yml \
  --secret=FOO=BAR

# Define multiple secrets when installing a template
influx pkg -f /path/to/template.yml \
  --secret=FOO=bar \
  --secret=BAZ=quz
```

_To add a secret after installing a template, see [Add secrets](/v2.0/security/secrets/manage-secrets/add/)._

## Use InfluxDB community templates
The [InfluxDB Community Templates repository](https://github.com/influxdata/community-templates/)
is home to a growing number of InfluxDB templates developed and maintained by
others in the InfluxData community.
<<<<<<< HEAD
Install community templates directly from GitHub using a template's raw code URL
or download them to your local machine.
=======
Install community templates directly from GitHub using a template's download URL
or download the template.
>>>>>>> influx-templates

<a class="btn" href="https://github.com/influxdata/community-templates/" target="\_blank">View InfluxDB Community Templates</a>