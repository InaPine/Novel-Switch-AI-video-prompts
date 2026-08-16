画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景 AI 绘图提示词（v1.11.0 · 分两部分）

> 依据：剧本《雨夜档案馆》（6 场，水墨画风）。本文件为第三阶段产物，场景提示词**分两部分**：第一部分文生图生成空间锚点图，第二部分一次图生图生成最终合成图。
> 画风贯穿全文件：柔化轮廓、低饱和墨色、留白构图；统一光照 = 冷白手电光（≈5000K）＋微弱冷蓝雨夜天光（≈6500K）。

---

## 〇、统一设定表与空间基准表（复用 + 推导，供人阅读与生成锚点图用）

### 统一设定表（原样复用剧本，不重造）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（剧本未给出，按剧本画面推导）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间约 9m（东西）× 进深约 16m（南北）× 层高约 3.4m，矩形古籍库 |
| 四面墙朝向与功能 | 北墙=双开木门（唯一入口）；南墙=走廊尽头老式推窗与窗台；东、西墙=到顶书架列贴墙延伸 |
| 固定布局 | 书架成排沿东西向排列，排间留南北向过道；中央主过道自北门直贯南窗；最后一排书架位于南侧近窗处；湿脚印自南窗台向北没入主过道后渐淡 |
| 机位坐标系约定 | 以俯视锚点图为唯一基准，北=入口、南=窗；机位统一用"位于锚点图何区、面朝何方向（N/S/E/W）"描述，全部分图共用此坐标系 |

---

## 第一部分：空间锚点图（1 条 · 文生图）

### 用户操作

复制本节提示词，用**文生图**单独生成，保存为"空间锚点图"。**本提示词是全流程唯一允许描绘空间布局与物品位置的提示词**，其余所有图的布局与方位均以此图为准。

### 提示词

```text
Watercolor / ink-wash painting style, top-down isometric aerial view, architectural floor plan / site map style. A rectangular third-floor archive room, 9 m wide east–west × 16 m deep north–south × 3.4 m high, drawn as one flat readable plan. North wall: a double wooden door, the only entrance. South wall: an old push-open window and sill at the far end. East and west walls: rows of floor-to-ceiling dark-brown wooden bookshelves running along the walls, framing a central north–south aisle that runs straight from the north door to the south window. The southernmost shelf row sits just north of the south window. A thin trail of wet footprints leads from the south windowsill north into the central aisle and fades out. An opened old county gazetteer (县志) lies open on top of the southernmost shelf row. A cold white handheld flashlight beam (≈5000K) reaches from the north entrance toward the south, and faint cold-blue rainy-night skylight (≈6500K) washes in from the south window. Label the four compass directions N / S / E / W, mark the scale, and place six clear numbered zone markers: 1 at the north doorway, 2 at the north end of the central aisle, 3 at the south window, 4 on the central aisle floor near the wet footprints, 5 at the southernmost shelf row, 6 just north of the southernmost shelf row. Add the note: "this plan is the only source of layout and orientation for all other views." Muted ink palette, low saturation, deep shadow negative space, soft ink-wash rendering, ultra HD, 8k.
```

---

## 第二部分：最终合成图（1 条 · 一整段提示词 · 一次图生图）

### 用户操作（固定）

将"空间锚点图"作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）；**锚点图是空间的唯一来源**，本段提示词不含任何空间/物品文字。**复制下面整段提示词，一次图生图**。**排版由 AI 一次完成**：AI 生成的合成图即最终排版成品（顶部 MACRO 全宽大格 + 下方 6 特写 2 列 × 3 行 + 每格图注），无需手动排版；如需单张使用，按"格子索引"裁剪即可。若工具允许调节参考强度，建议中等偏强（如 Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6）。

### 提示词（一整段，一次图生图）

```text
the spatial reference image is the ONLY source of room layout and scene content — follow it strictly; do not infer or alter the room structure or any objects from text. Compose a single multi-panel storyboard grid: one full-width top panel labeled MACRO, and below it six close-up panels arranged in 2 columns × 3 rows, each with its caption label drawn beneath it. Top panel MACRO: camera at a high vantage over the reference plan's north side, facing south across the entire depth; ink-wash rendering, cold low-saturation tones, deep shadow, generous negative space. Row 1 panel 1, SCENE 1: DOORWAY: camera at the reference plan's north side, at the position marked SCENE 1, facing south into the interior, eye level; ink-wash, cold low-saturation tones, deep shadow negative space, one cold light accent. Row 1 panel 2, SCENE 2: AISLE: camera just inside the reference plan's north side, at the position marked SCENE 2, facing south along the central line, slightly above eye level; ink-wash, cold low-saturation tones, deep shadow, soft light falloff. Row 2 panel 1, SCENE 3: WINDOW: camera at the reference plan's south side, at the position marked SCENE 3, facing north back toward the interior, eye level; ink-wash, cold low-saturation tones, deep shadow, faint cool edge light. Row 2 panel 2, SCENE 4: AISLE FLOOR: camera very low at the reference plan's south side, at the position marked SCENE 4, facing north along the central line; ink-wash, cold low-saturation tones, deep shadow, low light pool. Row 3 panel 1, SCENE 5: LAST SHELF: camera at the reference plan's south side, at the position marked SCENE 5, facing east, eye level then slightly pushing in; ink-wash, cold low-saturation tones, deep shadow, narrow cold beam highlight. Row 3 panel 2, SCENE 6: BEFORE SHELF: camera at the position marked SCENE 6 on the reference plan, just north of the position marked SCENE 5, facing east, wide stationary; ink-wash, cold low-saturation tones, deep shadow, cold beam with subtle motion. Watercolor / ink-wash painting style, consistent lighting from the cold flashlight beam (≈5000K) and faint cold-blue rainy-night skylight (≈6500K), same muted ink palette, multi-panel storyboard grid, deep focus, 8k hyper-detailed, unified color palette.
```

### 格子索引表（英文图注 + 中文对照）

| 格子位置 | 英文图注 | 中文对照 |
|----------|----------|----------|
| 顶部全宽大格 | MACRO | 空间全景总览（高位全景） |
| 第 1 行第 1 格 | SCENE 1: DOORWAY | 场景1 · 古籍库门口 |
| 第 1 行第 2 格 | SCENE 2: AISLE | 场景2 · 书架间过道（进门横移） |
| 第 2 行第 1 格 | SCENE 3: WINDOW | 场景3 · 窗边 |
| 第 2 行第 2 格 | SCENE 4: AISLE FLOOR | 场景4 · 书架过道（地面低机位） |
| 第 3 行第 1 格 | SCENE 5: LAST SHELF | 场景5 · 最后一排书架 |
| 第 3 行第 2 格 | SCENE 6: BEFORE SHELF | 场景6 · 最后一排书架前 |

---

## 一致性提醒

- **光照一致性**：所有格统一为冷白手电光（≈5000K）＋微弱冷蓝雨夜天光（≈6500K），冷灰蓝/墨褐低饱和，色温方向前后一致。
- **建筑一致性**：主色调、主要材质、标志性结构件统一，全部出自上方统一设定表。
- **空间一致性（唯一来源原则）**：空间的唯一来源是锚点图——第二部分提示词**不得用文字描绘房间布局或任何物品/道具/结构及其空间关系**；每格只给"机位（从锚点图何处、面朝何方）+ 画面风格（画风/光效氛围）"，机位取自锚点图坐标系；画面内容由锚点图与图注名称承载，模型不得自行改写房间结构。
- **生成顺序一致性**：第一部分锚点图先用文生图单独生成；第二部分**一次图生图**生成整张合成图（以锚点图为参考图、唯一空间来源），不允许逐格单独文生图。若工具不支持参考图，则空间一致性无法保证，应更换支持参考图的工具。
- **排版一致性**：排版由 AI 在第二部分一次完成——宏观大格置顶 + 特写 2 列 × 3 行 + 每格"序号+名称"图注（宏观标 MACRO）；禁止出现格子内容重复、宏观图不在顶部或图注缺失。
- **拍摄建议**：所有格子统一在"雨夜"同一时间设定下生成，禁止出现天光/夜景相互冲突；特写格纯空景、不描写人物。

---

## 生成说明（简短）

- **空间基准表为推导**：剧本仅给出统一设定表，本文件按 6 场画面（门口→过道→窗边→地面→最后一排书架→其前）推导出"北门、南窗、中央过道、南侧最后一排书架、湿脚印向北渐淡"的几何关系，并统一机位坐标系（北=入口、南=窗）。
- **画风适配（规则 6）**：布局图后缀句首补入画风词 `Watercolor / ink-wash painting style`；与水墨冲突的 `realistic material textures` 替换为 `soft ink-wash rendering`；光照统一句中的 `[主要光源方向]` 已替换为"冷白手电光 + 微弱冷蓝雨夜天光"。
- **两部分、仅两次操作**：文生图模型无跨图空间记忆，故锚点图先行生成并作为唯一空间来源；第二部分一次性图生图产出"宏观 + 6 特写 + 图注"的 AI 排版成品。
