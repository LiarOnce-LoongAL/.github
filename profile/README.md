# LiarOnce's Built Distributions for LoongArch
|   Flags   |   ![](./aosc-os-flag_compressed.png) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Arch+Linux&color=1793D1&logo=Arch+Linux&logoColor=FFFFFF&label=) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Debian&color=A81D33&logo=Debian&logoColor=FFFFFF&label=) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Deepin&color=007CFF&logo=deepin&logoColor=FFFFFF&label=)   |
| ---- | ---- |

## 编译主机硬件配置 / Build Machine Specs
可用于装机参考/It can be used as a reference for PC installation  
信创兼容机，整体配置可接近信创PC  
**其中带*硬件均可替换为信创名单内硬件，带!硬件为当前的接口暂无完整国产方案或目前的硬件类型暂无国产化替代（非硬件本身）**  

|          类型           | 型号                                                         |
| :---------------------: | :----------------------------------------------------------- |
|       处理器(CPU)       | Loongson 3A6000 (4-cores/8-threads, up-to 2.5GHz)                      |
|      桥片(Chipset)      | Loongson 7A2000 [^2]                                              |
|       *显卡(GPU)[^5]    | **AMD Radeon Pro WX 2100 (2GB GDDR5, Low-Profile, Current)** |
|    主板(Motherboard)    | XA61200                                                      |
|      *内存(Memory)      | UniIC SCC16GU03H2F1C-32AA DDR4 3200MT/s 16GB x2 (Total 32GB) |
|     *固态硬盘(SSD)      | ZHITAI TiPlus 5000 1TB (NVMe, System for AOSC OS) <br /> Kingston NV3 1TB (NVMe, Data) |
|     *散热器(Cooler)     | Thermalright SI-100 with Honeywell PTM7950 [^4]                   |
| *机箱风扇(External Fan) | ID-COOLING XF-12025-K <br /> ID-COOLING NO-8025-SD           |
|   有线网卡(Ethernet)    | Realtek RTL8111H (Integrated)                                |
|  *!有线网卡(Ethernet)   | Realtek RTL8125B (Mini-PCIe)                                 |
|  *有线网卡(Ethernet)   | Mellanox ConnectX-4 Lx MCX4421A-ACAN (PCIe x8)               |
|  *无线网卡(Wireless)   | Intel Wireless AC 9260 (M.2 Key A+E)                         |
|     *机箱(Chassis)      | Great Wall ShangQi R10 (长城商祺R10，mATX and Retail)        |
|  *!电源(Power Supply)   | XIGMATEK XTK-550 (550 watt, 80PLUS White)                   |
|  *！其他(Others)         | ASUS DRW-24D5MT <br /> 8BitDo Ultimate 2.4G Wireless Controller <br /> Logitech MX Mechanical Mini(Kailh CHOC Brown) <br /> Logitech MX Master 3 |

[^2]: 由于体质问题，为保证稳定性建议更换其原装散热片 (适用于 XA61200/XA612A0 主板) https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/chipset.md
[^4]: 需使用部分非原装零件安装 https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/cooler.md
[^5]: 由于龙芯平台的 ACPI 休眠机制不完善，若使用 AMD 显卡均需关闭动态断电功能 (添加内核参数 `amdgpu.runpm=0`)   
