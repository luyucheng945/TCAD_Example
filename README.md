# TCAD simulation: 32 nm 1.8V IO transistor
此模擬的目的是模擬出Intel 32 nm 製程的 1.8 V IO 電晶體的電性。
參考文獻DOI: 10.1109/IEDM.2009.5424258。  

The purpose of this simulation is to simulate the electrical properties of a 1.8 V IO transistor based on Intel's 32 nm process.
Reference DOI: 10.1109/IEDM.2009.5424258.

## Device Structure
從文獻中可以推得電晶體尺寸，但摻雜分布無法得知，所以摻雜分布是我自己設計的。  

The dimensions of the transistor can be inferred from the literature, but the doping profile is not known, so I designed the doping profile myself.
![image](https://github.com/luyucheng945/TCAD/blob/main/Device%20Structure%20of%2032%20nm%20IO%20transistor.png)

## Physical Model
考慮量子校正、本徵載子濃度校正、低場遷移率、高場遷移率校正、SRH複合、BTBT穿隧與Impact ionization效應。
其中，低場遷移率包含基本的聲子散射、庫倫散射、表面粗糙度散射與High-K Metal Gate的遠距聲子散射、遠距庫倫散射、遠距偶極子散射。  

Consider quantum correction, intrinsic carrier concentration correction, low field mobility, high field mobility correction, SRH recombination, BTBT tunneling and Impact ionization effects. Among them, low-field mobility includes basic phonon scattering, Coulomb scattering, surface roughness scattering and High-K Metal Gate's remote phonon scattering, remote Coulomb scattering, and remote dipole scattering.
## Simulation Results

| |Lch (nm)|EOT (nm)|Vdd (V)|Idsat (mA/um)|Ioff (nA/um)|
| -- | -- | -- | -- | -- | -- |
|Literature|170|4|1.8|0.68|0.1|
|Simulation|170|4|1.8|0.54|4.6|

結果顯示，模擬出來的Idsat比文獻低了20%，Ioff比文獻高了450%。
Idsat低估的原因可能是沒有對通道考慮拉伸應力，從而低估電子遷移率。
Ioff高估的原因可能是摻雜分布設計不良，導致BTBT，造成漏電流。  

The results show that the simulated Idsat is 20% lower than the literature, and the Ioff is 450% higher than the literature.
The reason for Idsat's underestimation may be that tensile stress is not considered for the channel, thereby underestimating the electron mobility.
The reason for the overestimation of Ioff may be poor doping distribution design, resulting in BTBT, resulting in leakage current.
