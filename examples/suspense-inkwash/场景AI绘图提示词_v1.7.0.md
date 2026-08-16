画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景 AI 绘图提示词（v1.7.0 · 阶段三）

> 依据剧本《雨夜档案馆》场景列表（6 场，单空间：三楼古籍库，雨夜）。本文件只含**两部分提示词，用户仅需两次操作**：第一次文生图生成空间锚点图，第二次图生图一次生成含"宏观图 + 6 特写"的多格合成图。画风全篇为水墨（Watercolor / ink-wash painting style）。

---

## 〇、统一设定表与空间基准表（复用 + 推导）

### 统一设定表（复用自剧本，不改动）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（按剧本 + v1.7.0 空间逻辑推导，全部分图共用）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 古籍库开间（东西）7m × 进深（南北）14m × 层高 3.6m（到顶书架即层高） |
| 四面墙朝向与功能 | 北墙=入口双开木门（中央，"古籍库"门牌）；南墙=老式铝合金推窗（中央，窗台）；东墙=成排到顶木书架（贴墙）；西墙=成排到顶木书架（贴墙） |
| 固定布局 | 中央过道贯通南北（北门—过道—南窗同一南北中轴）；书架成东西向排、被中央过道切分为西半排（过道→西墙）与东半排（过道→东墙），排间过道东西走向；最后一排书架位于南端（近南窗），顶层被抽出的《县志》摊开于东半排近过道一侧；湿脚印自南窗台起向北沿中央过道延伸并折入最后一排与倒数第二排之间的过道 |
| 机位坐标系约定 | 以入口门为北（N）、推窗为南（S）、面朝库内时东墙在右（E）、西墙在左（W）；每张图的机位用"位置 + 面朝方向（N/S/E/W 或相对方位）"描述，全部分图共用此坐标系 |

---

## 第一部分：空间锚点图（1 条提示词 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为"空间锚点图"。

```
Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style of a single rectangular archive reading room, 7m wide (east-west) by 14m deep (north-south) by 3.6m ceiling height, north wall = central double wooden entrance door labeled "古籍库", south wall = central old aluminum casement window with sill, east wall = full-height dark-brown wooden bookshelves, west wall = full-height dark-brown wooden bookshelves, central north-south aisle on the door-window axis, bookshelves arranged in east-west rows split by the central aisle into west-half and east-half rows, east-west cross aisles between rows, southernmost "last row" of shelves just north of the south window with an open county gazetteer 《县志》 pulled out on its top shelf near the aisle, wet footprints trail from the south windowsill northward along the central aisle, clear spatial layout with numbered zones and N/S/E/W compass labels and scale ratio, this top-down layout is the master reference for all other images, soft ink-wash line rendering, unified low-saturation ink-wash palette, ultra HD, 8k.
```

---

## 第二部分：最终合成图（1 条提示词 · 一次图生图）

**用户操作（固定）**：将"空间锚点图"作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）；**复制第二部分整段提示词，一次图生图**，得到一张包含"宏观图 + 6 特写"的多格合成图（分镜板式）；按格裁剪即可得到单张场景图。若工具允许调节参考强度，建议中等偏强（如 Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6）。

**提示词（一整段，直接复制，勿断行；9 格 = 3 列 × 3 行）**：

```
A 3-column by 3-row (9-panel) multi-panel storyboard grid, all panels share the same room layout per the spatial reference image. Row 1 Panel 1 (macro wide shot): camera at the north end of the central aisle just inside the entrance door, facing south, high wide view; frame anchors — near/bottom = north double wooden door with "古籍库" nameplate, left = west wall and west-half shelf rows receding into darkness, right = east wall and east-half shelf rows receding into darkness, center-depth = central north-south aisle ending at the south casement window and sill, southernmost "last row" of shelves just before the window; content = empty archive reading room, 3.6m ceiling height, 7m wide, 14m deep, central aisle, full-height dark-brown wooden shelves in east-west rows, wet footprint trail on the terrazzo floor from the south windowsill northward, open county gazetteer 《县志》 pulled out on the last row's top shelf near the aisle. Row 1 Panel 2 (scene 1 doorway): camera outside the north entrance door slightly east of center, facing south, close-to-medium shot; frame anchors — center = double wooden door ajar with a narrow gap and "古籍库" nameplate above, left = dark west corridor, right = dark corridor depth, depth = faint cold light through the door gap into the room; content = ajar double wooden door, narrow gap between leaves, cold light band spilling from the gap onto the corridor floor, empty scene. Row 1 Panel 3 (scene 2 shelf aisle): camera just inside the north door, facing south down the central aisle, medium-wide shot; frame anchors — left = west-half shelf rows receding into darkness, right = east-half shelf rows receding into darkness, center-depth = central aisle light channel ending at the south casement window; content = rows of full-height wooden shelves flanking the central aisle, sweeping light beam across the shelves, paper spines glowing warm off-white against dark-brown wood, dust floating in the beam, empty scene. Row 2 Panel 1 (scene 3 window side): camera at the south end of the central aisle slightly east of center, facing southwest, medium-wide to close shot with the window right-of-center; frame anchors — right = south casement window open with sill, center = small wet footprints on the windowsill in the light spot, left = west end of the last shelf row and dark west wall, depth = rainy night outside the window; content = open casement window at the corridor's end, rain slanting in, small narrow wet footprints on the sill, rainwater running down the frame, empty scene. Row 2 Panel 2 (scene 4 floor footprints): camera low at ground level at the south end of the central aisle, facing north, close-up; frame anchors — near/bottom = trail of wet footprints on the floor extending north from the south windowsill, left = west half of the last shelf row, right = east half of the last shelf row, depth = central aisle receding north to the dark entrance door; content = low-angle floor view, wet footprint trail fading into darkness along the aisle, terrazzo floor reflections, dark shelves in the background, empty scene. Row 2 Panel 3 (scene 5 last shelf row): camera in the cross aisle between the last row and the second-to-last row, facing the last row's north face, looking south, medium shot; frame anchors — center = top shelf of the last row with the open county gazetteer 《县志》 pulled out and laid open, left = west end of the last row toward the west wall, right = east end of the last row toward the east wall, depth = south casement window behind the row; content = the southernmost shelf row, open gazetteer on its top shelf with pages slightly moving, dark shelves receding on both sides, empty scene. Row 3 Panel 1 (scene 6 in front of the last row): camera at the south end of the central aisle slightly west of center, facing southeast, medium-wide shot; frame anchors — left-center = dark west end of the last shelf row and the central aisle, center = open county gazetteer 《县志》 laid open on the last row's top shelf, right = south casement window and cold blue light beam, depth = rainy night through the window; content = open gazetteer pages fluttering in the draft, wind and rain slanting through the open south window, terrazzo floor reflections, large dark negative space, empty scene. Row 3 Panel 2: empty panel. Row 3 Panel 3: empty panel. Watercolor / ink-wash painting style, consistent lighting from south-wall casement window rain-night skylight (approx. 6500K) plus faint cool-green emergency indicator, same architectural materials, multi-panel storyboard grid, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

---

## 格子索引（裁剪对照）

| 格子 | 对应图 | 图注 |
|------|--------|------|
| row 1 panel 1 | 宏观全景 | 宏观全景：古籍库整体·夜 |
| row 1 panel 2 | 场景1 | 场景1：三楼古籍库·门口·夜 |
| row 1 panel 3 | 场景2 | 场景2：古籍库·书架间过道·夜 |
| row 2 panel 1 | 场景3 | 场景3：古籍库·窗边·夜 |
| row 2 panel 2 | 场景4 | 场景4：古籍库·书架过道（地面湿脚印）·夜 |
| row 2 panel 3 | 场景5 | 场景5：古籍库·最后一排书架·夜 |
| row 3 panel 1 | 场景6 | 场景6：古籍库·最后一排书架前·夜 |
| row 3 panel 2 | 空白格 | （裁剪时跳过） |
| row 3 panel 3 | 空白格 | （裁剪时跳过） |

## 一致性提醒

- **光照一致性**：所有格子统一同一时间设定（雨夜），光源为南墙推窗雨夜天光（约 6500K）＋ 冷绿应急指示灯补光；特写格不描写人物（纯空景），故统一用环境光，不引入会漂移的移动手电主光。
- **建筑一致性**：主色调墨褐木色＋冷灰蓝＋纸张米白；材质统一为深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙；标志性结构件为双开木门、成排到顶木书架、南墙老式推窗与窗台。
- **空间一致性**：锚点图与合成图所有格子共用同一张空间基准表——空间尺寸 7m×14m×3.6m；四面墙功能（北门／南窗／东西书架）；固定布局（门—过道—窗同一南北中轴，书架东西向排、中央过道分东西半排，最后一排近南窗）；每个格子都带"视角定位"与"画面锚定"，锚点图标注 N/S/E/W 与比例。
- **生成顺序一致性**：第一部分锚点图先用**文生图**单独生成；第二部分**一次图生图**生成整张合成图（以锚点图为参考图），不允许逐格单独文生图；若工具不支持参考图，则退化为纯文生图，此时每格的画面锚定句是空间不乱的主要保障。
