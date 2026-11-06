# v0.2.4 — MediaTek MT7902 / MT7922 Wi-Fi update

[中文 README](../README.zh-CN.md) · [English README](../README.md) · [Source attribution](../NOTICE.md)

## English

This release addresses MT7902 (0x7902 / 14c3:7902) initialization and connection supervision:
- Restores DEV_INFO and BSS_INFO update sequence required by Connac2 firmware to activate the wireless interface before scanning.
- Ensures the supervisor background loop always starts even if passive wildcard scans time out on boot, enabling directed probe scanning and WPA2 association with configured networks.
- Uses immediate probe-all on initial supervisor boot to connect quickly to saved networks.
- Adds DMA ring diagnostic states for RX0 and RXdata.

## 中文

本版针对 MT7902 (0x7902 / 14c3:7902) 芯片的初始化与连接监管进行修复：
- 恢复 Connac2 固件激活无线接口所需的 DEV_INFO 与 BSS_INFO 更新序列。
- 确保即使开机被动全局扫描超时，连接监管后台任务也能正常启动，使配置的网络可通过定向探测完成扫描并建立 WPA2 连接。
- 监管任务开机首次循环立即发起定向探测，加速连接已知网络。
- 增加 RX0 与 RXdata 环形缓冲区的硬件 DMA 状态日志。

