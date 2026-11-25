# Role & Permission Matrix

## Purpose

This document defines the proposed responsibilities and access boundaries for the five primary user roles identified in the Digital Media CMS case study.

The matrix is a product-analysis artifact. Permissions are proposed for the fictional case study and should be validated with editorial, product, and security stakeholders before implementation.

## Role Definitions

| Role | Primary responsibility |
|---|---|
| Journalist / Editor | Create and maintain content drafts and submit them for editorial review. |
| Section Editor | Review content, provide feedback, request changes, and approve eligible submissions. |
| Publisher | Schedule and publish approved content to configured channels. |
| SEO Specialist | Maintain and validate search-discovery metadata for content. |
| CMS Administrator | Manage user accounts, roles, and permissions. |

## Permission Matrix

| Capability | Journalist / Editor | Section Editor | Publisher | SEO Specialist | CMS Administrator |
|---|---:|---:|---:|---:|---:|
| Create content draft | Yes | Yes* | No | No | No |
| Edit own draft | Yes | Yes* | No | No | No |
| View assigned / permitted content | Yes | Yes | Yes | Yes | No** |
| Submit content for review | Yes | Yes* | No | No | No |
| Review submitted content | No | Yes | No | No | No |
| Add editorial comments | No | Yes | No | No | No |
| Request changes | No | Yes | No | No | No |
| Approve content | No | Yes | No | No | No |
| Manage SEO metadata | No | No | No | Yes | No |
| Validate SEO metadata | No | No | No | Yes | No |
| Schedule approved content | No | No | Yes | No | No |
| Publish approved content | No | No | Yes | No | No |
| Unpublish / withdraw content | No | No | Yes* | No | No |
| Manage users and roles | No | No | No | No | Yes |
| Manage permissions | No | No | No | No | Yes |

* Proposed permission; scope and conditions require stakeholder validation. Section Editor authoring is limited to permitted content and should not bypass the review policy. Unpublishing requires an authorized action and a recorded reason.

** The administrator's operational access to content is intentionally not assumed. Technical support or exceptional access, if required, should be separately governed and audited.

## Core Access Rules

1. Permissions are enforced by the CMS API, not only by hiding user-interface controls.
2. Users receive the minimum permissions required for their responsibilities (least privilege).
3. Only an authorized Section Editor can approve content in the editorial review stage.
4. Only approved content can be scheduled or published in the standard workflow.
5. SEO Specialists can maintain SEO metadata but cannot approve or publish content solely by virtue of that role.
6. User and permission changes are restricted to the CMS Administrator role and recorded in the audit trail.
7. Access to content is additionally constrained by assignment, ownership, or section scope where applicable.

## Validation Items

- Confirm whether Section Editors can create content or only review and approve it.
- Define whether SEO Specialists can edit metadata on all content or only assigned sections.
- Confirm whether Publishers can unpublish content directly and which approval, if any, is required.
- Define whether CMS Administrators need exceptional read access for support purposes.
- Confirm the exact scope of content visibility for each role.
