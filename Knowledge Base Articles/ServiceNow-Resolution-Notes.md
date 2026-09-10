# Writing Effective ServiceNow Resolution Notes

**Document Type:** Knowledge Base Article (KB)  
**Author:** Molly Richardson  
**Status:** Portfolio Sample — Sanitized

> **Portfolio Disclaimer:** This document has been sanitized for portfolio use. Names, dates, times, ticket numbers, device identifiers, locations, and other identifying information in the examples are fictional and do not represent an actual user or incident.

## Purpose

This article provides guidance for creating clear, detailed, and useful ServiceNow ticket documentation throughout the lifecycle of an IT support incident.

Effective ticket documentation should tell the complete story of an issue, from the initial report through troubleshooting, resolution, and user confirmation.

A well-documented ticket should allow another technician to understand:

- What the user reported
- Who and what was affected
- When the issue occurred
- What troubleshooting was performed
- What was discovered
- What action resolved the issue
- Whether the user confirmed the resolution

## Why Detailed Ticket Documentation Matters

ServiceNow tickets serve as a historical record of IT support activity. Clear documentation helps technicians understand what has already been attempted and prevents unnecessary repetition.

Detailed ticket notes can also:

- Support troubleshooting and escalation
- Provide continuity between technicians
- Establish an incident timeline
- Identify recurring hardware or software problems
- Support service reporting and metrics
- Document changes made to devices or systems
- Provide evidence of completed support activities
- Help future technicians resolve similar incidents

The goal is not simply to document that a ticket was "worked." The documentation should explain **what happened, what was done, and why the issue was considered resolved.**

---

# 1. Initial Ticket Update

The initial update establishes the starting point of the incident.

When creating or updating a ticket, capture as much relevant information as possible before troubleshooting begins.

## Information to Include

When available and appropriate, document:

- Date the issue was reported
- Time the issue was reported
- User's name or approved user identifier
- Department or organizational unit
- Work location
- Device name
- Asset number
- Device type and model
- Application, system, or hardware involved
- Description of the reported issue
- When the issue began
- Whether the issue is intermittent or constant
- Error messages
- Recent changes reported by the user
- Troubleshooting already performed
- Impact to the user's work

## Example Initial Update

```text
09/10/2026 08:14

User: Jane D. [fictionalized]
Department: Finance
Location: Building A, Room 214
Device: Dell Latitude 5440
Asset: LT-10452

User reports that the external keyboard and mouse connected to the laptop are not functioning.The issue began this morning after connecting the laptop to the docking station. Laptop display is functioning normally, but the user is unable to type or move the mouse using the connected peripherals. User reports that disconnecting and reconnecting the keyboard and mouse did not resolve the issue.

## Troubleshooting Timeline

09/10/2026 08:27 — Keyboard and mouse tested through the docking station. Issue persisted.

09/10/2026 08:31 — Keyboard and mouse connected directly to the laptop. Both peripherals functioned normally.

09/10/2026 08:34 — Testing isolated the issue to the docking station.

09/10/2026 08:45 — Docking station power-cycled and retested.

09/10/2026 08:52 — Issue persisted through the original docking station.

09/10/2026 09:02 — Original docking station replaced with an approved replacement unit.

09/10/2026 09:08 — Keyboard and mouse tested through the replacement docking station. Both functioned normally.

09/10/2026 09:12 — User confirmed the issue was resolved.


## Detailed Resolution Note

Brief Synopsis: User reported that the external keyboard and mouse connected to the laptop were not functioning.

Final Fix: Testing determined that the keyboard and mouse functioned normally when connected directly to the laptop but failed when connected through the docking station. The original docking station was replaced with an approved replacement unit. Keyboard and mouse functionality was restored through the replacement docking station.

Confirmation from User: User confirmed that the keyboard and mouse are functioning normally after the docking station was replaced. User confirmed they are able to type and use the mouse as expected. No additional issues were reported.
