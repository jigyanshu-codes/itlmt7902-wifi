# v0.2.5 — MediaTek MT7902 Direct Target Locking

[中文 README](../README.zh-CN.md) · [English README](../README.md) · [Source attribution](../NOTICE.md)

## English

This release implements direct target locking for Airtel 5G:
- Skips wildcard passive sweeps on boot.
- Locks directly to 5 GHz Channel 36, BSSID fc:9f:2a:2a:aa:28.
- Synthesizes rates and WPA2 CCMP / PSK RSN elements for immediate handshake.

## 中文

本版实现对指定网络（Airtel 5G）的直连锁定：
- 跳过开机全局被动扫描。
- 直接锁定 5 GHz 36 信道与目标 BSSID fc:9f:2a:2a:aa:28。
- 自动准备 5G 速率与 WPA2 CCMP / PSK 握手参数。
