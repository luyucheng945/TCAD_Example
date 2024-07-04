# TCAD模擬: 32 nm 1.8V IO 電晶體
此模擬的目的是模擬出Intel 32 nm 製程的 1.8 V IO 電晶體的電性。
參考文獻DOI: 10.1109/IEDM.2009.5424258.

## 元件結構
從文獻中可以推斷出元件大概的尺寸，但摻雜分布無法得知，所以摻雜分布是我自己設計的。
![image]([Device Structure of 32 nm IO transistor.png](https://github.com/luyucheng945/TCAD/blob/main/Device%20Structure%20of%2032%20nm%20IO%20transistor.png))

## 模擬結果

| |Lch (nm)|EOT (nm)|Vdd (V)|Idsat (mA/um)|Ioff (nA/um)|
|Literature|170|4|1.8|0.68|0.1|
|Simulation|170|4|1.8|0.54|4.6|

結果顯示，模擬出來的Idsat比文獻低了20%，Ioff比文獻高了450%。
Idsat低估的原因可能是沒有對通道考慮拉伸應力，從而低估電子遷移率。
Ioff高估的原因可能是摻雜分布設計不良，導致BTBT，造成漏電流。
