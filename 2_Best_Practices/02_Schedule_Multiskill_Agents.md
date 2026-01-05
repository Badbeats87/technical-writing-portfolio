---
title: Schedule multiskill agents
product_label:
  - advanced
  - enterprise
  - classic
description: Schedule multiskill agents using optimized scheduling.
toc: true
---

Contact centers offer their customers multiple channels, e.g. phone numbers for orders, or email and chat for complaints, which requires multiple skills. Not all agents are skilled in all areas, and they can only handle contacts they are skilled for.

## Representation in Peopleware <a name="representation-in-peopleware"></a>

Optimized scheduling supports multiactivities that allow you to schedule multiskill or multichannel tasks.

Each input channel represents a subactivity and each employee skill a corresponding Peopleware skill. During scheduling, all employee skills are included simultaneously in the staff requirements calculation. This causes a pooling effect, so that the total requirement for agents decreases because all necessary skills are covered by fewer employees.

## Recommended approach <a name="recommended-approach"></a>

1. Create a {% link_new Multiactivity | features/administration/activity-types-and-properties.md | #subactivities %}.

2. Create the forecast. For multiactivity, you will need a workload for each skill and each contact channel.

3. Calculate the multiactivity staff requirements by using the `Calls - Multiactivity` requirement calculation. For more information, see {% link_new Staff requirement reference guide | features/forecast/staff-requirements/ref-requirement-calculations.md | #calls-multi-activity %}.

4. Run the **Create optimized schedule** functionality.

### Scheduling result <a name="scheduling-result"></a>

In _Shift Center_{:.menu-item}, the schedule only contains the multiactivity. The subactivities are visible in the parameter window:

{{ 2 | image: "Shift Center with parameters for multiactivity" }}

> Hint
>
> You cannot add up the staffing values for each subactivity to calculate the value for the multiactivity
>
> The multiactivity staffing always equals the number of people that has been scheduled. The Shift center does not display absolute numbers for subactivities, but the number of people skilled to perform this task. When people are skilled for multiple subactivities, the subactivity staffing values can be as high as the multiactivity staffing at maximum.

To see a person's assigned activities for a day, double-click a day cell and select the **Multi-Activities** tab.

{{ 1 | image: "subactivities in shift center dialog", '60%' }}

For intraday management, {% link_new Dashboards | features/monitoring/dashboards/manage-dashboards.md %} can display the coverage and staffing for multiactivities and their subactivities. Pull the staffing for the single subactivities and the multiactivity itself into the chart.

{{ 3 | image: "Multiactivity staffing dashboard" }}
