CMDLINE: "./nr-softmodem" "-O" "../../../targets/PROJECTS/GENERIC-NR-5GC/CONF/gnb.sa.band78.fr1.106PRB.usrpb210.conf" "--gNBs.[0].min_rxtxtime" "6" "--rfsim" 
[CONFIG] function config_libconfig_init returned 0
[UTIL]   running in SA mode (no --phy-test, --do-ra, --nsa option present)
[OPT]    OPT disabled
[HW]     Version: Branch: HEAD Abrev. Hash: 92980ceb72 Date: Sun Nov 16 07:21:47 2025 +0000
[GNB_APP] Initialized RAN Context: RC.nb_nr_inst = 1, RC.nb_nr_macrlc_inst = 1, RC.nb_nr_L1_inst = 1, RC.nb_RU = 1, RC.nb_nr_CC[0] = 1
[NR_PHY] Initializing gNB RAN context: RC.nb_nr_L1_inst = 1 
[NR_PHY] Registered with MAC interface module (0x629b003c2b70)
[NR_PHY] Initializing NR L1: RC.nb_nr_L1_inst = 1
[NR_PHY] L1_RX_THREAD_CORE -1 (15)
[NR_PHY] TX_AMP = 519 (-36 dBFS)
[PHY]    No prs_config configuration found..!!
[GNB_APP] pdsch_AntennaPorts N1 1 N2 1 XP 1 pusch_AntennaPorts 1
[GNB_APP] minTXRXTIME 6
[GNB_APP] SIB1 TDA 1
[GNB_APP] CSI-RS 1, SRS 1, report type 0 (ssb_rsrp), 256 QAM may be on, delta_MCS off, maxMIMO_Layers -1, HARQ feedback enabled, num DLHARQ:16, num ULHARQ:16
[GNB_APP] No RedCap configuration found
[GNB_APP] No PTRS configuration found
[GNB_APP] sr_ProhibitTimer 0, sr_TransMax 64, sr_ProhibitTimer_v1700 0, t300 400, t301 400, t310 2000, n310 10, t311 3000, n311 1, t319 400
[NR_MAC] Candidates per PDCCH aggregation level on UESS: L1: 0, L2: 2, L4: 0, L8: 0, L16: 0
[RRC]    Read in ServingCellConfigCommon (PhysCellId 0, ABSFREQSSB 641280, DLBand 78, ABSFREQPOINTA 640008, DLBW 106,RACH_TargetReceivedPower -96
[RRC]    absoluteFrequencySSB 641280 corresponds to 3619200000 Hz
[NR_MAC] TDD period index = 6, based on the sum of dl_UL_TransmissionPeriodicity from Pattern1 (5.000000 ms) and Pattern2 (0.000000 ms): Total = 5.000000 ms
[UTIL]   threadCreate() for MAC_STATS: creating thread with affinity ffffffff, priority 2
[NR_MAC] PUSCH Target 150, PUCCH Target 200, PUCCH Failure 10, PUSCH Failure 10
[NR_PHY] Copying 0 blacklisted PRB to L1 context
[NR_MAC] Set TX antenna number to 1, Set RX antenna number to 1 (num ssb 1: 80000000,0)
[NR_MAC] TDD period index = 6, based on the sum of dl_UL_TransmissionPeriodicity from Pattern1 (5.000000 ms) and Pattern2 (0.000000 ms): Total = 5.000000 ms
[NR_MAC] Set TDD configuration period to: 8 DL slots, 3 UL slots, 10 slots per period (NR_TDD_UL_DL_Pattern is 7 DL slots, 2 UL slots, 6 DL symbols, 4 UL symbols)
[NR_MAC] Configured 1 TDD patterns (total slots: pattern1 = 10, pattern2 = 0)
[NR_PHY] Set TDD Period Configuration: 2 periods per frame, 20 slots to be configured (8 DL, 3 UL)
[NR_PHY] TDD period configuration: slot 0 is DOWNLINK
[NR_PHY] TDD period configuration: slot 1 is DOWNLINK
[NR_PHY] TDD period configuration: slot 2 is DOWNLINK
[NR_PHY] TDD period configuration: slot 3 is DOWNLINK
[NR_PHY] TDD period configuration: slot 4 is DOWNLINK
[NR_PHY] TDD period configuration: slot 5 is DOWNLINK
[NR_PHY] TDD period configuration: slot 6 is DOWNLINK
[NR_PHY] TDD period configuration: slot 7 is FLEXIBLE: DDDDDDFFFFUUUU
[NR_PHY] TDD period configuration: slot 8 is UPLINK
[NR_PHY] TDD period configuration: slot 9 is UPLINK
[NR_MAC] Command line parameters for OAI UE: -C 3619200000 -r 106 --numerology 1 --band 78 --ssb 516 
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
[NR_PHY] dlfreq:3619200 ulfreq:3619200 deltaduplex:0 khz, uldl_min_offset:0 khz
DL frequency 3619200000: band 78, UL frequency 3619200000
[PHY]    DL frequency 3619200000 Hz, UL frequency 3619200000 Hz: band 78, uldl offset 0 Hz
[PHY]    Initializing frame parms for mu 1, N_RB 106, Ncp 0
[PHY]    Init: N_RB_DL 106, first_carrier_offset 1412, nb_prefix_samples 144,nb_prefix_samples0 176, ofdm_symbol_size 2048
[NR_MAC] TDA index 0: start 0 length 13 k2 6
[NR_MAC] TDA index 1: start 0 length 12 k2 6
[NR_MAC] TDA index 2: start 10 length 3 k2 6
[NR_RRC] SIB1 freq: offsetToPointA 86
[GNB_APP] F1AP: gNB idx 0 gNB_DU_id 3584, gNB_DU_name gNB-OAI, TAC 1 MCC/MNC/length 1/1/2 cellID 12345678
[GNB_APP] ngran_DU: Configuring Cell 0 for TDD
[GNB_APP] SDAP layer is disabled
[GNB_APP] Data Radio Bearer count 1
[GNB_APP] Parsed IPv4 address for NG AMF: 192.168.70.129
[UTIL]   threadCreate() for TASK_SCTP: creating thread with affinity ffffffff, priority 50
[X2AP]   X2AP is disabled.
[UTIL]   threadCreate() for TASK_NGAP: creating thread with affinity ffffffff, priority 50
[UTIL]   threadCreate() for TASK_RRC_GNB: creating thread with affinity ffffffff, priority 50
[NGAP]   Starting NGAP layer
[NGAP]   Registered new gNB[0] and macro gNB id 3584
[NGAP]   [gNB 0] check the amf registration state
[GTPU]   Configuring GTPu
[GTPU]   SA mode 
[GTPU]   Configuring GTPu address : 192.168.70.129, port : 2152
[GTPU]   Initializing UDP for local address 192.168.70.129 with port 2152
[GTPU]   Created gtpu instance id: 90
[UTIL]   threadCreate() for GTPrx_90: creating thread with affinity ffffffff, priority 50
[NR_RRC] Entering main loop of NR_RRC message task
[NR_RRC] Accepting new CU-UP ID 3584 name gNB-OAI (assoc_id -1)
[UTIL]   threadCreate() for TASK_GNB_APP: creating thread with affinity ffffffff, priority 50
[NGAP]   Send NGSetupRequest to AMF
[NGAP]   3584 -> 0000e000
[NGAP]   Served GUAMIs for AMF OAI-AMF (assoc_id=5):
[NGAP]    GUAMI:
[NGAP]      PLMN: MCC=001, MNC=01
[NGAP]      AMF Region ID: 1
[NGAP]      AMF Set ID: 1
[NGAP]      AMF Pointer: 1
[NGAP]   Supported PLMN 0: MCC=001 MNC=01
[NGAP]   Supported slice (PLMN 0): SST=0x01 SD=000
[NGAP]   Received NGSetupResponse from AMF
[UTIL]   threadCreate() for TASK_GTPV1_U: creating thread with affinity ffffffff, priority 50
[GNB_APP] [gNB 0] Received NGAP_REGISTER_GNB_CNF: associated AMF 1
[NR_RRC] Received F1 Setup Request from gNB_DU 3584 (gNB-OAI) on assoc_id -1
[NR_RRC] Accepting DU 3584 (gNB-OAI), sending F1 Setup Response
[NR_RRC] DU uses RRC version 17.3.0
[MAC]    received F1 Setup Response from CU (null)
[MAC]    CU uses RRC version 17.3.0
[MAC]    Clearing the DU's UE states before, if any.
[NR_RRC] cell PLMN 001.01 Cell ID 12345678 is in service
[MAC]    received gNB-DU configuration update acknowledge
[UTIL]   threadCreate() for time source iq samples: creating thread with affinity ffffffff, priority 2
[UTIL]   time manager configuration: [time source: iq_samples] [mode: standalone] [server IP: 127.0.0.1} [server port: 7374] (server IP/port not used)
[PHY]    RU clock source set as internal
[PHY]    number of L1 instances 1, number of RU 1, number of CPU cores 16
[PHY]    Initialized RU proc 0 (,synch_to_ext_device),
[PHY]    RU thread-pool core string -1,-1 (size 2)
[UTIL]   threadCreate() for Tpool0_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool1_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for ru_thread: creating thread with affinity ffffffff, priority 97
[PHY]    Starting RU 0 (,synch_to_ext_device) on cpu 0
[PHY]    Initializing frame parms for mu 1, N_RB 106, Ncp 0
[PHY]    Init: N_RB_DL 106, first_carrier_offset 1412, nb_prefix_samples 144,nb_prefix_samples0 176, ofdm_symbol_size 2048
[PHY]    fp->scs=30000
[PHY]    fp->ofdm_symbol_size=2048
[PHY]    fp->nb_prefix_samples0=176
[PHY]    fp->nb_prefix_samples=144
[PHY]    fp->slots_per_subframe=2
[PHY]    fp->samples_per_subframe_wCP=57344
[PHY]    fp->samples_per_frame_wCP=573440
[PHY]    fp->samples_per_subframe=61440
[PHY]    fp->samples_per_frame=614400
[PHY]    fp->dl_CarrierFreq=3619200000
[PHY]    fp->ul_CarrierFreq=3619200000
[PHY]    fp->Nid_cell=0
[PHY]    fp->first_carrier_offset=1412
[PHY]    fp->ssb_start_subcarrier=0
[PHY]    fp->Ncp=0
[PHY]    fp->N_RB_DL=106
[PHY]    fp->numerology_index=1
[PHY]    fp->nr_band=78
[PHY]    fp->ofdm_offset_divisor=8
[PHY]    fp->threequarter_fs=0
[PHY]    fp->sl_CarrierFreq=0
[PHY]    fp->N_RB_SL=0
[NR_PHY] nb_tx_streams 1, nb_rx_streams 1, num_Beams_period 1
[PHY]    Setting RF config for N_RB 106, NB_RX 1, NB_TX 1
[PHY]    tune_offset 0 Hz, sample_rate 61440000 Hz
[PHY]    Channel 0: setting tx_gain offset 12, tx_freq 3619200000 Hz
[PHY]    Channel 0: setting rx_gain offset 102, rx_freq 3619200000 Hz
[HW]     Running as server waiting opposite rfsimulators to connect
Initializing random number generator, seed 9954150170475230350
[HW]     [RAU] has loaded RFSIMULATOR device.
[PHY]    RU 0 Setting N_TA_offset to 800 samples (UL Freq 3600120, N_RB 106, mu 1)
[PHY]    Signaling main thread that RU 0 is ready, sl_ahead 6
[PHY]    L1 configured without analog beamforming
[PHY]    Attaching RU 0 antenna 0 to gNB antenna 0
[UTIL]   threadCreate() for Tpool0_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool1_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool2_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool3_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool4_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool5_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool6_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for Tpool7_-1: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for L1_rx_thread: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for L1_tx_thread: creating thread with affinity ffffffff, priority 97
[UTIL]   threadCreate() for L1_stats: creating thread with affinity ffffffff, priority 1
TYPE <CTRL-C> TO TERMINATE
[PHY]    got sync (L1_stats_thread)
[PHY]    got sync (ru_thread)
[PHY]    RU 0 rf device ready
[PHY]    RU 0 RF started cpu_meas_enabled 0
[HW]     No connected device, generating void samples...
[PHY]    Command line parameters for OAI UE: -C 3619200000 -r 106 --numerology 1 --ssb 516 
[NR_MAC] Frame.Slot 128.0

[HW]     Client connects from ::ffff:127.0.0.1:22661
[NR_MAC] Frame.Slot 256.0

[NR_PHY] [RAPROC] 339.19 Initiating RA procedure with preamble 55, energy 43.5 dB (I0 0, thres 120), delay 0 start symbol 8 freq index 0
[NR_MAC] 339.19 UE RA-RNTI 0113 TC-RNTI 8e03: initiating RA procedure
[NR_MAC] UE 8e03: Msg3 scheduled at 340.19 (340.10 TDA 0) start 0 RBs 8
[NR_MAC] UE 8e03: 340.10 Generating RA-Msg2 DCI, RA RNTI 0x113, state 1, preamble_index(RAPID) 55, timing_offset = 0 (estimated distance 0.0 [m])
[NR_MAC] 340.10 Send RAR to RA-RNTI 0113
[NR_MAC]  340.19 PUSCH with TC_RNTI 0x8e03 received correctly
[MAC]    [RAPROC] Received SDU for CCCH length 6 for UE 8e03
[RLC]    Activated srb0 for UE 36355
[RLC]    Added srb 1 to UE 36355
[NR_MAC] Activating scheduling Msg4 for TC_RNTI 0x8e03 (state WAIT_Msg3)
[NR_RRC] Decoding CCCH: RNTI 8e03, payload_size 6
[NR_RRC] [--] (cellID 0, UE ID 1 RNTI 8e03) Create UE context: CU UE ID 1 DU UE ID 36355 (rnti: 8e03, random ue id 24656d4761000000)
[RRC]    activate SRB 1 of UE 1
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send RRC Setup
[NR_MAC] UE 8e03 Generate Msg4: feedback at  341.17, payload 225 bytes, next state nrRA_WAIT_Msg4_MsgB_ACK
[NR_MAC]  341.17 UE 8e03: Received Ack of Msg4. CBRA procedure succeeded (UE Connected)
[NR_MAC] Adding new UE context with RNTI 0x8e03
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRCSetupComplete (RRC_CONNECTED reached)
[NGAP]   Selected PLMN in the NG Initial UE Message: MCC=001 MNC=01
[NGAP]   UE 1: Selected AMF 'OAI-AMF' (assoc_id 5) through selected PLMN MCC=001 MNC=01
[NGAP]   Create UE context (ID 1) for AMF 'OAI-AMF' (assoc_id 5)
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send DL Information Transfer [42 bytes]
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRC UL Information Transfer [24 bytes]
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send DL Information Transfer [21 bytes]
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRC UL Information Transfer [60 bytes]
[NGAP]   NGAP_FIND_PROTOCOLIE_BY_ID ie is NULL (searching for ie: 110)
[NGAP]   NGAP_FIND_PROTOCOLIE_BY_ID ie is NULL (searching for ie: 71)
[NGAP]   AllowedNSSAI.list.count 1
[NR_RRC] [--] (cellID bc614e, UE ID 1 RNTI 8e03) Selected security algorithms: ciphering 0, integrity 2
[NR_RRC] [UE 8e03] Saved security key 00
[NR_RRC] UE 1 Logical Channel DL-DCCH, Generate SecurityModeCommand (bytes 3)
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received Security Mode Complete
[NR_RRC] UE 1: Logical Channel DL-DCCH, Generate NR UECapabilityEnquiry (bytes 8, xid 1)
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received UE capabilities
[NR_RRC] Send message to ngap: NGAP_UE_CAPABILITIES_IND
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send DL Information Transfer [53 bytes]
[NR_RRC] Send message to sctp: NGAP_InitialContextSetupResponse
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRC UL Information Transfer [13 bytes]
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRC UL Information Transfer [35 bytes]
[NGAP]   PDUSESSIONSetup initiating message
[NR_RRC] UE 1: received PDU Session Resource Setup Request
[NR_RRC] Added QoS flow with qfi=1, total number of QoS flows = 1
[NR_RRC] Added PDU Session 10, (total nb of sessions = 1)
[NR_RRC] Bearer Context Setup: PDU Session ID=10, incoming TEID=0x00000002, Addr=192.168.70.134
[NR_RRC] Added DRB 1 to established list (PDU Session ID=10, total DRBs = 1)
[NR_RRC] UE 1: added DRB 1 for PDU session ID 10
[NR_RRC] [--] (cellID bc614e, UE ID 1 RNTI 8e03) selecting CU-UP ID 3584 based on exact NSSAI match (1:0xffffff)
[RRC]    UE 1 associating to CU-UP assoc_id -1 out of 1 CU-UPs
[E1AP]   UE 1: add PDU session ID 10 (1 bearers)
[GTPU]   [90] UE ID 1: Create tunnel TEID incoming 0xdb8fad60 outgoing 0x2 to remote IPv4 192.168.70.134, IPv6 ::, port 2152
[SDAP]   Default DRB for the created SDAP entity: DRB 1 
[PDCP]   Added DRB 1 to UE ID 1
[RRC]    activate SRB 2 of UE 1
[RLC]    Added srb 2 to UE 36355
[RLC]    Added drb 1 to UE 36355
[RLC]    Added DRB to UE 36355
[NR_RRC] SRS configured with 1 ports
[RRC]    UE 1 trigger UE context setup request with 1 DRBs
[RRC]    UE 8e03 replacing existing CellGroupConfig with new one received from DU
[E1AP]   UE 1: updating PDU session ID 10 (1 bearers)
[PDCP]   DRB 1 re-established
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Generate RRCReconfiguration (bytes 339, xid 3)
[NR_RRC] Received E1AP Bearer Context Modification Response for UE CU-CP ID 1
[RRC]    UE 1: PDU session ID 10 modified 1 bearers
[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRCReconfigurationComplete
[NR_RRC] PDU Session Setup: ID=10, outgoing TEID=0xdb8fad60, Addr=192.168.70.129
[NR_RRC] NGAP_PDUSESSION_SETUP_RESP: sending the message
[NR_MAC] DU received confirmation of successful RRC Reconfiguration
[NGAP]   Encoded PDU Session Transfer (10): TEID=0xdb8fad60, Addr=192.168.70.129
[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 61 dB PCMAX 20 dBm, average RSRP -44 (5 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 17/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.07290 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 41/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.07290 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            758 RX           1156 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              3 RX             54 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 18/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.06561 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 54/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.01853 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            777 RX           1416 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              3 RX             54 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 19/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.05905 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 66/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00523 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            798 RX           1656 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              3 RX             54 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 22/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.04305 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 85/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00133 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            859 RX           2162 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              6 RX            108 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 23/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.03874 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 97/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00038 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            878 RX           2402 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              6 RX            108 bytes

[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 24/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.03487 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 110/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00010 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            899 RX           2662 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              6 RX            108 bytes

[NR_MAC] Frame.Slot 128.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 26/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.02824 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 123/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00002 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            939 RX           2922 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              6 RX            108 bytes

[NR_MAC] Frame.Slot 256.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 27/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.02542 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 136/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00001 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX            958 RX           3182 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              6 RX            108 bytes

[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 29/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.02288 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 154/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1000 RX           3664 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 30/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.02059 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 167/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1019 RX           3918 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 32/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.01668 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 180/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1059 RX           4172 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 33/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.01501 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 192/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1080 RX           4406 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 34/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.01351 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 205/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1099 RX           4658 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 36/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.01094 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 218/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1139 RX           4912 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 128.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 37/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00985 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 231/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1160 RX           5166 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 256.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 38/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00886 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 244/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1179 RX           5420 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 39/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00798 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 256/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1200 RX           5654 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 41/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00646 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 269/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1240 RX           5906 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX              9 RX            162 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 43/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00523 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 287/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1280 RX           6388 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 44/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00471 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 300/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1301 RX           6648 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 46/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00382 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 313/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1341 RX           6908 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 47/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00343 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 325/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1360 RX           7148 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 128.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 48/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00309 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 338/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1381 RX           7408 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 256.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 49/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00278 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 351/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1400 RX           7668 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 51/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00225 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 364/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1440 RX           7928 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 52/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00203 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 377/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1461 RX           8188 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 53/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00182 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 389/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1480 RX           8428 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 54/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00164 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 402/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1501 RX           8688 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 56/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00133 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 415/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1541 RX           8948 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 57/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00120 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 428/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1560 RX           9208 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 128.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 58/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00108 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 441/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1581 RX           9468 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 256.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 60/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00087 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 453/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1621 RX           9708 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 61/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00079 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 466/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1640 RX           9968 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 62/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00071 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 479/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1661 RX          10228 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 63/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00064 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 492/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1680 RX          10488 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 65/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00052 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 505/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1720 RX          10748 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 66/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00046 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 517/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1741 RX          10988 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes

[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 68/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00038 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 536/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1781 RX          11492 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 128.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 70/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00030 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 548/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1821 RX          11726 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 256.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 71/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00027 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 561/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1842 RX          11978 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 384.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 72/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00025 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 574/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1861 RX          12232 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 512.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 73/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00022 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 587/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1882 RX          12486 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 640.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 75/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00018 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 600/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1922 RX          12740 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 768.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 76/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00016 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 612/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1941 RX          12974 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 77/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00015 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 625/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1962 RX          13226 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[NR_RRC] [UL] (cellID bc614e, UE ID 1 RNTI 8e03) Received RRC UL Information Transfer [27 bytes]
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send DL Information Transfer [3 bytes]
[NR_MAC] Frame.Slot 0.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 52 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 81/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00012 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 645/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 1 (Qm 2 deltaMCS 0 dB) NPRB 13  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           2049 RX          13614 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX             17 RX             38 bytes
UE 8e03: LCID 4: TX             15 RX            270 bytes

[E1AP]   releasing UE 1
[GTPU]   [90] UE ID 1: Delete all tunnels (1 tunnels)
[NR_RRC] [DL] (cellID bc614e, UE ID 1 RNTI 8e03) Send RRC Release
[RRC]    UE 1: received bearer release complete
[RLC]    Remove UE 36355
[NR_RRC] removed UE CU UE ID 1/RNTI 8e03 
[NR_RRC] [--] (cellID bc614e, UE ID 1 RNTI 8e03) Remove UE context
[NR_MAC] Remove NR rnti 0x8e03
[NR_MAC] Frame.Slot 128.0

[NR_MAC] Frame.Slot 256.0

[HW]     Lost socket
[NR_MAC] Frame.Slot 384.0

^C
** Caught SIGTERM, shutting down
Returned from ITTI signal handler
[GNB_APP] stopping nr-softmodem
[PHY]    Killing gNB 0 processing threads
[PHY]    Stopping RU 0 processing threads
[PHY]    RU 0 RF device stopped
[GNB_APP] turned off RU rfdevice
Bye.
