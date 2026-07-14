# mibs

常用 MIB 库,适用于任何支持 MIB 解析的 SNMP 工具(如 `snmpwalk`、`snmpget`、`Net-SNMP`、Prometheus SNMP Exporter、Zabbix、LibreNMS、PRTG 等)。

## 目录结构

```
mibs/
├── standard/    # 标准 / 公有 MIB,大部分工具的基础依赖
│   ├── rfc/     # RFC 系列 MIB(IF-MIB、HOST-RESOURCES-MIB、ENTITY-SENSOR-MIB 等)
│   ├── iana/    # IANA 维护的类型与编号(IANA-IFTYPE-MIB、IANA-CHARSET-MIB 等)
│   ├── ieee/    # IEEE 802 系列(Q-BRIDGE、IEEE8021-CFM、RMON 等)
│   └── other/   # 其他标准草案/LLDP/sFlow/WAPI 等
├── vendors/     # 厂商私有 MIB
└── other/       # 开源软件 / 工具 MIB(keepalived、net-snmp、misc)
```

## 厂商覆盖

`vendors/` 目录按厂商分类,当前包含:

| 厂商 | 目录 | 备注 |
| --- | --- | --- |
| 思科 Cisco | `vendors/cisco` | |
| 华为 Huawei | `vendors/huawei` | |
| 华三 H3C | `vendors/h3c` | |
| 锐捷 Ruijie | `vendors/ruijie` | 私有 MIB 以 `MY-` 前缀命名(`MY-INTERFACE-MIB.mib` 等) |
| 紫光 Unis | `vendors/unis` | |
| Palo Alto | `vendors/paloalto` | |
| Arista | `vendors/arista` | |
| APC | `vendors/apc` | UPS |
| 海康 Hikvision | `vendors/hikvision` | |
| Kemp | `vendors/kemp` | 负载均衡 |
| Liebert | `vendors/liebert` | UPS / 机房 |
| MikroTik | `vendors/mikrotik` | |
| NEC | `vendors/nec` | |
| ServerTech | `vendors/servertech` | PDU |
| Synology | `vendors/synology` | NAS |
| Synway | `vendors/synway` | 网关设备 MIB(`SYNWAY-GW-MIB.txt`) |
| T1 | `vendors/t1` | |
| 天融信 Topsec | `vendors/topsec` | |
| Ubiquiti | `vendors/ubiquiti` | |

> `MY-*` 为锐捷私有 MIB;`vendors/synway/` 为 Synway(信景)网关设备 MIB。

## 使用方式

将需要的 MIB 路径加入对应工具的 MIB 搜索路径即可,例如:

```bash
# Net-SNMP: 通过 MIBDIRS 环境变量
MIBDIRS+:/path/to/mibs/standard/rfc:/path/to/mibs/standard/iana:/path/to/mibs/vendors/cisco \
snmpwalk -v2c -c public 10.0.0.1 ifDescr
```

通常 `standard/` 需要全部加载,`vendors/<厂商>/` 按目标设备按需加入。

## 相关文章

[Prometheus SNMP Exporter 生成器使用](https://blog.51ai.vip/posts/prometheus-snmp-exporter-generator/)