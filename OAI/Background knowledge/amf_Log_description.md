# E2E amf Log 

> AMF (Access and Mobility Management Function)

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

#### 說明
```
[amf_sbi] [info] Send HTTP message to http://oai-nrf:8080/nnrf-nfm/v1/nf-instances/2d504252-5ab5-4289-a6bb-e1c05b5b6bd6
# AMF 正在向 NRF 發送 HTTP PATCH 請求，告訴 NRF 自己這個網路功能 (NF) 實例的最新狀態。

[amf_sbi] [info] HTTP message Body: [{"op":"replace","path":"/nfStatus","value":"REGISTERED"}]
# 代表 AMF 成功在 NRF 上保持註冊狀態，讓核心網的其他元件（如 SMF）需要時能透過 NRF 找到這個 AMF。

Get response with HTTP code (204)
# 收到 HTTP 204 (No Content) 是一個成功的回應，代表 NRF 已經接受了更新。


[amf_app] [debug] Set a timer to the next Heart-beat (10)
#  AMF 設定下一次心跳的計時器（每 10 秒觸發一次）。
```

