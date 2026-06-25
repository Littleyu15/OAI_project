# E2E amf log 

> AMF (Access and Mobility Management Function)

## Table Of Content
- [CN5G log](#cn5g-log)
- [gNB log](#gnb-log)
- [UE log](#ue-log)




### CN5G log
> ```
> [2026-06-25 08:43:57.857] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:43:57.857] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:43:57.861] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:43:57.861] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:43:57.861] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:43:57.861] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:43:57.861] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> [2026-06-25 08:44:07.862] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:44:07.862] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:44:07.862] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:44:07.862] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:44:07.862] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:44:07.865] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:44:07.865] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:44:07.865] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:44:07.865] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:44:07.865] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> [2026-06-25 08:44:17.689] [amf_app] [info] 
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |----------------------------------------------------------------------gNBs' Information---------------------------------------------------------------------|
>    |  Index |               Status               |              Global Id             |              gNB Name              |                PLMN                |
>    |    1   |            Disconnected            |               0x0E00               |               gNB-OAI              |               001,01               |
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |---------------------------------------------------------------------UEs' Information----------------------------------------------------------------------|
>    |  Index |     5GMM State     |                IMSI/SUPI               |        GUTI        |   RAN UE NGAP ID   |   AMF UE NGAP ID   |        PLMN        |       Cell Id      |
>    |    1   |  5GMM-DEREGISTERED |             001010000000001            |00101010041185491008|        0x01        |        0x01        |       001,01       |      0000e014e     |
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
> [2026-06-25 08:44:17.866] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:44:17.866] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:44:17.866] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:44:17.866] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:44:17.866] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:44:17.868] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:44:17.868] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:44:17.869] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:44:17.869] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:44:17.869] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> [2026-06-25 08:44:27.869] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:44:27.869] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:44:27.869] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:44:27.869] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:44:27.869] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:44:27.871] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:44:27.871] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:44:27.872] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:44:27.872] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:44:27.872] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> ```



### gNB log
> ```
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |---------------------------------------------------------------------UEs' Information----------------------------------------------------------------------|
>    |  Index |     5GMM State     |                IMSI/SUPI               |        GUTI        |   RAN UE NGAP ID   |   AMF UE NGAP ID   |        PLMN        |       Cell Id      |
>    |    1   |  5GMM-DEREGISTERED |             001010000000001            |00101010041185491008|        0x01        |        0x01        |       001,01       |      0000e014e     |
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
> [2026-06-25 08:43:17.841] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:43:17.841] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:43:17.841] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:43:17.841] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:43:17.841] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:43:17.843] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:43:17.844] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:43:17.844] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:43:17.844] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:43:17.844] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> [2026-06-25 08:43:27.845] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:43:27.845] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:43:27.845] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:43:27.845] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:43:27.845] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:43:27.847] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:43:27.847] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:43:27.848] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:43:27.848] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:43:27.848] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> [2026-06-25 08:43:37.688] [amf_app] [info] 
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |----------------------------------------------------------------------gNBs' Information---------------------------------------------------------------------|
>    |  Index |               Status               |              Global Id             |              gNB Name              |                PLMN                |
>    |    1   |            Disconnected            |               0x0E00               |               gNB-OAI              |               001,01               |
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |---------------------------------------------------------------------UEs' Information----------------------------------------------------------------------|
>    |  Index |     5GMM State     |                IMSI/SUPI               |        GUTI        |   RAN UE NGAP ID   |   AMF UE NGAP ID   |        PLMN        |       Cell Id      |
>    |    1   |  5GMM-DEREGISTERED |             001010000000001            |00101010041185491008|        0x01        |        0x01        |       001,01       |      0000e014e     |
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
> [2026-06-25 08:43:37.848] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:43:37.848] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:43:37.848] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:43:37.848] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:43:37.848] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:43:37.851] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:43:37.851] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:43:37.851] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:43:37.851] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:43:37.851] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> ```

### UE log
> ```
> [2026-06-25 08:41:55.813] [ngap] [debug] Handle a SCTP Shutdown event (association id: 4)
> [2026-06-25 08:41:55.813] [ngap] [debug] Sending ITTI SCTP Shutdown event to TASK_AMF_N2
> [2026-06-25 08:41:55.814] [amf_n2] [info] Received SCTP Shutdown Event, handling
> [2026-06-25 08:41:55.814] [amf_n2] [debug] Handle NG Shutdown ...
> [2026-06-25 08:41:55.814] [amf_app] [debug] Key for UE context search: app_ue_ranid_1:amfid_1
> [2026-06-25 08:41:55.814] [amf_app] [debug] Trigger PDU Session UP Deactivation towards SMF
> [2026-06-25 08:41:55.814] [amf_n1] [warning] No NAS context with amf_ue_ngap_id 1
> [2026-06-25 08:41:55.814] [amf_n2] [warning] No existed nas_context with amf_ue_ngap_id(1)
> [2026-06-25 08:41:55.814] [amf_n2] [debug] Removed UE NGAP context with amf_ue_ngap_id 1
> [2026-06-25 08:41:55.814] [amf_n1] [warning] No NAS context with amf_ue_ngap_id 1
> [2026-06-25 08:41:55.814] [amf_n2] [warning] No existed nas_context with amf_ue_ngap_id(1)
> [2026-06-25 08:41:55.814] [amf_n2] [debug] Removed UE NGAP context with ran_ue_ngap_id 1, gnb_id 3584
> [2026-06-25 08:41:55.814] [amf_app] [debug] The gNB's info has been successfully updated!
> [2026-06-25 08:41:55.814] [amf_n2] [debug] Remove gNB with association id 4, gnb_id 0xe00
> [2026-06-25 08:41:55.814] [amf_app] [info] 
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |----------------------------------------------------------------------gNBs' Information---------------------------------------------------------------------|
>    |  Index |               Status               |              Global Id             |              gNB Name              |                PLMN                |
>    |    1   |            Disconnected            |               0x0E00               |               gNB-OAI              |               001,01               |
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |---------------------------------------------------------------------UEs' Information----------------------------------------------------------------------|
>    |  Index |     5GMM State     |                IMSI/SUPI               |        GUTI        |   RAN UE NGAP ID   |   AMF UE NGAP ID   |        PLMN        |       Cell Id      |
>    |    1   |  5GMM-DEREGISTERED |             001010000000001            |00101010041185491008|        0x01        |        0x01        |       001,01       |      0000e014e     |
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
> [2026-06-25 08:41:57.685] [amf_app] [info] 
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |----------------------------------------------------------------------gNBs' Information---------------------------------------------------------------------|
>    |  Index |               Status               |              Global Id             |              gNB Name              |                PLMN                |
>    |    1   |            Disconnected            |               0x0E00               |               gNB-OAI              |               001,01               |
>    |------------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
>    |---------------------------------------------------------------------UEs' Information----------------------------------------------------------------------|
>    |  Index |     5GMM State     |                IMSI/SUPI               |        GUTI        |   RAN UE NGAP ID   |   AMF UE NGAP ID   |        PLMN        |       Cell Id      |
>    |    1   |  5GMM-DEREGISTERED |             001010000000001            |00101010041185491008|        0x01        |        0x01        |       001,01       |      0000e014e     |
>    |-----------------------------------------------------------------------------------------------------------------------------------------------------------|
> 
> [2026-06-25 08:41:57.806] [amf_sbi] [info] Receive Update NF Instance Request, handling ...
> [2026-06-25 08:41:57.806] [amf_sbi] [debug] Send NF Update to NRF
> [2026-06-25 08:41:57.806] [amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
> [2026-06-25 08:41:57.806] [amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
> [2026-06-25 08:41:57.806] [amf_sbi] [debug] Send a simple HTTP request
> [2026-06-25 08:41:57.808] [amf_sbi] [info] Get response with HTTP code (204)
> [2026-06-25 08:41:57.808] [amf_sbi] [info] Could not get JSON content from the response
> [2026-06-25 08:41:57.809] [amf_app] [debug] Received SBI_UPDATE_NF_INSTANCE_RESPONSE
> [2026-06-25 08:41:57.809] [amf_app] [debug] Handle NF Update response
> [2026-06-25 08:41:57.809] [amf_app] [debug] Set a timer to the next Heart-beat (10)
> ```
