title: Teamspeak Connection
# Teamspeak Connection

??? warning "Disclaimer"
    This document is provided for Houston ARTCC controllers to use when providing virtual ATC services on the VATSIM network. The information herein is **not intended for use in any real-world aviation applications**.

??? info "Revision Information"
    - Document Number: ZHU TS001
    - Date: 17 Oct 2024
    - Revision: **1**

    **Record of Revisions**

    | Date | Revision | Editor |
    |:---:|:---:|:---:|
    | 17 Oct 2024 | 1 | WS |

## 1. Administration
### 1-1. Introduction
TeamSpeak is a social voice platform that offers ZHU controllers a means of connecting and coordinating while controlling on the Vatsim network. The server is required to be utilized at all times by controllers when connected to the network for coordination.

The server is designed with “Hangout” channels for open discussion and “Controlling Floor” channels for controller communication and coordination.

The ZHU TeamSpeak is accessible to all members. Like our Discord, communications through TeamSpeak are governed by ZHU’s Member General Policy. Members are expected to act professionally, maturely, and respectfully at all times.

## 2. TeamSpeak 3 Installation & Connection
### 2-1. Background
This version of the guide was created in October 2024 and is based on the current version of TeamSpeak 3 at the time (3.6.2). If you find this guide to be out-of-date, please submit using the Bugs & Request section of the ZHU Discord.
### 2-2. Installing TeamSpeak 3
1. Visit the [TeamSpeak website.](https://teamspeak.com/en/downloads/#ts3client)
2. Navigate to the TeamSpeak 3 (TS3) downloads page. Please ensure you are downloading TeamSpeak 3, not TeamSpeak 5.
3. Select from either the 32-bit or 64-bit TeamSpeak 3 client (the first two downloads). If needed, use the instructions to determine which version of Windows you have.
4. Follow the instructions and prompts to download and install the program. Most members do not use the Overwolf overlay.

### 2-3. Getting Started

1. Once installed, open the program. To accept the License Agreement, scroll to the bottom of the window.
1. Next, you will be prompted to login to myTeamSpeak:

    !!! warning "MyTeamSpeak Accounts"
        Creating and using a MyTeamSpeak account is mandatory. Not using a MyTeamSpeak account could result in unintentionally losing roles and permissions if you sign in on another device.

    ??? success "**I have a MyTeamSpeak Account**"
        Login and your settings and bookmarks are synchronized through this account; logging in will recover them.
    ??? failure "**I do not have a MyTeamSpeak Account**"
        If you haven’t used TeamSpeak before, we recommend you create a myTeamSpeak account. To do so:

        1. Click `Create account` and enter the required information.
        1. You will be prompted to verify your email to activate the account.
        1. Once verified, click `Login`.
        1. You may wish to save the recovery key provided in case you forget your account’s password in the future.

### 2-4. Configuring Settings
Next, we’ll set some of the basic settings within the application, going through parts of the “Options” menu based on ZHU’s recommendations for best practices. Members are encouraged to use this initial configuration and then adjust based on personal preferences.

On each screen, click `Apply` to save the changes before moving to the next. To begin, select `Tools > Options`.

??? info "Application Section"
    - Server - tick all boxes
    - Misc - tick `Warn when talking while microphone is muted`
    - Channel Subscription Behavior - select `Subscribe to all channels`

??? info "Playback Section"
    - Choose your desired `Playback Device` using the drop-down menu.
    - The `Play Test Sound` button will enable you to test the chosen device.
    - You can also pre-select the volume of how you hear others (`Voice Volume Adjustment`).

??? info "Capture Section"
    - Select your desired `Capture Device`.
    - Select `Push-To-Talk` under `Activation`.
    - Select a `Hotkey`, ensuring it is different from the key used in your pilot or ATC client. Most members use the `Left Control` key.
    - Select the `Add Voice Activity Detection` option.

### 2-5. Connecting to the Server
The steps below provide instructions for creating a Bookmark and connecting to ZHU’s TeamSpeak server. The same instructions can be used to connect to a different server, substituting the connection information.

1. Click on `Bookmarks > Manage Bookmarks`
1. Click the `Add Bookmark` button.
1. Name the bookmark (we suggest `ZHU Center`).
1. Set your Nickname as your first and last name as displayed on the controller roster, plus your assigned operating initials.

    !!! warning
        Members should not add any other information (like a callsign, location, nickname, etc.) to their TeamSpeak Nickname.

1. Enter the “Server Nickname” and “Server Password” for the server.

    ??? tip "Server Information"
        Server Address: `houston.center`
        
        Server Password: `zhucenter`

1. Once all the settings have been entered, click `OK`
1. To connect: from the main TeamSpeak window, select the server (ZHU Center) you’ve just added from the `Bookmarks` menu.

### 2-6. Updating a Bookmark
Remember, the ZHU TeamSpeak password occasionally changes. When the ZHU TeamSpeak password is changed, update the password in your bookmark.

1. Click `Bookmarks > Manage Bookmarks`.
1. In the window that appears, click on the server you wish to update. Then, enter the new password into the `Server Password` field.
1. Click `OK` to save the changes.

### 2-7. Roles
Roles allow for movement around the various TeamSpeak channels. Some channels are locked behind certain roles that must be given by facility staff. The first time you connect to the ZHU TeamSpeak server, send a message on Discord in the `#tech-support` channel asking for roles to be given.

### 2-8. Support
The most common reason users are unable to connect to the
TeamSpeak server is because connection information (i.e., address and/or password) is not entered correctly.
Before asking for help, please check your settings.

!!! question "Support"
    For support accessing the ZHU TeamSpeak, send a message on Discord in the `#tech-support` channel.