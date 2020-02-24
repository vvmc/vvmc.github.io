---
title: Set Up Commission Memberships
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_set_up_commission_memberships.html
folder: mydoc
---

### Prerequisites
Set up commissions.

### Context
You can easily track different types of members by organizing your commission memberships. We recommend setting up commission memberships before you:
* Find potential commission members.
* Invite people to join a commission.
* Manage commission memberships.
* Create external commission members.

### Steps
1.  Access the **Maintain Commission Membership Type** task.

    Create and track different types of commission membership, such as officers, alumni, or graduate students.

1.  Access the **Maintain Event Categories and Reasons** task.

    Create categories and reasons for commission membership.

1.  <span style="color: blue;">Create Custom Business Processes</span>.

    Configure these business processes and security policies in the Organizations and Roles functional area:
    * *Manage Commission Membership*
    * *(Optional) Invite Commission Candidates*

    If you have external commission members, configure security for the *Create External Commission Member* initiating action on the *Manage commission Membership* business process.
1.  <span style="color: blue;">Edit Domain Security Policies</span>.

    Configure these domains in the Organizations and Roles functional area:
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Doamins</th>
    <th>Controls Access To</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><ul><li><i>Manage: Commission Invitations</i></li><li><i>Self-Service: Commission Invitation</i></li></ul></td>
    <td>Commission invitation tasks and data.</td>
    </tr>
    <tr>
    <td><ul><li>(Optional) <i>Commission Candidates: Academic</i></li><li>(Optional) <i>Commission Candidates: Demographic</i></li><li>(Optional) <i>Commission Candidates: HR</i></li><li>(Optional) <i>Commission Candidates: Talent</i></li><li>(Optional) <i>Search: Commission Candidates</i></li></ul></td>
    <td><b>Find Commission Candidates</b> report.</td>
    </tr>
    <tr>
    <td><ul><li><i>Commission Membership</i></li><li><i>Commission Membership: Current</i></li><li><i>Commission Membership: Historical</i></li><li><i>Commission Membership: Manage</i></li><li><i>Commission Membership: Reporting</i></li><li><i>Commission Membership: Self-Service</i></li></ul></td>
    <td>Commission membership tasks, reports, and profiles.</td>
    </tr>
    <tr>
    <td><ul><li><i>External Commission Member: Public Reports</i></li><li><i>External Commission Member: Contact Data</i></li><li><i>External Commission Member: Contact Information</i></li><li><i>External Commission Member: Photo
</i></li></ul></td>
    <td>View and update access to external commission member data.</td>
    </tr>
    </tbody>
    </table>
    Configure these super domains, or their subdomains, in the Contact Information functional area:
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Doamins</th>
    <th>Controls Access To</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><ul><li><i>Person Data: Name</i></li><li><i>Person Data: Personal Data</i></li><li><i>Self-Service: Name</i></li><li><i>Self-Service: Personal Data</i></li></ul></td>
    <td>View and update access to external commission member personal data.</td>
    </tr>
    </tbody>
    </table>
1.  (Optional) Access the **Edit Tenant** task.

    Use the **ID Definition for Academic Affiliate ID** and **ID Definition for External Commission Member ID** fields to select your own ID format definitions. Otherwise, the application assigns unique IDs to each academic affiliate and external commission member.

    See <span style="color: blue;">Reference: Edit Tenant</span>.
1.  (Optional) Access the **Edit Tenant - Notifications** task.

    Configure email notifications to invitees. For the **HCM** parent notification type, configure **E&G Commission Invitation**.

    See <span style="color: blue;">Reference: Edit Tenant - Notifications</span>.
1.  (Optional) <span style="color: blue;">Set Up Profiles and Profile Groups</span>.

    Add the **Commission Service** and **Commission Invitations** reports to the commission member profiles. Add commission membership reports to the commission profile groups.

### Next Steps
Configure the *End Commission Membership Service* step on the *Termination* business process in the Staffing functional area. This step enables the application to end a commission membership automatically on the same day of a termination.
