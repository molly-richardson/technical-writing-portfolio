# Troubleshooting a Missing or Inaccessible Network Drive

**Document Type:** Knowledge Base Article (KB)  
**Author:** Molly Richardson  
**Status:** Portfolio Sample — Sanitized

> **Portfolio Disclaimer:** This document has been sanitized for portfolio use. Organization-specific names, server names, network paths, credentials, and other internal details have been generalized or omitted.

## Purpose

This knowledge base article provides a structured approach for troubleshooting missing or inaccessible network drives in a Windows enterprise environment.

The procedures cover several common scenarios, including users who previously had access but can no longer connect, users who require access to an existing network drive, access-denied errors, and mapped drives that fail to reconnect after a restart.

## Common Scenarios

This article addresses the following situations:

1. A user previously had access to a network drive but can no longer access it.
2. A user needs access to an existing network drive.
3. A user receives an "Access Denied" message.
4. Other users can access the drive, but one user cannot.
5. A mapped drive disappears after a restart.

---

# 1. User Previously Had Access but Can No Longer Connect

If a user previously accessed the network drive successfully, first determine whether the problem is related to connectivity, authentication, permissions, or the drive mapping.

## Troubleshooting Steps

### Verify Network Connectivity

Confirm that the workstation is connected to the appropriate network.

If the user is working remotely, verify that the required VPN or remote network connection is active.

### Check the Existing Drive Mapping

Open Command Prompt and run:

```text
net use
