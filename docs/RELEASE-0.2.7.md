# v0.2.7 — Unified MCU Response Parser Fix & Radio Channel Tuning for MT7902

[中文 README](../README.zh-CN.md) · [English README](../README.md) · [Source attribution](../NOTICE.md)

## English

This release fixes unified MCU event response matching and ensures complete channel configuration:
- Fixed `mcuSend()` unified response parser to accept matching unified command responses without improper option bit or eid rejections.
- Fixed `m3Cmd()` validation to rely on firmware status code rather than overly restrictive header fields.
- Guaranteed that `bss(rlm)` (radio channel tuning to 5 GHz Channel 36), `bmc(wtbl)`, and `m3Edca()` execute reliably on MT7902.
- Ensured `m3Sta()` and `m3Roc()` are not skipped if `m3Bss` encounters non-fatal return codes.
- Added detailed diagnostic logging for RX0 MCU responses.

## 中文

本版修复统一 MCU 响应事件解析器并确保 MT7902 正确切换射频信道：
- 修复 `mcuSend()` 统一响应解析逻辑，消除对选项位与 eid 的过度过滤。
- 修复 `m3Cmd()` 校验，使之基于固件状态字进行判定。
- 确保 MT7902 能够稳定执行 `bss(rlm)`（信道切换至 5 GHz 信道 36）、`bmc(wtbl)` 和 `m3Edca()`。
- 保证 `m3Sta()` 与 `m3Roc()` 不会被中间非致命错误跳过。
- 增加 RX0 MCU 报文诊断日志。
