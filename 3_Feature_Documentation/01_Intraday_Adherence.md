---
title: Intraday adherence
toc: true
product_label:
  - advanced
  - enterprise
description: Get an overview of how closely people have adhered to their shift schedules throughout the day.
archive_ref: 20210422-de-adherence
related_articles:
  - overwrite_title: Add title for untranslated source
    filepath: features/intraday/real-time-adherence.md
  - overwrite_title: Add title for untranslated source
    filepath: features/intraday/edit-intraday-activities.md
---

In _Intraday > Intraday Adherence_{:.breadcrumbs}, you can compare people's scheduled activities with the actual activities to identify out-of-adherence periods throughout the day. Intraday adherence uses {% link_new real-time adherence | features/intraday/real-time-adherence.md %} data from your ACD or the Time Tracking app in Me. You can access the adherence data for the current month and the last six months.

## Display data <a name="display-data"></a>

To display adherence data for a specific day, follow these steps:

1. Select a _Planning unit_{:.label} and/or a _Selection_{:.label}.
2. At the top of the page, select a date by using the date picker, or click _Today_{:.doc-button} or _Yesterday_{:.doc-button}.

The page displays the total adherence score, adherence scores by interval, and a table with the details of the adherence data per person for the selected day.

### Adherence score <a name="adherence-score"></a>

The page shows different adherence score details:

- **Adherence**: Percentage of working time spent on scheduled activities. If the day has not ended, the score is calculated up to the last updated timestamp, which is displayed above the score. If the score falls below the {% link_new the target adherence score | features/intraday/real-time-adherence.md | #target-adherence-score %}, it is highlighted in red.
- **Scores by interval**: Vertical blue bars represent scores by interval. Scores lower than 100&nbsp;% represent intervals during which people’s actual activities deviate from their scheduled activities.
- **Target adherence score**: The dashed line in the graph shows the configured target score.

<!-- Adherence in %	Percentage of working time spent in activities that comply with the scheduled activities	Minutes in adherence/scheduled minutes * 100% -->

### Staff overview table <a name="staff-overview-table"></a>

Under the total adherence score and the scores by interval, a table displays adherence details for the selected day. To sort the table by adherence score, click the **Adherence** header. To sort the table by name, click the **Name** header.

Each row shows a person's adherence score. Differences between the person's scheduled activities and their actual activities are highlighted.

When a person's score drops below the configured adherence target score, their score is highlighted in red. {% link_new Matches | features/intraday/adherence-matches.md %} and {% link_new buffer times | features/intraday/real-time-adherence.md | #buffer-time %} may influence changes in status and adherence types. Learn more about the {% link_new status and types | features/intraday/real-time-adherence.md | #adherence-statuses %}.

Different colors identify the three out-of-adherence types:

- Red: Not present
- Yellow: Wrong activity
- Blue: Not scheduled

## Agent intraday adherence <a name="agent-intraday-adherence"></a>

To see the details of a person's intraday adherence in a new window, click their row. To change dates, use the month selector or the navigation arrows next to the dates.

On the left, two boxes display an overview of the selected month:

- **Person name**: Shows the person's adherence score, how long they were scheduled, and adherence details for the selected month. The values include the data up to the last completed interval of the current day.
- **Daily overview**: Days for which adherence scores are available are highlighted in red. Hover over a date to see the adherence score of the selected person. Click a date to see the details.

On the right, you can see in detail when this person was scheduled and where they did not adhere to the schedule:

- **Intraday adherence score**: Calculated using data up to the last completed interval of the current day. Identical to the day score when you hover a date in **Daily overview**.
- **Scheduled** and **Out of Adherence** durations: Sum of durations for all scheduled activities (activity types Present, Meeting, Break) and deviations in the schedule on the selected date.
- **Timeline**: Colored bars highlight scheduled activities, actual activities, and out-of-adherence statuses. In the **Out of adherence** row, you can click out-of-adherence time slots to zoom in. Click _Reset zoom_{:.doc-button} to reset the zoom.
- **Table**: Each row shows details for out-of-adherence periods. Click a header to sort data by time period, actual activity, status, scheduled activity or out of adherence duration.

## Adherence report (CSV file) <a name="adherence-report-csv-file"></a>

If you need to analyze adherence and conformance data for individual people over a longer time frame, e.g. to calculate bonus payments, you can download a report as a CSV file that includes aggregated adherence and conformance data. To download the Adherence report file , follow these steps:

1. Select a _Planning unit_{:.label} and/or a _Selection_{:.label}.
2. Click _Download report_{:.doc-button}.
3. In the **Download report** window, select a date range for the report. You can select any date range from one day to up to six months in the past.
4. Click _Download report_{:.doc-button}.

The table below explains the report columns:

| Column                     | Explanation                                                                              | Calculation                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Activity                   | The activity for which the adherence data is displayed.                                  | --                                                                         |
| Scheduled minutes          | The duration scheduled for the activity, in minutes.                                     | --                                                                         |
| Actual minutes             | The actual time spent on the scheduled activity, in minutes.                             | --                                                                         |
| Minutes in adherence       | Time spent in activities that comply with the scheduled activities                       | --                                                                         |
| Minutes out of adherence   | Time spent in activities that do not comply with the scheduled activities                | --                                                                         |
| Adherence in %             | Percentage of working time spent in activities that comply with the scheduled activities | Minutes in adherence/scheduled minutes \* 100%                             |
| Minutes out of conformance | The difference between the actual working time and the scheduled time                    | Actual working minutes - scheduled minutes                                 |
| Conformance in %           | Percentage of working time in compliance with the scheduled working time                 | Actual time/scheduled time \* 100%                                         |
| Scheduled in %             | The percentage of scheduled working time for an activity of a certain type               | Scheduled time for the relevant activity type/total scheduled time \* 100% |
| Actual in %                | The percentage of actual working time spent on an activity of a certain type             | Actual time for the relevant activity type/total actual time \* 100%       |

Each row of data includes a link to display the related data in _Intraday > Intraday Adherence_{:.breadcrumbs}.

## Frequently asked questions <a name="frequently-asked-questions"></a>

| Question                                     | Answer                                                                                                                                                                                                                                                                                |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Why are some or all people missing?          | Try to clear the search input. Check if the people you are looking for are scheduled today in the selected planning unit or selection.                                                                                                                                                |
| Why can't I select a specific date?          | You can access historical adherence data for the six months prior to the current date, plus the current month (e.g. if today is July 15, you can select dates between January 1 and July 15.)                                                                                         |
| Which time zone does Intraday adherence use? | Intraday adherence uses the selected planning unit's time zone. If you click a person to see the Agent Intraday Adherence details, all times appear in the _time zone_{:.css} configured in your user profile. The time zone is displayed at the top right of the adherence timeline. |
