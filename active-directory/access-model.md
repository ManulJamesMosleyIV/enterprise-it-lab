# Access Model

## Overview

This document defines how Mosley Technologies assigns access using role-based access control and least privilege.

## Engineering Roles

### Software Engineer

Normal access:
- GG-M365-Users
- GG-Slack-Users
- GG-Zoom-Users
- GG-GitHub-Users

Administrative access:
- None by default

Shared drive access:
- Engineering Shared Drive
- DL-Engineering-SharedDrive-Modify

### Engineering Manager

Normal access:
- GG-M365-Users
- GG-Slack-Users
- GG-Zoom-Users
- GG-GitHub-Users

Administrative access:
- None by default

Shared drive access:
- Engineering Shared Drive
- DL-Engineering-SharedDrive-Modify

### Engineering Intern

Normal access:
- GG-M365-Users
- GG-Slack-Users
- GG-Zoom-Users

Administrative access:
- None

Shared drive access:
- Engineering Shared Drive
- DL-Engineering-SharedDrive-Read

## IT Support Roles

### IT Support Technician

Normal access:
- GG-M365-Users
- GG-Slack-Users
- GG-Zoom-Users

Delegated administrative access:
- GG-M365-Support-Admins
- GG-Slack-Support-Admins
- GG-Zoom-Support-Admins

Restricted administrative access:
- No Full Admin access by default
- No Global Administrator access by default
- Elevated access requires business need and approval

## Access Principles

- Least privilege
- Group-based access
- No automatic full-admin access
- Administrative access requires business need and approval
- Access is reviewed when employees change roles
