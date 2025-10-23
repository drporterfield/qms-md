# MDI 15.03 Firmware Installation Work Instruction

<!-- Macro: :box:([^:]+):([^:]*):(.+):
     Template: ac:box
     Icon: true
     Name: ${1}
     Title: ${2}
     Body: ${3} -->

<!-- :box:info::Foobar:
:box:tip:Tip of day:Foobar:
:box:note::Foobar:
:box:warning:Alert!:Foobar: -->

<!-- Include: ac:toc -->

## 1 Scope

This work instruction is scoped to include how to download, verify the correct download, compilation, and flashing of the STM32 and MAX32660 microcontrollers on the MDI 15.03 prototype hardware with firmware. How to ensure you have properly configured and functional tools or equipment, how to set the bootloader pin necessary for remote flashing the firmware, and how to verify proper functionality of the final device is discussed elsewhere.

This work instruction applies to the MDI 15.03 Production Version Numbers, and describes tools and equipment available at BridgeSource Medical Corp headquarters, 3301 Northland Dr. Suite 214, Austin, TX 78731.

## 2 Purpose

The purpose of this production process is to describe how to download, verify download, compile, and flash the STM32 microcontroller on the MDI 14.XX prototype with production firmware.

## 3 Definitions

- Ref. 3000 Terms and Definitions Rev. 2
- Ref. 3004 MDI Terms and Definitions Rev. 2

## 4 References

- 3017 MDI Prototype 14.XX Hardware Assembly Work Instruction
- 4009 Equipment Log Rev. 3
- 4035 MDI Firmware Changelog Rev. 2

## 5 Requirements

### 5.1 Software  

|Software|Version/description|
|---|---|
|[git](https://git-scm.com/)|Used for version management. Version 2.50.1 was used to prepare instructions.|
|DesignPlex repositories hosted on [Bitbucket](https://bitbucket.org/)|Production firmware on main branch.|
|[repo](https://bitbucket.org/designplexbiomedical/xavier_production/src/main/)|The link to the production branch of firmware.|
|[IAR Embedded Workbench](https://www.iar.com/embedded-development-tools/iar-embedded-workbench)|Integrated Development Environment including toolchain.|
|[VS Code](https://code.visualstudio.com/)|Optional: For developing off-Windows, or for flashing production firmware with no development.|
|[Segger J-Link Software](https://www.segger.com/downloads/jlink/)|Software to use the Segger J-Link Plus EQ-010|

Git hashes corresponding to specific PVNs can be found in 4035 MDI Firmware Changelog.

### 5.2 Tools and Equipment

|Equipment ID|Description|
|---|---|
|EQ-010|Segger J-Link probe. Used to flash and debug firmware.|
||Windows Computer capable of running software as detailed in the [Software](#51-software) section|
||Assembled MDI production board with case unscrewed and programming header exposed.|

### 5.3 Roles, Responsibilities, and Authorities

The following are the roles and assigned responsibilities for the MDI project.

|Role|Responsibility|
|---|---|
|Engineering|Create and deploy the released build onto the target hardware|

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

### 6.2 Download and verify the STM32 firmware and associated libraries

### 6.3 Build, flash, and debug STM32 device firmware

### 6.4 Inspection

### 6.5 Product handling

## 7 Change History

## 8 Attachments

NOT CONTROLLED WHEN PRINTED

CONFIDENTIAL
