# LiarOnce's Built Distributions for LoongArch
|   Flags   |   ![](./aosc-os-flag_compressed.png) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Arch+Linux&color=1793D1&logo=Arch+Linux&logoColor=FFFFFF&label=) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Debian&color=A81D33&logo=Debian&logoColor=FFFFFF&label=) ![](https://img.shields.io/static/v1?style=for-the-badge&message=Deepin&color=007CFF&logo=deepin&logoColor=FFFFFF&label=)   |
| ---- | ---- |

## 编译主机硬件配置 / Build Machine Specs
可用于装机参考/It can be used as a reference for PC installation  
信创兼容机，整体配置可接近信创PC  
**其中带*硬件均可替换为信创名单内硬件，带!硬件为当前的接口暂无完整国产方案或目前的硬件类型暂无国产化替代（非硬件本身）[^1]**  

|          类型           | 型号                                                         |
| :---------------------: | :----------------------------------------------------------- |
|       处理器(CPU)       | Loongson 3A6000 (4-cores/8-threads, up-to 2.5GHz)                      |
|      桥片(Chipset)      | Loongson 7A2000 [^2]                                              |
|       *显卡(GPU)[^5]    | **AMD Radeon Pro WX 2100 (2GB GDDR5, Low-Profile, Current)** [^3]|
|    主板(Motherboard)    | XA61200                                                      |
|      *内存(Memory)      | UniIC SCC16GU03H2F1C-32AA DDR4 3200MT/s 16GB x2 (Total 32GB) |
|     *固态硬盘(SSD)      | ZHITAI TiPlus 5000 1TB (NVMe, System for AOSC OS) <br /> Kioxia RC10 500G (NVMe, System for Loong ArchLinux) |
|     *散热器(Cooler)     | DeepCool AN600 with Honeywell PTM7950 [^4]                   |
| *机箱风扇(External Fan) | ID-COOLING XF-12025-K <br /> ID-COOLING NO-8025-SD           |
|   有线网卡(Ethernet)    | Realtek RTL8111H (Integrated)                                |
|  *!有线网卡(Ethernet)   | Realtek RTL8125B (Mini-PCIe)                                 |
|  *!无线网卡(Wireless)[^14]   | Intel Wireless AC 9260 (M.2 Key A+E)                         |
|     *机箱(Chassis)      | Great Wall ShangQi R10 (长城商祺R10，mATX and Retail)        |
|  *!电源(Power Supply)   | XIGMATEK XTK-550 (550 watt, 80PLUS White)                   |
|  *!其他(Others)         | ASUS DRW-24D5MT <br /> 8BitDo Ultimate 2.4G Wireless Controller <br /> Dell(戴记严选) GM3323D Mouse <br /> IKBC C87 Keyboard (Cherry MX Red) |

[^1]: 例如当前消费端常见的国产 WiFi 6 网卡爱科微的 AIC8800 系列，该网卡接口常见为 USB 和 SDIO，并无 M.2 接口版本。
[^2]: 由于体质问题，为保证稳定性建议更换其原装散热片 (适用于 XA61200/XA612A0 主板) https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/chipset.md
[^3]: 原先因龙芯平台与 AMD Polaris 架构的兼容性问题，附带 Linux 内核参数为: `amdgpu.dpm=0 pcie_aspm=off`，但实测为 7A2000 桥片更换带有风扇的散热器并配合最新 BIOS 后稳定性大幅度提升，此时需开启 DPM (`amdgpu.dpm=1`)，且在 AOSC OS 和 Deepin 中使用最新内核后该问题已解决，但上游因某种原因未同意合并对应补丁，若需使用 AMD Polaris 架构的显卡请使用新世界发行版并更新到应用有修复补丁的最新内核。
[^4]: 需使用部分非原装零件安装 https://github.com/LiarOnce-LoongAL/.github/blob/main/cooler/cooler.md
[^5]: 由于龙芯平台的 ACPI 休眠机制不完善，若使用 AMD 显卡均需关闭动态断电功能 (添加内核参数 `amdgpu.runpm=0`)   
