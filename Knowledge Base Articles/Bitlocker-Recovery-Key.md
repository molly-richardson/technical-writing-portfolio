# Retrieve a BitLocker Recovery Key for a Windows 11 Device

**Document Type:** Knowledge Base Article (KB)  
**Author:** Molly Richardson  
**Status:** Portfolio Sample — Sanitized

> **Portfolio Disclaimer:** This document has been sanitized for portfolio use. Organization-specific names, credentials, device identifiers, and other internal details have been generalized or omitted.

## Purpose

This knowledge base article provides a step-by-step procedure for authorized IT administrators to retrieve a BitLocker recovery key for a Windows 11 device through Microsoft Entra ID.

The procedure covers identifying the affected device, locating the appropriate recovery information, verifying the recovery key, assisting with BitLocker recovery, and securely handling sensitive recovery information.

## When to Use This Procedure

Use this procedure when an authorized user is prompted for a BitLocker recovery key and the key must be retrieved from the organization's device management environment.

Common scenarios include:

- BitLocker recovery after a hardware or configuration change
- Recovery prompts during device startup
- Device recovery after certain security or firmware changes
- Authorized troubleshooting requiring BitLocker recovery

## Prerequisites

Before beginning, verify that:

- You are authorized to retrieve BitLocker recovery information.
- You have an approved administrative account.
- You have access to Microsoft Entra ID.
- The affected device can be identified by its device name or approved identifier.
- The user is available to provide the Recovery Key ID displayed on the BitLocker recovery screen.

---

# Procedure

## 1. Sign In to Microsoft Entra ID

1. Sign in to Microsoft Entra ID using an authorized administrative account.
2. Complete any required authentication.
3. Navigate to the organization's device management area.

Only use an account with the appropriate permissions to access BitLocker recovery information.

## 2. Locate the Affected Device

Search for the affected Windows 11 device.

Use an approved identifier such as:

- Device name
- Computer name
- Device ID
- Other approved device identifier

Verify that the device record corresponds to the user's affected computer before continuing.

## 3. Open the Device Record

Open the device record for the affected computer.

Review the available device information and confirm that the device is the correct system.

## 4. Locate BitLocker Recovery Information

Navigate to the BitLocker recovery information associated with the device.

Review the available recovery keys.

Multiple recovery keys may be associated with a device, so do not select a key based solely on the device name.

## 5. Verify the Recovery Key ID

Compare the Recovery Key ID shown in Microsoft Entra ID with the Recovery Key ID displayed on the user's BitLocker recovery screen.

The IDs must match before providing or entering the recovery key.

> **Important:** Do not provide or enter a recovery key unless the Recovery Key ID has been verified.

## 6. Provide or Enter the Recovery Key

Follow the organization's approved recovery procedure.

Depending on the support scenario, the authorized technician may:

- Enter the recovery key directly on the affected device
- Provide the key through an approved support process
- Guide the user through the recovery process

Do not transmit recovery keys through unauthorized communication methods.

## 7. Confirm Successful Recovery

After the recovery key is entered:

1. Confirm that the device successfully unlocks.
2. Allow Windows to start.
3. Verify that the user can sign in.
4. Confirm that the original issue requiring recovery has been addressed.
5. Document the recovery activity in the appropriate support ticket.

---

# Troubleshooting

## Device Cannot Be Found

Verify:

- Device name
- Device ID
- User-provided information
- Administrative permissions
- Device enrollment status

If the device cannot be located, follow the organization's approved escalation process.

## Recovery Key Is Not Available

Verify that:

- The correct device record was selected.
- The device has associated recovery information.
- The administrative account has the required permissions.
- The organization stores recovery information in the expected location.

Escalate when recovery information cannot be located through approved methods.

## Recovery Key ID Does Not Match

Do not use the key.

Recheck:

- Device identity
- Recovery Key ID
- Available recovery records
- User's BitLocker recovery screen

Using an incorrect recovery key may prevent successful recovery.

## Device Continues to Prompt for Recovery

If the correct recovery key was entered but the device continues to prompt for BitLocker recovery:

- Confirm the correct key was used.
- Verify the Recovery Key ID again.
- Document recent hardware or configuration changes.
- Check for additional recovery records.
- Follow the organization's approved escalation procedure.

---

# Security Considerations

BitLocker recovery keys are sensitive security information.

When handling recovery information:

- Use only authorized administrative accounts.
- Verify the affected device before retrieving a key.
- Verify the Recovery Key ID before using a key.
- Do not expose recovery keys unnecessarily.
- Do not store recovery keys in unapproved locations.
- Do not include full recovery keys in routine ticket notes unless explicitly required by organizational policy.
- Follow organizational requirements for protecting sensitive information.
- Use approved communication methods when providing recovery assistance.

---

# Resolution Checklist

Before completing the support request, verify:

- [ ] Correct device identified
- [ ] Authorized administrative access confirmed
- [ ] BitLocker recovery information located
- [ ] Recovery Key ID verified
- [ ] Correct recovery key used
- [ ] Device successfully unlocked
- [ ] Windows started successfully
- [ ] User confirmed access
- [ ] Recovery activity documented
- [ ] Sensitive recovery information handled according to policy

## Key Takeaway

The most important step when retrieving a BitLocker recovery key is **verifying the Recovery Key ID before using the key**.

A structured verification process helps ensure that the correct recovery information is used while protecting sensitive security data.
