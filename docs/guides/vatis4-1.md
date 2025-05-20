title: vATIS 4.1
# vATIS 4.1

??? warning "Disclaimer"
    This document is provided for Houston ARTCC controllers to use when providing virtual ATC services on the VATSIM network. The information herein is **not intended for use in any real-world aviation applications**.

??? info "Revision Information"
    - Document Number: N/A
    - Date: 1 Apr 2025
    - Revision: **1**

    **Record of Revisions**

    | Date | Revision | Editor |
    |:---:|:---:|:---:|
    | 1 Apr 2025 | 1 | DW |

## 1. Introduction
vATIS was recently updated to version 4.1 beta and several new features were added:

- Automatically updated official profiles from the cloud (previously known as composites).
- Ability to see ATIS letters of facilities hosted by other controllers if that facility is in your currently open profile.
- Manually input an ATIS letter rather than clicking through the whole alphabet (`SHIFT`+double click, enter the desired letter, `ENTER` to accept).
- Option to pull the real-world D-ATIS letter (for supported facilities) automatically Feature is disabled by default, but can be enabled in `User Settings > Automatically fetch ATIS letter`.
- Various backend improvements for future feature releases.

![vATIS GUI](https://vatis.app/assets/images/MainScreen.png)

## 2. First-Run Setup
1. Highly recommended that you uninstall any
previous versions of vATIS from your computer.
2. Visit https://vatis.app/ and download version 4.1 for
your operating system.
3. Install the program. Accept/allow/bypass any anti-virus or trusted developer messages (the program is safe).
4. Download the ZHU “Skeleton” Profiles ZIP file from the ZHU Facilities GitHub Repo and save to an easy-to-remember location (Desktop, Downloads, etc.)
5. Extract the ZIP file contents to an easy-to-remember location (see image to right). You will delete them from your computer later.
6. Open vATIS 4.1, click `Import`, and select all 16 profiles from the extracted ZIP.

    !!! danger
        After importing the profiles, close vATIS by pressing `EXIT`, wait a few moments and reopen vATIS.
        
        Do not open any of the profiles after initial import or the automatic update feature will fail to initialize and the process will need to be restarted.

7. After a few moments, reopen vATIS, and choose the
Profile you wish to use. Use the program the same way as
in previous versions.
8. You may safely delete the extracted file folder and ZIP file downloaded from the ZHU GitHub repository.
9. It is recommended to keep all 16 ZHU profiles in your vATIS installation so that they are always kept up to date.

## 3. Regular Use
Each time you open vATIS, it will check to see if the Facilities Team has made any updates to profiles and will automatically download the newest version (similar to how CRC automatically updates video maps and cab views).

## 4. Important Notes
On some presets, you may notice `^`, `@`, and `*` symbols in the Airport Conditions and NOTAMS sections. These are needed to help the vATIS Text to Speech (TTS) engine accurately render the computer-generated voice ATIS. Please do not remove these characters or the voice ATIS will not render correctly. These special markings are not parsed into the text ATIS shown on VATSIM maps or sent to pilots in their pilot clients.

The Facilities Team has created a wide combination of presets to be used in normal controlling sessions based on SOP flows - try to stick to these as much as possible.

!!! warning
    Any local changes made to a presets or profiles may be overwritten the next time the Facilities team makes an official edit to that profile.

## 5. D-ATIS Preset 
If you choose to copy and paste real-world D-ATIS information, use the D-ATIS preset for the facility. This will give you a blank canvas for each controlling session. Be aware that the TTS rendering of your ATIS may not be accurate or make sense without the special characters. Try to remove real world D-ATIS information that doesn’t apply in VATSIM (birds, equipment, etc.).