title: CRC Alias
# CRC Alias

??? warning "Disclaimer"
    This document is provided for Houston ARTCC controllers to use when providing virtual ATC services on the VATSIM network. The information herein is **not intended for use in any real-world aviation applications**.

!!! info
    *Updated: August 18, 2025*

## VATSIM/CRC Basics
| Command              | Returns                                      
|----------------------|------------------------------------------------------------------------|
| `.ALIAS`         | Opens ZHU Alias Reference website.           
| `.RVM`           | Opens ZHU Radar Vector Map website.                                         
| `.STRIPS`        | Opens ZHU Strip Marking Policy |
| `.LASTTX`<br>`.LTX`<br>`.WHO`<br>`.H` | Issues the CRC built-in last transmission command. |
| `.AIPREF ####`   | Opens the VATSIM AIP (CTAF frequencies) for the specified airport (####)|


## Pilot Help Messages
!!! note "Syntax"
    Type callsign and press aircraft select (default in CRC is `Numpad Add`). Type the alias command (not case-sensitive) and press `Enter`. All pilot help commands send a private message to the pilot.

### Wallops

| Command           | Returns                                      
|-------------------|-------------------------------------------------------------------------|
| `.WALLPC`           | Wallop indicating the pilot is unable to maintain control or command of aircraft |
| `.WALLCH`           | Wallop indicating the pilot is unable to follow charted procedures as directed/planned |
| `.WALLHM`           | Wallop indicating the pilot has a stuck mic and isn't responding        |
| `.WALLNORDO ####`   | Wallop for NORDO aircraft, first contact-me sent at ####Z               |
| `.WALLNORDOX ####`  | Wallop for NORDO aircraft, first contact-me sent at ####Z, will be conflict soon |
| `.WALLCACA`         | Wallop for NORDO aircraft, is immediate conflict                        |

### Flight Plan Missing

| Command   | Returns              
|-----------|-------------------------------------------------|
| `.PLAN`     | No flight plan with connected callsign.         |
| `.PLANC`    | Similar, but not same callsign on submitted flight plan |

### Bad Flight Plan Information

| Command        | Returns                             
|----------------|----------------------------------------------------------------|
| `.BADCALL ###`   | Chosen callsign is not the same as real-world airline (###)    |
| `.BADREG`        | Chosen registration does not comply with U.S.-registrered aircraft standards |
| `.BADEQ`         | Invalid or incorrect ICAO equipment suffix                     |
| `.BADTYPE`       | Invalid or incorrect aircraft type  
| `.BADTYPE2 ####` | Invalid or incorrect aircraft type, the correct type is ####   |
| `.BADPROC`       | Missing SID/STAR in flight plan. Links to IFR Route analyzer   |

### Bad Spawn

| Command   | Returns                   |
|-----------|---------------------------|
| `.BADRWY`   | Spawned on runway         |
| `.BADTWY`   | Spawned on taxiway        |

### Unauthorized Movements

| Command   | Returns                   |
|-----------|---------------------------|
| `.BADPUSH`  | Pushed without permission |
| `.BADTAXI`  | Taxi without permission   |
| `.BADTWR`   | Takeoff without permission|
| `.BADAIR`   | In controlled airspace    |
| `.BADMODEC` | Informs pilot that Mode C is required at the airport |

### Bad Pilot Phraseology

| Command   | Returns                                      
|-----------|-------------------------------------------------------------------------|
| `.BADFL`    | Pilot incorrectly used "flight level" when referencing altitude         |
| `.BADALC`   | Requests the pilot includes altitude or flight level on initial contact |
| `.BADVFR`   | Informs pilot VFR flight information is not visible to ATC in the U.S. and requests they include more information on intial contact |
| `.BADRC`    | Radio checks are not needed                  

### Bad Procedure Compliance

| Command   | Returns                             
|-----------|----------------------------------------------------------------|
| `.BADALT`   | Pilot did not comply with altitude of procedure                |
| `.BADDOF`   | Pilot did not comply with altitude for direction of flight     |
| `.BADLAT`   | Pilot did not comply with lateral course of procedure          |
| `.BADVEC`   | Pilot did not comply with vector segment of procedure          |
| `.BADSPD`   | Pilot did not comply with published speed restriction          |
| `.BADTURN`  | Pilot did not comply with direction of IAH departure turn      |

### Pilot Resources

| Command      | Returns                           
|--------------|--------------------------------------------------------------|
| `.PILOT`       | Sends link to VATSIM Pilot Resource Center                   |
| `.IAHPILOT`    | Sends link to KIAH Pilot Briefing on ZHU Website              |
| `.CHARTD`      | Sends link to charts for departure airport                   |
| `.CHARTA`      | Sends link to charts for arrival airport                     |
| `.CHARTS K###` | Sends link to charts for specified airport (K###)            |
| `.CHARTDD`     | Sends link to airport diagram for departure airport          |
| `.CHARTAD`     | Sends link to airport diagram to arrival airport             |
| `.CHARTSD K###`| Sends link to airport diagram for specified airport (K###)   |
| `.AIP K###`    | Sends link to VATSIM AIP for specified airport (K###)        |

## STARS Autotrack
| Command             | Example            | Function                                      
|---------------------|--------------------|--------------------------------------------------------------------------|
| `.autotrack ICAO`     | .autotrack KIAH    | Add a single airport to the autotrack list.   
| `.autotrack -ICAO`    | .autotrack -KIAH   | Removes a single airport from the autotrack list.                        |
| `.ZHUtrackday`        |                    | Adds autotrack of all ZHU controlled airports.
| `.ZHUtrackmid`        |                    | Adds autotrack of 24/7 towered airports. Used for late night (0300Z+) center operations. |
| `.I90track`<br>`.AUStrack`<br>`.SATtrack`<br>`.MOBtrack`<br>`.GPTtrack`<br>`.BTRtrack`<br>`.LFTtrack`<br>`.LCHtrack`<br>`.VLYtrack`<br>`.NQItrack`<br>`.DFLtrack`<br>`.MSYtrack`<br>`.POEtrack` | | Adds autotrack of all airports in the specified TRACON.<br><br>*Use `notrack` after TRACON to remove those airports from the autotrack list. (`.I90notrack`)* |

## ZHU Routing, LOAs, & SOPs
### Routing System

Results are printed in the CRC chat window. Leading K required. Only airport pairs with specific ZHU preferred routes are included.

`.K[DEP]K[ARR]`

| Entering | Returns |
|----------|---------|
| `.KSATKDFW` | ROUTE_SYSTEM: [RNAV Jet DFWN] ALAMO3 GOBBY ... |
| `.KIAHKDFW` | ROUTE_SYSTEM: [RNAV] BLTWY7 CRIED REEKO3 ... |

### LOA Recall

Some results are printed in the CRC chat window while others may open ZHU website resources.

`.[ZHU SPECIALTY]S[DESTINATION SPECIALTY]S/[ARTCC]`

| Entering    | Returns                                 |
|-------------|-----------------------------------------|
| `.NEWSLFKS`   | From NEW Specialty to LFK Specialty     |
| `.AUSSZFW`    | From AUS Specialty to ZFW               |


`.[ZHU SPECIALTY]S[TRACON]T`

| Entering    | Returns                                         |
|-------------|-------------------------------------------------|
| `.AUSSAUST`   | AUS Specialty to AUS TRACON                     |
| `.LFKSI90T`   | LFK Specialty to I90 TRACON                     |
| `.CRPSI90C`   | CRP Specialty to I90 College Station area*       |

**LOA Recall Parameters**

| Specialty      | Code |
|----------------|------|
| Austin         | AUSS |
| Corpus         | CRPS |
| Lake Charles   | LCHS |
| Lufkin         | LFKS |
| New Orleans    | NEWS |
| Ocean          | OCNS |
| Rocksprings    | RSGS |

| ARTCC        | Code |
|--------------|------|
| Fort Worth   | ZFW  |
| Atlanta      | ZTL  |
| Jacksonville | ZJX  |
| Monterrey    | MTY  |
| Merida       | MID  |
| Havana       | HAV  |

| *I90 Type                        | *Code |
|----------------------------------|-------|
| Quick Reference Cards            | I90T  |
| I90 College Station area arrivals| I90C  |
| I90 Industry area arrivals       | I90I  |
| I90 Beaumont area arrivals       | I90B  |
| I90 Overflights                  | I90O  |

### SOP Recall
Some results are printed in the CRC chat window while others may open ZHU website resources. Note: Leading K not used.

`.[AIRPORT]INFO`

| Entering | Returns |
|----------|---------|
| `.IAHINFO` | VATSIM ZHU specific KIAH information |
| `.NEWINFO` | VATSIM ZHU specific KNEW information |

## Controller Resources
!!! note
    All chart recall commands open the selected FAA chart in your computer's default browser.
### Approach Plate Recall
Single digit runways include a leading 0 UNLESS an approach variation AND/OR sidedness designator is used. If a double-digit runway includes approach variation AND/OR sidedness, the leading digit is omitted. Do not forget the C following all chart recall aliases.

`.[AIRPORT][APPROACH CODE]([VARIATION Z/Y/X])[RUNWAY]([L/C/R])C`

| Approach Type | Code | Approach Type | Code |
|---------------|------|---------------|------|
| ILS | I | LOC/DME | K |
| RNAV (GPS/RNP) | R | VOR/DME | F |
| Visual | V | LOC | L |
| VOR | O | LDA | D |
| NDB | N | TACAN | T |

| Example  | Opens |
|----------|-------|
| `.IAHI8LC` | Houston Intercon ILS 8L |
| `.IAHI09C` | 	Houston Intercon ILS 9 |
| `.IAHI27C` | 	Houston Intercon ILS 27 |
| `.IAHRZ7C` | 	Houston Intercon RNAV-Z 27 |
| `.GPTOY4C` | 	Gulfport VOR-Y 14 |
| `.GPTTZ4C` | 	Gulfport TACAN Z 14 |
| `.CRPRZ1C` | 	Corpus Christi RNAV-Z 31 |
| `.DLFF1CC` | 	Laughlin VOR/DME 31C |

### SID/STAR Plate Recall
All chart recall commands open the selected FAA chart in your computer's default browser. Note: do not use revision numbers. Digits in alias are only for procedure page numbers (if applicable). Do not forget the C following all chart recall aliases.

`.[AIRPORT][PROCEDURE NAME]([PAGE])C`

| Example         | Opens                        |
|-----------------|-----------------------------|
| `.SATBOWIEC`    | San Antonio BOWIE SID        |
| `.SATBOWIE2C`   | San Antonio BOWIE SID page 2 |
| `.HOUWAPPL3C`   | Hobby WAPPL STAR page 3      |
| `.MSYMNSTRC`    | New Orleans MNSTR STAR       |

### Miscellaneous Chart Recall
All chart recall commands open the selected FAA chart in your computer's default browser. Do not forget the C following all chart recall aliases.

`.[AIRPORT][CODE]C`

| Chart Type         | Code  |
|--------------------|-------|
| Airport Diagram    | APD   |
| LAHSO              | LAHSO |
| Takeoff Minimums   | TM    |
| Hot Spots          | HS    |
| Radar Minimums     | RM    |
| ODP                | ODP   |

| Example        | Opens                      |
|---------------|----------------------------|
| `.AUSAPDC`    | Austin Airport Diagram     |
| `.IAHLAHSOC`  | Houston Intercon LAHSO     |

### Navaid Recall
Results are printed in the CRC chat window.

`.NAV + three letter identifier` --or--<br>
`.NAV + full Navaid name without spaces`

| Entering           | Returns                                               |
|--------------------|-------------------------------------------------------|
| `.NAVADK`          | ZHU_ISR *** ADK 530 MOUNT MOFFETT NDB/DME             |
| `.NAVMOUNTMOFFETT` | ZHU_ISR *** ADK 530 MOUNT MOFFETT NDB/DME             |
| `.NAVCWK`          | ZHU_ISR *** CWK 112.80 CENTEX VORTAC                  |
| `.NAVCENTEX`       | ZHU_ISR *** CWK 112.80 CENTEX VORTAC                  |

### Airway Recall (ERAM)
Route points are highlighted on the scope. ERAM only.

`.[AIRWAY]F`

| Entering | Returns |
|----------|---------|
| `.V222F` | `.FF ELP GIFEN RIOWE SFL HOBAN FST ...` |
| `.J2F`   | `.FF MZB GWIRE IPL HEEDS BZA HOGGZ MOHAK ...` |

### FAA Airport Information Recall
Results are printed in the CRC chat window.

`.APT + 3 or 4 letter identifier`

| Entering    | Returns                                                                                                  |
|-------------|----------------------------------------------------------------------------------------------------------|
| `.APTIAH`   | ZHU_ISR *** FAA-IAH : ICAO-KIAH - GEORGE BUSH INTCNTL/HOUSTON AIRPORT - 96'MSL - Towered - ZHU           |
| `.APTKIAH`  | ZHU_ISR *** FAA-IAH : ICAO-KIAH - GEORGE BUSH INTCNTL/HOUSTON AIRPORT - 96'MSL - Towered - ZHU           |

### Airline/Telephony Recall
Results are printed in the CRC chat window.

`.id + 3 letter company callsign.`

| Entering   | Returns                                             |
|------------|-----------------------------------------------------|
| `.idDAL`   | FAA_ISR *** 3LD: DAL - TELEPHONY: DELTA             |
| `.idAAY`   | FAA_ISR *** 3LD: AAY - TELEPHONY: ALLEGIANT         |

## Text-Based Controlling
Syntax: Type callsign and press aircraft select (default in CRC is `Numpad Add`). Type alias command with any needed variables and press `Enter`. Alias commands are not case-sensitive.

### Clearance Delivery
| Command         | Example         | Returns                                                                                                    |
|-----------------|----------------|------------------------------------------------------------------------------------------------------------|
| `.clr $1`       | `.clr 6`       | "Clearance on request number 6.”                                                                           |
| `.clravail`     |                | "Clearance available, advise when ready to copy.”                                                          |
| `.amend`        |                | "I have an amendment to your flight plan, advise ready to copy.”                                           |
| `.fullam`       |                | "I have a full re-route clearance for your flight plan, advise ready to copy.”                             |
| `.faroute`      |                | Opens Flight Aware IFR route analyzer with selected aircraft’s origin and destination prefilled.            |
| `.ifrv DEPID`   | `.ifrv 1W`     | Sends full IFR clearance to the selected aircraft: climb via SID and departure frequency.                  |
| `.ifrvx $1 DEPID`| `.ifrvx 4000 1W`| Sends full IFR clearance to the selected aircraft: climb via SID except maintain and departure frequency. |
| `.ifr $1 DEPID` | `.ifr 4000 1W` | Sends full IFR clearance to the selected aircraft: altitude to maintain and departure frequency.           |
| `.ifrvu`        |                | Sends full IFR clearance to the selected aircraft: climb via SID and departure OFFLINE.                    |
| `.ifrvxu $1`    | `.ifrvxu 4000` | Sends full IFR clearance to the selected aircraft: climb via SID except maintain and departure OFFLINE.    |
| `.ifru $1`      | `.ifru 4000`   | Sends full IFR clearance to the selected aircraft: altitude to maintain and departure OFFLINE.             |
| `.rcor NEXTID`  | `.rcor 1D`     | "Readback correct, push and start at pilot's discretion, contact 1D freq for taxi.”                        |
| `.rcorg $1`     | `.rcorg 15L`   | "Readback correct, push and start at pilot's discretion, call ready for taxi, expect runway 15L for departure.” |
| `.h4rel`        |                | "Readback correct, hold for release. Advise this frequency when number 1 for the runway. Frequency change approved.” |
| `.faroute`      |                | With an aircraft selected, opens FlightAware IFR route analyzer with the aircraft's departure and destination pre-filled. |

### Ground
| Command | Example | Returns |
|---------|---------|---------|
| `.td $1 $2...` | `.td 18L G2 G B` | Departure taxi: "Runway 18L, taxi via G2 G B" |
| `.ta $1 $2...` | `.ta L A H G3` | Arrival taxi: "Taxi to the ramp via L A H G3" |
| `.tapd` |  | "Taxi to the ramp at pilot's discretion, cross all runways." |
| `.hs $1` | `.hs H` | "Hold short H." |
| `.hp` |  | "Hold position." |
| `.ct` |  | "Continue taxi." |
| `.gwt $1...` | `.gwt the A320 on G`<br>`.gwt the Cessna crossing right to left` | "Give way to the A320 on G"<br>"Give way to the Cessna crossing left to right" |
| `.crs $1...` | `.crs 15L` | "Cross runway 15L" |

### Local
| Command         | Example             | Returns                                                                 |
|-----------------|---------------------|-------------------------------------------------------------------------|
| `.ctl $1`       | `.ctl 26R`          | "Runway 26R, cleared to land. Wind `current wind`."                       |
| `.cto $1`       | `.cto 22`           | "Runway 22, cleared for takeoff. Wind `current wind`."                    |
| `.ctorh $1`     | `.ctorh 4`          | "Fly runway heading, runway 4, cleared for takeoff. Wind `current wind`." |
| `.ctohdg $1 $2` | `.ctohdg 36R 030`   | "Fly heading 030, runway 36R, cleared for takeoff. Wind `current wind`."  |
| `.ctotl $1 $2`  | `.ctotl 18L 150`    | "Turn left heading 150, runway 18R, cleared for takeoff. Wind `current wind`." |
| `.ctotr $1 $2`  | `.ctotr 15R 300`    | "Turn right heading 300, runway 15R, cleared for takeoff. Wind `current wind`." |
| `.ctor $1 $2`   | `.ctor 15L SCAMM`   | "RNAV to SCAMM, runway 15L, cleared for takeoff. Wind `current wind`."    |
| `.ctomrt $1`    | `.ctomrt 11`        | "Make right traffic, runway 11, cleared for takeoff. Wind `current wind`."|
| `.ctomlt $1`    | `.ctomlt 29`        | "Make left traffic, runway 29, cleared for takeoff. Wind `current wind`." |
| `.ctoc`         |                     | "Cancel takeoff clearance."                                             |
| `.gafpm`        |                     | "Go around, fly the published missed approach."                         |
| `.gavec $1 $2 NEXTID` | `.gavec 180 3000 1W` | "Go around. Fly heading 180, maintain 3000, contact `1W freq`."      |
| `.luaw $1`      | `.luaw 13R`         | "Runway 13R, line up and wait."                                         |
| `.wel $1 $2`    | `.wel Austin L`<br>`.wel AUS right` | "Welcome to Austin, exit L when able."<br>"Welcome to AUS, exit right when able." |
| `.xrhs $1 $2 $3`| `.xrhs 8R NA ground`| "Cross runway 8R, hold short NA, contact ground on the other side."     |
| `.xr $1 $2`     | `.xr 26L ramp`      | "Cross runway 26L, contact ramp on the other side."                     |
| `.elb $1`       | `.elb 18L`          | "Enter left base runway 18L."                                           |
| `.erb $1`       | `.erb 18R`          | "Enter right base runway 18R."                                          |
| `.erd $1`       | `.erd 22`           | "Enter right downwind runway 22."                                       |
| `.eld $1`       | `.eld 4`            | "Enter left downwind runway 4."                                         |

### TRACON
| Command                  | Example                        | Returns                                                                                                                        |
|--------------------------|--------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| `.rel4dep $1 $2`         | `.rel4dep 0 10`                | "Released for departure at time + 0 mins, clearance void if not off by time + 10 mins, time now time. Frequency change approved." |
| `.rc`                    |                                | "Radar contact."                                                                                                               |
| `.rcsalt`                |                                | "Radar contact, say altitude leaving."                                                                                         |
| `.rcv $1`                | `.rcv CWK`                     | "Radar contact distance and bearing of CWK, altitude altitude."                                                                |
| `.rcl`                   |                                | "Radar contact lost."                                                                                                          |
| `.cils $1 $2 $3 $4`      | `.cils RRTOO 220 2500 18L`     | "Distance from RRTOO, fly heading 220, maintain 2500 until established, cleared ILS runway 18L approach."                      |
| `.rnvptac $1 $2 $3 $4`   | `.rnvptac RRTOO 2500 RNAVZ 18L`| "Cleared direct RRTOO, cross RRTOO at or above 2500, cleared RNAV-Z runway 18L approach."                                      |
| `.apat`                  |                                | "Arrival airport is at clock position and distance, report in sight."                                                          |
| `.cvis $1`               | `.cvis 22`                     | "Cleared visual approach runway 22."                                                                                           |
| `.notwrifr`              |                                | "No visible traffic between you and the field, report IFR cancellation in the air or on the ground this frequency. Frequency change approved." |
| `.dept $1 $2`            | `.dept BEESO 270`              | "Depart BEESO heading 270."                                                                                                    |
| `.vr $1`                 | `.vr sequence`                 | "Vectors for sequence."                                                                                                        |
| `.vr spacing`            |                                | "Vectors for spacing."                                                                                                         |
| `.xapp $1 $2`            | `.xapp ILS 18L`                | "Expect ILS runway 18L, arrival altimeter altimeter."                                                                          |
| `.xils $1`               | `.xils 11`                     | "Expect ILS runway 11."                                                                                                        |
| `.xvis $1`               | `.xvis 29`                     | "Expect visual approach runway 29."                                                                                            |
| `.tra $1 $2 $3 ...`      | `.tra 3 2 turn right`          | "Traffic alert, 3 o'clock 2 miles, advise you turn right immediately."                                                         |
| `.laa $1`                | `.laa 1500`                    | "Low altitude alert. Check your altitude immediately. The MVA in your area is 1500."                                           |
| `.veratis $1`            | `.veratis K`                   | "Verify you have information K."                                                                                               |
| `.tr $1`                 | `.tr 350`                      | "Turn right heading 350."                                                                                                      |
| `.tl $1`                 | `.tl 140`                      | "Turn left heading 140."                                                                                                       |
| `.prd $1`                | `.prd MPORT`                   | "Proceed direct MPORT."                                                                                                        |
| `.cd $1`                 | `.cd CWK`                      | "Cleared direct CWK."                                                                                                          |
| `.fh $1`                 | `.fh 180`                      | "Fly heading 180."                                                                                                             |
| `.fhjr $1 $2 $3 $4`      | `.fhjr 270 IDU 259 outbound`   | "Fly heading 270, join the IDU 259 radial outbound."                                                                           |
| `.cm $1`                 | `.cm 4000`<br>`.cm 15000`      | "Climb and maintain 4000."<br>"Climb and maintain 15000."                                                                     |
| `.cma $1`                | `.cma 4`<br>`.cma 11`          | "Climb and maintain 4,000."<br>"Climb and maintain 11,000."                                                                   |
| `.dm $1`                 | `.dm 4`<br>`.dm 11`            | "Descend and maintain 4000."<br>"Descend and maintain 11,000."                                                                |
| `.dma $1`                | `.dma 4`<br>`.dma 11`          | "Descend and maintain 4,000."<br>"Descend and maintain 11,000."                                                               |
| `.dmpd $1`               | `.dmpd 4`                      | "Descend at pilot's discretion, maintain 4000."                                                                               |
| `.vfrcan`                |                                | "Radar service terminated, squawk and maintain VFR, frequency change approved."                                                |
| `.tll $1 $2`             | `.tll 200 18L`                 | "Turn left heading 200, intercept Runway 18L localizer."                                                                       |
| `.trl $1 $2`             | `.trl 160 18R`                 | "Turn right heading 160, intercept Runway 18R localizer."                                                                      |
| `.fhl $1 $2`             | `.fhl 010 4`                   | "Fly heading 010, intercept Runway 4 localizer."                                                                               |

### Enroute
| Command              | Example                        | Returns                                                                                                   |
|----------------------|--------------------------------|-----------------------------------------------------------------------------------------------------------|
| `.zhufix`            |                                | Displays selected list of ZHU fixes in ERAM scope. *(ERAM ONLY)*                                          |
| `.ocnfix`            |                                | Displays selected list of Oceanic fixes in ERAM scope. *(ERAM ONLY)*                                      |
| `.i90`               |                                | Displays selected list of I90 fixes in ERAM scope. *(ERAM ONLY)*                                          |
| `.x $1 $2 ...`       | `.x CVE FL180`                 | "Cross CVE at and maintain FL180."                                                                        |
| `.xaoa $1 $2 ...`    | `.xaoa CEW FL190`              | "Cross CEW at or above FL190."                                                                            |
| `.xspd $1 $2 $3`     | `.xspd AEX FL200 280`          | "Cross AEX at and maintain FL200 at 280 KTS."                                                             |
| `.xdme $1 $2 $3`     | `.xdme 10 AEX FL300`           | "Cross 10 DME of AEX at FL300."                                                                           |
| `.dvia $1`           | `.dvia DOOOBI2`                | "Descend via the DOOBI2 arrival."                                                                         |
| `.dviax $1 $2`       | `.dviax DOOBI2 maintain FL240 and 250kts` | "Descend via the DOOBI2 arrival except maintain FL240 and 250kts."                                |
| `.cmf $1`            | `.cmf 340`                     | "Climb and maintain FL340."                                                                               |
| `.dmf $1`            | `.dmf 180`                     | "Descend and maintain FL180."                                                                             |
| `.dvia $1`           | `.dvia DOOBI2`                 | "Descend via the DOOBI2 arrival, altimeter ."                                                             |
| `.homex $1 $2`       | `.homex Z01 HRL`               | Sends handoff message to specified controller with range and bearing from specified fix with current altitude. |
| `.ocnhomex $1 $2 $3` | `.ocnhomex Z01 DUTNA 1325Z`    | Sends handoff message to specified controller with time over specified fix and current altitude.           |
| `.holdap $1 $2 $3`   | `.holdap JERNY north 2130`     | "Cleared to JERNY, hold north of JERNY as published. Expect further clearance at 2130Z."                  |

### Miscellaneous
| Command        | Example        | Returns                                                                                      |
|------------------|------------------|----------------------------------------------------------------------------------------------|
| `.ho NEXTID`     | `.ho 81`         | "Contact HOU_81_CTR on 134.425, have a good flight!"                                         |
| `.hodep DEPID`   | `.hodep 1D`      | "Contact Departure 120.05. Cya!”                                                             |
| `.depoff`        |                  | No departure control available, monitor unicom 122.8, Thanks for flying!                     |
| `.rts`           |                  | Reset transponder, assigned beacon."                                                         |
| `.lmas`          |                  | Leaving my airspace, no further ATC available, radar service terminated, frequency change approved, thanks for flying! |
| `.ecb`           |                  | You're exiting Class B airspace, radar service is terminated, squawk VFR, frequency change approved, thanks for flying! |
| `.ecc`           |                  | You're exiting Class C airspace, radar service is terminated, squawk VFR, frequency change approved, thanks for flying! |
| `.close $1`      | `.close 15`      | "**NOTAM** Will be closing in 15 minutes.”                                                   |
| `.closing $1`    | `.closing 0300Z` | "**NOTAM** Closing at 0300Z.”                                                                |
| `.closed`        |                  | "**NOTAM** Closed. Have a good day.”                                                         |
| `.shift`         |                  | "**NOTAM** Shift change in progress. All aircraft please stand by.”                          |
| `.rst`           |                  | "Radar service is terminated, squawk VFR, frequency change approved.”                        |
| `.spa`           |                  | "Say position and altitude.”                                                                 |
| `.sas`           |                  | "Say indicated air speed.”                                                                   |
| `.sms`           |                  | "Say mach.”                                                                                  |
| `.spo`           |                  | "Say position.”                                                                              |
| `.smc`           |                  | "Squawk mode C.”                                                                             |
| `.ss`            |                  | "Squawk standby.”                                                                            |
| `.si`            |                  | "Squawk ident.”                                                                              |
| `.sqi`           |                  | "Squawk assigned beacon and Ident.”                                                          |
| `.sq`            |                  | "Squawk assigned beacon.”                                                                    |
| `.rtc`           |                  | "Reset transponder, squawk assigned beacon.”                                                 |
| `.rpt $1`        | `.rpt CWK`       | "Report over CWK.”                                                                           |
| `.rptabm $1`     | `.rptabm 18L`    | "Report abeam 18L.”                                                                          |
| `.ifrcangnd`     |                  | "IFR cancellation received, thanks for flying.”                                              |
| `.icanair`       |                  | "IFR cancellation received. Radar service terminated, squawk and maintain VFR, frequency change approved, good day.” |
| `.dist $1`       | `.dist AEX`      | "You are distancenm from AEX.”                                                               |
| `.bear $1`       | `.bear KAUS`     | "You are bearing from KAUS.”                                                                 |
| `.clock $1`      | `.oclock KIAH`   | "KIAH is at your clock position.”                                                            |
| `.route`         |                  | Prints selected aircraft route.                                                              |
| `.newatis`       |                  | "ATIS information letter is current. Wind wind, altimeter.”                                  |
| `.ratis $1`      | `.ratis K`       | "Report receiving ATIS K.”                                                                   |
| `.rmatis`        |                  | "Report receiving ATIS letter.”                                                              |
| `.cyrv`          |                  | "Can you receive voice?”                                                                     |