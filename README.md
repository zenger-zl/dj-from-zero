# DJ Learning Project

Personal DJ learning log, built from zero.
Covers gear selection, software setup (Rekordbox), livestream system (BlackHole + Zoom), and outdoor performance build. Documented in Chinese.

If you're interested in any part of this, feel free to open an Issue — happy to connect.

---

个人 DJ 学习项目记录。从零开始，覆盖硬件选型、软件使用、直播系统搭建，以及户外演出设备方案。

**开始时间：** 2026-03-30

---

## 文件结构 · File Structure

```
DJ_cowork_project/
├── README.md                        ← 本文件，项目总览
├── DJ_Milestones.md                 ← 学习进度时间轴（持续更新）
└── Doc/
    ├── DJ_learning_notes.md         ← Beat Grid、歌曲结构、四大核心技能
    ├── DJ_controller_notes.md       ← 控制器横向对比 + Rekordbox 分析设置
    ├── DJ_livestream_setup.md       ← 直播系统搭建文档（英文）
    ├── DJ_livestream_setup_CN.md    ← 直播系统搭建文档（中文）
    ├── DJ_outdoor_equipment_compare.md  ← 户外设备对比与选型
    ├── DJ_controller_compare_graph.png  ← 控制器对比图
    ├── energy_map.html                  ← 1st_Song.wav 能量结构图
    └── waveform_structure.html          ← 1st_Song.wav Waveform 结构图
```

---

## 硬件演进 · Hardware Timeline

```
Numark Party Mix（入门）
    └─► Pioneer DDJ-FLX4（主力，2026-04-17）
            └─► JBL PartyBox OTG（音箱，2026-04-18）
                └─► MacBook Pro M1（户外主机，2026-04-23下单）
                └─► SBAOH T101 移动电源（2026-04-18下单）
```

---

## 系统架构 · System Architecture

### 直播系统 · Livestream Setup（室内 Zoom）

```
[DDJ-FLX4] ──USB──► [Rekordbox]
                          │
                          ▼
               [Multi-Output Device]       ← Mac Audio MIDI Setup
               （音频分叉，同时输出两路）
                    │            │
                    ▼            ▼
           [耳机监听]       [BlackHole 2ch]
           （本地监听）      （虚拟音频管道）
                                  │
                                  ▼
             [EPOS麦克风] ──► [Aggregate Device]  ← Mac Audio MIDI Setup
             （主持声音）    （合并两路输入）
                                  │
                                  ▼
                               [Zoom]
                    （观众听到：DJ音频 + 主持声音）
```

### 户外演出系统 · Outdoor Performance Setup（规划中）

```
[DDJ-FLX4] ──USB──► [MacBook Pro M1]
                          │
                          │ RCA → 3.5mm
                          ▼
    [SBAOH T101] ──电源──► [JBL PartyBox OTG]
    （移动电源）
```

---

## 音频数据流 · Audio Signal Flow（直播）

```
FLX4 硬件输出
  → Rekordbox Master Output (L/R)
    → Multi-Output Device（分叉）
      ├─► 耳机
      │   （本地监听）
      └─► BlackHole 2ch
          （虚拟管道）
                │
                ▼
  EPOS麦克风 ──► Aggregate Device（合并两路输入）
  （主持声音）         │
                       ▼
                  Zoom 麦克风输入
                       │
                       ▼
               观众听到：DJ音频 + 主持声音
```

---

## 关键决策记录 · Key Decisions

| 决策 | 结论 | 原因 |
|------|------|------|
| Party Mix → FLX4 升级 | ✅ 升级 | Filter 缺失是核心短板；FLX4 三软件授权 + Club layout |
| MBA i3 → MBP M1 | ✅ 换机 | MBA i3 热节流，不适合户外长时间运行 |
| 直播平台 · Streaming | Zoom | WhatsApp 不支持虚拟音频设备 |
| 虚拟音频 · Virtual Audio | BlackHole 2ch | 免费，Mac 原生兼容，无延迟问题 |

---

## 总投入 · Total Investment（截至 2026-04-25）

| 设备 | 价格 |
|------|------|
| Pioneer DDJ-FLX4 | €349.90 |
| JBL PartyBox OTG（二手） | €125.00 |
| MacBook Pro 13" M1 | $434.95（≈€371.01）|
| SBAOH T101 移动电源 | €80.85 |
| RCA 转 3.5mm 连接线 | €4.88 |
| **合计** | **€931.64** |

---

## 里程碑 · Milestones

详见 [DJ_Milestones.md](./DJ_Milestones.md)
