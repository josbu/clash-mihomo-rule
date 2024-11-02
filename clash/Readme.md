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

