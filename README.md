# Parse du_stats_XXX.txt of each UE DL/UL Tput, BLER, and MCS

online tool => https://dustinchen26.github.io/parse_du3

## Example
```
Please paste the whole du_stats_XXX.txt content below, then it will parse the DL/UL Tput, BLER, MCS.
formula 1: DL-BLER = DL-RETX / (DL-RETX + DL-TX)
formula 2: UL-BLER = UL-CRC-FAIL / (UL-CRC-SUCC + UL-CRC-FAIL)

【Input】
---------------------------------------------------------------------------------------------
                       UE Instantaneous Statistics
---------------------------------------------------------------------------------------------
UE-ID     BEAM-ID   CSIRS-PORT   PCELL-ID  DL-PKT-RX   DL-TPT    UL-PKT-TX UL-TPT    DL-LC-1   DL-LC-2   DL-LC-3   DL-LC-4   UL-LC-1   UL-LC-2   UL-LC-3   UL-LC-4   DL-PADDING  UL-PADDING  DL-PRB    UL-PRB    NUM-SR    NUM-BSR-TMR    SCELL-ACT-CE   TA-CE     NUM-TA-TMR   TA        
17028     0         0            1         0           0.0000    0         0.0000    0.0000    0.0000    0.0000    0.0000    0.0000    0.0000    0.0000    0.0000    0.0000      0.1143      0         16        672       0              0              0         0            0         
17030     0         0            1         26          0.0020    11421     1.4805    0.0024    0.0000    0.0000    0.0000    1.4844    0.0000    0.0000    0.0000    0.0005      5.9686      1         60        596       0              0              0         0            0         

---------------------------------------------------------------------------------------------
                       UE MAC-Scheduler Instantaneous Statistics
---------------------------------------------------------------------------------------------
UE-ID   CELL-ID   ON-SUL   DL-TX   DL-RETX   ACK-TB[0] NACK-TB[0]  BLER-TB[0]  DTX-TB[0] ACK-TB[1] NACK-TB[1]  BLER-TB[1]  DTX-TB[1] DL-MCS  DL-RI-PER   DL-CQI-PER     UL-RX   UL-RETX  UL-CRC-SUCC   UL-CRC-FAIL   UL-CRC-DTX   UL-CQI  UL-MCS  UL-RI   NUM-BSR   SHR-BSR ST-BSR  LNG-BSR LT-BSR  NUM-CSI   NUM-SRS   
17028   1         0        0       0         0         0           0           0         0         0           0           0         0       0           0              672     0        673           0             0            12      9       0       673       673     0       0       0       0         0         
17030   1         0        67      2         66        2           3           0         0         0           0           0         7       1           8              12853   22       12845         14            0            7       8       0       12529     7724    0       4805    0       0         0         

【Output】
UE-ID=17028   DL-TPT=0.0000  UL-TPT=0.0000  
UE-ID=17030   DL-TPT=0.0020  UL-TPT=1.4805  
UE-ID=17028   DL-TX=0       DL-RETX=0       DL-BLER=NaN     DL-MCS=0       UL-CRC-SUCC=673     UL-CRC-FAIL=0       UL-BLER=0.0000  UL-MCS=9       
UE-ID=17030   DL-TX=67      DL-RETX=2       DL-BLER=0.0290  DL-MCS=7       UL-CRC-SUCC=12845   UL-CRC-FAIL=14      UL-BLER=0.0011  UL-MCS=8   
```