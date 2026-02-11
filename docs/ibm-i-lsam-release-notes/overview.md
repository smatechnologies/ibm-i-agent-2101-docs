---
sidebar_label: 'Overview & Reader Notes'
---

# Overview & Reader Notes

These release notes include all enhancements and fixed issues and for the IBM i LSAM, versions:

- [Version 21.1 New Features](./version-21.1-new-features.md)
- [Version 21.1 Fixes](./version-21.1-fixes.md)

## Reader Notes

The term "LSAM" used in this documentation refers to "Local Schedule Activity Monitor." This is the Continuous software that is installed under IBM i to enable OpCon automation of IBM i and any jobs executing under this operating system. Continuous documentation also refers to this software as the OpCon "Agent" for the operating system.  The OpCon server application itself executes the SAM (Schedule Activity Monitor) that orchestrates scheduling and event response among many instances of Agents and Connectors.

References in this documentation to “LSAM PTFs” refer to software patches for the OpCon Agent for IBM i. These are separate from IBM's PTFs for the operating system, and they are not related. However, Continuous recommends that users should keep their IBM i PTFs current, updating them at least every six months (IBM provides quarterly updates to their PTFs). The following instructions are not related in any way to IBM i PTFs.

The IBM i LSAM was managed as a single version 04.00.03 for as many years as the Agent software was compiled over IBM i version V5R4. This version of the Agent introduced many fixes and enhancements, but all of those software improvements were carried forward into the LSAM versions 18.1 and 21.1.  LSAM version 04.00.03 is no longer supported by Continuous.  All clients of Continuous must be using LSAM Version 18.1, 21.1 or newer.  

Any clients who might still be using LSAM version 04.00.03 should contact Continuous Support for special assistance to successfully upgrade to a newer version of the agent.  The minimum IBM i operating system level supported for version 18.1 of the agent is i7.1 (V7R1), and for version 21.1 it is i7.2 (V7R2).

:::warning
IBM i LSAM Version 04.00.03 (or patch level 04.00.04) is no longer supported by Continuous. Any use of this software version will be at your own risk and that is certainly not recommended.  (See note above about requesting assistance from Continuous Support if your site is still using this unsupported software.)

IBM i LSAM Version 18.1 will no longer be updated with software fixes.  It is retired and is replaced by the newer LSAM version 21.1.  All clients still using this version are urged to upgrade to LSAM Version 21.1 as soon as possible, before this version cannot be physically supported by Continuous due to the evolution of the IBM i operating system.
:::

As of the publication of this document version, the current version of the IBM i LSAM was agent version 21.1. This version of the LSAM software was compiled over IBM i7.2.  (IBM only supports i7.2 under custom, extended support contracts.) Version 21.1 of the agent has been certified to operate correctly on currently supported versions of the IBM i operating system, through i7.5.  Continuous states its intention to soon certify this IBM i LSAM for IBM i version i7.6 (V7R6).

:::tip
New installs of the IBM i LSAM should use the install file named LI211043J (or newer LI211* file) install file.
:::

Clients performing LSAM PTF updates of existing IBM i LSAM installations should refer to "Managing LSAM Software Enhancements", begining at [Introduction to IBM i Agent Software Patches](lsam-ptf-readme.md).

## Continuous IBM i LSAM 21.1 Patches

Please be careful to distinguish between Continuous software patches for different versions of the IBM i LSAM. At Continuous' secure ftp server there are different sub-directories for all resources pertaining to each version. Although the LSAM PTF save file names are similar (LSCTLDTA and LSCUMPTF), they are NOT interchangeable, so it is important to verify that a site uses the latest available versions of these IBM i save files that are stored under the matching LSAM directory under the IBM i Agent release sub-directory IBMiLSAMptf.

Using the wrong LSAM PTF files for a version could corrupt the LSAM software and require a restoration from the most recent backup of the LSAM libraries. Continuous advises clients to always backup the LSAM libraries before attempting any patching or upgrading of the software.

Instructions for installing software patches (PTFs) to Continuous' IBM i LSAM may be found in two places. There is a stand-alone Installation documentation that explains partially manual procedures that may be necessary after an initial installation or upgrade of the LSAM. Detailed instructions and explanations are found just below at [Link to Detailed Instructions for LSAM Patch Installations](#link-to-detailed-instructions-for-lsam-patch-installation).

### Summary of LSAM Enhancements and Fixes

The release notes that follow this introduction include lists of the most recent batch of enhancements and patches available for application after the installation of the IBM i LSAM version 21.1. 

LSAM PTF numbers are assigned within the Continuous internal product management control tools. Support incidents are generated and tracked within Continuous' latest tracking systems, and the incident numbers are associated with the LSAM PTF numbers. There may be more than one support incident associated with a given PTF number. The LSAM PTF numbers assigned to enhancements are associated with the Continuous Development department's project tracking system.  The list of LSAM PTFs available from the LSAM menu system documents the connections with support incidents or product enhancement tasks via the detail records listed under each PTF master record.  Type option 7 next to any PTF master record to view the list of details, then notice the "Case ID" column at the far right of the list. These Case ID's are assigned within the Continuous Development JIRA project control system, and each of the JIRA tasks are linked to the Continuous Support incident tracking database.

### Link to Detailed Instructions for LSAM Patch Installation

Instructions for downloading and installing LSAM PTFs are found in a simple form in [Managing LSAM Software Enhancements](./lsam-ptf-readme#introduction-to-ibm-i-agent-software-patches), a topic below in this section. Clients should study the instructions under [Installing IBM i LSAM Patches](./lsam-ptf-readme#installing-ibm-i-lsam-patches) for additional CAUTIONS and other important instructions that may be added when new software patches are developed.

## Compatibility
This LSAM version is generally compatible with all supported releases of the OpCon central server application.  

One possible exception is that the IBM i LSAM's File Arrival job type might not have full support for every available parameter that defines these jobs, when the oldest OpCon server User Interface verions are still being used.  Details about methods available for engaging some important File Arrival job parameters are provided within the Commands and Utilities chapter, at discussions under the topic of [Introduction to IBM i File Arrival Jobs](/commands-utilities/file-arrival#introduction-to-ibm-i-file-arrival-jobs).