# MTK UE Manual

### Lock NR Cell through ELT
1. Enter flight mode
2. Choose Lock NR Cell in command line : MOD_L4C(for SIM1)、MOD_L4C_2(for SIM2)
3. Fill in AT command : AT+EMMCHLCK=1,11,0,==630048==,==0==. 630048 is SSB ARFCN. 0 is PCI.
4. If you don't want to lock cell id then use this AT command : AT+EMMCHLCK=1,11,0,630048
5. Press `send` to activate
