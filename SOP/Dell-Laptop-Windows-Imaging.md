# Windows Imaging Process for Dell Laptops and Desktops

**Version:** 1.2  
**Author:** Molly Richardson  

---

## 1. Purpose

This Standard Operating Procedure (SOP) outlines the complete procedure for preparing, configuring, and imaging Dell laptops and desktops in an enterprise environment. It includes BIOS/UEFI configuration, network boot preparation, disk provisioning, Windows imaging, and new-device network registration.

## 2. Scope

Applies to all Dell equipment being deployed or reimaged in an organization using centralized PXE boot and enterprise Windows imaging tools.

## 3. Roles & Responsibilities

* **IT Support Technician:** Performs BIOS configuration, network setup, and imaging.
* **Network Administrator:** Manages device network authorization and VLAN assignments.
* **System Administrator:** Maintains the imaging server and approves image selections.

## 4. Prerequisites

Before starting, ensure you have:

* A new or existing Dell system requiring imaging
* Access to BIOS/UEFI settings
* Access to organizational network-access control (NAC) / MAC-registration portal
* Assigned static or DHCP reservation IP (if required)
* Cabled Ethernet or USB-C Ethernet adapter
* Access to PXE imaging network
* Approved Windows enterprise image
* Computer naming convention
* Asset number and location information
* Firmware package available if updates are required

---

## 5. Procedure

<Steps>
  <Step title="Enter BIOS Setup" subtitle="Prerequisite">

1. Power on the device.
2. Press **F2** to open BIOS/UEFI configuration.
3. *Verification:* Confirm the BIOS/UEFI main configuration menu loads successfully.

  </Step>

  <Step title="Configure Boot Settings">

Navigate through the BIOS menu and configure the following parameters:

* **General > Boot Sequence:**
  * **Windows Boot Manager:** **ON** (Enabled)
  * **Onboard NIC (IPv4):** **ON** (Enabled)

* **General > Advanced Boot Options:**
  * **Enable Legacy Option ROMs:** **OFF** (Disabled)

* **General > UEFI Boot Path Security:**
  * Set to `Always, Except Internal HDD`

* **General > Date/Time:**
  * Set to current date and local timezone.

*Verification:* Review the Boot Sequence list to ensure `Windows Boot Manager` and `Onboard NIC (IPv4)` are checked, and Legacy Option ROMs is unchecked.

  </Step>

  <Step title="Configure System Setup & Drives">

* **System Configuration > Integrated NIC:**
  * **Enable UEFI Network Stack:** **ON** (Checked / Enabled)
  * **NIC Mode:** Set to **Enabled w/ PXE**

* **System Configuration > SATA Operation:**
  * Set to **AHCI**

* **System Configuration > Drives:**
  * **M.2 PCIe SSD (Primary OS Drive):** **ON** (Enabled)
  * **All other drives (SATA/Secondary):** **OFF** (Disabled)

* **System Configuration > Thunderbolt Adapter Configuration:**
  * **Enable Thunderbolt Technology Support:** **ON** (Enabled)
  * **Enable Thunderbolt Adapter Boot Support:** **ON** (Enabled)
  * **Enable Thunderbolt Adapter Pre-boot Modules:** **ON** (Enabled)
  * **Security Level:** Set to **No Security**
    *(Note: Required when imaging laptops using a USB-C to Ethernet adapter).*

*Verification:* Verify SATA Operation shows AHCI selected and UEFI Network Stack is checked.

  </Step>

  <Step title="Configure Security Settings">

* **Security > UEFI Capsule Firmware Updates:**
  * **Disable:** **OFF** (Disabled), unless organization mandates automated firmware updates.

* **Security > TPM 2.0 Security:**
  * **TPM On:** **ON** (Enabled)
  * **PPI Bypass for Enable Commands:** **ON** (Enabled)

* **Security > Microsoft UEFI CA Key:**
  * **Enable:** **ON** (Enabled)

* **Security > Secure Boot Enable:**
  * **OFF** (Temporarily Disabled during imaging if required by your PXE environment; re-enable post-image).

*Verification:* Ensure TPM On is checked and Secure Boot is toggled off for the initial imaging workflow.

  </Step>

  <Step title="Configure Intel SGX Settings">

* **Intel SGX Settings:**
  * **Enable Intel SGX:** **ON** (Enabled)
  * **Enclave Memory Size:** Set to **128MB**

*Verification:* Confirm Intel SGX status displays as Enabled.

  </Step>

  <Step title="Configure Power Management Settings">

* **Power Management:**
  * **Wake on AC:** **ON** (Enabled)
  * **AC Recovery:** Set to **Power On**
  * **Auto On Time:** Set to **Every Day**
  * **Wireless Radio Control:** Set to **Control WLAN Radio**
  * **Deep Sleep Control:** **OFF** (Disabled)
  * **Wake on LAN/WAN:** Set to **LAN or WLAN**
  * **Block Sleep:** **ON** (Enabled)
  * **Type-C Connector Power:** Set to **7.5 Watts**

*Verification:* Confirm Deep Sleep Control is set to Disabled and Wake on LAN is active.

  </Step>

  <Step title="Configure Virtualization Settings">

* **Virtualization Support:**
  * **Intel Virtualization Technology:** **ON** (Enabled)
  * **VT for Direct I/O (Trusted Execution):** **ON** (Enabled)

*Verification:* Verify both virtualization checkboxes remain checked.

  </Step>

  <Step title="Apply BIOS Changes">

1. Click **Apply** at the bottom of the screen to save changes.
2. Click **Exit** to reboot the machine.

*Verification:* Machine reboots without displaying BIOS setup error prompts.

  </Step>

  <Step title="Register Device in Network Authorization System (NAC)">

If imaging a new laptop or desktop, add it to the organization's device-authorization tool:

1. **Access NAC/MAC-Registration Portal:** Log into the network device-authorization tool using admin credentials and select **Add or Update MAC**.

2. **Enter Device Information:**
   * **Service Area / Department:** Select deployment region or organizational unit.
   * **Site Code / Location:** Select building or deployment site.
   * **MAC Address:** Enter MAC address printed on device or retrieved from BIOS.
   * **Identity Group / Device Type:** Choose **Workstation** or **Laptop**.
   * **VLAN Assignment:** Choose the designated **Computer Imaging VLAN**.

3. **Review & Submit:** Submit entry and allow time for policy propagation.

*Verification:* Reboot device and confirm it receives an IP address and PXE boot prompt over the network.

  </Step>

  <Step title="Initiate PXE Boot">

1. Restart the system.
2. Press **F12** to enter the Boot Options menu.
3. Select boot media:
   * **Onboard NIC (IPv4)** for onboard Ethernet cable imaging.
   * **USB NIC (IPv4)** for USB-C adapter imaging.
4. Press **ENTER** when prompted to load the WinPE/PXE imaging environment.

*Verification:* System successfully boots into the network imaging environment screen.

  </Step>

  <Step title="Perform Disk Preparation">

1. Press **F8** within the imaging environment to launch the Command Prompt window.
2. Run the following commands sequentially:

   ```cmd
   diskpart
   select disk 0
   clean
   convert gpt
   exit
   exit

   
##  Select and Deploy Image

1. Choose the correct enterprise Windows image.
2. Select the organizational region, business unit, or site (genericized).
3. Enter the computer name using the standard naming convention:
   - Example: `[Location]-LT-[Asset#]`
4. Confirm the selected options.
5. Start the imaging process.

## Acceptance Criteria

Imaging is considered successful when all of the following are verified:

- [ ] Device boots cleanly into Windows.
- [ ] Correct enterprise image loads with no post-install errors.
- [ ] Device is authorized on the network.
- [ ] Secure Boot and TPM settings match organizational policy.
- [ ] Computer naming convention is applied correctly.
- [ ] Device appears in required asset/inventory systems.
- [ ] NIC functions properly through wired Ethernet or USB-C.


