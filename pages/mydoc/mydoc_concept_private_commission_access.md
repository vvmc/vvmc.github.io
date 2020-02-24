---
title: "Concept: Private Commission Access for Unconstrained Role Holders"
tags:
keywords:
last_updated:
summary:
sidebar: mydoc_sidebar
permalink: mydoc_concept_private_commission_access.html
folder: mydoc
---

Private commissions can only be accessed by:
* Commission members with self-service access.
* Roles assigned directly on the private commission.
* Unconstrained roles that have not been restricted to public commissions.

After you classify a commission as private on the **Maintain Commission Definition** task, if you do nothing, unconstrained roles will have access to both public and private commissions.

We provide the *Commission - Public* security segment to help you easily control unconstrained role holders' access to private commissions. To restrict unconstrained role holders to public commissions only, you remove access to private commissions. To do this, create a segment-based security group for the public commission unconstrained security group and assign access rights to the *Commission - Public* security segment.

Example: Create 2 unconstrained Commission Administrator roles:
* Commission Administrator (access to both private and public commissions).
* Commission Administrator – Public (has the *Commission - Public* segment assigned to restrict access to public commissions only).
