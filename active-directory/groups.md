# Active Directory Group Design

## Overview

This document defines the security group structure for Mosley Technologies.

The goal is to use group-based access rather than assigning permissions directly to individual users.

This supports:

- Role-Based Access Control
- Least Privilege
- Easier onboarding
- Easier offboarding
- Cleaner internal transfers
- Better auditing

## Naming Convention

Global groups use:

GG-

Domain local resource groups use:

DL-

Examples:

GG-Engineering-Users

DL-Engineering-SharedDrive-Modify

## Engineering Groups

### Department Group

GG-Engineering-Users

Purpose:
Represents employees who belong to the Engineering department.

### Application Groups

GG-GitHub-Users

Purpose:
Provides GitHub access only to users who require it.

GG-M365-Users

Purpose:
Provides Microsoft 365 access.

GG-Slack-Users

Purpose:
Provides Slack access.

GG-Zoom-Users

Purpose:
Provides Zoom access.

## Shared Drive Groups

GG-Engineering-SharedDrive

Purpose:
Represents Engineering users who require access to the Engineering shared drive.

Resource permission groups:

DL-Engineering-SharedDrive-Read

DL-Engineering-SharedDrive-Modify

DL-Engineering-SharedDrive-FullControl

## Access Model

Example:

Jason Lee
↓
GG-Engineering-Users
↓
GG-Engineering-SharedDrive
↓
DL-Engineering-SharedDrive-Modify
↓
Engineering Shared Drive

## Least Privilege

Users should only receive access required for their role.

For example:

A Software Engineer may require GitHub access.

An Engineering Project Manager may not.

Therefore, GitHub access should be assigned through GG-GitHub-Users rather than automatically to every Engineering employee.
