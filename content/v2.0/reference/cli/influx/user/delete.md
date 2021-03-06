---
title: influx user delete
description: The 'influx user delete' command deletes a specified user.
menu:
  v2_0_ref:
    name: influx user delete
    parent: influx user
weight: 201
---

The `influx user delete` command deletes a specified user in InfluxDB.

## Usage
```
influx user delete [flags]
```

## Flags
| Flag             | Description                           | Input type  | {{< cli/mapped >}}    |
|:----             |:-----------                           |:----------: |:------------------    |
| `-h`, `--help`   | Help for the `delete` command         |             |                       |
| `--hide-headers` | Hide table headers (default `false`)  |             | `INFLUX_HIDE_HEADERS` |
| `-i`, `--id`     | **(Required)** User ID                | string      |                       |
| `--json`         | Output data as JSON (default `false`) |             | `INFLUX_OUTPUT_JSON`  |

{{% cli/influx-global-flags %}}
