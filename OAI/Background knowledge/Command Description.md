```
sudo ninja nr-softmodem nr-uesoftmodem dfts ldpc params_libconfig
```
- `ninja` : compiler tool
- `nr-softmodem` : main code of 5G gNB in OAI *(OAI 中 5G gNB（基地台） 的主程式)*
- `nr-uesoftmodem` : main code of 5G UE in OAI *(OAI 中 5G UE（使用者） 的主程式)*
- `dfts` : (Discrete Fourier Transform Spread) module of **DFT-s-OFDM** Signal processing algorithms *(負責訊號處理演算法)*
- `ldpc` : (Low-Density Parity-Check)Channel Coding in 5G NR, doing error correction and error detection. *(負責在傳輸數據時進行糾錯與檢錯)*
- `params_libconfig` : Function library of OAI loading Configuration Files *(OAI 用於載入設定檔的函式庫)*
