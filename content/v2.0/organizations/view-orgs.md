---
title: View organizations
seotitle: View organizations in InfluxDB
description: Review a list of organizations in InfluxDB using the InfluxDB UI or the influx CLI.
menu:
  v2_0:
    name: View organizations
    parent: Manage organizations
weight: 102
---

Use the InfluxDB user interface (UI) or the `influx` command line interface (CLI)
to view organizations.

## View organizations in the InfluxDB UI

1. In the navigation menu on the left, click the **Account dropdown**.

    {{< nav-icon "account" >}}

2. Select **Switch Organizations**. The list of organizations appears.

## View organizations using the influx CLI

Use the [`influx org list` command](/v2.0/reference/cli/influx/org/list)
to view organizations.

```sh
influx org list
```

Filtering options such as filtering by name or ID are available.
See the [`influx org list` documentation](/v2.0/reference/cli/influx/org/list)
for information about other available flags.

## View your organization ID
Use the InfluxDB UI or `influx` CLI to view your organization ID.

### Organization ID in the UI
After logging in to the InfluxDB UI, your organization ID appears in the URL.

{{< code-tabs-wrapper >}}
{{% code-tabs %}}
[InfluxDB Cloud](#)
[InfluxDB OSS](#)
{{% /code-tabs %}}
{{< code-tab-content >}}
<pre class="highlight">
https://us-west-2-1.aws.cloud2.influxdata.com/orgs/<span class="bp" style="font-weight:bold;margin:0 .15rem">03a2bbf46249a000</span>/...
</pre>
{{< /code-tab-content >}}
{{< code-tab-content >}}
<pre class="highlight">
http://localhost:9999/orgs/<span class="bp" style="font-weight:bold;margin:0 .15rem">03a2bbf46249a000</span>/...
</pre>
{{< /code-tab-content >}}
{{< /code-tabs-wrapper >}}

_For specific InfluxDB Cloud provider and region URLs, see [InfluxDB Cloud URLs](/v2.0/cloud/urls/)._


### Organization ID in the CLI
Use [`influx org list`](#view-organizations-using-the-influx-cli) to view your organization ID.

```sh
> influx org list

ID                  Name
03a2bbf46249a000    org-1
03ace3a859669000    org-2
```
