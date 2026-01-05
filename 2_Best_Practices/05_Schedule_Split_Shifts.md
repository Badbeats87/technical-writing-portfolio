---
title: Schedule split shifts
product_label:
  - advanced
  - enterprise
  - classic
description: Learn how to schedule two or more shifts per person per day with split shifts.
redirect_from:
  - /best-practice-split-shifts/
related_articles:
  - overwrite_title: Add title for untranslated source
    filepath: features/administration/work-with-skills.md
  - overwrite_title: Add title for untranslated source
    filepath: features/administration/activities.md
  - overwrite_title: Add title for untranslated source
    filepath: features/administration/daymodels/daymodel-creation.md
  - overwrite_title: Add title for untranslated source
    filepath: features/administration/work-time-pattern-models.md
  - overwrite_title: Add title for untranslated source
    filepath: features/scheduling/schedules/schedules-shift-bidding.md
---

## What are split shifts? <a name="what-are-split-shifts"></a>

A split shift consists of two (or more) shifts on the same workday. The shifts are separated by an extended break, e.g. longer than two hours.  
Split shifts are not very popular with some people.

Use split shifts if the following is true:

- Your staff requirements go down repeatedly at a particular time of day (see 1 p.m. to 4 p.m in the image below)
- You only have a few part-timers to cover peaks in staff requirements (see 10 a.m to 2 p.m.)
- You want to allow optimized scheduling to cover peak staff requirements by scheduling split shifts for full-timers (see 10 a.m to 2 p.m. and 3 p.m. to 6:30 p.m.)

{{ 6 | image: 'M curve for staff requirements with shifts', '90%' }}

## Set up split shifts <a name="set-up-split-shifts"></a>

To use split shifts in optimized scheduling, create {% link_new day models | features/administration/daymodels/daymodel-creation.md %} of the _Fixed_ or _Variable_ type. The type determines the flexibility of a day model. Learn more about {% link_new day model types | features/administration/daymodels/daymodel-basics.md | #types-of-day-models %}.

To increase scheduling flexibility, vary different break lengths and positions in multiple day models.

Use an _Absence_ activity to cover the break. This way, a person who signs out for their break will not show as out-of-adherence in the Adherence feature.

### Balance a recurring gap in staff requirements <a name="balance-a-recurring-gap-in-staff-requirements"></a>

To compensate a gap in staff requirements at a certain time of the day, create long day models of the _Fixed_ type. Add a (fixed) absence to counter a midday low, for example:

{{ 1 | image: 'Split shift day model of type Fixed Shift', '50%' }}

### Make schedules more flexible <a name="make-schedules-more-flexible"></a>

To make schedules more flexible, create day models of the _Variable Shift_ type. Add an absence in a corridor in which the break can be flexibly scheduled.

{{ 2 | image: 'Split shift day model of type Variable Shift', '50%' }}

## Limit the use of split shifts <a name="limit-the-use-of-split-shifts"></a>

Split shifts are unpopular with most people. To set a maximum number of split shifts per week, you can use work time pattern models with exception days:

1. Create a {% link_new week time pattern | features/administration/work-time-pattern-models.md %} and add the standard day models you want to use for scheduling.
2. Set the **Maximum number of exception days per week** to the number of allowed split shifts per person per week.

   {{ 3 | image: 'Week time pattern standard', '50%' }}

3. Create another week time pattern and add the day model for split shifts. Do not change the number of exception days.

   {{ 4 | image: 'Week time pattern exception for split shifts', '50%' }}

4. Create a {% link_new work time pattern model | features/administration/work-time-pattern-models.md %}.

5. In the **Week time pattern - exception days** drop-down menu, select the week time pattern that contains the split shifts which will be used to schedule exception days.

   {{ 5 | image: 'Work time pattern model with split shifts', '50%' }}

6. Assign the work time pattern model to your people.

Optimized scheduling aims at the best coverage using normal or split shifts. Exception days ensure that split shifts are only scheduled up to the defined maximum.

## Limit split shifts to certain people <a name="limit-split-shifts-to-certain-people"></a>

By adding a skill to your activity for a gap between shifts, you can specify that only selected people are scheduled for split shifts:

1. Create a new skill, e.g _Break (Split Shift)_.
2. Create an _Absence_ activity, e.g. _Break (Split Shift)_ and assign the new skill.
3. Create a day model for the split shift and add the absence activity.
4. Add the new skill to people you want to schedule for split shifts.

Only skilled people will receive the split shift day model in optimized scheduling.

## Use split shifts in shift bidding <a name="use-split-shifts-in-shift-bidding"></a>

Besides the long day models for split shifts introduced above, {% link_new shift bidding | features/scheduling/schedules/schedules-shift-bidding.md %} can also schedule two or more short standard day models per person as separate shifts.

For this, set the scheduling parameter _2613_{:.id-label} **Max. shifts per day** to the value of 2 or higher in the person's contracts

The shifts are generated according to staff requirements. Enter correct numbers in the shift requirements table:

- Add enough short shifts so that all people an achieve their weekly target
- For day models of the _Fixed Shift_ type, ensure that employees can get one shift at the beginning and one at the end of the day. If shifts overlap, only one of the shifts will be assigned.

> Shift bidding and optimized scheduling
>
> If a shift has already been scheduled by the shift bidding process, optimized scheduling cannot schedule additional shifts for the same day because it only allows one day model per day.
