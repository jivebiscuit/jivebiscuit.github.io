title: Rundown Lists
# Rundown Lists

??? warning "Disclaimer"
    This document is provided for Houston ARTCC controllers to use when providing virtual ATC services on the VATSIM network. The information herein is **not intended for use in any real-world aviation applications**.

## Background
The Coordination List, also referred to as the “Rundown List,” shows coordination message information for departing flights prior to their radar track association. Flights are removed from coordination lists upon their acquisition by radar. A coordination list provides a means where a tower controller typically can convey the sequence and related data of pending departures to the sector controller (also called the departure controller) who will be handling the flight.

The tower controllers are referred to as the “senders” of coordination messages, while the sector controller(s) are referred to as the “receiver(s).” The senders and associated receivers constitute a coordination “channel.” Multiple coordination channels may be adapted to support multiple tower facilities or multiple senders within a single tower facility.

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
| `<F7>(LISTID) (1-100)<ENTER>` | Set Coordination list size |
| `<F13>T<ENTER>` | Toggle display of Coordination list title temporarily |
| `<F13>TE<ENTER>` | Enable display of Coordination list title temporarily |
| `<F13>TI<ENTER>` | Inhibit display of Coordination list title |

!!! important
    F13 = `<SHIFT>+<F3>`

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
| `<F13>(LISTID) A*` | Enable automatic acknowledge for messages with no message text (`LISTID` required) |
| `<F13>(LISTID) M*` | Disable automatic acknowledge for messages with no message text (`LISTID` required) |

*Note: `LISTID` is optional when only one list is adapted for the position*

### Example - Austin TRACON
Austin TRACON (consolidated) is online along with all 4 local controllers.
- AUS Local can only send messages to its coordination list (P01)
- GTU Local can only send messages to its coordination list (P02)
- HYI Local can only send messages to its coordination list (P03)
- EDC Local does not have STARS feed from the TRACON and must verbally coordinate calls for release

#### KAUS departures with automatic releases
AAL123 is number 1 for 18R at KAUS with an assigned departure heading of 210 degrees:

1. Local: `<F13>AAL123 18R 210<ENTER>` immediately sends coordination message to Austin TRACON. The message may blink green for a moment while auto-acknowledgement is processed. `LISTID` is not needed since there is only one coordination list between Austin Local and TRACON.
1. TRACON: Receives the message on P01 and auto-acknowledge activates.
1. Local: notices the coordination message turns solid green and launches the aircraft.

#### KGTU departures with Call for Release
N123 is number 1 for 18 at KGTU with an assigned departure heading of runway heading. N456 is number 2 for 18 with an assigned deparute heading of 260.

1. Local: `<F13>N123 18 RH<ENTER>`, then `<F13>N456 18 260<ENTER>`. Sends two messages (in sequence) to Austin TRACON. Both messages will blink green until the TRACON acknowledges. *Note: `LISTID` is not needed since there is only one coordination list between Georgetown Local and TRACON.*
1. TRACON: Receives both messages on P02 and acknowledges the first with `<F13>P02 N123<ENTER>`. As desired, TRACON can release the second aircraft at any time with `<F13>P02 N456<ENTER>`. Local shall apply standard same-runway separation for departures. *Note: `LISTID` is required for all TRACON coordination commands because it receives messages on 3 coordination channels.*
1. Local: notices the coordination message turns solid green for one (or both) and launches the aircraft(s) while applying same-runway separation.

### Additional Notes
- Text in coordination messages (e.g. `18R 210` or `18 RH`) is not required if the Local controller is departing aircraft within SOP guidelines, pre-arranged coordination, or other verbal coordination with relevant controllers.
- Local controllers can continually build a departure sequence by sending subsequent messages to their respective coordination list. In the TRACON, list entries are sorted by time of message arrival.
- TRACON controllers can toggle automatic acknowledgment on any list by entering `<F13>(LISTID) A*<ENTER>` or `<F13>(LISTID) M*<ENTER>`. *Note: only messages without additional coordination text will be auto-acknowledged.* 
- Coordination lists are for **departure releases only** and the acknowledgment of coordination messages (automatic or manual) does not grant permission to violate SOP procedures or separation minima as outlined in the 7110.65.