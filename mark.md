# 3019 MDI 15.XX Firmware Installation Work Instruction

<!-- Macro: :box:([^:]+):([^:]*):(.+):
     Template: ac:box
     Icon: true
     Name: ${1}
     Title: ${2}
     Body: ${3} -->

<!-- Macro: \!\[.*\]\((.+)\)\<\!\-\- width=(.*) \-\-\>
     Template: ac:image
     Attachment: ${1}
     Width: ${2} -->

<!-- :box:info::Foobar:
:box:tip:Tip of day:Foobar:
:box:note::Foobar:
:box:warning:Alert!:Foobar: -->

<!-- Include: ac:toc -->

## 1 Scope

This work instruction is scoped to include downloading, compilation, and flashing of the STM32 microcontrollers on the MDI 15.XX prototype hardware with firmware (15.03 is used in examples). How to ensure you have properly configured and functional tools or equipment, how to set the bootloader pin necessary for remote flashing the firmware, and how to verify proper functionality of the final device is discussed elsewhere.

This work instruction applies to the MDI 15.XX Production Version Numbers, and describes tools and equipment available at BridgeSource Medical Corp headquarters, 3301 Northland Dr. Suite 214, Austin, TX 78731.

## 2 Purpose

The purpose of this production process is to describe how to download, verify download, compile, and flash the STM32 microcontroller on the MDI 15.XX prototype with production firmware.

## 3 Definitions

- Ref. 3000 Terms and Definitions Rev. 2
- Ref. 3004 MDI Terms and Definitions Rev. 2

## 4 References

- 3017 MDI Prototype 15.XX Hardware Assembly Work Instruction
- 4009 Equipment Log Rev. 3
- 4035 MDI Firmware Changelog Rev. 2

## 5 Requirements

### 5.1 Software  

|Software|Version/description|
|---|---|
|[git](https://git-scm.com/)|Used for version management. Many different clients exist, but Git Bash for Windows v. 3.7.7. was used to prepare instructions.|
|DesignPlex repositories hosted on [Bitbucket](https://bitbucket.org/)|Production firmware on main branch.|
|[repo](https://bitbucket.org/designplexbiomedical/xavier_production/src/main/)|The link to the production branch of firmware.|
|[IAR Embedded Workbench](https://www.iar.com/embedded-development-tools/iar-embedded-workbench)|Integrated Development Environment including toolchain. Version 9.60.3 was used to prepare instructions.|
|[VS Code](https://code.visualstudio.com/)|Optional: For developing off-Windows, or for flashing production firmware with no development.|
|[Segger J-Link Software](https://www.segger.com/downloads/jlink/)|Software to use the Segger J-Link Plus EQ-010|

Git hashes corresponding to specific PVNs can be found in 4035 MDI Firmware Changelog.

### 5.2 Tools and Equipment

|Equipment ID|Description|
|---|---|
|EQ-010|Segger J-Link probe. Used to flash and debug firmware.|
|70-00021|Rev. E MDI PCBA, Xavier|
|98-00127|Rev. A Battery Assembly, Xavier|
|99-00045|Rev. A MDI Assembly|
|G00279|Rev. 0 Test Fixture, Xavier|
||Windows Computer capable of running software as detailed in the [Software](#51-software) section|

### 5.3 Roles, Responsibilities, and Authorities

The following are the roles and assigned responsibilities for the MDI project.

|Role|Responsibility|
|---|---|
|Engineering|Create and deploy the released build onto the target hardware|
|Quality Assurance|Ensure that the released build follows a documented and repeatable process for maintaining consistent deployment. Assist in establishing traceability and documentation for build processes.|
|Project Lead|Give final approval for release of flashed hardware.|

### 5.4 Environment and Facilities

These procedures assume an electrical engineer’s workbench with a non-conducting top is being used, similar to those at BridgeSource Medical Headquarters. Standard mains power for the computer is recommended but not essential for laptop devices.

## 6 Process Steps

These procedures assume an electrical engineer’s workbench with a non-conducting top is being used, similar to those at BridgeSource Medical Headquarters. Standard mains power for the computer is recommended but not essential for laptop devices.

The steps required to flash the MDI device firmware to each microcontroller are:

1. Setup
2. Download and verify the STM32 firmware and associated libraries
3. Build, flash, and debug STM32 device firmware
4. Inspection
5. Product handling

These steps are repeated for each MDI device in sequence.

### 6.1 Setup

Ensure the equipment in the tools and equipment list is available and have been set up per their tooling specification.

### 6.2 Download and verify the STM32 firmware and associated libraries

|Instructions|Images|
|---|---|
|Navigate to the Xavier Repository at [Bitbucket](https://bitbucket.org/designplexbiomedical/xavier_production/) in your favorite browser. This repository requires access rights granted by DesignPlex Biomedical.|![DesignPlex Biomedical Repository](/screenshots/120719.png) |
|Find the tag of the commit you would like to install on the MDI.|![Tag location 15.03](/screenshots/111703.png) |
|checkout the proper tag in the development machine using Git Bash (this example uses version 3.7.7). To accomplish this, type `git checkout 15.03` in the chosen directory (here we choose `~/repos/xavier-production-1`).|![Check out software](/screenshots/112105.png) |
|Open IAR Workbench (Here we use v. 9.60.3). Go to `File > Open Workspace` |![IAR Workbench Load Project](/screenshots/112405.png) |
|Navigate to Project.eww (the project file). Here it has a logo of IAR Workbench. This will load all of the code into the workspace.|![Project File *.eww](/screenshots/112552.png) |
|Configure the project to use the J-Link, by navigating to `Project > Options` |![Project>Options then J-link](/screenshots/113000.png) |

### 6.3 Build, flash, and debug STM32 device firmware

|Instructions|Images|
|---|---|
|Connect the J-link to the test unit and to the computer. Ensure both are receiving power by confirming there are two green lights are on. You may need to depress the button on the MDI to get the power on the MDI to turn on. ||
|Build and Flash the firmware. This button both compiles, and loads the firmware on the MDI if properly referenced in the [Download](#62-download-and-verify-the-stm32-firmware-and-associated-libraries) section.|![Build and Flash](/screenshots/113243.png) |
|Stop the debugging process. This simply exits the debugger. Now everything can be unplugged, and the MDI firmware is loaded and ready for testing.|![Stop](/screenshots/113538.png) |

### 6.4 Inspection

Inspection procedures will vary depending on the version of the firmware installed. Expected behavior should be confirmed.

### 6.5 Product handling

This work instruction is for use on prototype devices and production devices. For all production devices, a record will be made of the serial number of each prototype MDI device and the firmware installed upon it. Because development devices may require rapid iteration, documentation of installation of firmware versions on board hardware is only required for formal testing, or for production devices.

## 7 Change History

|Revision|Revision Description|Effective On|Approved By|Date|
|---|---|---|---|---|
|1|||QA, Project Lead, Software Lead||

## 8 Attachments

NOT CONTROLLED WHEN PRINTED

<div style="text-align: right;">
CONFIDENTIAL
</div>
