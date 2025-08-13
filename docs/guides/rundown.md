title: Rundown Lists
# Rundown Lists

??? warning "Disclaimer"
    This document is provided for Houston ARTCC controllers to use when providing virtual ATC services on the VATSIM network. The information herein is **not intended for use in any real-world aviation applications**.

## Background
The Coordination List, also referred to as the "Rundown List," shows coordination message information for departing flights prior to their radar track association. Flights are removed from coordination lists upon their acquisition by radar. A coordination list provides a means where a tower controller typically can convey the sequence and related data of pending departures to the sector controller (also called the departure controller) who will be handling the flight.

The tower controllers are referred to as the "senders" of coordination messages, while the radar controller(s) are referred to as the "receiver(s)." The senders and associated receivers constitute a coordination "channel." Multiple coordination channels may be adapted to support multiple tower facilities or multiple senders within a single tower facility.

## Message States
The entry of a flight in a coordination list is called a coordination message. A coordination message can be in any one of the following states:

- **Unsent:** Displayed in steady green at sender (tower) position.
- **Unacknowledged:** Displayed at sender and receiver positions in blinking green to indicate receiver acknowledgement is needed.
- **Acknowledged:** Displayed at sender and receiver positions in steady green and includes the plus symbol (+).
- **Recalled:** At the receiver’s position, displayed in blinking green with `RECALL` in the text area for an adapted interval before the entire message is removed from the list. At the sender’s position, displayed with steady green and with `RECALL` in the text area for an adapted interval, and then displayed as Unsent. If there was text associated with the message, the text is displayed after the adapted interval.
- **Departure Expiration Warning:** Displayed at sender and receiver positions with a blinking yellow color to indicate that the corresponding flight has not yet departed and the acknowledgement of the flight’s coordination message is about to expire (will become Unacknowledged).
- **Void Unacknowledged:** Displayed at sender and receiver positions with a blinking green color and an expired time stamp to indicate that the corresponding flight has not yet departed and the acknowledgement of the flight’s coordination message has expired, rendering the message as Unacknowledged. Receiver acknowledgement is needed.

Each entry in the list will display the time remaining until release expiration (if released), the position in the sequence, a released indicator (`+`), the aircraft callsign, the aircraft type, the assigned beacon code, the weight class, scratchpad assigned, if any, and any message text entered.

## Command Reference
### General Commands
| Command | Function |
| --- | --- |
| `<F7>(LISTID)<SLEW LOCATION>` | Relocate Coordination list |
| `<F7>(LISTID) (1-100)<ENTER>` | Set Coordination list size (number of lines)|
| `<F13>T<ENTER>` | Toggle display of Coordination list title temporarily |
| `<F13>TE<ENTER>` | Enable display of Coordination list title temporarily |
| `<F13>TI<ENTER>` | Inhibit display of Coordination list title |

!!! important
    `F13` = `<SHIFT>+<F3>`

### Local Commands
| Command | Description |
| --- | --- |
| `<F7>ZDE<ENTER>` | Enable Departure release audible alarm |
| `<F7>ZDI<ENTER>` | Inhibit Departure release audible alarm |
| `<F13>(LISTID) (ACID OR BEACON)<ENTER>` | Create and send coordination message |
| `<F13>(LISTID) (ACID OR BEACON) /<ENTER>` | Create and do not yet send coordination message | 
| `<F13>(LISTID) (ACID OR BEACON) / ##<ENTER>` | Create and do not yet send coordination message at line number ## |
| `<F13>(LISTID) (ACID OR BEACON) / ## TEXT<ENTER>` | Create and do not yet send coordination message at line number ## with message TEXT |
| `<F13>(LISTID) (ACID OR BEACON) /<ENTER>` | Send a previously held coordination message |
| `<F13>(LISTID) (ACID OR BEACON) ##<ENTER>`| Reorder a coordination message |
| `<F13>(LISTID) (ACID OR BEACON)<ENTER>` | Delete an existing coordination message |
| `<F13>(LISTID) (ACID OR BEACON) /<ENTER>` | Recall a previously sent coordination message |
| `<F13>(LISTID) (ACID OR BEACON) TEXT<ENTER>` | Modify message text for a coordination message (must not be sent) |

*Note: `LISTID` is optional when only one list is adapted for the position*

### TRACON Commands
| Command | Description |
| --- | --- |
| `<F13>(LISTID) (FLID)<ENTER>` | Acknowledge coordination message |
| `<F13><ENTER>` | Acknowledge coordination message when only one is pending |
| `<F13>(LISTID) A*<ENTER>` | Enable automatic acknowledge for messages with no message text (`LISTID` required) |
| `<F13>(LISTID) M*<ENTER>` | Disable automatic acknowledge for messages with no message text (`LISTID` required) |

*Note: `LISTID` is optional when only one list is adapted for the position*

## Important Notes
- The primary field at an up/down facility will not use coordination/rundown lists, especially where the facility SOP specifies that the Local controller will tag and handoff all departures.
- If an aircraft will be departing from a non-advertised runway, turned in a direction other than SOP-defined departure headings, or any other unusual situation exists, extra text in coordination messages (e.g. `18 R270` or `11 RH`) should be included.
- Local controllers can continually build a departure sequence by sending subsequent messages to their respective coordination list. In the TRACON, list entries are sorted by time of message arrival.
- TRACON controllers can toggle automatic acknowledgment on any list by entering `<F13>(LISTID) A*<ENTER>` or `<F13>(LISTID) M*<ENTER>`. *Note: only messages without additional coordination text will be auto-acknowledged.* 
- Coordination lists are for **departure releases only**. The acknowledgment of a coordination messages (automatic or manual) does not grant permission to violate SOP procedures or separation minima as outlined in the 7110.65.

## Example: Austin TRACON
Austin TRACON (AUS_W) is online with all 4 local controllers.

- AUS Local will tag departures and hand off to the TRACON
- GTU Local will send messages to its coordination list (P01)
- HYI Local will send messages to its coordination list (P02)
- EDC Local does not have STARS feed from the TRACON and must verbally coordinate all calls for release

N123 is number 1 for RWY 18 at KGTU with an assigned departure heading of 100 (standard SOP). N456 is number 1 for RWY 11 with an assigned departure heading of 090 (non-standard SOP).

**Coordination Message Sequence:**

1. GTU Local: `<F13>N123<ENTER>`, then `<F13>N456 11 L090<ENTER>`. Sends two messages (in sequence) to Austin TRACON. Both messages will blink green until the TRACON acknowledges. *Note: `LISTID` is not needed since there is only one coordination list between Georgetown Local and the TRACON.*
1. AUS TRACON: Receives both messages on P01 and acknowledges the first with `<F13>P01 N123<ENTER>`. As desired, TRACON can release the second aircraft at any time with `<F13>P01 N456<ENTER>`. Local shall apply standard separation minima for departures. *Note: `LISTID` is required for all TRACON coordination commands when the position is a recipient of multiple lists. Not all TRACONS in ZHU have multiple lists and the `LISTID` can be omitted.*
1. GTU Local: notices the coordination message turns solid green for one (or both) and launches the aircraft(s) while applying standard separation minima.

## Example: I90 TRACON
I90 Consolidated (I90_D) is online with KCLL, KGLS, and KSGR Local control.

- KIAH and KHOU will tag departures and hand off to the TRACON
- KSGR Local will send messages to its coordination list (P07)
- KGLS Local will send messages to its coordination list (P06)
- KCLL Local will send messages to its coordination list (P02)

N123 is at KSGR taxing to RWY 17. N456 is at KGLS taxing to RWY 18. N789 is at KCLL taxing to RWY 29 (but KCLL is advertising RWY 35 for departures). All aircraft will be given standard SOP departure headings.

**Coordination Message Sequence:**

1. KSGR Local: `<F13>N123<ENTER>`
1. I90_D: Receives the message on P07 and acknowledges by entering `<F13>P07 N123<ENTER>`
1. KSGR Local notes the coordination message stops blinking and launches the aircraft.
1. KGLS Local: `<F13>N456<ENTER>`
1. KCLL Local: `<F13>N789 29 RH<ENTER>`
1. I90_D: Receives the messages on P06 and P02 and approves the KGLS departure by entering `<F13>P06 N456<ENTER>`.
1. I90 decides that all KGLS departures can be automatically released and enters `<F13>P06 A*<ENTER>`. College Satellite is busy and needs KCLL departures to hold for release.
1. KGLS Local notes the acknowledgment and launches the aircraft. KCLL Local notes their coordination message is still flashing (not acknowledged) and holds the aircraft
1. I90_D: `<F13>P02 N789<ENTER>`
1. KCLL Local notes the coordination message stops flashing and launches the aircraft.
1. I90 no longer desires automatic acknowledgments at KGLS and enters `<F13>P06 M*<ENTER>`