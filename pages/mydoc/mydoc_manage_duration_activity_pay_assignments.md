---
title: Manage Duration Activity Pay Assignments
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_manage_duration_activity_pay_assignments.html
folder: mydoc
---

### Prerequisites
* Set up duration activity pay.
* Assign pay group to employee and employee position.
* Security: *Duration Activity Pay* in the Academic Faculty functional area.

### Context
You can use the **Manage Duration Activity Pay Assignments** task to assign new or adjust existing activity assignments during an academic duration.

### Steps
1. Access the **Manage Duration Activity Pay Assignments** task.
1. As you complete the task, consider:
    <table>
    <colgroup>
    <col width="30%" />
    <col width="70%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Field</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td markdown="span">**Effective Date**</td>
    <td>Select a date on or after the current date and after the employee's <b>Hire Date</b>.
    </td>
    </tr>
    <tr>
    <td markdown="span">**Eligible Activities**</td>
    <td>You can select activities here if you assigned eligible activities to the employee using the <b>Assign Eligible Duration Activities for Employee</b> task.</td>
    </tr>
    </tbody>
    </table>
    Your selections on the **Quick Entry Choices** section automatically populates the **Units** and **Compensation** columns for each activity on each assignment in the subsequent step.
1. Click **OK** to proceed to the next page.
1. As you complete the task, consider:
    <table>
    <colgroup>
    <col width="30%" />
    <col width="70%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Field</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td markdown="span">**Work Hours Per Week, Work Hours Per Activity Duration, and Weekly Service Hours**</td>
    <td>Available if you activated on the <b>Maintain Localization Settings</b> task. You can use these fields to track your assignee's work and service hours for reporting and regulatory requirements.
    </td>
    </tr>
    <tr>
    <td markdown="span">**(Optional) Costing Overrides**</td>
    <td>These settings override worktags from the <i>Change Organization Assignments</i> and <i>Assign Costing Allocation</i> business processes and enable you to adjust the costing settings for each activity assignment.<br/><br/>For more control of payroll expense reporting, you can configure related worktags on the <b>Maintain Related Worktag Usage</b> task. Example: Configure Cost Center as a related worktag for one-time payments.<br/><br/>Overrides for each organization type must add up to 100%. To override the default assignment, you can configure 1 override at 100%.<br/><br/>You can also add, delete, or change overrides after the assigned activity begins.<br/><br/>Select a <b>Payment End Date</b> equal to the <b>Pay Group Duration End Date</b> to ensure costing overrides resolve in the current duration pay results.</td>
    </tr>
    <tr>
    <td markdown="span">**(Optional) Do Not Pay**</td>
    <td>Select if you're only recording the activities, and don't want to process payment.
    </td>
    </tr>
    <tr>
    <td markdown="span">**Assigned Unit Rate/Total Amount**</td>
    <td>When you first assign an activity to an employee, the application uses the duration activity rate matrix to populate these fields. If you change an employee's activity, the application doesn't evaluate the duration activity rate matrix again. However, for reference, the application displays the rate matrix used for the original assignment.<br/><br/>To change an employee's activity and automatically populate these fields:
    <ul><li>Delete the row for their existing activity.</li>
    <li>Create a new row for the new activity.</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

### Result
The application uses payment dates, the total amount for the activity, and the employee's pay group to calculate the amount and number of payments.

Each duration activity pay assignment triggers a *Payroll Activity Payment* event for each scheduled payment. Payroll processes these assignments similarly to one-time payments. Each activity assignment row creates its own pay result.

You can view current and historical duration activity, compensation, and pay change history from the worker profile. Other reports include:
* **Duration Activity Pay Assignments**
* **Duration Activity Payment Details**
* **Eligible Duration Activities for Employee**
* **Activity Pay - Remaining Balance Costing Estimates**
* **Audit - Inactive Employee Jobs with Open Activity Pay**

Whenever you change duration activity assignments, The application recalculates the payment schedule and amount. Changes that affect the total amount can cause changes to the scheduled payment amounts. Extending the payment end date results in more but smaller payments.

{% include note.html content="We recommend that you avoid using on-demand checks to pay employees for duration activities. The application doesn't include on-demand check payments on duration activity pay reports. If you use on-demand checks, then manually adjust the Total Amount to avoid double payment." %}
