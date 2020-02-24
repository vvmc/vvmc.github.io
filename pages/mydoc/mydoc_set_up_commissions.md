---
title: Set Up Commissions
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_set_up_commissions.html
folder: mydoc
---

### Context
You can track various types of groups including corporate, department, regulatory, or special subgroups. You can maintain commission memberships and meeting details to have a complete record of commission related activity.

You can classify a commission as private to restrict access to the commission, its members, and its meetings.

### Steps
1.  <span style="color: blue;">Edit Domain Security Policies</span>.

    Configure the *Commissions: View* domain to grant access for updating or viewing any commission information. You can then control access to specific commission information by combining other commission domains with the *Commissions: View* domain.

    To enable access to the commission profile and commission Member **Directory for Profile** report, configure the *Commissions: View* and *Commissions: Directory* domains.
1.  Access the **Maintain Commission Type** task.

    Create commission types for categorization purposes, such as faculty, student, or administrative. Selecting the **Search Commission** check box enables you to associate search commissions with job requisitions.

    Security: *Commission Definition: Set Up* domain in the Organizations and Roles functional area.
1. Access the **Maintain Organization Subtypes** task.

    Assign subtype levels to the commission organization type for reporting purposes. Subtypes are levels used in hierarchy-related calculated fields and in the definition of organization hierarchy structures.

    Security: *Commission Definition: Set Up* domain in the Organizations and Roles functional area.
1.  (Optional) Access the **Maintain Commission Classification Groups** task.

    Create groups that you can use to combine similar commission classifications for greater ease of reporting and usability, such as meeting frequency.

    Security: *Commission Definition: Set Up* domain in the Organizations and Roles functional area.
1. (Optional) Access the **Maintain Commission Classification** task.

    Classify commission definitions to correspond with your classification groups.

    Security: *Commission Definition: Set Up* domain in the Organizations and Roles functional area.
1. <span style="color: blue;">Maintain Commission Definition</span>.

    Create a commission.
1. <span style="color: blue;">Set Up Assignable Roles</span>.

    Create roles for commission type organizations, and assign them to academic affiliates, admission counselors, external commission members, students, or workers.
1. Link the roles to a role-based security commission.

    Associate roles with security groups to restrict role assignee access to only the data and business process actions of their commission.

    See <span style="color: blue;">Create Role-Based Security Groups</span>.
1. (Optional) <span style="color: blue;">Create Organization Membership Security Groups (Constrained)</span>.

    Grant current members access to commission information by creating a constrained organization membership security group for the commission.
1. (Optional) <span style="color: blue;">Steps: Set Up Profiles and Profile Groups</span>.

    Set up the commission profile and add its profile report to the sponsoring organization type profile.
1. (Optional) <span style="color: blue;">Steps: Set Up Dashboards and Landing Pages</span>.

    Set up the commissions dashboard to combine analytics and actions for managing your commissions from a single place.

### Result
You can use the com: search prefix to limit your results to commissions.


### Next Steps
We provide a number of standard reports to help you manage commissions. For a list, access the **Standard Reports** report and select the *Commissions* category.
