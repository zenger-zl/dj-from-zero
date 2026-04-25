# DJ 直播系统搭建 — 第一阶段

**最后更新：** 2026-04-19  
**状态：** 第一阶段完成 — DJ音频 + 主持人声音已在 Zoom 中验证

---

## 目标

将 Rekordbox 的 DJ 音频输入 Zoom 通话，同时通过耳机本地监听。

---

## 硬件设备

| 设备 | 用途 | 连接方式 |
|------|------|----------|
| Pioneer DDJ FLX4 | DJ 控制器 + 内置声卡 | USB → MacBook Air |
| MacBook Air | 主机 | — |
| EPOS ADAPT 360 | 主持人声音采集（麦克风）+ 监听（耳机） | USB-C → Mac |
| USB 麦克风 | 主持人声音 — 升级选项（尚未购买） | USB → Mac |

> **注意：** EPOS ADAPT 360 蓝牙模式下麦克风采样率限制为 16kHz。第一阶段可接受，建议后续升级为 USB 麦克风以获得更好音质。USB-C 有线模式不受此限制。

---

## 软件栈

| 软件 | 用途 | 费用 |
|------|------|------|
| Rekordbox | DJ 软件，音频来源 | 免费（随 FLX4 附带授权）|
| BlackHole 2ch | 虚拟音频管道（Mac）| 免费 |
| Zoom | 视频通话平台 | 免费版 |

---

## 系统架构

```
[DDJ FLX4控制器] ──USB──► [Rekordbox DJ软件]
                                │
                                ▼
                    [Multi-Output Device]  ← 同时输出到两个设备
                         │              │
                         ▼              ▼
               [EPOS耳机播放]     [BlackHole 2ch]
               （本地监听）        （虚拟管道）
                                        │
                                        ▼
                             [Aggregate Device]  ← 合并两路输入
                                        ▲
                             [EPOS麦克风采集]
                             （主持人声音）
                                        │
                                        ▼
                                      [Zoom]
                          （朋友同时听到DJ音乐＋主持声音）
```

---

## 音频数据流

```
FLX4 硬件输出
  → Rekordbox Master Output（左声道 Output 1，右声道 Output 2）
    → Multi-Output Device（同时分叉输出）
      → EPOS 耳机            （DJ 本地监听音乐）
      → BlackHole 2ch        （虚拟管道，传递 DJ 音频）
          → Aggregate Device （合并两路输入）
              ↑ 同时接收：EPOS 麦克风输入（主持人声音）
                → Zoom 麦克风输入（朋友听到：DJ 音乐＋主持声音）
```

---

## 配置步骤

### 1. 安装 BlackHole 2ch
- 下载地址：existential.audio/blackhole
- 安装 BlackHole 2ch（不是 16ch 或 64ch）

### 2. 创建 Multi-Output Device（Mac Audio MIDI Setup）
- 打开 Audio MIDI Setup → 左下角"+"→ Create Multi-Output Device
- 勾选：External Headphones（设为 Primary Device）
- 勾选：BlackHole 2ch（开启 Drift Correction）
- Sample Rate：44,100 Hz

### 3. 配置 Rekordbox
- Preferences → Audio → Audio Output：选 **Multi-Output Device**
- Sample Rate：44100 Hz
- Input/Output → Mixer Mode：**Internal**
- Master Output：L → Output 1，R → Output 2

> **注意：** DDJ FLX4 通过 USB 连接后，Rekordbox 可能自动将音频输出切换回 FLX4。每次连接控制器后请检查此设置。

### 4. 创建 Aggregate Device（Mac Audio MIDI Setup）
- 打开 Audio MIDI Setup → 左下角"+"→ Create Aggregate Device
- 勾选：EPOS ADAPT 360（设为 Clock Source — 主设备）
- 勾选：BlackHole 2ch（开启 Drift Correction）
- 作用：将麦克风输入 + DJ 音频合并为一个虚拟输入设备

### 5. 配置 Zoom
- Settings → Audio → Microphone：选 **Aggregate Device**
- Settings → Audio → Speaker：选 **EPOS ADAPT 360**
- 关闭："Automatically adjust microphone volume"

---

## 已验证信号链

- [x] Rekordbox 播放音频 → 电平表有反应
- [x] BlackHole 2ch 接收音频 → 通过 QuickTime 录音验证
- [x] EPOS 麦克风在 Aggregate Device 中采集 → Zoom 电平表有反应
- [x] DJ 音频 + 主持人声音同时存在 → 通过 QuickTime 录音回放验证

---

## 当前限制

| 限制 | 原因 | 解决方案（第二阶段）|
|------|------|------------------|
| 声音质量上限 16kHz（蓝牙模式）| EPOS ADAPT 360 蓝牙协议限制 | 购买 USB 麦克风（推荐 Rode NT-USB Mini）|
| 没有视频画面 | 无摄像头 | 购买摄像头（推荐 Logitech C920）|
| 不支持 WhatsApp | WhatsApp 不接受虚拟音频设备 | 以 Zoom 为主要平台 |

---

## 第二阶段计划

1. 购买：USB 麦克风（推荐 Rode NT-USB Mini，约 100 美元）— 替换 EPOS 作为麦克风输入
2. 购买：摄像头（推荐 Logitech C920）
3. 更新 Aggregate Device：将 EPOS 麦克风替换为 USB 麦克风
4. 可选：安装 OBS — 用于视频混合，适合未来扩展到更大规模观众（30人以上）

---

## 术语表

| 术语 | 解释 |
|------|------|
| 电平 / Level meter | 音频信号强度的可视化指示器 |
| 虚拟音频设备 | 软件模拟出来的音频硬件 |
| Multi-Output Device | Mac 功能，将一路音频同时复制输出到多个设备 |
| Aggregate Device | Mac 功能，将多个音频输入合并为一个虚拟输入设备 |
| BlackHole | 虚拟音频管道，在应用程序之间传递音频 |
| Drift Correction | 补偿两个同时运行的音频设备之间的时钟偏差 |
| Master Output | Rekordbox 的最终混音输出 |
| Buffer size | 音频处理延迟；256 samples = 约 5.8ms 延迟 |
| Sample Rate | 音频采样率；44.1kHz 为标准，16kHz 为蓝牙麦克风限制 |
| Clock Source | Aggregate Device 的时钟基准设备 |
