
#Windows Imaging SOP

```markdown
# Windows Imaging Process for Dell Laptops and Desktops

**Document Type:** Standard Operating Procedure (SOP)  
**Version:** 1.2  
**Author:** Molly Richardson  
**Status:** Portfolio Sample — Sanitized

> **Portfolio Disclaimer:** This document has been sanitized for portfolio use. Organization-specific names, credentials, network information, addresses, internal procedures, and other identifying details have been generalized or omitted.

## Purpose

This Standard Operating Procedure (SOP) provides a structured process for preparing, configuring, and imaging Dell laptops and desktops in an enterprise environment.

The procedure covers BIOS/UEFI preparation, network configuration, PXE boot, disk preparation, Windows deployment, network authorization, post-image verification, and device handoff.

## Scope

This procedure applies to approved Dell laptops and desktops that require enterprise Windows imaging through a centralized network deployment process.

The procedure includes:

- BIOS/UEFI configuration
- Network and PXE preparation
- Network access control registration
- Disk preparation
- Enterprise Windows imaging
- Device naming
- Post-image configuration and verification
- Troubleshooting
- Documentation and handoff

> **Note:** BIOS/UEFI options and names vary by Dell model and organizational configuration. Follow current organizational deployment standards when configuring settings.

## Roles and Responsibilities

### IT Support Technician

Responsible for:

- Preparing the device
- Configuring required BIOS/UEFI settings
- Registering the device for network access
- Initiating PXE imaging
- Preparing the disk
- Selecting the appropriate enterprise image
- Performing post-image validation
- Documenting the completed deployment

### Network Administrator

Responsible for:

- Network authorization
- NAC registration
- VLAN configuration
- Connectivity
- Network-related troubleshooting

### System Administrator

Responsible for:

- Enterprise Windows images
- Deployment infrastructure
- Image availability
- System-level configuration requirements

## Prerequisites

Before beginning imaging, verify that the following are available:

- Approved Dell laptop or desktop
- Administrative access to BIOS/UEFI
- Device MAC address
- Access to the approved network registration system
- Appropriate imaging network
- Ethernet connection or approved USB-C Ethernet adapter
- PXE-enabled network connection
- Approved enterprise Windows image
- Device naming convention
- Asset information
- Device location
- Required firmware
- Required deployment documentation

---

# Procedure

## 1. Enter BIOS/UEFI

1. Power on the Dell device.
2. Press `F2` during startup to enter BIOS/UEFI configuration.
3. Allow the BIOS/UEFI interface to load completely.

## 2. Configure Boot Settings

Verify the boot configuration according to the organization's approved imaging standard.

Common settings may include:

- Windows Boot Manager
- Onboard NIC IPv4
- UEFI boot mode
- Legacy Option ROMs disabled
- UEFI Boot Path Security configured according to organizational policy
- Correct system date and time

Do not change settings that are not required for the approved deployment process.

## 3. Configure System Settings

Verify applicable system settings, including:

- UEFI Network Stack enabled
- Integrated NIC enabled
- PXE capability enabled
- SATA configuration according to the approved image requirements
- M.2 PCIe SSD detected
- Thunderbolt or USB-C settings configured according to the approved imaging process

Hardware and BIOS options vary by model. Follow current deployment standards for the specific device.

## 4. Configure Security Settings

Verify required security settings according to organizational policy.

Depending on the approved imaging process, settings may include:

- TPM enabled
- Secure Boot temporarily disabled if required for imaging
- Microsoft UEFI CA enabled
- Required UEFI security options configured
- UEFI Capsule Firmware Updates configured according to policy

> **Security Note:** Secure Boot and other security controls should only be changed when required by the approved imaging process. Re-enable required security controls after imaging.

## 5. Configure Additional Hardware Settings

Verify applicable settings required by the enterprise deployment process.

These may include:

- Intel SGX
- Power recovery settings
- Wake on AC
- AC recovery
- Auto On Time
- WLAN radio
- Deep Sleep
- Wake on LAN/WAN
- Sleep settings
- USB-C power settings
- Intel Virtualization Technology
- Trusted Execution

Only configure settings required by the organization's approved device standard.

## 6. Apply BIOS/UEFI Changes

1. Review the configuration.
2. Confirm that required settings are correct.
3. Apply the changes.
4. Exit BIOS/UEFI.
5. Allow the system to restart.

## 7. Register the Device on the Network

Register the device through the organization's approved network access control system.

1. Open the network registration portal.
2. Select the applicable service area or site.
3. Enter the device MAC address.
4. Select the appropriate identity group.
5. Assign the approved imaging network or VLAN.
6. Submit the registration.
7. Allow the registration to propagate.

The device must be authorized on the appropriate network before PXE imaging can begin.

## 8. Initiate PXE Boot

1. Restart the device.
2. Press `F12` during startup to access the boot menu.
3. Select the appropriate network boot option, such as:
   - Onboard NIC IPv4
   - Approved USB NIC IPv4
4. Press `Enter`.
5. Confirm that the device reaches the enterprise deployment environment.

If PXE does not start, verify network connectivity, MAC registration, VLAN assignment, and network authorization.

## 9. Prepare the Disk

> **Warning:** The following command permanently removes data from the selected disk. Verify that the correct device is being prepared before running `clean`.

At the deployment environment command prompt, use the approved disk preparation procedure.

```text
diskpart
select disk 0
clean
convert gpt
exit
exit
