画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景AI绘图提示词（v1.10.0）

> 依据剧本《雨夜档案馆》的场景列表与统一设定表生成；只生成文本提示词，不生成实际图片。
> 本文件分两部分，用户只需复制两次提示词即可完成全部生图：
> ① 空间锚点图（文生图）；② 最终合成图（图生图，锚点图为唯一空间来源）。

## 〇 统一设定表与空间基准表（复用 + 推导）

### 统一设定表（复用自剧本，供一致性核对）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（推导，供人阅读与生成锚点图用）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间（东西）7m × 进深（南北）14m × 层高 3.6m |
| 四面墙朝向与功能 | 北墙=入口双开木门（门口）；南墙=走廊尽头老式推窗与窗台（窗边）；东墙=成排到顶木书架；西墙=成排到顶木书架 |
| 固定布局 | 中央过道沿南北中轴贯通；东西两侧书架成排贴墙；最后一排书架近南窗，顶层《县志》摊开；湿脚印自南窗台沿过道向北延伸、渐淡消失 |
| 机位坐标系约定 | 每张图机位用"位于空间何处、面朝哪个方向（N/S/E/W）"描述，全部分图共用此坐标系 |

---

## 第一部分：空间锚点图（1 条 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为"空间锚点图"。这张图是第二部分全部空间信息的唯一来源。

**提示词（复制全部）**：

```text
Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones, ink-wash texture rendering, ultra HD, 8k. A single rectangular archive room 7m wide (east-west) by 14m deep (north-south) with a 3.6m ceiling, drawn as a top-down floor plan with compass directions labeled N / S / E / W. North wall: the double wooden entrance door at the center (SCENE 1: DOORWAY). South wall: the old push-open window with its ledge at the far end (SCENE 3: WINDOW). East wall: full-length rows of tall wooden bookshelves. West wall: full-length rows of tall wooden bookshelves. A central aisle runs along the north-south axis between the two shelf blocks (SCENE 2: AISLE). The last shelf row sits near the south window, with the "县志" county chronicle lying open on its top shelf (SCENE 5: LAST ROW SHELF); the open book is viewed from in front of that last row (SCENE 6: BEFORE SHELF). A trail of small wet footprints runs from the south window ledge northward along the aisle floor, fading out (SCENE 4: FOOTPRINT TRAIL). Label each zone with its number and name as above; mark the dimensions (7m × 14m, ceiling 3.6m) and compass N / S / E / W; add a note: "THIS PLAN IS THE ONLY SOURCE OF LAYOUT AND ORIENTATION FOR ALL OTHER IMAGES".
```

---

## 第二部分：最终合成图（1 条 · 一整段提示词 · 一次图生图）

**用户操作（固定）**：

> 将"空间锚点图"作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）。**AI 的空间信息唯一来自锚点图，提示词不描绘房间布局**；复制下面整段提示词，**一次图生图**。排版拼接由 AI 一次完成（顶部宏观全宽大格 + 下方 6 特写 2 列 × 3 行，每格带"序号+名称"图注），无需手动排版；如需单张使用，按"格子索引表"裁剪即可。参考强度建议中等偏强（Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6，建议偏强以让模型跟随锚点图）。

**提示词（一整段，复制全部）**：

```text
the spatial reference image is the ONLY source of room layout — follow it strictly; do not infer or alter the room structure from text. Render a single multi-panel storyboard grid in one image: a full-width top panel labeled MACRO, and below it six close-up panels in a 2-column × 3-row grid, each panel labeled with its number and name — SCENE 1: DOORWAY, SCENE 2: AISLE, SCENE 3: WINDOW, SCENE 4: FOOTPRINT TRAIL, SCENE 5: LAST ROW SHELF, SCENE 6: BEFORE SHELF — with thin gaps between panels and a uniform canvas. Top full-width panel (caption MACRO): camera at a high overhead vantage above the entrance area from the reference plan, facing down the central aisle toward the window end; content: the whole archive room in one wide ink-wash overview — rows of tall dark-brown wooden shelves, the terrazzo floor, the double wooden door, the far push-open window, a cold-white flashlight beam and faint blue rainy-night window light, drifting dust in the beam, deep ink shadows and generous negative space. Row 1 panel 1 (caption SCENE 1: DOORWAY): camera just inside the north doorway from the reference plan, facing south; content: the ajar double wooden door with a narrow gap of light, a cold-white flashlight beam falling across the terrazzo floor, a rain-darkened threshold, ink-wash softened edges and deep shadows. Row 1 panel 2 (caption SCENE 2: AISLE): camera partway down the central aisle from the reference plan, facing south toward the window end; content: tall dark-brown wooden shelves receding into darkness on either side, a cold flashlight beam sweeping across the aisle, dust motes floating in the beam, pale ivory book spines, terrazzo floor, low-saturation ink tones. Row 2 panel 1 (caption SCENE 3: WINDOW): camera at the window position from the reference plan, facing the window ledge; content: an open old push window with slanting rain, a small patch of wet footprints on the windowsill, rainwater running down the window frame, cold blue rain light, ink-wash silver rain lines. Row 2 panel 2 (caption SCENE 4: FOOTPRINT TRAIL): low camera near the window position from the reference plan, facing north back along the central aisle; content: a trail of small wet footprints on the terrazzo floor receding and fading into darkness, a flashlight beam grazing low across the floor, deep negative space. Row 3 panel 1 (caption SCENE 5: LAST ROW SHELF): camera at the last row position from the reference plan, facing the top shelf; content: the county chronicle volume "县志" pulled out and lying open on the top shelf, pale yellowed paper with vertical brush-stroke text, pages faintly lifting, a cold flashlight beam pinned on it, surrounding shelves dissolving into ink shadow. Row 3 panel 2 (caption SCENE 6: BEFORE SHELF): camera in front of the last row position from the reference plan, facing the open book; content: the open county chronicle with pages turning in a draft, a trembling cold flashlight beam on the paper, wind-stirred dust, deep ink shadows and large negative space. Watercolor / ink-wash painting style, consistent lighting from the cold-white flashlight beam (about 5000K) with faint blue rainy-night window light (about 6500K), same dark-brown wood and terrazzo materials throughout, soft ambient light, multi-panel storyboard grid, deep focus, 8k hyper-detailed, unified low-saturation ink color palette.
```

---

## 格子索引表（英文图注 + 中文对照）

| 位置 | 英文图注 | 中文对照 |
|------|---------|---------|
| 顶部全宽大格 | MACRO | 宏观全景 |
| 第 1 行第 1 格 | SCENE 1: DOORWAY | 场景1·门口 |
| 第 1 行第 2 格 | SCENE 2: AISLE | 场景2·书架间过道 |
| 第 2 行第 1 格 | SCENE 3: WINDOW | 场景3·窗边 |
| 第 2 行第 2 格 | SCENE 4: FOOTPRINT TRAIL | 场景4·书架过道（湿脚印） |
| 第 3 行第 1 格 | SCENE 5: LAST ROW SHELF | 场景5·最后一排书架 |
| 第 3 行第 2 格 | SCENE 6: BEFORE SHELF | 场景6·最后一排书架前 |

---

## 一致性提醒

- **空间唯一来源 = 锚点图**：第二部分提示词的空间信息只来自锚点图，生成时以锚点图为参考图，模型不得自行改写房间结构。
- **提示词无空间布局文字**：第二部分全文不出现 "north wall = door" / "south wall = window" / "east/west walls = shelves" 等空间结构描述，也不在机位句里补述门窗方位；空间结构信息一律只存在于锚点图。
- **每格只含机位 + 画面内容**：每个格子只写"格子位置/图注 + 机位（从锚点图何处、面朝何方）+ 画面内容（物体/道具/光线/画风）"三件事；机位取自锚点图坐标。
- **光照一致性**：所有格子统一雨夜光照——冷白手电光柱（约5000K）+ 微弱冷蓝雨夜天光（约6500K）+ 微弱冷绿应急光。
- **材质/画风一致性**：深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙；全图水墨画风（低饱和墨色、留白、柔化轮廓）。
- **生成顺序一致性**：先用第一部分文生图生成锚点图；第二部分一次图生图生成整张合成图，不允许逐格单独文生图（工具不支持参考图时无法保证空间一致，请更换支持参考图的工具）。
- **排版一致性**：宏观大格置顶、特写按空间动线（门口→过道→窗边→湿脚印→最后一排→最后一排前）排列、每格带"序号+名称"图注。
- **拍摄建议**：所有格子统一在同一雨夜时间设定下生成；特写格为纯空景（无人物）。
