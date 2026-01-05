---
title: Set up the base configuration
description: Required configuration data to create a schedule.
redirect_from:
  - /configuration-hints/
  - /quickstart-base-configuration/
redirect_reason: Updated filename on 24 July 2023
product_label:
  - essential
  - advanced
  - enterprise
---

Before you can start scheduling, you need to set up your basic configuration. Some of the basic configuration items are strictly required to create a schedule, while others are optional and depend on the {% link_new scheduling methods | features/scheduling/scheduling-methods.md %} you want to use.

## Configuration order <a name="configuration-order"></a>

We recommend setting up the configuration items in the order presented in the next section. Configuration items have interdependencies and can be assigned to one another. Follow the links in the table to learn more about each configuration item and how to configure them.
No configuration setup is the same, which is why the optimal order might be different for your organization. Use this article as a checklist to support your onboarding. Contact your consultant if you have any questions.

### Required configuration elements <a name="required-configuration-elements"></a>

The table below gives an overview of the configuration items required regardless of the scheduling method you want to use.

<table>
  <colgroup>
    <col style="width: 25%;">
    <col style="width: 75%;">
  </colgroup>
  <thead>
    <tr>
      <th>Configuration item</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>{% link_new Skills | features/administration/work-with-skills.md %}</td>
      <td>Skills represent the qualifications of your people. By assigning skills to people, they become qualified to work on certain activities. You need to assign skills to activities that only certain people can work on. You are not required to add skills to the activities that everybody can work on.</td>
    </tr>
    <tr>
      <td>{% link_new Activities | features/administration/activities.md %}</td>
      <td>Activities are tasks, meetings, and time off that you schedule and report on in your company.<br> Activities are added to day models and planning units.</td>
    </tr>
    <tr>
      <td>{% link_new Day models | features/administration/daymodels/daymodel-creation.md %}</td>
      <td>Day models are shift templates. Day models define the start and end times of a shift, as well as how many hours a person works per day. They contain all presence, break, and absence activities in a shift.<br>Day models are assigned to planning units. They can also be grouped in week time patterns (optional).</td>
    </tr>
    <tr>
      <td>{% link_new Planning units | features/administration/create-and-manage-planning-units.md %}</td>
      <td>Planning units represent your real or virtual locations. They are used to group people for scheduling purposes.</td>
    </tr>
    <tr>
      <td>{% link_new Contracts | features/administration/create-contracts.md %}</td>
      <td>Contracts contain information about your people's contractual working arrangements, including their target, minimum, and maximum work hours each day, week, or month.<br>Contracts are assigned to people.</td>
    </tr>
    <tr>
      <td>{% link_new Employees | features/administration/employee-overview.md %}</td>
      <td>In Employees, you enter information about each person you schedule. Based on that and their assignments (day models, planning units, contracts, skills), Peopleware knows when your people can work and what they can work on.</td>
    </tr>
  </tbody>
</table>

### Optional configuration elements <a name="optional-configuration-elements"></a>

The table below gives an overview of the further configuration items you can optionally configure, based on your organizational setup and the scheduling method you want to use.

<table>
  <colgroup>
    <col style="width: 25%;">
    <col style="width: 75%;">
  </colgroup>
  <thead>
    <tr>
      <th>Configuration item</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>{% link_new Shift sequences | features/administration/shift-sequences.md %} (required for fixed scheduling)</td>
      <td>A shift sequence is a set of day models or activities with a repeating pattern.<br>Shift sequences are assigned to people.</td>
    </tr>
    <tr>
      <td>{% link_new Selections | features/administration/selections.md %}</td>
      <td>Selections allow you to filter and group people or to schedule them based on any given criteria, e.g., people who share the same team or contract type.<br> Selections are assigned to people.</td>
    </tr>
    <tr>
      <td>{% link_new Work time pattern models and week time patterns | features/administration/work-time-pattern-models.md %}</td>
      <td>Work time pattern models and week time patterns help you organize shifts by ensuring a fair distribution of (rotating) shifts among the people you schedule. Work time pattern models contain at least one week time pattern. Week time patterns group shifts by parameters such as start time, shift length, or activities. They contain sets of day models.<br>Week time patterns are assigned to work time pattern models. Work time pattern models are assigned to people.</td>
    </tr>
    <tr>
      <td>{% link_new Planning calendars and day types | features/administration/configure-planning-calendars.md %}</td>
      <td>Planning calendars contain days with deviating business hours and staffing needs (e.g., marketing campaign days or public holidays). These special days are configured using day types. This helps ensure they are automatically considered during scheduling without any additional manual effort.<br> Planning calendars are assigned to planning units.</td>
    </tr>
  </tbody>
</table>

## What's next? <a name="whats-next"></a>

Congratulations! You are ready to {% link_new create your first forecast | getting-started/calculate-a-forecast.md %}. Happy planning!
