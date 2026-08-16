画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景 AI 绘图提示词（v1.9.0 · 两部分）

> 依据阶段一剧本《雨夜档案馆》场景列表生成，共 6 场。水墨画风贯穿全篇：柔化轮廓、低饱和墨色、留白构图；雨夜氛围保持不变（冷蓝雨光＋冷绿应急灯，墨色层次加深）。
> 本文件严格分为**两部分**，用户只需复制两次提示词即可完成全部生图：
> **第一部分**＝空间锚点图（1 条 · 文生图）；**第二部分**＝最终合成图（1 条 · 一整段提示词 · 一次图生图 · AI 完成排版）。

---

## 〇、统一设定表与空间基准表（复用＋推导，全部提示词以此为准）

### 统一设定表（复用阶段一）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

> 注：阶段三特写格为**纯场景空景**（无人物），故主光去掉手电筒冷白光柱，统一以「南窗雨夜冷蓝天光（约6500K）＋北门应急冷绿指示灯」为恒定光源；手电光仅用于人出现时，空景不画。

### 空间基准表（推导自剧本场景列表与门/窗/书架方位）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间 7m（东西）× 进深 14m（南北）× 层高 3.6m；长方形，南北为长轴 |
| 四面墙朝向与功能 | 北墙＝入口双开木门（门口，场景1）；南墙＝老式推窗＋窗台（窗边，场景3）；东墙＝到顶木书架；西墙＝到顶木书架 |
| 固定布局 | 中央过道贯通南北中轴；书架沿东、西两侧墙成排；最后一排书架靠近南窗，《县志》在其顶层；湿脚印自南窗台沿过道向北延伸 |
| 机位坐标系约定 | 北门为入口起点、南窗为纵深终点；每格机位用「位于空间何处、面朝哪个方向（N/S/E/W）」描述，全部分图共用此坐标系 |

---

## 第一部分：空间锚点图（1 条提示词 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为「空间锚点图」。此图是后续所有图的几何基准。

```
Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, a top-down isometric floor plan of a long rectangular archives room (古籍库), 7m wide (east-west) × 14m deep (north-south) × 3.6m ceiling height; NORTH wall = double wooden entrance door (DOORWAY), SOUTH wall = old metal casement window with sill (WINDOW), EAST wall = floor-to-ceiling wooden bookshelves, WEST wall = floor-to-ceiling wooden bookshelves; a central aisle runs north-south along the central axis; the last bookshelf row stands near the south window with the county gazetteer (县志) spread open on its top shelf; a trail of wet footprints extends north from the south windowsill along the central aisle; label compass directions N / S / E / W and a dimension scale on the plan; mark the six scene zones with numbered labels and color blocks: 1 DOORWAY at the north wall, 2 AISLE at the central passage, 3 WINDOW at the south wall, 4 FOOTPRINTS on the floor, 5 LAST SHELF near the south window, 6 BEFORE SHELF in front of the last row; this plan is the master spatial reference for all other images; soft ink-wash rendering, muted low-saturation ink colors, soft ambient light, ultra HD, 8k.
```

---

## 第二部分：最终合成图（1 条提示词 · 一整段提示词 · 一次图生图 · AI 完成排版）

**用户操作（固定说明）**：
> 将「空间锚点图」作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）；**复制下面整段提示词，一次图生图**。**排版拼接由 AI 一次完成**：AI 生成的合成图即最终排版成品（顶部宏观全宽大格 + 下方 6 特写 2 列 × 3 行 + 每格序号＋名称图注），无需用户手动排版；如需单张使用，按「格子索引表」裁剪即可（裁剪可选）。若工具允许调节参考强度，建议中等偏强（如 Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6）。

**一整段提示词（复制以下全部英文）**：

```
All panels share the same room layout per the spatial reference image: a long rectangular archives room (古籍库) 7m wide (east-west) × 14m deep (north-south) × 3.6m ceiling height, with the double wooden entrance door on the NORTH wall, the old metal casement window with sill on the SOUTH wall, and floor-to-ceiling wooden bookshelves on the EAST and WEST walls; a central aisle runs north-south along the central axis; the last bookshelf row stands near the south window; a trail of wet footprints extends north from the south windowsill along the central aisle. Render a single multi-panel storyboard grid in Watercolor / ink-wash painting style, muted low-saturation ink colors (ink-brown wood, cold grey-blue, paper off-white), soft ambient light, unified color palette. Layout: one full-width top macro panel, then six close-up panels arranged in 2 columns × 3 rows with thin gaps between panels, reading order row 1 left-to-right, then row 2, then row 3. Draw a clear caption with the panel number and name beneath each panel in small legible English text, e.g. SCENE 1: DOORWAY, and label the macro panel MACRO.

Top full-width macro panel (MACRO): camera positioned high above the north doorway looking south along the central axis; the double wooden door in the near foreground (north), the central aisle receding to the south window in the deep background, the floor-to-ceiling bookshelves lining both east and west walls, the last bookshelf row near the south window, the faint wet footprint trail on the floor leading north from the window; overall cold blue rain-night ambient light from the south window, dim cold-green emergency light near the north door, ink-wash shading with large dark areas and reserved empty space.

Row 1 panel 1 (SCENE 1: DOORWAY): camera just outside the north doorway facing south into the room; the half-open double wooden door on the left, the narrow door-crack line of light on the right, the dark corridor receding behind, cold green emergency light glow; caption SCENE 1: DOORWAY.

Row 1 panel 2 (SCENE 2: AISLE): camera at eye level in the central aisle facing south; rows of floor-to-ceiling wooden bookshelves on both left and right receding into darkness, the central aisle light channel leading to the south window in the deep background, dust drifting in the faint light; caption SCENE 2: AISLE.

Row 2 panel 1 (SCENE 3: WINDOW): camera near the aisle center facing the south wall window; the open casement window on the right, slanting rain and raindrops on the windowsill, a small wet footprint on the sill, deep dark reserved space on the left; caption SCENE 3: WINDOW.

Row 2 panel 2 (SCENE 4: FOOTPRINTS): low camera angle near the floor facing north along the aisle; a trail of wet footprints on the terrazzo floor in the foreground leading north and fading into the dark depth, bookshelves towering on both sides, large dark reserved space; caption SCENE 4: FOOTPRINTS.

Row 3 panel 1 (SCENE 5: LAST SHELF): camera at eye level facing the last bookshelf row near the south window; the county gazetteer (县志) spread open on the top shelf, faint cold blue light from the south window on the aged paper, surrounding shelves in dark reserved shadow; caption SCENE 5: LAST SHELF.

Row 3 panel 2 (SCENE 6: BEFORE SHELF): camera in the aisle before the last bookshelf row facing south; the last bookshelf row with the open gazetteer at center, the south window with drifting rain beyond, the empty aisle foreground in dark reserved space; caption SCENE 6: BEFORE SHELF.

Consistent soft ambient light from the south window (cold blue rain-night light, ~6500K), same architectural materials (deep-brown aged wooden shelves, terrazzo floor, aged paper, dark double wooden door, old aluminum window frame, grey-blue brick wall), multi-panel storyboard grid, soft ink-wash rendering, 8k hyper-detailed, unified muted low-saturation color palette.
```

### 格子索引表（英文图注 + 中文名称对照）

| 格子位置 | 英文图注 | 中文名称对照 |
|----------|----------|--------------|
| 顶部全宽大格 | MACRO | 宏观全景（空间总览） |
| 第 1 行第 1 格 | SCENE 1: DOORWAY | 场景1·门口 |
| 第 1 行第 2 格 | SCENE 2: AISLE | 场景2·过道 |
| 第 2 行第 1 格 | SCENE 3: WINDOW | 场景3·窗边 |
| 第 2 行第 2 格 | SCENE 4: FOOTPRINTS | 场景4·地面脚印 |
| 第 3 行第 1 格 | SCENE 5: LAST SHELF | 场景5·最后一排书架 |
| 第 3 行第 2 格 | SCENE 6: BEFORE SHELF | 场景6·书架前 |

---

## 一致性提醒

- **光照一致性**：所有格子统一「南窗雨夜冷蓝天光（约6500K）＋北门应急冷绿指示灯」；空景不画手电光；色温与主色调（墨褐木色＋冷灰蓝＋纸张米白）全程一致。
- **建筑一致性**：主色调、主要材质（深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙）、标志性结构件（双开木门、到顶书架、老式推窗与窗台）统一。
- **空间一致性**：锚点图与合成图所有格子共用同一张**空间基准表**——开间 7m×进深 14m×层高 3.6m、北门/南窗/东西书架、中央过道南北中轴、最后一排近南窗《县志》、湿脚印自南窗台北延；每个格子都带「视角定位（机位位置＋朝向）＋画面锚定（左/中/右/纵深标志物）」，锚点图标注 N/S/E/W 与比例。
- **生成顺序一致性**：第一部分锚点图先用文生图单独生成；第二部分**一次图生图**生成整张合成图（以锚点图为参考图），不允许逐格单独文生图（工具不支持参考图时退化为纯文生图，此时每格画面锚定句是空间不乱的主要保障）。
- **排版一致性**：排版由 AI 在第二部分一次完成——宏观大格置顶、6 特写按空间动线（门口→过道→窗边→地面脚印→最后一排书架→书架前）排列为 2 列 × 3 行，**每格带「序号＋名称」图注（如 SCENE 1: DOORWAY，宏观标 MACRO）**；禁止出现格子内容重复、宏观图不在顶部或图注缺失。
- **拍摄建议**：所有格子统一在同一「雨夜」时间设定下生成，禁止出现相互冲突的天光/夜景/色调；特写格纯空景、不画人物。

---

## 改编说明（阶段三）

- 空间基准表在复用阶段一统一设定表的基础上，按剧本场景列表推导：门口（场景1）＝北墙双开门、窗边（场景3）＝南墙推窗、书架沿东西墙成排、中央过道贯通南北中轴，据此补全尺寸（7m×14m×3.6m）与「最后一排近南窗《县志》」「湿脚印自南窗台北延」两条几何锚定，全图共用同一坐标系。
- 特写格机位方向均回推自剧本【镜头】与【画面内容】：场景1 门口（近景）、场景2 过道（中全景横移）、场景3 窗边（中全景→近景）、场景4 地面脚印（低机位近景→特写）、场景5 最后一排书架（近景→特写）、场景6 书架前（中全景固定）。
- 宏观大格置顶作空间总览，6 特写按「门口→过道→窗边→地面脚印→最后一排书架→书架前」的空间动线排列，即观众入室后由门到窗、由地面脚印追到最后一排书架《县志》的动线。
