# Active Directory OU Design

## Overview

This document defines the Organizational Unit structure for the Mosley Technologies enterprise lab.

The goal is to separate user and computer objects so policies, administration, and troubleshooting can be handled cleanly and at scale.

## Domain

```text
corp.mosleytech.com
corp.mosleytech.com

Users
├── IT
├── Finance
├── HR
├── Engineering
└── Operations

Computers
├── IT Computers
├── Finance Computers
├── HR Computers
├── Engineering Computers
└── Operations Computers
