---
title: 8X8
product_label:
  - essential
  - advanced
  - enterprise
  - classic
description: Learn how to connect your 8X8 ACD to import data.
related_articles:
  - overwrite_title: Add title for untranslated source
    filepath: features/acd-integration/cloud/how-integrations-work.md
  - overwrite_title: Add title for untranslated source
    filepath: features/acd-integration/cloud/import-agent-status-data.md
---

An 8X8 integration is a cloud integration that imports calls, chats, emails, voicemails, agent status and real-time adherence data.

New to integrations? Learn {% link_new the basics | features/acd-integration/cloud/how-integrations-work.md %} first.

## Add an 8X8 integration <a name="add-an-8X8-integration"></a>

1. Go to *Account > Integrations*{:.breadcrumbs}.
2. Click _Create_{:.doc-button}.
3. Enter a unique name for the new integration that identifies the data source.
4. From the **External system** drop-down menu, select **8X8**.
5. Click _Save_{:.doc-button}.

## Set up your 8X8 integration <a name="set-up-your-8x8-integration"></a>

1. In the **Credentials** section, enter the [required information](#credentials).
2. In the **Configuration** section, enter the [required information](#configuration)
3. Click _Save_{:.doc-button}.

### Credentials <a name="credentials"></a>

<style>
table {
   margin-left: 0px;
}
</style>

| Field         | Description                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------ |
| Client ID     | Your 8X8 client ID <!-- can we add an example? (e.g., https://<customerID>.rest.afas.online) --> |
| Client secret | Your 8X8 client secret <!-- can we add an example?    -->                                        |

### Configuration <a name="configuration"></a>

<style>
table {
   margin-left: 0px;
}
</style>

| Field          | Description                    |
| -------------- | ------------------------------ |
| Account region | The region of your 8x8 account |

## Queue data and channel mapping <a name="queue-data-and-channel-mapping"></a>

The integration imports interactions that have a `queueName` and whose direction is either `InboundDir` or `OutboundDir`.
Peopleware handles data as explained in the table below:

<style>
table {
   margin-left: 0px;
}
</style>

| Data type             | Report/metric used                                                               |
| --------------------- | -------------------------------------------------------------------------------- |
| Queue data            | `historical-metrics` report with the type `detailed-reports-interaction-details` |
| Interaction timestamp | `queueTime`                                                                      |

`Handled` is set to `true` when the interaction includes the `Handled` label.

Peopleware maps media types to channels as explained below:

<style>
table {
   margin-left: 0px;
}
</style>

| 8x8 channel | Peopleware channel |
| ----------- | ------------------ |
| phone       | call               |
| chat        | chat               |
| email       | email              |
| voicemail   | call               |

## Agent status data <a name="agent-status-data"></a>

Peopleware uses the `agentId`, `status`, and `statusCode` from the report to build the agent statuses.<br>
If there is a `statusCode`, Peopleware includes it in brackets, e.g.: "OnBreak (Lunch)".<br>
If the `status` is `LoggedOut`, Peopleware does not include the `statusCode`.

### Historical agent status data <a name="historical-agent-status-data"></a>

Peopleware retrieves the historical agent statuses by triggering a `historical-metrics` detailed report with the type `detailed-reports-agent-status-change`.

> Potential time discrepancy in Intraday Adherence
>
> The 8X8 API accepts timestamps only in UTC format but interprets them as local time when returning data. This can cause a time discrepancy for tenants in time zones that differ from UTC.<br>
> In addition, the integration imports historical agent status data every 15 minutes. This can introduce an additional delay of 15-30 minutes.<br>
> If present, these time discrepancies will appear in the historical agent status data in _Intraday > Intraday Adherence_{:.breadcrumbs}.

### Live agent status data <a name="live-agent-status-data"></a>

Peopleware retrieves live agent status data as explained in the table below:

<style>
table {
   margin-left: 0px;
}
</style>

| Data type              | Report/metric used                                                                                                                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Live agent status data | `realtime-metrics`                                                                                                                                                                                      |
| Person's timestamp     | `loggedInTime` is added to `lastLogin`, then `timeOnStatus` is subtracted. <br>If the person's status is `LoggedOut`, Peopleware sets both the status start and end time to the `lastLogout` timestamp. |

## AHT calculation <a name="aht-calculation"></a>

For each call, the integration calculates handling time as the difference between `Wrap Up End Time` and `Offer Action Time`.<br>
The average handle time (AHT) is calculated as follows:
(Sum of handling times for 15-minute interval) / (Number of handled calls for 15-minute interval)
