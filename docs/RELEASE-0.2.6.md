# v0.2.6 — MediaTek MT7902 System Stutter Fix & Connection Pipeline Update

[中文 README](../README.zh-CN.md) · [English README](../README.md) · [Source attribution](../NOTICE.md)

## English

This release fixes the UI stutter / freeze cycle and updates the connection sequence for MT7902:
- Replaced CPU-spinning `IODelay(1000)` with non-blocking `IOSleep(1)` in `m3Pump()`, completely eliminating the 3-4 second system stutter.
- Added adaptive scheduler yielding in `mcuSend()` polling loops.
- Prevented supervisor from triggering full 20s wildcard scans when target locking on MT7902.
- Updated MT7902 ROC grant handling and added detailed diagnostics for BSS, STA, ROC, and Auth exchanges.

## 中文

本版彻底解决系统卡顿/掉帧问题并更新 MT7902 连接链路：
- 将 `m3Pump()` 中占用 CPU 的 `IODelay(1000)` 改为协作式 `IOSleep(1)`，彻底消除 3-4 秒的周期性系统卡顿。
- 在 `mcuSend()` 轮询等待中加入自适应调度让渡。
- 目标锁定模式下禁止后台监管循环执行耗时 20 秒的全局被动扫描。
- 优化 MT7902 锁定信道等待逻辑，增加 BSS、STA、ROC、Auth 阶段的完整诊断日志。
