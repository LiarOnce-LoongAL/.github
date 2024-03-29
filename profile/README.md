# LiarOnce's Built Distributions for LoongArch

## 编译主机硬件配置 / Build Machine Specs
可用于装机参考/It can be used as a reference for PC installation  
信创兼容机，整体配置可接近信创PC  
**其中带*硬件均可替换为信创名单内硬件，带!硬件为当前的接口暂无完整国产方案或目前的硬件类型暂无国产化替代（非硬件本身）[^2]**  

|           类型          | 型号                                                         |
| :---------------------: | :----------------------------------------------------------- |
|      处理器(CPU)        | Loongson 3A6000 (8-cores, up-to 2.5GHz)                      |
|     桥片(Chipset)       | Loongson 7A2000                                              |
|       *显卡(GPU)        | AMD Radeon Pro WX 2100 (2GB GDDR5, Low-Profile)              |
|   主板(Motherboard)     | XA61200                                                      |
|      *内存(Memory)      | UniIC SCC16GU03H2F1C-32AA DDR4 3200MT/s 16GB x2 (Total 32GB) |
|     *固态硬盘(SSD)      | Kioxia RC10 500G (NVMe, System)                              |
|     *散热器(Cooler)     | DeepCool AN600 with Honeywell PTM7950 [^1]                   |
| *机箱风扇(External Fan) | ID-COOLING 80*25(mm)                                         |
|   有线网卡(Ethernet)    | Realtek RTL8111H (Integrated)                                |
|  *!有线网卡(Ethernet)   | Realtek RTL8125B (Mini-PCIe)                                 |
|  *!无线网卡(Wireless)   | Intel Wireless AC 9260                                       |
|     *机箱(Chassis)      | QuickPC (OEM-like, Low-Profile)                              |
|  *!电源(Power Supply)   | Seasonic SSP-300TBS (300 watt, 80PLUS Bronze)                |

[^1]: 需使用部分非原装零件安装 Need to be used some non original accessories for installation https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/cooler.md
[^2]: 例如当前消费端常见的国产 WiFi 6 网卡爱科微的 AIC8800 系列，该网卡接口常见为 USB 和 SDIO，并无 M.2 接口版本。
