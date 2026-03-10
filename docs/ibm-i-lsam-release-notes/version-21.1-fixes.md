---
sidebar_label: 'Version 21.1 Fixes'
---

# Version 21.1 Fixes

This topic shows a combined list of the LSAM fixes and enhancements that have been added to the OpCon Agent for IBM i since LSAM version 21.1 was released.  The enhancements listed here are the ones that were added to the LSAM version after it was published.  They are included with the fixes to help evaluate the status of an installed LSAM.

## IBM i LSAM 21.1 PTFs

The PTF Level is the value that clients and Continuous Support will use to confirm the software level of each LSAM installation.  View the PTF List display from LSAM menu 9, option 1, to identify the PTF Level of each PTF.  It may or may not be the same as the last three digits of the PTF Names shown in the following list.

### LSAM DB LVL # 21.1.003

- **Enhanced**: (# 211043) This PTF marks the end of software patches developed during beta site testing, and the initial version code of the first public release of the IBM i Agent version 21.1 at PTF level 043.

- Fixed: (# 211044)  The LSAM utility command LSAINIT was failing as sub-program LSARESETR issued error message ID CPF4131.  This program had not been recompiled over the new file layout for log file CMNLOGF10.

### LSAM DB LVL # 21.1.004

- Fixed: (# 211045)  The (revised) Client eMail log display was showing some fields with no labels.

- Fixed: (# 211046)  The Alternate Job Notify Configuration function was failing due to incorrect parameter management of the DTALIB value as program JOBNFYR30 was calling program JOBNFYC01.

- **Enhanced**: (# 211047) The (revised) Client eMail feature is upgraded with user prompting and better support for using either EDTIF or WRKMBRPDM to manage the optional email message text source members.

- **Enhanced**: (# 211048)  The model for a Dynamic Variable user-defined value calculator program has been updated to support a longer parameter that exchanges a variable’s value to/from the program. As of LSAM version 21.1 the variable value length has been increased from 128 bytes to 1024 bytes. For more details, view the LSAM PTF Post-Install Instructions.  User Help documentation has also been upgraded within the Client eMail feature.

- Fixed: (# 211049) The Dynamic Variable function code *DTAARA was not able to retrieve content from a job’s Local Data Area (LDA).  A special format for the *DTAARA function code definition is required in order to access the *LDA value.  Instructions about the correct format have been added to the secondary display where *DTAARA access is defined during LSAM menu-driven maintenance to Dynamic Variables.

- **Enhanced**: (# 211050) Type-L Dynamic Variables are updated to support an indirect interface with multi-instance variables.  The User Help for the IBM i Agent has a new subsection that outlines new capabilities for managing the Local Data Area, under the chapter about Dynamic Variables.  This PTF also improves the LSAM utility command DSPDYNVAR so that it can now display and test Type-L variables.  Type-L variables will always show a complete 1024 characters of LDA content that would be updated, including all variable master records that have the same variable name (usually a Job name) so that all sequence numbered records with that name will be included in the test display.

- **Enhanced**: (# 211051) LSAM messages in message file SMAMSGF are updated to support the PTF # 211050 enhancements to Type-L Dynamic Variables.

- Fixed: (# 211052) The LSAM log file LSALOGF40 that stores a history of job management transactions received from the OpCon server can reach its maximum number of log records that are supported by the LIDUNIQ key field that is limited to a size of 8 digits, in high volume environments.  The periodic database reorganization command (SMARGZ) is enhanced to backup this file (by renaming it) and then create a new, empty version of the file that can start over with a record ID value of 1.  No historical data that is normally retained by daily log purging will be lost, using this technique.

- **Enhanced**: (# 211053) Supporting the improvement implemented by PTF # 211052, the SMASUP command will now include the new backup file copy LSALOGF40B whenever Job Scheduler logs are requested for extract by this utility command.

- Fixed: (# 211054) Dynamic Variable maintenance of *DB2 and *DTAARA function codes showed an unsupported function key in the F-Key legend on line 23 of F4=Prompt.  F4 is now removed from line 23.

- Fixed: (# 211053) The special convention of using this External Event command: "$CONSOLE:DISPLAY,QCMD:" was not being executed when LSAM Message Management was configured to run Event commands in-line with all message management activity (instead of spawning a cmd job).

- Fixed: (# 211054) The LSAM menu 6, option 6, uses the WRKSMASVR command and program to support a user interface to the Agent tools for starting/stopping parts of the LSAM server jobs.  Option 6=STRGRP for JORS was not working to start that Group's server jobs.

- Fixed (# 211055) The special convention of using this External Event command: “$CONSOLE:DISPLAY,QCMD:" was not being executed when LSAM Message Management was configured to run Event commands in-line with all message management activity (instead of spawning a cmd job).

- Fixed (# 211056) The LSAM menu 6, option 6, uses the WRKSMASVR command and program to support a user interface to the Agent tools for starting/stopping parts of the LSAM server jobs.  Option 6=STRGRP for JORS was not working to start that Group's server jobs.

- **Enhanced** (# 211057, 211058) Add User Env Matrix utility control: A control data area (USRMTXCTL) will be present if the User Environment Matrix maintenance function is installed in an LSAM environment.  This function may be customized and the driver program name changed, depending on Continuous client site requirements.                                                    

    Fix Operator Replay menu opt # 12: A control data area (USRMTXCTL) will contain the custom maintenance program name for a User Environment Matrix feature that may be installed and customized for an Continuous client site.  PTF211058 adds the proposed DB files and fixes LSAM menu 4, option 12 name.

- Fixed (# 211059) Remove function key F7 from the Operator Replay master file maintenance display format OPRRPYR10-4B, since it is not supported from this display. 

- Fixed (# 211060) Operator Replay Screen Capture definitions display format OPRRPYR40R2 has the function keys F10 and F11 revised to perform as planned, in a standard fashion resembling other Agent functions that perform Data Capture.

- Fixed (# 211061) The Agent workstation prompting window for External Events was not producing correct results when requesting the XML raw format of commands via the CPYTOMSGIN wrapper command.

- Fixed (# 211062) The Message Management – message data capture rule maintenance needed to suppress the display of F10=Capture Application.

- Fixed (# 211063) The Message Management activity log program LSALOGR10 showed incorrect log entry content when F13 was pressed to view more data from the “Log Entry Text” field.

- Fixed (# 211064) The Operator Replay master file maintenance display format OPRRPYR10-R4 was not correctly supporting F8-DynVar to product a prompting list of registered variable names.

- Fixed (# 211065) The multi-purpose Captured Data display program got a spelling correction and an improvement in the flow when it was accessed using function key F10 to branch here from other programs.

- Fixed (# 211066) The Dynamic Variable maintenance function accessed from various locations among the LSAM workstation menus could cause a failure when returning from the Dynamic Variable selection window, usually if F3=Exit was pressed during some phases of he variable selection and formatting process.  (LSAVARR00:MCH1202 error @ F8=DynVar).

- **Enhanced** (# 211067) The GETCLTEML command, part of the Agent’s Client eMail generation feature, was expanded to support up to 435 characters when a command parameter could refer to a fully-qualified Dynamic Variable name.

### LSAM DB LVL # 21.1.005

- **Enhanced** (# 211068, 211069, 211070, 211071, 211072, 211074) a new Job Status monitor server program is added to the Agent software, replacing a function that IBM removed from its Navigator Monitors when the newer Navigator version was introduced.  The Agent’s new ability to monitor any IBM i subsystem for jobs that are stuck in a MSGW (message waiting) status provides a better implementation of this service, and it can still be combined with other Agent features to support alerts and, optionally, automated recovery functions.  Several Agent menu options and programs were enhanced to support this new, optional but standard, Agent server job named “JOBSTS.”

- **Enhanced** (# 211075) The Agent’s feature interconnection utility command, WAITDYNVAR, is enhanced to support value parameters up to the longer length of 1024 that matches the new extended capability of Dynamic Variable values introduced at Agent version 21.1.

- Fixed (# 211076) The Agent’s Job Scheduler communications program no longer sends a warning about a duplicate connection attempt if an OpCon server connection request comes from the same IP address as the Agent believes it was already connected to.  There are only local IBM i Agent communications log file entries that record the reconnection activity, and no longer any messages sent to the IBM i QSYSOPR message queue nor to the OpCon SAM Log.

- **Enhanced** (# 211077, 211078) The old, not-recommended Agent utility command SETCAPVAR is nevertheless upgraded to manage a fully-qualified Dynamic Variable name.  However, this command was not changed to support the improved Agent database normalization of Capture Application IDs, which are now keyed by the 9-digit APPKEY.  The SETCAPVAR command only supports the original method of using a 30-character App ID description field to link captured data from an Agent log file to store the captured value to a Dynamic Variable.  This action is better supported by the newest versions of the Agent’s Capture Data and Response Rules features.
PTF 211078 enhances this same SETCAPVAR command to support up to 435 characters for the Dynamic Variable name, in case a fully-qualified variable name is required for parallel processing.

- Fixed (# 211079) The Multi-Step Script driver program was failing with a false error code of “NoLVar” and error message text indicated that a Dynamic Variable for updating a job’s Local Data Area was not found.  This happened during the Multi-Step Job’s startup procedures, before Step processing started.  The fix ignores this return code, since it simply means that there are no Dynamic Variables available to update the Script job’s IBM i Local Data Area.

- Fixed (# 211080) Corrects the format of the IBM i Job ID character string reported via a variable in the message ID SMA5802.

### LSAM PTF release 21.1.123 (DB LVL # 21.1.005)

#### ENHANCEMENTS

**IBMI-495:** PTF211121  Add SMAFT log entry when job denied @ exceed MAX

Add messages that log when a connect request is rejected by the LSAM Job Scheduler as SMAFT Agents jobs would exceed the max allowed jobs.

**IBMI-892:** PTF211088  Add Operator Replay error report for MLTJOB script

An Operator Replay script can be executed from the Agent's Multi-Step Job Scripts, but previously the failure of the Operator Replay Script was not being reported to the OpCon server's job that started the Multi-Step Job Script execution. For more information, see the [Operator Replay user help](/operator-replay/additional-info#configuration-of-multi-step-scripts-for-sending-operator-replay-exit-codes-to-opcon-detailed-job-messages).

**IBMI-893:** PTF211097  Add 5 field codes to SM File Arrival job

The Solution Manager user interface for the IBM i File Arrival job sub-type is enhanced with 5 new fields that make it easy to specify frequently used job attributes.  These replace the difficult $@variables registration, though those are still supported.  This enhancement of the Solution Manager web application is available with OpCon version 22.3.1, and later versions.  
Please refer to the IBM i Agent User Help for information about the new SM data entry fields, and also an update to options for keeping or replacing the optional $@Variable names that previously provided support for these same five parameters.

**IBMI-890:** PTF211090   Display ID of Job Track control LSAM 

The pop-up window that reports the status of Job Tracking (active or inactive) showed a warning message when a different LSAM within the partition already had control of Job Tracking.  This window now shows the LSAM name and its SMAGPL library.

**IBMI-900:** PTF211107  Add "Display Data Capt App where used"

As of LSAM 21.1, Data Capture applications can be reused among multiple Operator Replay Script Steps and also among more than one Message Management Parameters records.  Changes to any Data Capture Rules or Response Rules will now warn about affecting any other OR Script or Msg Mgmt Parm record that share a Capture Application.  Inquiry lists of the Capture Applications now support an option to see every Step or Parameter that shares that same application.

**IBMI-936:** PTF211098  Update SMALOOKUP for File Arrival fields

An extract from the OpCon transaction field codes table SMALOOKUP is refreshed with new data that labels the File Arrival job fields added to the Solution Manager user interface, supporting LSAM detail displays of log file entries showing these fields.

**IBMI-952:**  PTF211117  Suppress false SMA0019 2nd connection attempt messages.

The LSAM communications program connected to the OpCon server will no longer send this message to the OpCon server's SAM log. This prevents a potential LSAM communication program loop that can block recovery of the connection to the OpCon server.

**IBMI-977:**  PTF211111  Removed an attempt to report SMA0019 (rejected 2nd connection attempt)

There is little or no use for attempting to add an error message to the SAM log of an OpCon server
That is not communicating with the IBM i Agent at the time when error SMA0019 is being handled.

**IBMI-978:**  PTF211114  Add LSAM utility command SMACMDDTL to report the PRDLIB value of a command

Some of the LSAM utility commands in the SMAGPL library are Control Language programs that need 
to know the SMAGPL library name.  They can now simply call this utility command to quickly fetch the library name.

**IBMI-978S:**  PTF211117  Add new data area SMAGPL/ENVIRONG to the LSAM object authority master file

The new data area SMAGPL/ENVIRONG holds the LSAM environment name, using the same value that has always been stored in SMADTA/ENVIRON.  This copy of that data supports LSAM utility commands to establish the LSAM library list when they have been called from outside of an LSAM environment.

**IBMI-979:**  PTF211112  Add the Response Rules Sequence number to lists of Response Rules.

The description of a Response Rule is not always helpful to identify the specific Rule that might
need maintenance.


#### FIXES

- Fixed (# 211087) IBMI-857:  Update LSAAUTF01 attribute (LSAM Object Authority master file) on type *MENU records with DSPF (display file).

- Fixed (# 211081) IBMI-868: The LSAM object reference utility command REFFLOW is improved with better optional (default) suppression of references to commonly used IBM i modules that have names beginning with the letter Q.  The new command option can be changed to 0 to show them.

- Fixed (# 211082)  IBMI-868: The SMAADDLIBL utility command was adding libraries to the correct position of an existing job's library list, but the order of the libraries added was the reverse of the library priorities registered in the LSAM environment management master file.

- Fixed (# 211083)  IBMI-868: The LSAM object reference tools supporting table PGMREF is updated with corrected and expanded data content.  This replacement fixes some omissions from the original Agent 21.1 release and it adds information from the latest LSAM PTFs as of 211083.

- Fixed (# 211084) IBMI-880: Operator Replay job start requests were being rejected in many cases with a false error SMA0108.  The Script Name was not being properly extracted by the LSAM Job Scheduler program.  Also, a diagnostic dump report from the script driver job is removed.

- Fixed (# 211085) IBMI-882: The Dynamic Variable master record inquiry routines show the wrong variable name in the function code details display (LSAVARR7) when the function code is *DTAARA. This happens only in Inquiry mode, but not Change or Copy modes.

- Fixed (# 211086) IBMI-883: The Multi-Step Script Step maintenance function was reporting a false "duplicate label not allowed" error when using option 2=Change to change a Step record but without changing the Label value.

- Fixed (# 211091) IBMI-895: The new JOBSTS Server Job reported a divide by zero error and another error reporting a receiver field too small. Improved LSAM control data for this new server job and also added a non-zero default value for the server to use at job initiation.

- Fixed (# 211089) IBMI-898: The Operator Replay Steps maintenance sometimes fails to link a selected Data Capture Rule to the Step record.  Also, after leaving the Select Capture Rule program with F3 or F12, the Operator Replay Step record Capt App ID text is blanked out.

- Fixed (# 211092) IBMI-913: The Multi-Step Job Script driver program was failing with error RNQ0121 (array index error) when a Script had more than 99 steps.  This error had been patched in LSAM version 18.1 with PTF# 181100, but 3 lines of the patch were missing in LSAM 21.1.

- Fixed (# 211093) IBMI-915: When adding the |SCANSPLF extension to an OpCon IBM i job Call command line, the IBM i Agent was incorrectly returning job failure code SMA0249 to OpCon. This was caused by a failure of the Capture Data Response module, unmatched to the LSAM 21.1 database.

- Fixed (# 211094) IBMI-920: The LSAM Server job LSAJOR would fail if the SCANSPLF command was appended to an OpCon IBM i job Call command, and the Scan Rules were executing an OpCon External Event command via the CPYTOMSGIN utility. A RCLACTGRP command is removed from CPYTOMSGIC.

- Fixed (# 211095) IBMI-924: Check,rebuild PFF211035 ctrl data area in SMADTA.  This PTF must execute before PTF211086 to avoid a false error about a missing PTF. The PTF was incorrectly named PFF211035, and the control data area for this PTF got removed before PTF distribution.

- Fixed (# 211096) IBMI-927: The LSAM install/update/audit utility progra SMADTAARAC had a weakness in the logic for managing the Job Tracking control data area named SMAXNBR.  The result of running this logic should leave SMAXNBR in library QGPL, moved out of the local LSAM SMAGPL.    

- Fixed (# 211099) IBMI-930: The LSAM Job Scheduler communications program was incorrectly handling warning messages whenever the Agent was not yet updated with an OpCon User ID and Password (or Token) for External Event commands. Comm log entries were all being overridden to type L.

- Fixed (# 211123) IBMI-993:  F4=Prompt on Copy Operator Replay Capture Application fails/not supported.

    Error occurs after staring the operation to copy an Operator Replay Script to a new Script name. If there is one or more linked Capture Data Applications, a prompt show asking if they should also be copied (to a new name). The same capture application could be re-used by the new OR Script, in which case answer Yes to copy the link, but do not change the To-Application on the next window (OPRR10W8):

    When answering Yes to copy the Capture App, a second window shows Old/New Capt App ID, and it allows a new name be assigned to the New copy. It’s possible to link an existing, other Capture Data App, in which case the F4=Prompt function key can be used to access a list of existing Capture Apps, from which one would be selected. However:

    “Function key not allowed” error when attempting to prompt for new APP with F4, within window that requests a new name for an associated Capture Data Application.

- Fixed (# 211110) IBMI-941: SMASETUP fails at SETLIBAUT when no objects in the library. The LSAM install/upgrade program SMASETUPC is fixed by adding additional error message monitoring for the expected condition that a library getting its object authority managed might not have any content.  Adding CPF2123 for the RVKOBJAUT command helps.

- Fixed (# 211100) IBMI-945: The LSAM Work with Import Batches list display showed an incorrect Group subset value because it was missing new Capture Data Rules groups added at LSAM 21.1.  Display SMA0038 when Exp/Imp Config was not updated. Add fetch of DESC for new imp save files.

- Fixed (# 211101) IBMI-948: Fix APPIDN5 error @ SCANSPLF utility. The SCANSPLF and SCANOUTQ utilities failed when old Scan Application IDs converted from LSAM 18.1 contain duplicate ID text as is used for other LSAM applications, including Message Management or Operator Replay. The App Type is added to search for APPKEY.

- Fixed (# 211120) IBMI-950:  Refine authority for SMAMSGQ job completion message queue, to improve the security of LSAM operational details.

- Fixed (# 211119) IBMI-951:  Fix 999999 for Job Start Time on job end log entry and job end status message sent to OpCon.  This initial "no value" string was overlaying the actual job start time during the management of the job end data.

- Fixed (# 211102) IBMI-958:  Bypass “NoLVar” false failure in the LSAM job scheduler program (LSASCHR00).

- Fixed (# 211103) IBMI-959:  Prevent error CPD0078 when restoring the LSAM Job Scheduler server program’s library list.  Each job is supported by the Job Scheduler temporarily setting its own library list to manage all the possible job definition parameters requested by the OpCon job master.

- Fixed (# 211104) IBMI-967:  Prevent possible errors during LSAM upgrades by monitoring for no objects in a library.  Added monitor for this error on DSPOBJD, RVKOBJAUT and DLTOVR commands in program SETLIBAUTC.

- Fixed (# 211106) IBMI-968:  Revise the File Arrival job command CHKFILE to prevent a false file name error CKF0002. When a DB2 library and file are listed in the File Arrival job using the IFS file system format (which directs the LSAM to use the CHKIFSFIL command), the parameters that pass the DB2 library name and the file name to the CHKFILE command were sometimes being passed as parameters in an incorrect format.

- Fixed (# 211105) IBMI-969:  The LSAM data Export tool was incorrectly storing duplicates of a single Dynamic Variable. Exporting duplicate Dynamic Variable names created a “duplicate key” error during the Import process.

- Fixed (# 211109) IBMI-972: Prevent error message MCH1210 (receiver too small to hold value) in the Message Management server job.

- Fixed (# 211108)  IBMI-975:  Prevent failures of the Job Tracking process by correcting the  SMASBMJOB and SBMJOB clone command attributes to use the specific SMAGPL librar of the LSAM environment that is controlling Job Tracking in the partition.  (Leaving the command processor program location set to *LIBL sometimes does not work.)

- Fixed (# 211118) IBMI-976:  Fix the "Capture Data Where Used" maintenance warning to prevent a false return reporting multiple uses for a Capture Data Application that is used in only one place.

- Fixed (# 211122) IBMI-980: Fix the Operator Replay Configuration maintenance of the QGPL/OPRDEVLOG debug data area. This data area is a critical component for managing the LSAM Telnet Exit Program, used primarily to Manage virtual workstation device selection for Operator Replay workstation automation.

- Fixed (# 211123) IBMI-933: Fix F4=Prompt on OPRRPY10-3, W8: Copy Application.                     
During the process of copying an Operator Replay Script, if a choice is made to copy an existing link to a Capture Data Application, the window that supports selecting the same, or new Capture Application ID was not supporting the F4=Prompt function key.                                               

### LSAM PTF release 21.1.146 (DB LVL # 21.1.006)

#### ENHANCEMENTS
##### LSAM DB LVL # 21.1.005

**DE5779:**  PTF211124  Add SMAFT setting file auth @ new files

The Continuous File Transfer jobs, both the on-demand Agent job and the inter-LSAM Server job, are enhanced to assign the Destination User Profile authority to new files added to the DB2 database or an IFS stream file system, per the new SMAFT Control option.

**IBMI-997:**  PTF211128  Extend Oper Replay Top/Bottom string

The "Top/Bottom" comparison strings that validate the current display format were extended to 435 bytes to support a fully qualified Dynamic Variable multi-instance token.  Now that full length can also be used for the
comparison string itself.

**IBMI-998:**  PTF211136  Operator Replay enhance for large data

The Operator Replay Step maintenance display is enhanced to support F8=DYNVAR and to prompt for de facto limit of 30 characters in the Top/Bottom control data field.  Logging of long data entries during Script execution 
ehanced to show all in log display.

##### LSAM DB LVL # 21.1.006

**IBMI-1006, IBMI-1023:**  PTF211137, PTF211142  Add flex parameters to Job Tracking

The Job Tracking Parameters master file has the OpCon Schedule ID fields expanded to 435 to allow for a long multi-instance qualified Dynamic Variable.  The IBM i Job ID fields now have parallel Prefix/Suffix flag fields, as explained in instructions.

- IBMI-1023  PTF211142  Add LSAM log  “JT:” entry to Job Tracking for $VAR replacement

The LSAM "submitted job log" entry types are expanded to support a new type "JT:" for Job Tracking to record any replacement of an LSAM $-system variable with its actual value.  

The Job Tracking Parameters maintenance display now only shows F10=$VAR if/where the Job Tracking variable tokens are supported.  This PTF also fixes a bug of not selecting the proper qualified Job Tracking Parameters record when more than one record matches the same job name (but has any of the other 5 job filter fields that are unique).

**IBMI-1017:**  PTF211141  Enhance LSAM gen log search to LC:

The LSAM "Submitted Job Log" file, which has become a general purpose log file for LSAM tools that span features, such as Dynamic Variables, has its list of log codes expanded with code LC: which logs any command executed by the LSAM utility LSAMCMD.

#### FIXES

- Fixed (# PTF211125) IBMI-991: Prevent dup recs in Export: LSAJORF50

Prevent duplicate records in the LSAM data Export library tables for files LSAJORF50, OPRRPYF40 and OPRRPYF50 (data capture and response rules tables).  The Import process cannot handle exact duplicates of record keys.

- Fixed (# PTF211126) IBMI-994: Fix load of Job Track/Queue INLLIBL

Fix load of Job Track/Queue INLLIBL. There was an incompatible field size in the LSAM Job Scheduler program that could cause a failure to fetch Dynamic Variable values, and this was preventing proper management of the 
Initial Library List for Tracked Jobs.

- Fixed (# PTF211127) IBMI-996: Show options 7 and 8 @ dsp fmt LSAJ50R1

Options 7=CaptChart and 8=Export were not showing on the display format LSAJORD50:LSAJ50R1.  The options worked, but a recent enhancement that added another list option had overlaid the display position of these two option prompts. Fix = repositioned.
                                             
- Fixed (# PTF211129) IBMI-1000: Register files for Job Monitor server

The new files for the "Job Status" monitor server needed to be registered in an Agent control file that keeps all the special file attributes for reference whenever files are updated in their design by LSAM PTFs or LSAM 
release upgrades.

- Fixed (# PTF211130) IBMI-1002: WAITDYNVAR fix and other DynVar fixes

(1) Fixes the default for WAITDYNVAR command parameter WAITVARNAM to be "WAITDYNVAR" as in LSAM 18.1; 
(2) Add missing DV: log of simple DynVarvalue change; 
(3) Display Captured Data Log F8 = access to R6: Response Rule Compares from R5: Entry detail.

- Fixed (# PTF211131) IBMI-1005: Change LSAM User Management to not pre-load passwords

On the LSAM menu 4, option 1 = User Management.  The data entry program is changed to not pre-load any existing password to the data entry fields.  This change helps prevent invalid passwords created by left over characters from a longer previous value.

- Fixed (# PTF211132) IBMI-1010: Fix F10=FOLD on MLTJOB Script flow chart

Fix F10=FOLD on Multi-Step Job Script list option 9=FlowChart where continuation lines showing the whole command were being truncated at the start of each continuation line.

- Fixed (# PTF211133) IBMI-1004: Fix Import Batch reports and library management

The LSAM Data Import processing programs were not showing valid totals.  The Import process when executing within the same IBM i partition as the Export was not always correctly managing the Export-Import library that had been stored in the save file.

- Fixed (# PTF211134) IBMI-1012: Prevent Non-numeric data errors in SMAFT programs

The Continuous File Transfer programs would sometimes generate a "Non-numeric data error" when there was a slight pause during the reception of a very long data transaction (near the limit of 32000 bytes).  Controls added 
to retry once after a read with no data.

- Fixed (# PTF211135) IBMI-1001: Prevent CPF3EC2 error at Job Track exit

Prevent CPF3EC2 error from the Job Tracking feature as it executes a test of every submitted job.  The error is uncommon, but it originated as the LSAM exit program for handling the command QSYS/SBMJOB was using an 
API to fetch exit program information.

- Fixed (# PTF211138) IBMI-1015: DSPOBJWU rept drops right char:  shift Left

DSPOBJWU report drops right-most character in the list lines. Lines are now shifted Left 3 bytes.

- Fixed (# PTF211139) IBMI-1016: Fix SCHNAM, FRENAM sizes for CHKTRKPAR

The CHGTRKPAR command processor programs did not get the sizes of fields SCHNAM, FRENAM expanded to 435/436 during the Job Tracking enhancement of project IBMI-1006.  This would have caused the utility command processing to fail.

- Fixed (# PTF211140) IBMI-1017: Refine Job Track revised activity management

The Job Tracking revised activity management is updated with one small program change and also a minor revision of one field definition within the Job Tracking Parameters file.

- Fixed (# PTF211143, 211144) IBMI-1009: Update the LSAM utility LSAINIT to manage the LSAM ENV value after cloing an LSAM

When an existing LSAM enironment's libraries are copied to a new LSAM environment, the LSAM PTF control records must be updated to match the new LSAM ENV (environment) name, otherwise the LSAM PTF process in the newly cloned environment cannot correctly process subsequent PTFs.

- Fixed (# PTF211145) IBMI-1017A  Redistribute Job Tracking interception program with late fix from PTF211140.

The Job Tracking program TRKJOBR00 was revised during the beta site testing phase, but after public distribution of the final version of this program there were complications with PTF administration at the beta site.  The easiest remedy for this obstacle was to re-issue the beta site program fix as a new, separate LSAM PTF that can easily be applied at the beta site and all Continuous client sites.
 
- Fixed (# PTF211146) IBMI-1027  Fix truncated IBM i Job Entry Date and Time.

The Dynamic Variable Multi-Instance keys were showing a truncated IBM i Job Entry Date and Time in the Dynamic Variable instance log display  and the Instance Key displays from the LSAM Submitted Job (general purpose) Log display.


### LSAM PTF release 21.1.195 (DB LVLs # 21.1.007, 21.1.008)

#### DB LVL # 21.1.006 (continued)

- Fixed (# PTF211147) SI-2389  Job Status log shows 26 of 28 IBM i JobID.

DSPIDXR2, R3, R4, R5 and R6 show only 26 of 28 IBM i Job ID. This also disabled function key F21=WRKJOB whenever a complete Job ID exceeds 26 characters in length in its edited form of 123456/USERNAME/JOBNAME.  

#### DB LVL # 21.1.007

- **Enhanced** (# PTF211148, PTF211149, PTF211150) IBMI-1027 Add Job Tracking trace logging diagnostic tool       

*See Post-Install Instructions*

A simple new control feature can now be used to produce a large amount of detailed, technical trace data that can help diagnose problems with Job Tracking in case jobs are not being tracked and there is no information appearing in the Job Tracking Log display (LSAM menu 1, option 2). PTF # 211148 adds file TRKLOGF10 to the LSAM database, bumping the DB Level to 007.  PTF # 211150 includes some small, technical fixes that prevent a failure to qualify certain jobs for tracking and also improve the accuracy of the Job Tracking activity log file content.

- Fixed (# PTF211151) IBMI-1040  Operator Replay attempt to write log to closed file

A log write early in OPRRPYR01 was not being controlled by the required test for the Operator Replay logging file to be open.               

- Fixed (# PTF211152) IBMI-1038  Fix *HEX and LDA Dynamic Variable management bugs

The *HEX function code was not storing the correctly entered hexadecimal values into the Dynamic Variable master file.  The Type L (LDA content) variables showed incorrect formatting by the DSPDYNVAR command.  Add instructions to DSPDYNVAR full display and offer a prompted DSPDYNVAR command to override output format when option 6=DSPDYNVAR is used from the LSAM menu list of Dynamic Variables.                                                 

- Fixed: (# PTF211153) IBMI-1041  Remove SMAGPL after Job Track process

The library SMAGPL was being left in the submitting job's library list, in error.  The registered LSAM Job Tracking exit program (TRKJOBR10) is updated to restore the accidentally lost step to remove the SMAGPL library that it had added to the job. This malfunction was preventing job users with limited authority from submitting their jobs.

- **Enhanced** (# PTF211154) IBMI-1041  Add GETDVRVALR utility

*See User Help* - [Utility Commands for Manipulating Dynamic Variables](/dynamic-variables/manipulation-commands)

This PTF adds a utility program to the LSAM that can be used by programs to fetch just the value of any given Dynamic Variable, including multi-instance variables, without the variable attributes.  It also changes the ACTGRP for some DynVar utilities.                                                  

- **Enhanced** (# PTF211155) IBMI-1041  Fix VARTYP value prompt for DSPDYNVAR

The VARTYP value of U in the DSPDYNVAR command is no longer supported, due to an improvement in the ability to display Type-L variables.  Use the OUTPUT parameter set to LINE24MSG to view just one sequence number for a group of Type-L variables @ same job.

- Fixed (# PTF211156) IBMI-1045  Fix DynVar value error; change DSPDYNVAR

The Dynamic Variable token replacement module enhancement for Type L variables in PTF # 211152 caused incorrect value replacement for Type V variables.  The PTF list option 6=DSPDYNVAR is now accompanied by 7=DSPDYNVAR(F4) for prompting the command.

- Fixed (# PTF211157) IBMI-1047  *DB2 DynVar erases SQL: replace program

When function code *DB2 was assigned to a Dynamic Variable, and the WHERE clause of the SQL definition included a Dynamic Variable token, the value of the token was replacing the whole SQL statement.  This was fixed at PTF211156, but one program missed.

- Fixed (# PTF211158) IBMI-1050  Dynamic Variable Numeric value string error

The numeric value type of Dynamic Variables was producing an error following recent PTFs that improved support for different types of variables with character (not numeric) values.  Added code to assure that value, start and length are always correct.

- **Enhanced** (# PTF211159, PTF211160) IBMI-1049  Add OPRLOGF44 file: F2=Select JOBNBR

The LSAM general inquiry program that shows just Captured Data entries (separate from the Captured Data Debug display) is improved with F2 = Select JOBNBR.  This function that appears in other inquiries limits the list display to entries from just one job. As the list of isolated Captured Data is enhanced with the subset capability appearing in other LSAM inquiries: F2=Subset by JobID, the list display also needed a fix to correct the function key legend appearing below the log entries list.

- **Enhanced** (# PTF211161, PTF211162) IBMI-1052  Edit prevents prefix to Type-L DynVars

This PTF adds a message to the SMAMSGF message file, as part of an edit to prevent applying a multi-instance prefix to Type-L (Local Data Area) variables.  See the IBM i Agent User Help, chapter [Managing the Local Data Area](/dynamic-variables/local-data-area) for various methods and examples for providing values to Type-L DynVars. 

PTF211162 adds an edit to prevent applying a multi-instance prefix to Type-L (Local Data Area) variables to the variables maintenance command and program. 
 
- **Enhanced** (# PTF211163) IBMI-1060  Bypass SMA0106 connect retry if TLS		

*See Post-Install Instructions*

The error SMA0106 reports unable to connect to a virtual display device.  The Operator Replay script driver has a built-in retry loop that will attempt to connect up to 3 times before failing the job.  A new option prevents the connect retry if TLS active.

- **Enhanced** (# PTF211164, PTF211165) IBMI-1061  Improve RESET response to BELL signal

*See Post-Install Instructions*

When the 5250 display device (emulated via VT100) protects from invalid keyboard input with a BELL signal, normally accompanied by an Input Inhibited keyboard status, the Operator Replay function key RESET is used to clear the keyboard.

When the RESET function will be the next Operator Replay Script Step to process, following a Step that generated a BELL keyboard input error, the Operator Replay visual capture log will no longer show the unsent Function Key of the failed Step.

- Fixed (# PTF211166, PTF211167) IBMI-1065  Job Tracking error RNX0100 when $SUFFIX option is used, for non-generic job names

The Job Tracking feature supporting generic job names, when active, can cause a failure of program TRKJOBR01, which does job detection for tracking, for certain sizes of job names. This PTF also adds an edit to Job Tracking Parameters for generic names.

- Fixed (# PTF211168) IBMI-1068  CHKIFSFIL fails if space in path name

A PATH name is allowed to have spaces between characters with in the name of a directory.  The LSAM CHKIFSFIL command uses a CL program to execute QSHELL commands, and those commands needed single quotes around a PATH name that includes space characters.                                                

- **Enhanced** (# PTF211169, PTF211170) OC-1881  Update LSAM table ctl file for JORLOGF00

File JORLOGF00 control now registers preferred size(*NOMAX), which prevents program failures in high volume environments, in case the file would get very full in between LSAM database reorganization by the SMARGZ command.

Change JORLOGF00 to size(*NOMAX) for high-volume environments that might have filled the size-limited file in between cycles of database reorganization that is performed by a properly scheduled execution of this LSAM's SMARGZ utility.

- Fixed (# PTF211171) OC-2146  SCANSPLFR fails: OCCUR value out of range

The SCANSPLF command was failing when any more than 299 instances of a given spool file name matched the Scan Rule search criteria.  There are strategies for using SCANSPLF parameters to limit the search results.  But the program is expanded to 499 files.

- Fixed (# PTF211172) OC-2694  LSATBLCSIR force blanks for PFSIZE2, PFSIZE3 if PFSIZE1=*NOMAX

The LSAM database table parameters control assignment program LSATBLCSIR must set PFSIZE2 and PFSIZE3 to blanks when PFSIZE1 is *NOMAX.  These three fields represent three segments of the SIZE() parameter in the CHGPF and CRTPF IBM i commands.                                                          

- Fixed (# PTF211173) OC-2766  MLTJOB Log display function keys F16, F17, F18 not working

The Multi-Step Script job log list display, format R2, is not supporting the display function keys 16=Search, F17=Top and F18=Bottom.  The program had never been updated to respond to these listed function keys which are important for studying script steps.
                                                
- **Enhanced** (# PTF211174) OC-2781  Expand JORS for extreme SPLF count

The LSAJOR server job was unable to accommodate more than 99,999 spool files that were produced by the same Job Name in IBM i partitions that had retained aged spool files. 
                                                
- **Enhanced** (# PTF211175) OC-2896  Control SCANSPLF dumps with data area

The LSAM report management utilities SCANSPLF and SCANOUTQ are enhanced with more carefully managed options to dump the program contents in case of an unexpected error, but only when the new data area LSAUTLU1 is set to a value of 'U1*YES'.   

Instructions to Continuous internal technical staff are provided at [How to Produce a Formatted Program Dump for Failure Diagnosis of SCANSPLF](/events-utilities/scansplf-scanoutq#how-to-produce-a-formatted-program-dump-for-failure-diagnosis-of-scansplf).

- Fixed (# PTF211176) OC-2917  SCANOUTQ temp debug code removed

The SCANOUTQ utility began displaying a temporary debug message after changes made by PTF211175.  This code is no longer necessary so it is completely removed.

- Fixed (# PTF211177) OC-2940  Support *APPKEY as SCANOUTQ APPID value

The special value of *APPKEY was supposed to be added to the  SCANOUTQ command prompt of the APPID keyword.  At the same time, the parameter rule that was causing a false error that APPID cannot be blank has been removed.  The APPKEY is the critical key.

#### DB LVL # 21.1.008

- **Enhanced** (# PTF211178, PTF211179) OC-1931  User Matrix master file change key field type to INST(3.A)

The User Matrix master file and maintenance are changed to support 3 characters instead of limiting the Institution ID to just numeric digits.

- **Enhanced** (# PTF211180) OC-3322  Add DV token replace for func code *DB2

Add Dynamic Variable token replace for the SQL query fields when the function code *DB2 is assigned.

- Fixed (# PTF211181) OC-3467  LSAM Export wrong values in new batch

The LSAM Export program that builds new batch control records assigned wrong values to new records because the program's initial list display leaves the last previously created record values instead of clearing the record before creating a new one.

- **Enhanced** (# PTF211182) OC-3492  Export/Import include DynVar @ *DB2 SQL

The LSAM Export/Import tools needed enhancement to include the newly supported option to insert Dynamic Variable {TOKENS} into the SQL Query definition fields that support the Dynamic Variable Function Code (*DB2): Include when LSAM scripts are Exported.

- **Enhanced** (# PTF211183) OC_3553  Support DV *DB2 SQL QRY FLDS {TOKENS}

The various LSAM list displays that support option 7 = Capt Chart are updated to also include Dynamic Variable {TOKENS} that can be inserted in the SQL Query definition fields when a Variable uses Function Code (*DB2).

- Fixed (# PTF211184) OC-3595  Disable diagnostic counter "StackCnt"

Disables diagnostic counter "StackCnt" because it was not being reset to zero as anticipated.  It is not needed for production use of the Dynamic Variable token replacement module.  Failure to reset the counter caused the LSAM Job Scheduler to fail.

- Fixed (# PTF211185) OC-3960  Oper Replay Step copy: Show Application ID & Key

When copying an Operator Replay Step record, the window that prompts the From and To Application ID and Key values was failing to include the Capture Application ID and Key of the From-Step record.                        

- Fixed (# PTF211186) OC-4369  Fix second Search for many list displays

Requesting a second Search value from the same session of many different LSAM menu function list displays was causing error "Length or start position is out of range for the string operation."

- **Enhanced** (# PTF211187) OC-4450  Add Resp Seq# to Capt Data Debug Log

Add Resp Seq# to Capt Data Debug Log view.  The redundant data column labelled "T" (for entry Type) is removed because the sub-title on line 2 of the list display reveals the strict limit of which type of captured data is presented in the list.                  

- Fixed (# PTF211188) OC-4451  Report Oper Replay loop error as SMA010F

Previously, whenever an Operator Replay script would loop back to the same step label more than the configured general limit, the Script driver job would fail and report Error14 using message ID SMA0107. This is corrected to use SMA010F (code F). 

- **Enhanced** (# PTF211189) OC-4584  Retro-fit loading JOBDTE, JOBTME to Dynamic Variables @ LSAM version 21.1

The full support for Job Entry Date and Time is retro-fitted from pending version LSAM 23.1 (wherever this can be supported) back to 21.1 in order to enable full support for multi-instance Dynamic Variables, especially for the IU.instance.  Avoids temporary assignment of zeros to Date & Time.                                             

- **Enhanced** (# PTF211190) OC-4603  Adapt Dynamic Variables to retrieve larger data areas via function code *DTAARA

Dynamic Variables using the Function Code of *DTAARA can now extract up to 1024 bytes of data from anywhere within a data area of larger size. This PTF also fixes a flaw in data area value extraction that was introduced in a recent older LSAM PTF.                                                     

- **Enhanced** (# PTF211191) OC-4458  Add AbortLoc code to record the point of a File Arrival failure

New support has been added to the File Arrival jobs executed by the IBM i Agent, providing a program location whenever the LSAM commands CHKFILE or CHKIFSFIL might fail.  In such cases, a simplified program dump report points to the location of failure.                                                

- Fixed (# PTF211192) OCAG-440  Add LSAVARF10 Dynamic Variable Auxiliary file to the SMASUP LSAM log extract utility

The Dynamic Variable Auxiliary master file with definitions for Function Code operations was never added to the SMASUP log extract utility.  This is always required whenever an LSAM feature uses Dynamic Variables.

NOTE:  The LSAM PTF published PTF control file list display incorrecly shows the JIRA rask as OC-440 (as was also incorrectly registered in the LSAM PTF production database). The Continuous internal PTF control master file is updated with a note referring to the correct JIRA Task ID.
 
- Fixed (# PTF211193) OCAG-393  Fix SMA File Transfer target file overwrite option

Under certain SMA File Transfer job configurations, the setting of the Overwrite File option could cause a program failure.

- **Enhanced** (# PTF211194) OCAG-447  SMASUP utility save operations enhanced for *NOCMTBDY; add LSAVARF10 to SMASUP

The *NOCMTBDY option for saves of objects or libraries has been added to the SMASUP command. This "ragged save" supports file journaling added by clients for mirroring.  The SMASUP command was also fixed to save the Dynamic Variable auxiliary data file named LSAVARF10.

- **Enhanced** (# PTF211195) OCAG-447  Add *NOCMTBDY to save of daily logs

The *NOCMTBDY command option for save-while-active has been added to the daily LSAM log file backup performed before aged records are deleted.  This "ragged save" method allows the LSAM saves to accommodate file journalling added by sites using mirroring.

### LSAM PTF release 21.1.199 

- Fixed (# PTF211196) OCAG-530  Fix Dynamic Variable negative value math

When using a negative value such as VALUE('-1') with the SETDYNVAR command, the variable value was being increased instead of descreased.  This started with LSAM version 21.1 (patch level not determined).  

- **Enhanced** (# PTF211197) OCAG-508  Add IBM i LSAM Restricted Mode messages

Additional messages are added to support Restricted Mode Configuration prompts and access to a window for viewing and managing the job logging parameters during execution of the Restricted Mode Script.  Messages match entries in the Activity Log display.

- **Enhanced** (# PTF211198) OCAG-508  Prompt CHGJOBD SAVRSTJ00; add job logging	*See Post-Install Instructions*

A new prompting window is now displayed upon initial access to the IBM i Agent menu 5, option 2: Setup Restricted Mode Environment.  This PTF also adds writes to the SAVRSTMODE script execution job log, echoing LSAM logging of Activity History.

- **Enhanced** (# PTF211199) OCAG-508  Fix PTF211194 update to SMASUP command

The previous PTF improved the SMASUP command so that it could retrieve LSAM logs and master files even while other system activity could have active locks on the requested files.  However, the added save command parameter was missing a ')' causing failure.
