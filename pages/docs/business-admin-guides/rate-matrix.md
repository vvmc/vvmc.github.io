---
title: Create Duration Activity Rate Matrix
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: rate-matrix.html
folder: mydoc
---

### Prerequisites
* Define duration activity categories and duration activity unit types.
* Security: *Set Up: Duration Activity* domain in the Academic Faculty functional area.

### Context
The *Duration Activity Pay* business process uses rate matrices to automatically populate a unit rate for a duration activity category and duration activity unit type combination.

### Steps
1.  Access the **Create Duration Activity Rate Matrix** task.
1.  As you complete the task consider:
    <table>
    <colgroup>
    <col width="35%" />
    <col width="65%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Field</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td markdown="span">**Employee Eligibility Rules**</td>
    <td>Specifies which employees can use the matrix during the duration activity pay assignment process.{% include note.html content="For the eligibility rule definition to apply to the rate matrix, the employee and their position must exist for all fields available. <b>Run the Manage Duration Activity Pay Assignments</b> task after the <i>Hire</i> or <i>Add Job</i> business processes complete." %}
    </td>
    </tr>
    <tr>
    <td markdown="span">**(Optional) Minimum/Default Rate**</td>
    <td>Use when there is:
    <ul>
    <li>No <b>Accelerator</b>.</li>
    <li>An <b>Accelerator</b>, but <b>Accelerator Base</b> is empty.</li>
    <li>An <b>Accelerator</b> and an <b>Accelerator Base</b>, but the <b>Minimum/Default Rate</b> is higher than the accelerated rate during the past academic year.</li></ul></td>
    </tr>
    <tr>
    <td markdown="span">**(Optional) Accelerator**</td>
    <td markdown="span">The accelerator rate calculation uses the highest rate from the **Minimum/Default Rate** and the **Accelerator Base**.
    </td>
    </tr>
    </tbody>
    </table>

### Result
The application uses **Minimum/Default Rate** and the **Accelerator** to automatically populate the unit rate when you assign activities using the **Manage Duration Activity Pay Assignments** task.

### Next Steps
Assign duration activities to employees.
