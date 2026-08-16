画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景 AI 绘图提示词（v1.5.0）

> 依据《雨夜档案馆 · 横屏短剧剧本》的场景列表生成。仅生成文本提示词，不生成图片。
> 本剧为单一"时空组"：**古籍库·夜**，全部提示词共用同一套光照与空间基准。
>
> **生成流程（两步，固定）**：
> **第 1 步：单独生成"空间锚点图"（★ 一，最先输出）→ 第 2 步：以空间锚点图为参考图（图生图/垫图/ControlNet）生成"宏观整体图"与"各小场景特写"。**

---

## 〇、统一设定表与空间基准表（复用，不重新发明）

### 统一设定表（复用自剧本）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（从剧本推导，全部提示词共用同一几何与坐标系）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间（东西）16m × 进深（南北）22m × 层高 4m |
| 四面墙朝向与功能 | 北墙=入口双开木门（居中偏西）+门旁"古籍库"门牌；南墙=走廊尽头老式推窗与窗台（居中，夜雨半开）；东墙=5排到顶木书架（南北纵深排列）；西墙=5排到顶木书架（南北纵深排列） |
| 固定布局 | 中央走道南北贯通（宽约2.5m），北接入口、南通窗台；东西两侧各5排到顶木书架，排间过道宽约1.5m，第1排靠北、第5排（最后一排）紧邻南墙窗台两侧；窗台正下方水磨石地面为湿脚印起点 |
| 机位坐标系约定 | N=北墙入口木门，S=南墙推窗与窗台，E/W=东西两侧书架纵深；全部机位用"位于空间何处、面朝哪个方向（N/S/E/W 或相对方位）"描述，全部分图共用此坐标系 |

---

## ★ 一、空间锚点图（俯视平面布局图，1条提示词）—— 生成流程第 1 步，单独生成、特殊列出

> **本节是全份提示词中唯一"先生成、独立生成"的图：请先单独生成此图并保存为"空间锚点图"，作为后续所有图的空间基准；之后生成宏观图与各特写时，把它（或其局部裁剪）作为参考图输入生图工具。其余所有图的布局与方位以此图为准。**

**提示词（英文）**：

```
Top-down isometric aerial view of a rectangular third-floor archive reading room (古籍库), architectural floor plan / site map style, drawn to scale with a marked scale bar and compass rose. Room dimensions 16m wide (east-west) × 22m deep (north-south) × 4m ceiling height. N wall = double wooden entrance door (slightly west of center) with the "古籍库" nameplate beside it; S wall = old casement window and sill (center, at the far end of the corridor); E wall = five rows of floor-to-ceiling dark-brown wooden bookshelves; W wall = five rows of floor-to-ceiling dark-brown wooden bookshelves; a central corridor (about 2.5m wide) runs north-south from the door to the window. Clearly label the six shot positions as numbered zones with tags: ① 门口 (north end, at the door), ② 书架间过道 (central corridor, north section), ③ 窗边 (south window sill), ④ 书架过道·湿脚印 (mid-corridor, footprint trail curving into the west aisle), ⑤ 最后一排书架 (west row 5, nearest the south wall), ⑥ 最后一排书架前 (in front of west row 5). Mark N/S/E/W and the scale ratio on the drawing; this image is the spatial anchor — the layout and orientation of ALL other images must follow it. Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones, soft ink-wash textures, ultra HD, 8k.
```

**用户操作（写给用户）**：先单独生成此图 → 保存得到"空间锚点图"；随后生成宏观图与各特写时，把它（或其局部裁剪）作为**参考图/垫图/ControlNet** 输入，文字提示词只描述该视角下与锚点图的差异。

---

## 二、宏观整体图（1条提示词）—— 生成流程第 2 步，以锚点图为参考图

> **以空间锚点图为参考图（图生图）生成。** 主视角方位：**从北墙入口向内看，面朝南**（N 在身后、S 南墙窗台在画面深处），与锚点图共用同一坐标系。

**提示词（英文）**：

```
Architectural/environmental wide-angle shot of the entire archive reading room (古籍库) at night, seen from the north entrance double wooden door looking south toward the far casement window, 4m ceiling height, room 16m wide and 22m deep per the spatial benchmark. Rows of floor-to-ceiling dark-brown wooden bookshelves line the east and west walls in receding perspective; a central terrazzo corridor runs north-south from the door to the south window; the old casement window at the far end is half open with rain slanting in. Lighting: faint cold-blue rainy-night skylight (about 6500K) entering from the south window, a cold-white handheld flashlight beam (about 5000K) sweeping down the corridor, weak cold-green emergency indicator glow at the corridor end. Overall tone: ink-brown wood, cold gray-blue, and paper off-white in low-saturation ink-wash washes with large areas of negative space. Watercolor / ink-wash painting style, architectural/environmental wide-angle shot, deep depth of field, 8k hyper-detailed, soft ambient light, ink-wash color washes and negative space.
```

---

## 三、各小场景特写（每个编号各1条，共6条）—— 生成流程第 2 步，以锚点图为参考图

> 每条均为**纯场景空景**（无人物、无角色）。视角回推自剧本【镜头】字段；`[主光源方向]` 已替换为统一设定表具体光源。

### 场景1 - 古籍库·门口 - 近景→中全景

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于北墙双开木门北侧（走道北端外），面朝南；门缝与门牌在前，南墙窗台在画面深处

```
Close-up of the slightly ajar double wooden door of the archive room (古籍库) at night: a narrow gap between the door leaf and the frame, the "古籍库" nameplate beside the door faintly lit, the dark corridor receding south behind the gap. Cold-white handheld flashlight beam (about 5000K) strikes the door gap and nameplate; faint cold-blue rainy-night skylight (about 6500K) glows faintly at the far end. Dark-brown old wood, terrazzo floor, blue-gray brick wall; ink-wash low-saturation tones with the door gap as the only bright line against deep ink darkness. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景2 - 古籍库·书架间过道 - 中全景

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于中央走道北段（刚进门处），面朝南；东西两侧第1-2排书架入画，深处是南墙窗台

```
Medium-wide shot of the central corridor between the bookcases in the archive room (古籍库) at night, looking south from just inside the door. Floor-to-ceiling dark-brown wooden bookshelves recede on both east and west sides; a cold-white handheld flashlight beam (about 5000K) sweeps sideways, lighting the bookshelf spines one by one, their paper spines turning off-white against the dark-brown wood; dust drifts in the beam like fine snow. Terrazzo floor corridor, faint cold-blue rainy-night skylight (about 6500K) from the south window far ahead. Ink-wash low-saturation contrast with two dark shelf depths flanking a bright central light channel and large negative space. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景3 - 古籍库·窗边 - 近景

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于南墙窗台正前方（走道南端），面朝南略偏西；推窗在画面右侧，湿脚印在窗台正下方

```
Close shot of the old casement window and sill at the far end of the archive room (古籍库) at night. The window is half open, rain slants in and glints as fine bright threads at the edge of a cold-white handheld flashlight beam (about 5000K); rainwater runs down the old aluminum window frame. On the sill is a small wet footprint, tiny and narrow, like a child's bare foot, caught in the center of the light spot. The window sits on the right of the frame, the wet footprint centered in the light, large dark negative space on the left. Faint cold-blue rainy-night skylight (about 6500K); ink-wash low-saturation tones, the rain threads like thin silver ink strokes. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景4 - 古籍库·书架过道·湿脚印 - 特写（低机位）

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于中央走道中段低机位，面朝南俯视地面；湿脚印从南墙窗台向北延伸，拐入西侧第4-5排之间过道

```
Low-angle close-up of the terrazzo floor of the archive room (古籍库) at night: a trail of small wet footprints stretches south-to-north from the window sill area, curving into the aisle between the west-side rows 4 and 5, growing fainter until it fades into darkness. A cold-white handheld flashlight beam (about 5000K) held close to the floor slides the light spot along the wet trail; faint cold-blue rainy-night skylight (about 6500K) from the south window far behind. Foreground wet footprints on dark terrazzo, background dark bookshelf depth, large ink-dark negative space. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景5 - 古籍库·最后一排书架 - 特写（略带仰视）

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于走道南端偏西，面朝西（朝向最后一排书架，即西侧第5排）；《县志》在顶层，南墙窗台在画面右侧后方

```
Close shot, slightly low angle, of the top shelf of the last row of bookcases in the archive room (古籍库) at night: a volume of 《县志》 has been pulled out and left lying open on the shelf, its yellowed pages slightly lifting, vertical-script characters on the paper. A cold-white handheld flashlight beam (about 5000K) stops on the open book; the shelves around it fall into ink-dark negative space. Faint cold-blue rainy-night skylight (about 6500K) from the south casement window behind to the right. Dark-brown old wood shelves, yellowed paper pages, low-saturation ink-wash tones with the book as the only bright center. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景6 - 古籍库·最后一排书架前 - 中全景

**以空间锚点图对应部位为参考（图生图）**
空间定位：位于西侧最后一排书架前（第5排前），面朝西略偏南；《县志》居中，右侧为南墙窗台与光柱

```
Medium-wide shot in front of the last row of bookcases in the archive room (古籍库) at night, looking slightly west. Wind pours in from the south casement window, flipping the open pages of the 《县志》 left on the top shelf, pages fluttering in the light; a cold-white handheld flashlight beam (about 5000K) stays fixed on the book, its light spot trembling faintly. The window and light column sit on the right, the open book in the center, large ink-dark negative space around; wind, rain and fluttering pages against the stillness of the dark room. Faint cold-blue rainy-night skylight (about 6500K); low-saturation ink-wash tones. Watercolor / ink-wash painting style, consistent lighting from a cold-white handheld flashlight beam (≈5000K) with faint cold-blue rainy-night skylight from the south casement window (≈6500K), same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

---

## 四、排版拼接方案

- **空间锚点图独立放置**：放大单列（或置于整页一角），不与特写混排——它是参考图，生成宏观图与各特写时需单独调用，图注写"空间锚点图（先单独生成）"。
- **主区域排列**：宏观图置于首行居中，6 张特写按空间动线排列——自上而下沿"N→S 走道"顺序排布：场景1（北门口）→ 场景2（走道北段）→ 场景3（南窗台）→ 场景4（走道中段湿脚印）→ 场景5（最后一排书架）→ 场景6（最后一排书架前）；每张图独立成块。
- **图注文字**：
  - 空间锚点图（先单独生成）
  - 宏观全景：古籍库·夜·从北墙入口向南看
  - 场景1：古籍库·门口·夜
  - 场景2：古籍库·书架间过道·夜
  - 场景3：古籍库·窗边·夜
  - 场景4：古籍库·书架过道·湿脚印·夜
  - 场景5：古籍库·最后一排书架·夜
  - 场景6：古籍库·最后一排书架前·夜

---

## 五、一致性提醒

- **光照一致性**：所有人物的光照方向、色温一致——主光源为老周手持手电筒冷白光柱（约5000K），辅以窗外雨夜天光微弱冷蓝（约6500K）与走廊尽头应急指示灯微弱冷绿。
- **建筑一致性**：主色调（墨褐木色＋冷灰蓝＋纸张米白）、主要材质（深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙）与标志性结构件（双开木门、成排到顶木书架、老式推窗与窗台）统一。
- **空间一致性**：锚点图、宏观图、特写共用同一张空间基准表——空间尺寸（开间16m×进深22m×层高4m）、四面墙功能、固定布局、机位坐标系必须一致；每条特写与宏观图都带机位方位（"位于何处、面朝何方"），锚点图标注 N/S/E/W 与比例。
- **生成顺序一致性**：锚点图必须先单独生成；宏观图与特写一律以锚点图为参考图（图生图）生成，不得脱离锚点图纯文生图（若工具不支持参考图，才退化为纯文生图，此时空间漂移无法完全消除）。
- **拍摄建议**：各图统一在同一时间设定（古籍库·雨夜）下生成，禁止出现相互冲突的天光/夜景/色调；小场景特写不描写人物。

---

## 交付说明（空间一致性生成流程，写给用户，两步固定）

纯文生图模型对"同一个房间"没有跨图记忆，宏观图/布局图/特写各自生成必然产生几何漂移。因此生成顺序固定为：
1. **先单独生成"空间锚点图"**（本文件★一节，全份提示词中唯一先生成的图），保存为空间基准；
2. **用空间锚点图图生图**：宏观图与每条特写一律以锚点图（或其局部裁剪）为参考图/垫图/ControlNet 输入，文字提示词只描述该视角下与锚点图的差异；
3. 若生图工具不支持参考图，才退化为纯文生图（此时空间基准表 + 空间定位行只能降低漂移概率，无法根除——如仍不一致，用图生图迭代修正）。
