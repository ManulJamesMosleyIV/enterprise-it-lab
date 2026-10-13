# Employee Onboarding Process

## Overview

This document defines the standard onboarding process for new employees at Mosley Technologies.

The goal is to make onboarding consistent, secure, auditable, and scalable.

## Onboarding Inputs

Before IT begins onboarding, the following information should be confirmed:

- Employee name
- Department
- Job title
- Manager
- Start date
- Required applications
- Required shared resources
- Required device type
- Any special access requirements

## Identity Creation

Steps:

1. Create a user object in Active Directory for the employee.
2. Place the user object in the appropriate department OU.
3. Configure the employee's username, email/UPN, department, job title, manager, and initial account settings.

## Group and Access Assignment

Steps:

1. Add the employee to the appropriate role group based on department and job responsibilities.
2. Add the user to the correct shared-resource permission groups.
3. Assign standard application access groups such as Microsoft 365, Slack, and Zoom based on business requirements.

Access should be assigned through groups rather than directly to individual users whenever possible.

## Application Access

Steps:

1. Assign standard applications such as Microsoft 365, Slack, and Zoom based on company policy.
2. Assign department-specific applications based on the employee's responsibilities.
3. Verify the user can sign in successfully and confirm they only have the application roles and data access required for their job.

Sensitive applications, such as payroll or financial systems, may require additional approval before access is granted.

## Device Preparation

Steps:

1. Select and prepare an approved company device for the employee.
2. Enroll the device into the company MDM or endpoint management platform.
3. Apply operating system updates, security patches, and required device policies.
4. Join or register the device with the company identity environment and place the computer object in the appropriate department computer OU or device group.
5. Install required standard and department-specific applications.
6. Verify the employee can sign in successfully and access required applications and resources.

## Security Requirements

The device should have:

- A temporary password configured that requires the user to change it at first sign-in.
- Company EDR or antivirus successfully deployed and reporting healthy through the approved endpoint management policy.
- BitLocker enabled on Windows devices or FileVault enabled on macOS devices.
- Required security policies applied, including screen-lock timeout, firewall settings, and current operating system security updates.

## Validation Before Handoff

Before giving the device to the employee, IT should verify:

1. Confirm the correct device is assigned to the correct employee, especially when multiple onboardings are being prepared at the same time.
2. Verify the employee account is configured correctly and the user can sign in to the device.
3. Confirm the device is enrolled and actively checking in with the company MDM or endpoint management platform.
4. Verify required applications, security policies, group memberships, and device configurations have been applied correctly.
5. Confirm the user can access all required applications and resources while also verifying they do not have unnecessary or unauthorized access.

## Documentation

IT should document:

- The employee who was onboarded, including department, role, manager, and start date.
- The device assigned to the employee, including hostname and asset tag or serial number.
- The security groups, application groups, and shared-resource groups assigned to the user.
- The applications, licenses, and any special access or approved exceptions granted during onboarding.

## Example Employee

Name:
Maya Chen

Department:
Finance

Role:
Financial Analyst

Device:
Windows laptop

User OU:
Users > Finance

Computer OU:
Computers > Finance Computers

Assigned groups:

- GG-Finance-Analysts
- DL-Finance-SharedDrive-Modify
- GG-M365-Users
- GG-Slack-Users
- GG-Zoom-Users

Applications:

- Microsoft 365
- Slack
- Zoom
- Approved Finance applications based on job responsibilities

Shared resources:

- Finance Shared Drive with Modify access

Device policies:

- BitLocker enabled
- Company EDR/antivirus deployed
- Windows Firewall enabled
- Screen-lock policy applied
- Current Windows updates and security patches installed

## Onboarding Principle

The onboarding process follows this general workflow:

HR / Manager Request
        ↓
Create Identity
        ↓
Place User in Correct OU
        ↓
Assign Role and Access Groups
        ↓
Provision Applications
        ↓
Prepare and Enroll Device
        ↓
Apply Security Policies
        ↓
Validate Access
        ↓
Document and Hand Off

The onboarding process follows least privilege so employees receive the access required for their role without unnecessary administrative or resource permissions.
