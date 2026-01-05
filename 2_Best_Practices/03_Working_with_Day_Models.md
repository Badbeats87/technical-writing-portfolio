---
title: Create flexible shifts that fit your employees' contracts
product_label:
  - advanced
  - enterprise
  - classic
description: Create shifts that match the contracts of your full-time and part-time employees.
---

## Scenario <a name="scenario"></a>

You want to create shifts that match the contracts of your full-time and part-time employees.

You have different contracts, for example:

- 40 hours (5 x 8h)
- 32 hours (4 x 8h)
- 30 hours (5 x 6h)
- 24 hours (4 x 6h)
- 20 hours (5 x 4h)
- 12 hours (3 x 4h or 2 x 6h)

In our example, your Contact Center is open between 07:00-19:00. For your call volume, let's assume a distribution with two peaks; one in the morning and one in the afternoon.

> Note
>
> For simplicity, this example does not include breaks. When you create day models, you must take breaks into account and add them to the total working time. For example, an unpaid 30-minute break per day increases the total working time for an employee who works 8 hours a day to 8.5 hours.

## Representation in Peopleware <a name="representation-in-peopleware"></a>

Peopleware creates shifts using {% link_new day models | features/administration/daymodels/daymodel-creation.md %}. Day models are based on {% link_new contracts | features/administration/create-contracts.md %} which define the possible shifts an employee can work. Day models are assigned to {% link_new planning units | features/administration/create-and-manage-planning-units.md %}.

You can use day models with a variety of {% link_new scheduling methods | features/scheduling/scheduling-methods.md %} to create your schedules. You can also {% link_new combine | features/scheduling/combined-scheduling-methods.md %} all of these scheduling methods to balance schedule optimization and schedule predictability.

## Recommended approach <a name="recommended-approach"></a>

All you need to start is information on what contracts are assigned to your employees. You can then start creating your day models:

1. Create a single day model for all shifts with the same working hours per day. The number of working days and the total hours per week are determined by the employee's contract.

   So, in theory the 12-, 24- and 30-hour contracts only need a single 6-hour day model, if the employees work the same number of hours per day, and all other activities included in the day model are the same.<br><br>

   In reality, contracts are often more flexible, allowing employees to work more hours on busy days and fewer hours on slow days. For example, your employees may be allowed to work shifts between 6 and 8 hours long to reach a target working time of 37.5 hours per week. Thus, depending on the desired flexibility, several day models may be required.<br><br>

   Fixed activities within a shift (such as daily huddles) may require a separate day model, even though the daily working time is the same.

2. Define for all your day models
   - Total working hours
   - Number, valid times, and duration of breaks
   - Any fixed activities required

3. Determine if employees have flexible start and end times, and if so how flexible they are

   At the start and end of the day, you may need less employees than in the middle of your day. Variable day models with different start times make your schedules more flexible.

   Use short part-time shifts to cover the morning and afternoon peaks, while your full-time staff is sufficient to handle the low volume at lunch. This way, the day models for the part-time employees are placed in the morning or afternoon so that there is as little overlap as possible in the middle of the day.

## Scheduling result <a name="scheduling-result"></a>

By setting up flexible day models for your part-time employees to help add coverage with your full-time employees, you have created all the required elements to create optimal schedules for your employees.

{{ 1 | image: 'Covering the opening hours with shifts', '75%' }}
