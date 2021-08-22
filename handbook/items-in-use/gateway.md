# ⭐️ 路由网关

> 影响网络质量的核心设备，负责部分网络安全事务，[历史设备见文档](../devices/device-list.md)。

| 资源类型 | 明细 | 网络 | 储存 | 开始服务 |
| --- | --- | --- | --- | --- |
| 交换机 | NETGEAR GS116E ^1 | 千兆LAN x16 | - | 2017 |
| 路由器 | Xiaomi AIot AX 3600 ^2 | 2G Wi-Fi / 5G Wi-Fi（Wi-Fi6） / 千兆LAN | - | 2020 |
| 路由器 | Newifi D2 ^3 | 2G Wi-Fi / 5G Wi-Fi / 千兆LAN | 8G | 2018 |
| 路由器 | Xiaomi AC2100 ^4 | 5G WIFI / 千兆LAN | - | 2020 |
| 路由器 | Xiaomi Mini 青春版 ^5 | 2G Wi-Fi / 百兆LAN | - | 2016 |
| 路由器 | 施耐德旅行插座 ^6 | 2G WIFI / 百兆LAN | - | 2018 |

## 简要说明

- [1] 八口千兆交换机，用于扩展主路由网络吞吐能力，带 Web 管理界面，拥有铁壳散热能力，最大功耗仅10w，性价比颇高。
- [2] 扩展主路由的 AP 能力，提供屋内设备以 Wi-Fi 6 模式，进行高速无线接入。
- [3] 全千兆四口主路由（二级路由），拥有 512M 内存和铁壳散热的路由器，延续 Newifi 极高的性价比，一度使用两台相同规格的设备作为拨号路由器和二级路由。
- [4] 偶尔在开发调试时使用，用于替换之前使用的[小米路由器第一版](../devices/XiaoMi-Route-Mini.md)，相比较之下，固件修改复杂度稍高一些，但是胜在全千兆。
- [5] 功耗极低，小巧方便，适合旅游或者临时需要网络进行调试的场景，三方适配的固件功能强大，如果公司不限制使用自建路由作为调试环境，强烈建议入一台。
- [6] 此插座自带一个简易的热点 WiFi 功能，如果你需要插上设备就自动组网，可以使用上面的设备，如果你没有自动组网等需求，那么这个能让你上网的插座，用起来体验还不错，唯一槽点，插座本身发热比较严重，或许对网络稳定性/质量有一定影响。

## 家用网络为什么需要交换机

因为性价比高，不论是性能，还是成本，亦或者是稳定性。

有没有想过为什么大家总是会说路由器的性能不够，网络体验卡顿，需要不断的更新换代呢？

抛开外部网络环境不提，单看内网场景下，除了一些希望在不额外添加设备的情况下，进行个性化需要：

- 用路由器运行一些软件做虚拟组网
- 用路由器运行一些软件做广告过滤
- 用路由器进行脱机下载
- 用路由器提供游戏加速

我们日常对路由器性能要求最高的莫过于：**接入设备**的包转发负载、以及无线网络接入和处理。如果这些功能集成在一台设备上，最终这台设备的价格会变的相对比较高，且可能出现某块短板在几年内随着科技的发展显的特别突出（落后）。

以2021年两千元中高端路由设备[ASUS AX88U](https://www.asus.com/Networking-IoT-Servers/WiFi-Routers/ASUS-Gaming-Routers/RT-AX88U/techspec/)为例：

先计算有线状态下的性能（都按照线性无阻塞计算）：

- 因为设备算上WAN口共计9个全千兆端口（双工 2000Mbps），无线网络极限为 1148+4804 Mbps，则如果该设备支持所有连接设备将其带宽跑满，该设备极限背板带宽为24G不到。
- 而文档中提到的，我使用了五年的交换机的面板属性是16个端口，32G背板带宽，五年前购入价格498元。

简单的结论是，我们可以通过一台相对廉价的交换机，获取至少五年以上的家用高端设备在有线数据交换上的体验，成本只有其四到五分之一。

然后接着来看无线状态下的性能：

- AX88U 标称无线网络极限带宽 1148+4804 Mbps。
- 小米 AX6000 无线路由器标称无线带宽为 6000 Mbps，整台设备价格599元。

简单结论是，无线 AP 功能部分也可以使用一台相对廉价的设备进行替换，成本也只有其四到五分之一。

算到这里其实还没有结束，因为交换机并不具备宽带拨号/DHCP管理能力，我们还需要计算一台真正的路由器的成本。不过庆幸的是，因为家用宽带的出口有限（普遍在2G内），所以我们随便购买或者使用运营商赠送的全千兆路由器，其实都够跑满外部带宽。在上面无线 AP 和交换机的加持下，拨号路由器负载会异常的低，而相同软件状况下，低负载意味着你的设备可以无故障运行更长时间，以及做更多你想做的事情。

当然，使用单一设备也有好处，当你设备压力复杂没有那么大的时候，单一的设备，不论是从空间体积、设备发热、还是产品设计来看，会优于组合方案，至于到底选择哪种，就仁者见仁了。

我的设备一般运行时间会是半年到一年，偶尔小区断电或者我打扫机柜，会让它的计时器中断，在它在线的时间里，除非运营商故障，我的网络会一直比较通畅。

- [关联知乎问题：如何跟小白解释路由器和交换机的区别？并且家用路由器充当了路由器和交换机的功能吗？](https://www.zhihu.com/question/22007235/answer/2072616337)