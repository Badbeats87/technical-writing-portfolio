---
title: Edit or delete staff requirements
toc: true
product_label:
  - advanced
  - enterprise
description: Learn how to edit or delete the calculated staff requirements.
archive_ref: 20210819-en-employee-requirement
related_articles:
  - overwrite_title: Add title for untranslated source
    filepath: features/scheduling/shiftcenter/shift-center-overview.md
  - overwrite_title: Add title for untranslated source
    filepath: getting-started/calculate-a-forecast.md
  - overwrite_title: Add title for untranslated source
    filepath: features/forecast/staff-requirements/task-set-up-staff-requirement-calculation.md
  - overwrite_title: Add title for untranslated source
    filepath: features/scheduling/schedules/schedules-job-optimization.md
  - overwrite_title: Add title for untranslated source
    filepath: features/scheduling/schedules/schedules-optimized-schedules.md
redirect_from:
  - /employee-requirement/
redirect_reason: Updated filename on 28 February 2024
---

Staff requirements define how many people you need for an activity at a specific time. You need staff requirements to create schedules with the **Create optimized schedule** functionality, or to optimize them with **Job optimization** or **Optimize breaks**.

Generating staff requirements is the last step of the forecasting process. In _Forecasting_{:.breadcrumbs}, you can use the automatically generated requirements, or run a specific staff requirements calculation method. Before you create a schedule, make sure that staff requirements have been generated for all relevant activities.

## View and edit staff requirements <a name="view-and-edit-staff-requirements"></a>

You can view staff requirements in the following four places:

- _Forecasting_{:.menu-item}
- _Analytics > Dashboards_{:.breadcrumbs}
- _Scheduling > Schedules_{:.breadcrumbs}
- _Scheduling > Shift Center_{:.breadcrumbs}

The following table includes details about the options available in each place:

<style>
table {
   margin-left: 0px;
}
</style>

| Where                                      | View | Edit | Delete |
| ------------------------------------------ | ---- | ---- | ------ |
| _Forecasting_{:.breadcrumbs}               | Yes  | Yes  | Yes    |
| _Analytics > Dashboards_{:.breadcrumbs}    | Yes  | No   | No     |
| _Scheduling > Schedules_{:.breadcrumbs}    | Yes  | No   | No     |
| _Scheduling > Shift Center_{:.breadcrumbs} | Yes  | Yes  | No     |

### Edit staff requirements in Shift Center <a name="edit-staff-requirements-in-shift-center"></a>

1. Go to _Scheduling > Shift Center_{:.breadcrumbs}.
2. At the bottom of the panel, select the **Activities - Requirement** or the **Activity Overview** tab.<br>

   > No Data message in a cell
   >
   > If a cell in the lower table shows the message No Data, select **Schedule** or **Actual** from the **Levels** drop-down menu at the top right.

3. To expand a planning unit, click the {% icon plus %} on the left side of each table.
4. Right-click any cell in the lower table and select **Edit Employee Requirement**.
5. In the **Edit Employee Requirement** window, click a cell and enter the new value.<br>
   You cannot edit cells highlighted in blue because they represent deleted activities that are still assigned to the planning unit.<br>

6. (Optional) To edit several cells at once, copy a row of values from a spreadsheet. Click a cell and drag the mouse to the right. Press Ctrl+V to paste the values.<br>
7. Click _OK_{:.doc-button}.

### Edit staff requirements in Forecast <a name="edit-staff-requirements-in-forecast"></a>

To manually edit staff requirements, you can run the constant requirement script in _Forecasting_{:.breadcrumbs}. The following procedure explains how to configure the script for this specific use case. For more information on the individual configuration options, see the article {% link_new Constant requirement | features/forecast/requirement-scripts/constant-requirement-script.md %}.

1. Go to _Forecasting > Requirement Scripts_{:.breadcrumbs}.
2. In the **Other - Constant Requirement** tile, click _Open_{:.doc-button}.<br>
3. In the script configuration window, configure the following settings:
   - In the **Date** section:
     - **Start Date**
     - **Number of Days**: Enter for how many consecutive days after the start date the changed staff requirements apply.
     - **Consider Each Day of the Week**: Select **No**.
     - **Add to Existing Requirement**: Leave the checkbox unchecked.
     - **Number Of Days With Timespans**: To edit the staff requirements for all days in a date range, select 1.
     - **Timespans Per Day**: Select the number of time periods per day for which you want to edit staff requirements (e.g. 1 if you want to edit the staff requirements for the whole day, but 3 if you want to set different staff requirements for the morning, afternoon, and evening).
     - **Number of Activities**: Select the number of activities for which you want to edit the staff requirements.
   - In the **Data** section:
     - _Planning unit_{:.label} and **Activity**: Select the relevant data for each activity whose staff requirements you want to edit.
     - **Agents**: Enter the number that you want to use as staff requirements.
     - **Start** and **End**: Define the time range or ranges for which you want to edit the staff requirements.
4. Click _OK_{:.doc-button}.

## Delete staff requirements <a name="delete-staff-requirements"></a>

You cannot delete staff requirements. You can edit staff requirements to be 0, which has the same effect as deleting them.

You have two options to set the staff requirements to 0:

- Follow the steps to [edit staff requirements in Shift Center](#edit-staff-requirements-in-shift-center) and enter or copy 0 in the relevant cells.

- Follow the steps to [edit staff requirements in Forecasting](#edit-staff-requirements-in-forecast) and enter 0 in the **Agents** field.

The following image shows the configuration of the constant requirement script to delete staff requirements in _Forecasting_{:.breadcrumbs} for an entire calendar day (here: Day 1):

{{ 3 | image: 'Constant requirements script example with one activity from 00:00 to 00:00 and 0 requirements', '80%' }}
