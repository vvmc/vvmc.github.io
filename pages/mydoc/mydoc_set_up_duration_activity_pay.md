---
title: Set Up Duration Activity Pay
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_set_up_duration_activity_pay.html
folder: mydoc
---

### Prerequisites
Create time periods using the **Maintain Time Periods** task.

### Context
You can set up duration activity pay so you can pay your employees for activities they perform during a fixed duration.

### Steps
1.  Access the **Edit Tenant** task.<br/><br/>In the **Educational Institutions** section, select the **Enable Duration Activity Pay** check box.<br/><br/>See <span style="color: blue;">Reference: Edit Tenant</span>.
1.  Access the **Maintain Compensation Elements** task.<br/><br/>Select the **Time Duration Pay Enabled** option on compensation elements you want to enable for duration activity pay.
1.  Set up cost centers to enable costing overrides:
* Access the **Maintain Worktag Usage** task, select **Duration Activity Pay Costing Allocation**, and add **Cost Center** to the **Primary Worktag** Types.
* Access the **Maintain Organization Types** task, select **Costing** > **Cost Center**, and select **Yes** for **Available for Payroll Costing Allocation**.
1.  Access the **Maintain Duration Activity Categories** task.<br/><br/>Define the classifications of the activities. Example: degree program, credit course, or noninstructional.
1.  Access the **Create Duration Activity Unit** task.<br/><br/>Define the unit types. Examples: Hours, students, or course credits.
1.  Access the **Create Duration Activity** task.<br/><br/>Define the activity to assign to employees. Examples: Contact hours, lecturing, grading, running labs, or course development.<br/><br/>For reporting purposes, you can select the Instructional **Activity** check box to identify duration activities that are instructional activities.
1.  (Optional) **Access the Create Duration Activity Task** task.<br/><br/>Use duration activity tasks to provide a greater level of detail for an activity assignment. Example: Create a task named History 101 associated with the Lecturing activity. When you assign the Lecturing activity to the employee, you can include the History 101 task.
1.  <span style="color: blue;">Create Duration Activity Rate Matrix</span>.
1.  Access the **Maintain Event Categories and Reasons** task.<br/><br/>Create categories and reasons for the *Duration Activity* event.
1. <span style="color: blue;">Edit Domain Security Policies</span>.<br/><br/>Configure these domains in the Academic Faculty functional area:
    * *Self-Service: Duration Activity Pay*
    * *Worker Data: Duration Activity Pay*
1. <span style="color: blue;">Edit Business Process Security Policies</span>.<br/><br/>Configure initiating actions on these business process security policies in the Academic Faculty functional area:
* *Duration Activity Pay*
* *Duration Activity Eligibility*
1. <span style="color: blue;">Create Custom Business Processes</span>.<br/><br/>Configure these business processes in the Academic Faculty functional area:
    <ul>
    <li><i>Duration Activity Pay</i></li>
    <li><i>Duration Activity Eligibility</i></li>
    <ul><li> (Optional) <span style="color: blue;">Configure Generate Document Step</span>.<br/><br/>Configure the <i>Generate Document</i> step as a subprocess on the <i>Duration Activity Pay</i> business process to create, edit, and print documents in an event.<br/><br/>We recommend that you add the <i>Review Documents</i> step on the <i>Duration Activity Pay</i> business process, after the <i>Generate Documents</i> step. The <i>Generate Documents</i> step inherits security from the <i>Duration Activity Pay</i> business process security policy.</li>
    <li> (Optional) <span style="color: blue;">Add Worklets to Business Processes</span>.<br/><br/>Embed worklets on any step of the <i>Duration Activity Pay</i> business process to display information from your custom reports to help users complete the step.</li></ul>
1. (Optional) <span style="color: blue;">Edit Business Processes</span>.<br/><br/>Add the *Add Activity Pay* subprocess to the *Hire* and the *Add Additional Job* business processes.<br/><br/>Add the *End Activity Pay* subprocess to the *Terminate* and the *End Additional Job* business processes. The *End Activity Pay* step requires you to pay in full or forfeit any remaining pay balance for each activity assignment as of the **Pay Through Date**.
    {% include note.html content="If you don't end duration activity payments at termination, the assignee could have unprocessed payments." %}
1. (Optional) Access the **Create Payroll Commitment Rule** task.<br/><br/>Use Payroll to obligate the budget for workers who have duration activity pay assignments.<br/><br/>Select the activity pay earning from the **Earning** field. The application automatically populates the **Compensation Elements for Earning** field with the **Activity Pay** task.

### Next Steps
Access the **Manage Duration Activity Pay Assignments** task to assign activity assignments to an employee.
