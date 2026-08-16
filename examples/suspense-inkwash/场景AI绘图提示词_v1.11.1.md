画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景AI绘图提示词（v1.11.1）

> 依据阶段一《雨夜档案馆》剧本（6 场，水墨画风）生成。本文件为**阶段三场景提示词**；v1.11.1 关键改动：**图注改用「方位+功能词」命名，全流程零物品名词**（不出现 DOOR / WINDOW / SHELF 等物品词；中文物品词仅存在于格子索引表与一致性提醒，用于人工识别，不进入生成提示词）。

## 〇 统一设定表与空间基准表

### 统一设定表（复用自剧本·阶段一）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（推导——剧本阶段一未含本表，按任务给定空间信息＋统一设定表推导）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间（东西）8m × 进深（南北）16m × 层高 3.2m，矩形古籍库 |
| 四面墙朝向与功能 | 北墙=入口双开木门；南墙=老式推窗（走廊尽头，雨夜开启）；东墙=到顶木书架；西墙=到顶木书架 |
| 固定布局 | 中央过道沿南北中轴贯通（北门↔南窗）；东西两侧到顶木书架成排；最后一排书架贴南端近南窗（顶层《县志》摊开）；湿脚印自南窗台沿中央过道地面北延、渐淡消失 |
| 机位坐标系约定 | 以锚点图为准：上北、下南、左西、右东；每格机位用「位于空间何处、面朝 N/S/E/W」描述，全图共用同一坐标系 |

---

## 第一部分：空间锚点图（1 条 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为「空间锚点图」。本图是**唯一允许空间/物品描述**的图，也是其后所有图的空间唯一来源。

```
Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones.

A rectangular archive room, 8m wide (east-west) by 16m deep (north-south) by 3.2m high, oriented north at top / south at bottom. North wall = double wooden entry door (entry zone). South wall = old metal-frame casement window, the far end of the room, open on this rainy night. East wall and west wall = full-height wooden bookshelves running along both sides. A central aisle runs along the north-south axis, connecting the north entry to the south window. The last row of bookshelves stands against the south end near the south window, with a single open book lying on its top shelf. A trail of wet footprints runs from the south windowsill northward along the central aisle floor, fading toward the middle of the room.

Mark a clear N / S / E / W compass and a scale bar. Label six numbered zones (1-6) at their relative positions: zone 1 = north entry; zone 2 = central aisle; zone 3 = south window; zone 4 = central floor (footprint trail); zone 5 = south row (last row of bookshelves); zone 6 = mid floor in front of the last row.

This plan is the ONLY source of room layout and orientation for all other panels. Soft ink-wash rendering, low-saturation ink tones, deep shadow, generous negative space, ultra HD, 8k.
```

---

## 第二部分：最终合成图（1 条 · 一整段 · 一次图生图 · 锚点图为唯一来源）

**用户操作（固定格式）**：将「空间锚点图」作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束，参考强度中等偏强）；复制本段整段提示词，**一次图生图**。排版拼接由 AI 一次完成（顶部 MACRO 全宽大格 + 下方 6 特写 2 列 × 3 行 + 每格图注），无需手动排版；如需单张使用，按「格子索引表」裁剪。**空间的唯一来源是锚点图**，本段不含任何房间布局或物品空间关系文字。

```
Compose one single composite image. All panels must strictly follow the spatial reference image, which is the ONLY source of room layout and scene content; do not infer or alter the room structure from text. AI lays out the final grid: a full-width top MACRO panel, then six close-up panels in a 2-column × 3-row grid below, thin gaps between panels, one unified frame; draw a clear caption label beneath every panel (sequence number + name).

- Top panel (full-width), caption "MACRO": camera from the reference plan at a high position above the center, facing down the north-south axis. Style: ink-wash, low-saturation cool tone, deep shadow, negative space.
- Row 1 panel 1, caption "SCENE 1: NORTH ENTRY": camera from zone 1 in the reference plan, facing south. Style: ink-wash, cold beam cutting darkness, deep shadow.
- Row 1 panel 2, caption "SCENE 2: CENTER AISLE": camera from zone 2 in the reference plan, facing south along the central axis. Style: ink-wash, sweeping cold beam, low-saturation contrast, deep shadow.
- Row 2 panel 1, caption "SCENE 3: SOUTH END": camera from zone 3 in the reference plan, facing south. Style: ink-wash, rain streaks glinting silver at the beam edge, faint cold blue, deep shadow.
- Row 2 panel 2, caption "SCENE 4: CENTER FLOOR": camera from zone 4 in the reference plan, low angle, facing north. Style: ink-wash, cold beam low over the floor, receding shadow, negative space.
- Row 3 panel 1, caption "SCENE 5: SOUTH ROW": camera from zone 5 in the reference plan, facing south, slight low angle up. Style: ink-wash, cold beam fixed on one bright spot, dark void around, negative space.
- Row 3 panel 2, caption "SCENE 6: MID FLOOR": camera from zone 6 in the reference plan, facing south. Style: ink-wash, contrast of motion and stillness, trembling cold beam, deep shadow, negative space.

Watercolor / ink-wash painting style, consistent lighting from a moving cold white beam and faint cold blue from outside, same architectural materials throughout, multi-panel storyboard grid, deep focus, 8k hyper-detailed, unified low-saturation ink palette.
```

---

## 格子索引表（英文图注 + 中文名称对照）

| 格子位置 | 英文图注 | 中文名称对照 |
|------|------|------|
| 顶部大格（全宽） | MACRO | 宏观全景（古籍库总览） |
| 第 1 行 · 左 | SCENE 1: NORTH ENTRY | 场景1·北侧入口（门口） |
| 第 1 行 · 右 | SCENE 2: CENTER AISLE | 场景2·中央过道（书架间过道） |
| 第 2 行 · 左 | SCENE 3: SOUTH END | 场景3·南侧尽端（窗边·湿脚印起点） |
| 第 2 行 · 右 | SCENE 4: CENTER FLOOR | 场景4·中央地面（湿脚印延伸处） |
| 第 3 行 · 左 | SCENE 5: SOUTH ROW | 场景5·南侧排位（最后一排书架·《县志》） |
| 第 3 行 · 右 | SCENE 6: MID FLOOR | 场景6·中部地面（最后一排书架前） |

> 图注英文为「方位+功能词」，零物品名词；中文对照含物品词仅用于人工识别，不进入生成提示词。

---

## 一致性提醒

- **光照一致性**：全 6 格＋宏观格统一「雨夜」设定——主光＝移动冷白光柱（约5000K），补光＝窗外微弱冷蓝（约6500K）＋应急指示灯微弱冷绿；各格光向、色温一致，禁止白天/暖光/不同方向光源。
- **建筑一致性**：主色调（墨褐木色＋冷灰蓝＋纸张米白）、主要材质、标志性结构件（门/书架/窗/地面）均以统一设定表与锚点图为准，各格不得自行改色改材质。
- **空间一致性（唯一来源原则）**：空间的唯一来源是锚点图——第二部分提示词不含房间布局或任何物品/道具/结构的空间关系文字；每格只给「机位（从锚点图何处、面朝何方）」＋「画面风格（画风/光效氛围）」，机位坐标取自锚点图；画面内容由锚点图与图注名称承载，模型不得自行改写房间结构。
- **图注命名（v1.11.1）**：每格图注为「方位+功能词」（NORTH ENTRY / CENTER AISLE / SOUTH END / CENTER FLOOR / SOUTH ROW / MID FLOOR），宏观标 MACRO；**全文（含图注）零物品名词**——不出现 DOOR / DOORWAY / WINDOW / SHELF 等物品词。
- **生成顺序一致性**：第一部分锚点图先用文生图单独生成；第二部分以锚点图为参考图、一次图生图生成整张合成图，禁止逐格单独文生图。若工具不支持参考图，本方案无法保证空间一致（提示词不含空间文字），需换用支持参考图的工具或退回旧版文字锚定方案。
- **排版一致性**：排版由 AI 在第二部分一次完成——宏观大格置顶＋6 特写按空间动线（门口→过道→南端→地面→南排→排前）2 列 × 3 行＋每格「序号+名称」图注；禁止格子内容重复、宏观图不在顶部或图注缺失。
- **拍摄建议**：所有格子统一在同一「雨夜」时间设定下生成，禁止天光/夜景/色调冲突；特写格纯空景、不描写人物（老周不入图）。
