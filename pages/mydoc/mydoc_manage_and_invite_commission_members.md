---
title: Manage and Invite Commission Members
tags: [getting_started]
keywords: release notes, announcements, what's new, new features
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_manage_and_invite_commission_members.html
folder: mydoc
---

### Prerequisites
Set up commissions and commission memberships.

### Context
You can assign or invite academic affiliates, admissions counselors, students, workers, and external commission members to be members of commissions. When you invite commission candidates, you can monitor their responses.

### Steps
1.  Access the **Manage Commission Membership** task.

    Create new or update existing commission memberships. If a commission member is inactive or terminated, then you can only end their existing commission memberships.

    If you change an existing membership type, the previous membership type ends 1 day before the new **Effective Date**. The **Membership Service** Start Date is the date of the initial membership type and never changes. If you specify an end date for commission membership, the application automatically removes the member from the commission on that date.
1.  (Optional) Access the **Create External Commission Member** task.

    Add a new external commission member to application and assign them to a commission.
1. (Optional) Access the **Invite Commission Candidates** task.

    When the business process completes, invitees receive a notification, including attachments, and a link to the **Commission Invitation Response** task. Invitees can edit their responses until the invitation expires.

    {% include note.html content="You can browse and invite potential commission members based on custom criteria using the **Find Commission Candidates** report." %}
1.  (Optional) Access the **Manage Commission Invitation Responses** task.

    You can cancel or resend invitations that are pending responses.

1.  (Optional) <span style="color: blue;">Edit Business Processes</span>.

    Add the Manage Professional Affiliations business process as a subprocess of the **Manage Commission Membership** business process.

### Result
You can assign commission members to roles on commissions so they can participate in commission related tasks. The roles must be in security groups that have permission on the domains that control access to those tasks.

You can configure access for these groups to view commission membership information for their workers and affiliates.
* Academic unit role holders.
* Student cohort role holders.
* Supervisory organizations.

You can use the ecm: search prefix to limit your search results to external commission members. To view them, users must be in an unconstrained role-based security group or have a role on the commission, its superior commission, or the sponsoring organization. The role must be in a security group with permission on the *Commissions: View* and external commission member domains.
