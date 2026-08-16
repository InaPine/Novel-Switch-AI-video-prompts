画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景 AI 绘图提示词（v1.4.0 · 空间一致性版）

> 依据《雨夜档案馆》剧本场景列表（编号 | 地点 | 时间）生成，纯文本提示词，不生成图片。水墨画风：柔化轮廓、低饱和墨色、留白构图。本版新增**空间基准表 + 空间定位**机制：宏观图、布局图、每条特写共用同一套几何锚点（尺寸 / 四面墙功能 / 固定布局 / 机位坐标系），压制跨图空间漂移。

## 零、统一设定表（复用，不重新发明）与空间基准表（本版新增，由剧本推导）

### 统一设定表

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

> 时空组：全程为「古籍库·夜」一组。主光源=手电冷白光柱（约5000K，移动）+ 窗外雨夜冷蓝天光（约6500K）；补光=应急指示灯微弱冷绿。特写为纯空景，机位处无人物，故空景以「北墙推窗冷蓝雨夜天光 + 应急指示灯冷绿」为环境主光（手电属老周随身光源，仅在有人物入画时叠加）。

### 空间基准表（几何锚点，全部分图共用）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 开间（东西）8m × 进深（南北）20m × 层高 3.2m（开间:进深 ≈ 1:2.5） |
| 四面墙朝向与功能 | 南墙=双开木门入口（门牌"古籍库"）；北墙=老式推窗与窗台（走廊尽头、北墙正中）；东墙=成排到顶木书架区（东侧两排）；西墙=成排到顶木书架区（西侧两排） |
| 固定布局 | 中央走廊南北贯通（宽约1.8m，自南门直抵北墙推窗）；东西两侧各两排到顶木书架（南北向、书脊面朝中央走廊）；东侧两排之间、西侧两排之间各一条侧过道（宽约1.2m）；「最后一排书架」=东西书架区靠北墙的最北一跨（距北墙约0.8m，与推窗相邻），顶层放《县志》 |
| 机位坐标系约定 | 以南墙双开木门为基准：进门朝北为「前」、朝南为「后」、左手为西、右手为东；机位统一用「位于××处、面朝 N/S/E/W」描述；空间原点取南墙门内侧中点，X 轴向东、Y 轴（进深）向北 |

## 一、宏观整体图（1条提示词）

**主视角方位**：从古籍库双开木门处向内看，面朝北——门在机位身后（南墙），北墙老式推窗在画面深处正前方，东西两侧为到顶木书架区。

A third-floor ancient-archive reading room at midnight, seen from the double wooden door on the south wall looking north, an 8m × 20m room with a 3.2m ceiling, rows of dark aged wooden bookshelves reaching to the ceiling receding along both the east and west sides into shadow, a narrow 1.8m central aisle running south to north, an old aluminum casement window open at the far end of the north wall with rain drifting in and a faint cold-blue rainy-night glow, dust floating in a cold-white flashlight beam, wet footprints faint on the windowsill, ink-wash rendering with softened outlines, low-saturation muted ink-brown and cold gray-blue palette, generous negative space. `Watercolor / ink-wash painting style, architectural/environmental wide-angle shot, deep depth of field, 8k hyper-detailed, soft ambient light, low-saturation ink color palette, expressive ink-wash gradients, layered blank-space composition.`

## 二、俯视平面布局图（1条提示词）—— 空间锚点图

> 本图是**空间基准图**：图面严格按空间基准表绘制（开间:进深 ≈ 1:2.5，四面墙 N/S/E/W 标注，双开木门在南墙、老式推窗在北墙、东西两侧成排到顶木书架、中央走廊贯通南北），并注明"其余所有图的布局与方位以此图为准"；图内标注尺寸比例与方位。**其余所有图的布局与方位以此图为准。**

Top-down isometric aerial view of a third-floor ancient-archive reading room, an 8m × 20m rectangular floor plan with a 3.2m ceiling, drawn to the 1:2.5 width-to-depth proportion, with N/S/E/W compass labels — the double wooden entrance door (门牌"古籍库") centered on the south wall, the old push window with windowsill centered on the north wall, floor-to-ceiling wooden bookshelf rows running north-south along both the east and west sides with side aisles between each pair of rows, a 1.8m central corridor running south to north, numbered zones 1 to 6 marking: 1 door, 2 central shelf aisle, 3 window edge, 4 side shelf aisle, 5 last shelf row, 6 the space before the last shelf row, plus scale and compass annotations; note "all other images follow this layout and orientation", ink-wash muted palette with softened outlines. `Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones and N/S/E/W compass labels, soft ink textures, ink-line outlines, ultra HD, 8k.`

## 三、各小场景特写（每个编号各1条，纯空景无人物）

**场景1 - 古籍库·门口 - 平视近景**
空间定位：位于南墙双开木门外侧走廊约1.5m处，面朝北（正对门扇）；门牌"古籍库"在门右侧（东侧）墙面，门扇与门框之间虚掩留缝。

An aged double wooden door of the ancient-archive reading room at night, slightly ajar, a narrow gap of light between door and frame, a worn "古籍库" nameplate on the dark wood to the right (east) of the door, deep brown wood grain, faint cold-green emergency-indicator glow from the corridor, deep shadow on the corridor side, ink-wash softened outlines, low-saturation ink-brown palette. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

**场景2 - 古籍库·书架间过道 - 平视中全景**
空间定位：位于南墙门口内侧约2m处，面朝北（沿中央走廊看向北墙推窗方向）；左右两侧为东西到顶木书架区，中央走廊居中、直抵北墙窗。

The central aisle between rows of dark aged wooden bookshelves reaching to the ceiling, seen from 2m inside the south door looking north toward the push window on the far north wall, aged paper spines in pale beige catching the faint cold-blue rainy-night window light, dust motes floating in the air, terrazzo floor reflecting a faint cold gleam, shelves receding into ink-shadow on both the east and west sides, softened outlines, low-saturation muted ink-brown and paper-white palette, negative space in the shadows. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

**场景3 - 古籍库·窗边 - 略带俯视**
空间定位：位于中央走廊北端尽头约1.5m处，机位略偏西，面朝北（北墙老式推窗与窗台在画面右侧）；窗台湿脚印在光斑正中，窗下方地面为水磨石。

An old aluminum casement window open at the far end of the archive corridor on the north wall at night, placed on the right side of the frame, rain drifting in as fine bright threads, water trickling down the dark window frame, a small wet footprint on the windowsill with faint child-sized toe marks, cold gray-blue rainy-night light from outside, terrazzo floor beneath, ink-wash softened outlines, low-saturation muted palette, the windowsill footprint the single bright focal point. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

**场景4 - 古籍库·书架过道 - 低机位贴地**
空间定位：位于东侧过道南端入口处（中央走廊与东侧侧过道交口），低机位贴水磨石地面，面朝北（沿东侧过道看向书架纵深）；湿脚印自北墙窗侧向南延伸进过道，越往南越淡。

A low close view of the terrazzo floor at the south mouth of the east-side shelf aisle at night, a trail of small wet footprints leading north from the direction of the north-wall window into the dark space between the bookshelf rows and fading away, a faint cold-blue gleam, water stains glinting faintly, the aisle mouth dark and empty, ink-wash softened outlines, low-saturation muted ink-brown and cold gray-blue palette, generous negative space. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

**场景5 - 古籍库·最后一排书架 - 仰视**
空间定位：位于「最后一排书架」（靠北墙最北一跨）正前方约1m处，仰视机位，面朝北（朝顶层）；《县志》摊开在顶层，其后方即北墙老式推窗，窗与书架间留约0.8m尽端过道。

An upward view of the top shelf of the last bookshelf row — the north-most bay against the north wall — at night, an aged county chronicle volume pulled out and laid open on the shelf, its yellowed pages with vertical printed characters barely rising and falling in the draft, the north-wall push window just behind the shelf with faint cold-blue rainy-night light, surrounding shelf edges melting into ink-shadow, ink-wash softened outlines, low-saturation paper-white and ink-brown palette. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

**场景6 - 古籍库·最后一排书架前 - 平视中全景**
空间定位：位于「最后一排书架」前、距北墙约3m处，面朝北；画面右侧为北墙老式推窗，中间为摊开的《县志》顶层，左侧大片暗部留白（空景，无人物）。

A wide view of the space before the last bookshelf row at night, the open county chronicle volume lying on the top shelf in the center, the north-wall push window on the right side with rain drifting in, large empty dark negative space filling the left and middle foreground, wind-turned pages the only motion, ink-wash softened outlines, low-saturation muted ink-brown and cold gray-blue palette. `Watercolor / ink-wash painting style, consistent lighting from the north-wall push window with faint cold-blue rainy-night skylight (approx. 6500K) plus a faint cold-green emergency-indicator glow, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.`

## 四、排版拼接方案

- **顶部横幅**：放「宏观整体图」，作为整组画面的空间总览与画风基调（机位自南门朝北，定下全组方位基准）。
- **中段左侧**：放「俯视平面布局图（空间锚点图）」，标注 N/S/E/W、尺寸比例与 6 个编号区域，作为其余所有图的空间参照。
- **主区域**：按 3 列 × 2 行排列 6 张小场景特写，行序自上而下、列序自左而右为：场景1、场景2、场景3（第一行）；场景4、场景5、场景6（第二行），与空间动线（门口→书架间过道→窗边→书架过道→最后一排书架）一致。
- **图注文字**：
  - 「宏观全景：古籍库·夜（面朝北）」
  - 「俯视布局（空间锚点图）：古籍库·夜·N/S/E/W」
  - 「场景1：古籍库·门口·夜」
  - 「场景2：古籍库·书架间过道·夜」
  - 「场景3：古籍库·窗边·夜」
  - 「场景4：古籍库·书架过道·夜」
  - 「场景5：古籍库·最后一排书架·夜」
  - 「场景6：古籍库·最后一排书架前·夜」

## 五、一致性提醒

- **光照一致性**：全部场景统一为手电冷白光柱（约5000K，移动）＋窗外雨夜冷蓝天光（约6500K）双光源，补光为应急指示灯微弱冷绿；禁止出现白昼、暖阳或其他色温冲突的天光。
- **建筑一致性**：主色调统一为墨褐木色＋冷灰蓝＋纸张米白（低饱和）；材质统一为深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙；标志性结构件统一为双开木门、成排到顶木书架、走廊尽头老式推窗与窗台。
- **空间一致性（本版新增）**：宏观图、布局图、特写共用同一张**空间基准表**——开间8m×进深20m×层高3.2m、四面墙功能（南门/北窗/东西书架）、固定布局（中央走廊贯通、最后一排书架靠北墙）、机位坐标系（朝北为前）必须一致；宏观图带主视角方位（自南门朝北），每条特写带"空间定位"行（位于何处、面朝何方），布局图标注 N/S/E/W 与 1:2.5 比例并声明为空间锚点图。
- **拍摄建议**：各图统一在同一「午夜雨夜」时间设定下生成，画风统一为水墨（柔化轮廓、低饱和、留白构图）；所有小场景特写均为纯空景、不描写任何人物；光影方向与空间动线前后呼应。
- **生成方式建议**：为获得最强跨图空间一致性，先出「俯视平面布局图」作空间锚点图，再用图生图/参考图（垫图/ControlNet）模式生成宏观图与特写；纯文生图模式下空间漂移无法完全消除，属模型固有局限。
