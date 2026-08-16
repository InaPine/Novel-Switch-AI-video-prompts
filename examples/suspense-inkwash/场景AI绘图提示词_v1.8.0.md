画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · AI 绘图场景提示词（v1.8.0 · 阶段三）

> 依据《剧本.md》场景列表（编号 1-6，单时空「古籍库·夜」）生成。水墨画风贯穿全篇：柔化轮廓、低饱和墨色、留白构图；夜景仍保持——墨色层次加深、雨夜冷蓝天光与手电冷白光柱形成冷暖对比。
>
> 结构分**两部分，用户仅需复制两次提示词**即可完成全部生图：
> - **第一部分（文生图）**：空间锚点图，复制第 1 次；
> - **第二部分（图生图）**：最终合成图，复制第 2 次，一次图生图，**排版由 AI 一次完成**。

---

## 〇、统一设定表与空间基准表（复用，不重新发明）

以下两张表出自《剧本.md》，阶段三全部提示词（锚点图 / 宏观格 / 各特写格 / 一致性提醒）的数值与措辞均出自此表，禁止另起炉灶。

### 统一设定表

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间 7m × 进深 14m × 层高 3.6m |
| 四面墙朝向与功能 | 北墙=入口双开木门（门牌「古籍库」）；南墙=老式推窗与窗台（雨夜天光来源）；东墙、西墙=成排到顶木书架 |
| 固定布局 | 中央过道沿南北中轴贯通（自北门至南窗）；书架贴东西两墙成排；最后一排书架靠近南窗，《县志》在其顶层摊开；湿脚印自南窗台沿过道向北延伸 |
| 机位坐标系约定 | 每张图机位用「位于空间何处、面朝哪个方向（N/S/E/W）」描述，全部分图共用此坐标系；锚点图标注 N/S/E/W 与比例 |

**锚定顺序建议**：先按第一部分文生图生成空间锚点图 → 第二部分以锚点图为参考图/垫图一次图生图，靠各格「画面锚定句」把画面左/中/右/纵深应出现哪个结构写进文字；纯文生图时靠空间基准表+机位定位句降低漂移（模型无法保证 100% 几何一致，属已知局限）。

---

## 第一部分：空间锚点图（1 条提示词 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为「空间锚点图」。此图是其余所有图的布局与方位基准。

**提示词（整段复制）**：

> Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones, soft ink textures and muted low-saturation color palette, ultra HD, 8k.
>
> A top-down isometric floor plan of a third-floor archive room measuring 7m wide × 14m deep × 3.6m high. North wall = entrance double wooden door with the nameplate "古籍库" (zone 1 DOORWAY); South wall = old aluminum-frame window and sill (zone 3 WINDOW, source of the cold-blue rainy-night light); East wall and West wall = rows of floor-to-ceiling dark-brown wooden bookshelves; a central aisle runs north–south along the central axis from the north door to the south window (zone 2 AISLE). Mark the trail of wet footprints extending northward from the south windowsill along the central aisle floor (zone 4 FOOTPRINTS). Mark the last row of bookshelves near the south window with an open county gazetteer on its top shelf (zone 5 LAST SHELF and zone 6 BEFORE SHELF). Label compass directions N / S / E / W and the size proportions 7m × 14m × 3.6m. Note: all other images use this plan's layout and orientation as the reference.

---

## 第二部分：最终合成图（1 条提示词 · 一次图生图 · AI 完成排版）

**用户操作（固定格式）**：

> 将「空间锚点图」作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）；**复制下面整段提示词，一次图生图**。**排版拼接由 AI 一次完成**：AI 生成的合成图即最终排版成品（宏观图置顶大格 + 特写按空间动线排列 + 图注标签），无需用户手动排版；如需单张使用，按下方「格子索引表」裁剪即可。若工具允许调节参考强度，建议中等偏强（如 Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6）。

**提示词（整段复制 · 一次图生图）**：

> All panels share the same room layout per the spatial reference image: a 7m-wide × 14m-deep × 3.6m-high third-floor archive room, north wall = entrance double wooden door with the nameplate "古籍库", south wall = old aluminum-frame window and sill (source of the cold-blue rainy-night light), east and west walls = rows of floor-to-ceiling dark-brown wooden bookshelves, a central aisle running north–south along the central axis from the north door to the south window, the last row of bookshelves near the south window with an open county gazetteer on its top shelf, and a trail of wet footprints extending northward from the south windowsill along the aisle.
>
> Arrange the image as one AI-composed multi-panel storyboard grid with thin gaps between panels and uniform frame sizes: one full-width top panel plus six equal close-up panels in 2 columns × 3 rows below it, no empty panels, each panel with a small caption label drawn beneath it ("MACRO", "SCENE 1 DOORWAY", "SCENE 2 AISLE", "SCENE 3 WINDOW", "SCENE 4 FOOTPRINTS", "SCENE 5 LAST SHELF", "SCENE 6 BEFORE SHELF").
>
> TOP PANEL (full-width, label "MACRO"): elevated wide establishing view, camera high at the northwest corner looking southeast down the central aisle. Anchoring: left frame = west-wall bookshelf rows receding; right frame = east-wall bookshelf rows receding; center = the north–south central aisle; far depth = the south window glowing faint cold blue from the rainy night; near depth = the north entrance double wooden door. Content: the whole archive room in muted ink wash, rows of dark-brown floor-to-ceiling bookshelves along both side walls, the empty central aisle, faint wet footprints on the gray water-matte stone floor, deep ink shadows and broad negative space, no people.
>
> ROW 1 PANEL 1 (label "SCENE 1 DOORWAY"): camera outside the north door in the dark corridor, facing south toward the doorway. Anchoring: left = door frame and the "古籍库" nameplate caught in a cold-white flashlight beam; center = the slightly ajar dark double wooden door with a narrow vertical crack of faint light; right = the dark corridor depth falling into ink shadow. Content: close view of the ajar double wooden door, the nameplate lit by a narrow cold-white flashlight beam, the door crack a thin bright line against the ink-dark wood, muted ink-wash rendering, no people.
>
> ROW 1 PANEL 2 (label "SCENE 2 AISLE"): camera just inside the north doorway, facing south straight down the central aisle. Anchoring: left = west-wall bookshelf row receding into darkness; right = east-wall bookshelf row receding into darkness; center = the central aisle as a corridor of faint light leading to the south window at the far end. Content: the long empty aisle between two walls of floor-to-ceiling bookshelves, a cold-white flashlight beam sweeping sideways across the shelves, dust drifting like fine snow in the beam, book spines glinting dim beige against dark-brown wood, the far south window a faint cold-blue rectangle, no people.
>
> ROW 2 PANEL 1 (label "SCENE 3 WINDOW"): camera at the south end of the aisle facing the south wall, slight low angle toward the open window. Anchoring: right = the open old aluminum-frame window with rain slanting in; center = the windowsill with a single small narrow wet footprint in the light; left = dark interior wall and bookshelf edge in ink shadow. Content: the open window at the end of the aisle, rain slanting in as fine silver threads in the cold light, water running down the window frame, a small child-sized wet footprint on the sill, cold-blue rainy-night glow, broad dark negative space on the left, no people.
>
> ROW 2 PANEL 2 (label "SCENE 4 FOOTPRINTS"): low camera near the floor, facing north away from the south window, looking along the floor. Anchoring: foreground = wet footprints glistening on the gray water-matte stone floor; center = the trail of footprints extending northward and fading into darkness; background = dark bookshelf shadows. Content: a trail of small wet footprints on the stone floor leading north, each print dimmer until the last one dissolves in shadow, a cold-white flashlight beam grazing the floor at a low angle, extreme low-angle emptiness, muted ink palette, no people.
>
> ROW 3 PANEL 1 (label "SCENE 5 LAST SHELF"): camera before the last row of bookshelves near the south window, slight low angle looking up at the top shelf. Anchoring: center = the top shelf with an old yellowed county gazetteer pulled out and lying open; left and right = dark bookshelf edges and book spines; behind = faint cold-blue south-window glow. Content: the top shelf of the last bookshelf row, an ancient gazetteer pulled from the shelf and lying open with vertical-print pages slightly rippling, a cold-white flashlight beam fixed steady on the open pages, surrounding shelves in deep ink shadow, no people.
>
> ROW 3 PANEL 2 (label "SCENE 6 BEFORE SHELF"): camera at mid distance before the last bookshelf row, facing the shelf from a slightly off-center angle. Anchoring: center = the open county gazetteer on the top shelf; right = the south window and its cold-blue rain glow; left = dark bookshelf rows and the empty aisle. Content: a wide view before the last bookshelf row, the gazetteer's pages fluttering in the wind blowing from the open window, the flashlight beam trembling faintly on the pages, large ink-black negative space, wind-and-rain motion contrasting with the still empty room, no people.
>
> Watercolor / ink-wash painting style, consistent lighting from the cold-white handheld flashlight beam and the faint cold-blue rainy-night glow from the south window, same architectural materials, multi-panel storyboard grid, soft ink textures, muted low-saturation palette, deep focus, 8k hyper-detailed, unified color palette.

---

## 格子索引表（供识别格子与按格裁剪，可选）

| 位置 | 内容 | 图注标签 |
|------|------|----------|
| 顶部大格（full-width top panel） | 宏观全景（空间总览） | MACRO |
| 第 1 行第 1 格 | 场景1·门口（北门虚掩 + 门牌） | SCENE 1 DOORWAY |
| 第 1 行第 2 格 | 场景2·书架间过道（中央过道） | SCENE 2 AISLE |
| 第 2 行第 1 格 | 场景3·窗边（南窗 + 窗台湿脚印） | SCENE 3 WINDOW |
| 第 2 行第 2 格 | 场景4·地面脚印（湿脚印北延） | SCENE 4 FOOTPRINTS |
| 第 3 行第 1 格 | 场景5·最后一排书架（顶层《县志》摊开） | SCENE 5 LAST SHELF |
| 第 3 行第 2 格 | 场景6·最后一排书架前（纸页被风吹动） | SCENE 6 BEFORE SHELF |

---

## 一致性提醒

- **光照一致性**：所有格子统一「手电冷白光柱（约5000K）+ 窗外雨夜冷蓝天光（约6500K）」；补光仅窗台微弱泛光与走廊尽头应急指示灯微弱冷绿；水墨夜景＝更深墨色层次+留白，不做明快配色。
- **建筑一致性**：主色调（墨褐木色＋冷灰蓝＋纸张米白）、材质（深褐旧木书架/水磨石地面/泛黄古籍纸页/深色双开木门/老式铝合金窗框/青灰砖墙）、标志性结构件（双开木门/到顶书架/老式推窗与窗台）全部统一。
- **空间一致性**：锚点图与合成图所有格子共用同一张**空间基准表**（7m×14m×3.6m；北门/南窗/东西书架；中央过道南北中轴；最后一排近南窗《县志》；湿脚印自南窗台北延）；每个格子都带「视角定位」（机位位置+朝向）与「画面锚定」（画面左/中/右/纵深标志物）；锚点图标注 N/S/E/W 与比例。
- **生成顺序一致性**：第一部分锚点图先用文生图单独生成；第二部分**一次图生图**生成整张合成图（以锚点图为参考图），不允许逐格单独文生图（工具不支持参考图时退化为纯文生图，此时每格画面锚定句是空间不乱的主要保障）。
- **排版一致性**：排版由 AI 在第二部分一次完成——**宏观大格置顶**、**特写按空间动线排列（门口→过道→窗边→地面脚印→最后一排书架→书架前，2 列×3 行）**、**每格带图注标签**；格间细缝、画幅统一、无空白格；禁止出现格子内容重复或宏观图不在顶部。
- **拍摄建议**：所有格子统一在同一时间设定（雨夜·古籍库）下生成，禁止出现相互冲突的天光/夜景/色调；特写格一律**纯空景、不描写人物**。
