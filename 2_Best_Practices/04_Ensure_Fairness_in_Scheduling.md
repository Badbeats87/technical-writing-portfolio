---
title: Ensure fairness in scheduling
product_label:
  - essential
  - advanced
  - enterprise
  - classic
description: Ensure a more even distribution of shifts and achieve a greater perception of schedule fairness.
---

Regardless of the {% link_new scheduling method | features/scheduling/scheduling-methods.md %} you use, it may turn out that some employees receive unpopular shifts more often than others because of their availability or the fact that they possess rare skills. This can quickly lead to employee dissatisfaction, a reduction in morale, and increased staff turnover.

This article gives you some best practice tips for ensuring a more even distribution of shifts and greater perception of fairness.

## Shift sequences for even distribution <a name="shift-sequences-for-even-distribution"></a>

Use shift sequences to ensure a more even distribution of tasks or shifts. With shift sequences, you create schedules that repeat regularly.

{{ 1 | image: 'Shift Sequences'}}

Shift sequences are recommended, especially for weekend shifts. Weekend shifts are evenly distributed among your employees. Your employees can even predict when they will work weekends.

### Combining shift sequences with schedule optimization <a name="combining-shift-sequences-with-schedule-optimization"></a>

If you want to use schedule optimization but also want to evenly distribute some shifts, it is possible to combine the use of shift sequences with schedule optimization.

For example, if you want to rotate weekend shifts, do the following:

1. Create a {% link_new day model availability | features/administration/availabilities.md %} with a length of 1 minute that sets the day to be completely unavailable.
2. Insert this day model availability into a two-week shift sequence, alternating every other weekend, and leaving all other days blank.

Before running the schedule optimization, you can insert the shift sequence into the schedule.

- On weeks with the blocking availability period, the employee will not be scheduled for the weekend, and their schedule during the week will be optimized.
- On weeks when the weekend is not blocked, the employee can work on the weekend. Both the schedule for the weekend and the rest of the week will be optimized.

## Optimized rotation: Work time pattern models <a name="optimized-rotation-work-time-pattern-models"></a>

If you want to optimize shifts while applying rotating patterns, use _work time pattern models_{:.menu-item}.

Work time pattern models let you schedule your employees work early, middle, and late shifts on a rotating weekly basis (for example). In each week, the shifts that may be worked are chosen from a list of **day models** that you specify in a **week time pattern**. The optimization is constrained by the **type** you specify in the work time pattern model - _Flexible Rotation_, _Fixed Rotation_, etc.

## Unpopular shifts: Exception days <a name="unpopular-shifts-exception-days"></a>

If you don’t want to assign unpopular shifts or tasks for entire weeks, but only schedule one or two per week for each employee, you can use _week time patterns_{:.menu-item} with **exception days**:

1. Create a **week time pattern** with your standard shifts.
   {{ 4 | image: 'week time pattern with day models for standard shifts', '50%' }}
2. In the week time pattern, enter a value of 1 (or more) in the **Maximum Number of Exception Days per Week** field to define how many unpopular shifts an employee can get within a week.
   {{ 3 | image: 'Week Time Pattern Model', '50%' }}
3. Create a second **week time pattern** with your unpopular shifts.
4. In a work time pattern model, add the week time pattern(s) with your standard shifts.
   {{ 5 | image: 'work time pattern model with week time pattern(s) for standard shifts', '50%' }}
5. Select the week time pattern with unpopular shifts from the **Week Time Pattern - Exception Days** drop-down menu.
   {{ 2 | image: 'work time pattern model', '50%' }}

## Fairer shift bidding <a name="fairer-shift-bidding"></a>

In the short term it is possible in shift bidding that employees do not get the shifts for which they stated a preference. For more fairness, you can give preference to certain selections. This way, a fair lottery will be achieved in long run, which may not be given by the pure random principle.

For this, assign the employees to different selections and rotate the selection for which you first assign shifts in each scheduling cycle.

Example:

- In June, selection A gets to bid first, followed by B, and then C.
- In July, selection B gets to bid first, followed by C, and then A.
- In August, selection C gets to bid first, followed by A, and finally B.
- Etc.
