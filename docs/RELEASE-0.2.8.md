# v0.2.8 — Router Flood Protection, Boot Quiet Delay, and MT7902 Single Antenna Fix

[中文 README](../README.zh-CN.md) · [English README](../README.md) · [Source attribution](../NOTICE.md)

## English

This release prevents AP denial-of-service / radio crash on ISP routers during connection attempts:
- Blocked unassociated deauthentication frames: `m3Teardown()` will never transmit 802.11 Deauth frames unless actually connected.
- Fixed MT7902 antenna configuration: changed `spe_index` from dual-antenna beamforming mask (24) to single-antenna path (0).
- Gentle exchange timing: reduced maximum frame attempts from 4 to 2 on MT7902, increased response wait window from 150ms to 500ms, and added 200ms spacing between retries.
- Boot quiet delay: delayed supervisor start by 8 seconds on MT7902 to keep verbose boot completely silent and let the system reach desktop before transmitting.
- Throttled reconnect backoff: increased retry interval to 10-15+ seconds to prevent router rate-limiting or kernel panic.

## 中文

本版消除连接重试时对路由器 5 GHz 射频的过载保护与异常崩溃：
- 阻断未关联去认证报文：仅在实际建立关联后才允许发送 Deauth 帧，彻底防止路由器 SCB 空指针异常。
- 修正 MT7902 天线配置：将双天线波束成形掩码（24）修正为单天线路径（0）。
- 缓和报文发送节奏：MT7902 单次重试上限从 4 降至 2，等待窗口从 150ms 拓宽至 500ms，重试间隔 200ms。
- 启动静默延时：开机前 8 秒保持静默，待进入桌面后再发起连接尝试。
- 节流重连退避：将重试退避间隔拉长至 10-15 秒以上。
