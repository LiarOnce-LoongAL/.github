# LiarOnce's Built Distributions for LoongArch
<img src="aosc-os-flag_compressed.png" width=120 height=30 /> <img src="https://img.shields.io/static/v1?style=for-the-badge&message=Arch+Linux&color=1793D1&logo=Arch+Linux&logoColor=FFFFFF&label=" /> <img src="https://img.shields.io/static/v1?style=for-the-badge&message=Debian&color=A81D33&logo=Debian&logoColor=FFFFFF&label=" /> <img src="https://img.shields.io/static/v1?style=for-the-badge&message=Deepin&color=007CFF&logo=deepin&logoColor=FFFFFF&label=" />

## 编译主机硬件配置 / Build Machine Specs
可用于装机参考/It can be used as a reference for PC installation  
信创兼容机，整体配置可接近信创PC  
**其中带*硬件均可替换为信创名单内硬件，带!硬件为当前的接口暂无完整国产方案或目前的硬件类型暂无国产化替代（非硬件本身）[^2]**  

|          类型           | 型号                                                         |
| :---------------------: | :----------------------------------------------------------- |
|       处理器(CPU)       | Loongson 3A6000 (8-cores, up-to 2.5GHz)                      |
|      桥片(Chipset)      | Loongson 7A2000 [^9]                                              |
|       *显卡(GPU)[^8]        | **AMD Radeon R7 360 (2GB GDDR5, Low-Profile, Current)[^7]** <br /> AMD Radeon Pro WX 2100 (2GB GDDR5, Low-Profile) [^3] <br />AMD Radeon R5 340 (1GB GDDR5, Low-Profile, Alternative)[^4] <br /> AMD Radeon 520 (2GB GDDR5, Low-Profile, Recommending Alternative)[^5]|
|    主板(Motherboard)    | XA61200                                                      |
|      *内存(Memory)      | UniIC SCC16GU03H2F1C-32AA DDR4 3200MT/s 16GB x2 (Total 32GB) |
|     *固态硬盘(SSD)      | Kioxia RC10 500G (NVMe, System) <br /> Samsung PM961 (NVMe, Source Code Data)|
|     *散热器(Cooler)     | DeepCool AN600 with Honeywell PTM7950 [^1]                   |
| *机箱风扇(External Fan) | ID-COOLING 80*25(mm)                                         |
|   有线网卡(Ethernet)    | Realtek RTL8111H (Integrated)                                |
|  *!有线网卡(Ethernet)   | Realtek RTL8125B (Mini-PCIe)                                 |
|  *!无线网卡(Wireless)   | Intel Wireless AC 9260                                       |
|     *机箱(Chassis)      | QuickPC (OEM-like, Low-Profile)                              |
|  *!电源(Power Supply)   | FSP Group FSP350-701UJ (350 watt, 80PLUS Bronze, with TFX to FLEX Converter) [^6]|

[^1]: 需使用部分非原装零件安装 Need to be used some non original accessories for installation https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/cooler.md
[^2]: 例如当前消费端常见的国产 WiFi 6 网卡爱科微的 AIC8800 系列，该网卡接口常见为 USB 和 SDIO，并无 M.2 接口版本。
[^3]: 因龙芯平台与 AMD Polaris Lexa 架构的兼容性问题，附带 Linux 内核参数为: `amdgpu.dpm=0 pcie_aspm=off`
[^4]: 附带 Linux 内核参数为: `amdgpu.si_support=1 radeon.si_support=0 pcie_aspm=off`
[^5]: 该卡曾常见于现有各类信创台式机产品中，兼容性最好，可使用 R5 340 相同的内核参数
[^6]: TFX 机箱使用 FLEX 电源需定制转接板，当前价格为 CNY￥ 100 
[^7]: 该卡的半高版本相当少见，铭牌为 PSTHD，来源应该是 OEM 工控机，内核参数为`amdgpu.cik_support=1 radeon.cik_support=0 amdgpu.sg_display=0 pcie_aspm=off`  
[^8]: 由于龙芯平台的 ACPI 休眠机制不完善，若使用 AMD 显卡均需关闭动态断电功能 (添加内核参数 `amdgpu.runpm=0`)   
[^9]: 由于体质问题，为保证稳定性建议更换其原装散热片 (适用于 XA61200/XA612A0 主板) https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/chipset.md
