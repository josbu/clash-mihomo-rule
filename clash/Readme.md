# OpenClash DNS 配置

在 OpenWrt 中，OpenClash 的配置文件路径位于 `/etc/config`。

## DNS 配置步骤

1. **防火墙 DNS 设置**:
   - 可以在 OpenClash 的配置中设置 DNS，确保防火墙规则适当配置。

2. **DHCP/DNS 设置**:
   - 导航到 OpenWrt 的 **网络** -> **DHCP/DNS**。
   - 将 DNS 重定向的选项取消勾选。

## 注意事项
- 确保在配置完毕后重启 OpenClash 和网络服务，以使更改生效。

# ipv6 网络架构配置

## 1. 网络架构
- **主路由**（中兴巡天）+ **旁路由**（iStoreOS）

## 2. 主路由配置
- 负责拨号、开通 IPv6
- 负责 DHCP (V4) 的 IP 地址及 DNS 分配
- 关闭 DHCPV6 服务
- 开启 DHCPV6 的 IPv6 路由器通告（RA）

## 3. 旁路由配置

### 3.1 网络 - 接口配置
- **建立 LAN6 接口**：
  - 常规默认
  - 高级默认
  - 防火墙（选 LAN）
  - DHCP 关闭
  - 禁止 DHCP IPv6
- **LAN 接口**：
  - 高级设置，委托 IPv6 前缀
- **DHCP 配置**：
  - 忽略此接口√
- **IPv6 设置**：
  - RA 服务：服务器模式
  - DHCPv6 服务：服务器模式
  - 本地 IPv6 DNS 服务器：√
  - NDP 代理：禁用
  - IPv6 RA 启用 SLAAC

### 3.2 DHCP/DNS 配置
- **高级设置**：
  - 过滤 IPv6 AAAA 记录：取消√

### 3.3 OpenClash 配置
- **插件设置**：
  - 允许 IPv6 DNS 解析
