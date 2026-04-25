# DJ Live Streaming Setup — Phase 1

**Last updated:** 2026-04-19  
**Status:** Phase 1 complete — DJ audio + host voice both verified in Zoom

---

## Goal

Stream DJ audio from Rekordbox into Zoom calls, while monitoring locally through headphones.

---

## Hardware

| Device | Role | Connection |
|--------|------|------------|
| Pioneer DDJ FLX4 | DJ controller + onboard soundcard | USB → MacBook Air |
| MacBook Air | Host machine | — |
| EPOS ADAPT 360 | Host voice (mic) + monitoring (headphone) | Bluetooth → Mac |
| USB Microphone | Host voice — upgrade option (not yet purchased) | USB → Mac |

> **Note:** EPOS ADAPT 360 is a Bluetooth headset. Its microphone is capped at 16kHz sample rate due to Bluetooth protocol limitations. Audio quality is acceptable for Phase 1 but USB microphone is recommended for better voice quality.

---

## Software Stack

| Software | Role | Cost |
|----------|------|------|
| Rekordbox | DJ software, audio source | Free (bundled with FLX4) |
| BlackHole 2ch | Virtual audio pipe (Mac) | Free |
| Zoom | Video call platform | Free tier |

---

## System Architecture（系统架构）

```
[DDJ FLX4] ──USB──► [Rekordbox]
                          │
                          ▼
               [Multi-Output Device]  ← Mac Audio MIDI Setup
                    │         │
                    ▼         ▼
            [EPOS ADAPT 360] [BlackHole 2ch]
            (local monitor)        │
                                   ▼
                          [Aggregate Device]  ← Mac Audio MIDI Setup
                                   ▲
                          [EPOS ADAPT 360]
                          (microphone input)
                                   │
                                   ▼
                                 [Zoom]
                    (friends hear DJ audio + host voice)
```

**中文说明：**
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

## Audio Data Flow（音频数据流）

```
FLX4 hardware output
  → Rekordbox Master Output (Output 1 L, Output 2 R)
    → Multi-Output Device
      → EPOS ADAPT 360 headphone  (DJ monitors locally)
      → BlackHole 2ch             (virtual pipe)
          → Aggregate Device
              ↑ also receives: EPOS ADAPT 360 microphone (host voice)
                → Zoom Microphone Input (friends hear DJ audio + host voice)
```

**中文说明：**
```
FLX4硬件输出
  → Rekordbox Master Output（左声道Output 1，右声道Output 2）
    → Multi-Output Device（同时分叉输出）
      → EPOS耳机            （DJ本地监听音乐）
      → BlackHole 2ch       （虚拟管道，传递DJ音频）
          → Aggregate Device（合并两路输入）
              ↑ 同时接收：EPOS麦克风输入（主持人声音）
                → Zoom麦克风输入（朋友听到：DJ音乐＋主持声音）
```

---

## Configuration Steps

### 1. Install BlackHole 2ch
- Download from: existential.audio/blackhole
- Install BlackHole 2ch (not 16ch or 64ch)

### 2. Create Multi-Output Device (Mac Audio MIDI Setup)
- Open Audio MIDI Setup → "+" → Create Multi-Output Device
- Check: External Headphones (Primary Device)
- Check: BlackHole 2ch (enable Drift Correction)
- Sample Rate: 44,100 Hz

### 3. Configure Rekordbox
- Preferences → Audio → Audio Output: **Multi-Output Device**
- Sample Rate: 44100 Hz
- Input/Output → Mixer Mode: **Internal**
- Master Output: L → Output 1, R → Output 2

> **Note:** If DDJ FLX4 is connected via USB, Rekordbox may auto-switch audio output back to FLX4.
> Always verify the audio output setting after connecting the controller.

### 4. Create Aggregate Device (Mac Audio MIDI Setup)
- Open Audio MIDI Setup → "+" → **Create Aggregate Device**
- Check: EPOS ADAPT 360 (Clock Source — primary device)
- Check: BlackHole 2ch (enable Drift Correction)
- This merges microphone input + DJ audio into one virtual input device

### 5. Configure Zoom
- Settings → Audio → Microphone: **Aggregate Device**
- Settings → Audio → Speaker: **EPOS ADAPT 360**
- Disable: "Automatically adjust microphone volume"

---

## Verified Signal Chain

- [x] Rekordbox plays audio → level meter active
- [x] BlackHole 2ch receives audio → verified via QuickTime Audio Recording
- [x] EPOS microphone captured in Aggregate Device → level meter responds in Zoom
- [x] DJ audio + host voice both present → verified via QuickTime recording playback

---

## Current Limitations

| Limitation | Cause | Fix (Phase 2) |
|------------|-------|---------------|
| Voice quality capped at 16kHz | Bluetooth protocol limitation of EPOS ADAPT 360 | Buy USB microphone (e.g. Rode NT-USB Mini) |
| No video | No webcam | Buy webcam (e.g. Logitech C920) |
| WhatsApp not supported | Does not accept virtual audio devices | Use Zoom as primary platform |

---

## Phase 2 Plan

1. Purchase: USB microphone (recommended: Rode NT-USB Mini ~$100) — replaces EPOS as mic input
2. Purchase: Webcam (recommended: Logitech C920)
3. Update Aggregate Device: swap EPOS mic → USB microphone
4. Optional: OBS — for video mixing and future streaming to larger audiences (30+)

---

## Glossary

| Term | Definition |
|------|------------|
| Audio level / Level meter | Visual indicator of signal strength |
| Virtual audio device | Software-simulated audio hardware |
| Multi-Output Device | Mac feature that duplicates one audio stream to multiple outputs simultaneously |
| Aggregate Device | Mac feature that merges multiple audio inputs into one virtual input device |
| BlackHole | Virtual audio pipe that routes audio between applications |
| Drift Correction | Compensates for clock differences between two audio devices running simultaneously |
| Master Output | Final mixed audio output from Rekordbox |
| Buffer size | Audio processing delay; 256 samples = ~5.8ms latency |
| Sample Rate | Audio resolution; 44.1kHz = standard, 16kHz = Bluetooth mic limitation |
| Clock Source | The device that sets the timing reference for an Aggregate Device |
