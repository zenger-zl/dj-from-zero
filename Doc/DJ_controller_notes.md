# DJ软件与控制器知识记录
> 目标：整理各类DJ控制器对比，以及Rekordbox软件使用知识
> 记录方式：按话题分类，持续追加

---

## 控制器横向对比（2026.4）

| 参数 | Numark Party Mix | AlphaTheta DDJ-FLX2 | Numark Mixtrack Platinum FX | Pioneer DJ DDJ-400 | Pioneer DJ DDJ-FLX4 |
|------|-----------------|--------------------|-----------------------------|-------------------|-------------------|
| 新品价 | ~$99 | ~$189 | ~$279 | 停产 | ~$329 |
| 二手价 | ~$50–80 | ~$120–150 | ~$130–170 | ~$150–200 | ~$200–250 |
| 软件 | Serato Lite | Rekordbox + Serato Lite + djay | Serato Lite | **Rekordbox full** | **Rekordbox + Serato Lite + Traktor + djay** |
| Jog wheel | Small, no display | Small, no display | 6", color display | 5", no display | 5", no display |
| Decks | 2 | 2 | 4（需Pro版） | 2 | 2 |
| Pads | 4/deck | 8/deck | 8/deck | 8/deck | 8/deck |
| EQ | **2-band, no filter** | 3-band + CFX filter | 3-band + filter | 3-band + filter | 3-band + filter |
| Gain knob | Yes | No | Yes | Yes | Yes |
| Effects | Basic pad FX | Smart CFX | FX paddle + 6 FX | Beat FX | Beat FX + Smart CFX |
| Mic input | No | No | Yes (1/4") | Yes (1/4") | Yes (1/4") |
| Mic livestream routing | No | No | No | No | **Yes** |
| Master output | RCA | 3.5mm | RCA | RCA | RCA |
| Headphone output | 3.5mm | 3.5mm | 3.5mm + 6.35mm | 3.5mm | 3.5mm |
| USB | USB-A | USB-C | USB-B | USB-B | USB-C |
| Bluetooth | No | Yes | No | No | **Yes** |
| Mobile device support | No | Yes | No | No | **Yes** |
| Club layout | No | Basic | No | **Yes** | **Yes** |

### 关键区别总结
- **Party Mix**：入门最便宜，但EQ只有2-band，无filter，功能最受限
- **DDJ-FLX4**：功能最全面，软件兼容性最广，有Mic直播路由，是本项目选定机型
- **DDJ-400**：已停产，但二手市场是Club layout的高性价比选择

---

## Hercules DJControl Mix — 操作要点（2026.4）

### Filter/Bass 按钮（⑪号按钮）
双功能按钮，状态如下：

| LED状态 | 当前模式 |
|---------|---------|
| **亮** | FILTER/BASS 旋钮控制 **Bass（低音）** |
| **灭** | FILTER/BASS 旋钮控制 **Filter（滤波器）** |

> 来源：Hercules DJControl Mix 官方说明书 Page 14–15

---

## Rekordbox 曲库分析设置（DDJ-FLX4 首次导入）

### 分析选项说明

| 选项 | 建议 | 说明 |
|------|------|------|
| **BPM / Grid** | ✅ 勾选 | 必须。Sync、Beat Jump 均依赖此项 |
| High precision analysis | 不勾 | 分析更慢，普通使用无明显差别 |
| Analysis Mode | Normal | 够用，Extended 更慢 |
| BPM Range | 70–180 | 覆盖绝大多数音乐类型，保持默认 |
| **Key** | 按需 | Harmonic Mixing 需要。Free Plus 可用 |
| **Phrase** | 按需 | 自动识别段落结构。Free Plus 状态待确认 |
| Vocal | ❌ 不勾 | 付费功能，界面已显示锁定 |
| CUE (Manual) | 不勾 | 手动打点，无需自动分析 |

> **初始建议**：只勾 BPM/Grid，先把曲库导入完成。之后按需重跑分析。

---

### 分析功能说明

**Key（调性分析）**
- 检测每首歌的音乐调性（如 Am、C major）
- 用于 Harmonic Mixing：选调性相近的歌衔接，过渡更和谐
- Free Plus 状态下可用

**Phrase（段落分析）**
- 自动识别歌曲结构：Intro / Verse / Chorus / Breakdown / Outro
- 波形上显示颜色标记，方便判断过渡时机
- Free Plus 状态下是否可用：**待确认**（2025.3 Rekordbox 7 订阅结构调整后）

**Vocal（人声分析）**
- 标注歌曲中人声位置（波形上方蓝线）
- 避免混音时人声叠加
- **付费专属功能**

---

### 重新分析方法
- **单曲**：右键曲目 → **Analyze Track**
- **批量**：框选多首 → 右键 → Analyze Track
- **设置入口**：`Preferences > Analysis`（Mac: `⌘ + ,` / Win: `Ctrl + ,`）

---

### 分析结果查看位置

| 位置 | 可查看内容 |
|------|-----------|
| 曲库列表 | BPM、Key（需右键表头开启列显示） |
| 波形区（加载到Deck后） | Phrase颜色标记、当前Key |
| Track Info 面板 | 完整分析数据 |

---

### DDJ-FLX4 的 Rekordbox 权限说明

DDJ-FLX4 连接后自动触发 **Hardware Unlock**，账户从 Free 升级为 **Free Plus**。

| 功能 | Free Plus（FLX4连接）|
|------|---------------------|
| Performance Mode（控制器演出） | ✅ 可用 |
| BPM / Grid 分析 | ✅ 可用 |
| Key 分析 | ✅ 可用 |
| Phrase 分析 | ⚠️ 待确认 |
| Vocal 分析 | ❌ 付费专属 |

> 参考：rekordbox.com/en/plan 查看完整 Free vs 付费功能对比
