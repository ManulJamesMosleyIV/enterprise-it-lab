# Engineering File Share Design

## Overview

This document defines the access model for the Engineering shared drive at Mosley Technologies.

The design uses role groups and resource permission groups to keep access scalable and aligned with least privilege.

## Shared Resource

Engineering shared drive:

\\fileserver\engineering

## Role Groups

### Software Engineers

Group:

GG-Engineering-SoftwareEngineers

Required access:
- Modify

Why:
- Software Engineers need Modify access so they can create, edit, and delete files required for their day-to-day engineering work without receiving unnecessary administrative control over permissions.

### Engineering Managers

Group:

GG-Engineering-Managers

Required access:
- Modify

Why:
- Engineering Managers need Modify access so they can create, edit, and manage departmental files without receiving unnecessary administrative control over permissions.

### Engineering Interns

Group:

GG-Engineering-Interns

Required access:
- Read

Why:
- Engineering Interns receive Read access by default to follow least privilege and reduce the risk of accidental changes or deletion. Additional access can be granted if their responsibilities require it.

### IT File Administrators

Group:

GG-IT-FileAdmins

Required access:
- Full Control

Why:
- IT File Administrators receive Full Control because they are responsible for managing permissions, ownership, access issues, and administration of the shared resource.

## Resource Permission Groups

DL-Engineering-SharedDrive-Read
DL-Engineering-SharedDrive-Modify
DL-Engineering-SharedDrive-FullControl

## Group Mapping

GG-Engineering-Interns
        ↓
DL-Engineering-SharedDrive-Read
        ↓
Engineering Shared Drive

GG-Engineering-SoftwareEngineers
        ↓
DL-Engineering-SharedDrive-Modify
        ↓
Engineering Shared Drive

GG-Engineering-Managers
        ↓
DL-Engineering-SharedDrive-Modify
        ↓
Engineering Shared Drive

GG-IT-FileAdmins
        ↓
DL-Engineering-SharedDrive-FullControl
        ↓
Engineering Shared Drive

## Permission Strategy

The environment avoids assigning file permissions directly to individual users.

Instead:

User
↓
Role Group
↓
Resource Permission Group
↓
Shared Resource

Why this model is used:
- Auditable because access can be traced through group membership.
- Scalable because new users can be added to existing groups instead of receiving individual permissions.
- Consistent because users in the same role receive the same access model.

## Least Privilege

Full Control is reserved for:
- IT File Administrators or specifically approved administrators.

Business users receive:
- Read or Modify access based on job responsibilities.

## Permission Inheritance

The root Engineering shared drive uses inherited permissions where appropriate.

Sensitive subfolders may have inheritance changed when a smaller group of users requires access.

Example:

Engineering
├── Projects
├── Documentation
└── Restricted

A restricted folder may use separate security groups instead of inheriting all Engineering permissions.

## Troubleshooting Considerations

If a user cannot access the shared drive, check:

1. Verify the user is in the correct role group, such as GG-Engineering-SoftwareEngineers.
2. Verify the role group is nested into the correct resource permission group.
3. Check the share and NTFS permissions on the Engineering shared drive.
4. Check for inheritance issues, explicit Deny permissions, or conflicting group memberships.
5. If group membership was recently changed, refresh the user session and test access again.
