# Antminer S9


- [crs S9 Test Repair spreadsheet](https://docs.google.com/spreadsheets/d/1OY2vIPBp0MtdGgWja4nCJwE-r7zml7iQ-lLumCsUtlI/edit#gid=1822583908) - ask chris
- [Copy Excel to Markdown](https://thisdavej.com/copy-table-in-excel-and-paste-as-a-markdown-table/)

### Rework Status 01.23.2021

| Triage | Detail                       | location | Log on crs.2cld | ASICS |
|--------|------------------------------|----------|-----------------|-------|
| ASIC   | chain 6 - 0, 7 - 60, 8 - 63  | Chris    | crs-s9-w1.log   | 123   |
| ASIC   | chain 6 - 62, 7 - 62, 8 - 63 | Joey     | crs-s9-w2 - na  | 187   |
| FAN    | bad fan                      | Joey     | crs-s9-w3.log   |       |
| AOK    | all OK - ssh                 | Chris    | crs-s9-w4.log   | 189   |
| AOK    | all OK                       | Joey     | crs-s9-w5.log   | 189   |
| ASIC   | chain 6 - 0, 7 - 63, 8 - 63  | Joey     | crs-s9-w6.log   | 126   |
| AOK    | all OK                       | Joey     | crs-s9-w7.log   | 189   |
| FAN    | bad fan                      | Chris    | crs-s9-w8.log   |       |
| FAN    | bad fan                      | Chris    | crs-s9-w9.log   |       |
| ASIC   | chain 6 - 0, 7 - 63, 8 - 63  | Chris    | crs-s9-w10.log  | 126   |
| AOK    | all OK - ssh                 | Chris    | crs-s9-w11.log  | 189   |
|        | not tested                   | Joey     | crs-s9-w12      |       |
|        | not tested                   | John     | crs-s9-w13      |       |
|        | not tested                   | John     | crs-s9-w14      |       |
|        | not tested                   | John     | crs-s9-w15      |       |
|        | not tested                   | John     | crs-s9-w16      |       |
|        | not tested                   | John     | crs-s9-w17      |       |
|        | not tested                   |          | crs-s9-w18      |       |
|        | not tested                   |          | crs-s9-w19      |       |
|        | not tested                   |          | crs-s9-w20      |       |

## S9 Triage
Many of the units have min issues.  All units need restoration work.  Set up a lab to triage units as they come in into the following:

#### S9 unit Triage Tags
1. DOA
    - nothing works 
    - no lights or fans
2. WEB
    - unit controller lights up
    - unit gets DHCP 
    - browser is able to access via WEB 
    - Unit has no HASH status
3. FAN 
    - unit has WEB
    - unit FANS do not spin
    - unit reports FAN issues
4. ASIC
    - unit passes WEB
    - unit passes FAN
    - unit has at least one RED LED on hashboards
    - unit reports hash units but not 189 ASICS
5. AOK 
    - unit passes WEB
    - unit passes FAN
    - unit has RED LED on all hashboards
    - unit reports all 189 ASICS and starts to hash

### Triage control station
1. Internet router with DCHP server
2. Computer with browser access to [http://crs.2cld.net/docs/antminerS9/](http://crs.2cld.net/docs/antminerS9/)
3. User access to [crsBoardRefresh](https://docs.google.com/spreadsheets/d/1OY2vIPBp0MtdGgWja4nCJwE-r7zml7iQ-lLumCsUtlI/edit#gid=1822583908)
4. 3 x S9 triage station (see below)

### S9 triage station will require:
1. Dedicated 15 amp 120 volt power
2. J45 Ethernet jack
3. Known good 1300 Watt 120 volt power supply

### S9 triage proceedure
1. Label unit and recored crs-s9-w<number> in [crsBoardRefresh](https://docs.google.com/spreadsheets/d/1OY2vIPBp0MtdGgWja4nCJwE-r7zml7iQ-lLumCsUtlI/edit#gid=1822583908).  Label inbound power supply also.
2. Power up unit as is
3. Obtain IP from DHCP server and attempt to access unit
    - Update Miner Configuraion and worker node info
    - Record crs-s9-w<number>.log
4. If controller board does not come up (start to remove possible power faults)
    - Unplug power from hashboards
    - Unplug fans from controller board
    - Unplug and remove inbound powersupply
    - Mark label on Powersupply as BAD with date
5. Use good power supply to identify good parts
    - Plug in just controller board, set and collect data from web
    - Plug in each fan, remove and label fan as BAD as you find them
    - Plug in hashboards and identify and record status as you find them
4. Identify and record unit status
    - DOA - nothing works no lights or fans
    - WEB - unit gets DHCP and able to access via WEB but no HASH status
    - FAN - unit reports FAN issues
    - ASIC - unit reports hash units but not 189 ASICS
    - AOK - unit reports all 189 ASICS and starts to hash
  
## S9 Setup
- [AntMiner S9 Setup Guide Part I by CryptoCrane](https://www.youtube.com/watch?v=sz-XZL77qqs)
- [AntMiner S9 Setup Guide Part II by CryptoCrane](https://www.youtube.com/watch?v=tUQcE6I7jzk)

## S9 Repair [Zeus Mining - ASIC Miner Repair](https://www.zeusbtc.com/ASIC-Miner-Repair/)
- [Antminer S9 hash board repair guide pdf](./S9hashBoardRepairGuide.pdf)
- [Antminer S9 hash board repair and fault diagnosis video tutorial](https://www.youtube.com/watch?v=5WH7g61d90w)
- [Antminer S9 hash board repair and fault diagnosis video tutorial 2018](https://www.youtube.com/watch?v=yAiaHwRkrC4)
  - [DC mode to probe test points](https://youtu.be/yAiaHwRkrC4?t=260)
  - [Probe CLK CO RI BO RST test points](https://youtu.be/yAiaHwRkrC4?t=277)
  - [Expected voltage chart](https://youtu.be/yAiaHwRkrC4?t=279)
  - [450 C heat gun 1cm distance for 10 sec](https://youtu.be/yAiaHwRkrC4?t=299)
  - [Remove heat sink and chip with same technique](https://youtu.be/yAiaHwRkrC4?t=325)
  - [Add tin solder paste to replacement chip](https://youtu.be/yAiaHwRkrC4?t=332)
  - [Flow tin solder paste with 450 C heat gun 10 cm distance](https://youtu.be/yAiaHwRkrC4?t=344)
  - [Place and align chip on board](https://youtu.be/yAiaHwRkrC4?t=353)
  - [450 C heat gun 1cm distance for 10 sec](https://youtu.be/yAiaHwRkrC4?t=358)
  - [Check chip alignment](https://youtu.be/yAiaHwRkrC4?t=366)
  - [Cool and test hashboard](https://youtu.be/yAiaHwRkrC4?t=369)
  - [Reheat and Attach front heatsink](https://youtu.be/yAiaHwRkrC4?t=381)
  - [Apply thermal black glue to chip, reheat heatsink and place on back of chip](https://youtu.be/yAiaHwRkrC4?t=387)
  - [Test points are for NEG lead](https://youtu.be/yAiaHwRkrC4?t=405)
  - [ASIC chip number serial pattern](https://youtu.be/yAiaHwRkrC4?t=412)
  - [ASIC chip next chip signal directions](https://youtu.be/yAiaHwRkrC4?t=416)

## Spares
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
- [tbd]()
