画风：水墨（Watercolor / ink-wash painting style）

# 雨夜档案馆 · 场景AI绘图提示词（v1.6.0）

> 依据剧本《雨夜档案馆》场景列表（6 场，均为内景·夜，三楼古籍库）生成。
> 结构严格分**两部分**：第一部分 = 空间锚点图（文生图）；第二部分 = 宏观图 + 全部特写（图生图，以锚点图为参考图）。
> 全片水墨画风：柔化轮廓、低饱和墨色、大面留白；夜景以更深墨色层次与留白呈现，不因画风改时间/明暗。

## 〇 统一设定表与空间基准表

### 统一设定表（复用剧本）

| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 老周手持手电筒冷白光柱（约5000K，随动作移动）；窗外雨夜天光微弱冷蓝（约6500K） |
| 补光 | 走廊尽头应急指示灯微弱冷绿；雨云遮蔽月光，仅窗台处微弱泛光 |
| 主色调 | 墨褐木色＋冷灰蓝＋纸张米白（水墨低饱和） |
| 材质清单 | 深褐旧木书架、水磨石地面、泛黄古籍纸页、深色双开木门、老式铝合金窗框、青灰砖墙 |
| 标志性结构件 | 古籍库双开木门、成排到顶木书架、走廊尽头老式推窗与窗台 |
| 关键道具 | 老周铁皮手电筒、窗台上一小片湿脚印、顶层被抽出的《县志》（摊开） |

### 空间基准表（由剧本推导，全部分图共用）

| 项目 | 设定 |
|------|------|
| 空间尺寸 | 古籍库开间（东西）8m × 进深（南北）12m × 层高 3.4m（书架到顶） |
| 四面墙朝向与功能 | 北墙=入口：古籍库双开木门（门外为东西向走廊，门虚掩）；南墙=老式推窗＋窗台（中央过道南端尽头，雨从窗飘入，正对北墙入口门）；东墙=到顶木书架（整排贴墙）；西墙=到顶木书架（整排贴墙） |
| 固定布局 | 中央过道南北贯通（宽约1.5m）：北接双开木门，南抵推窗窗台；书架贴东西两墙整排到顶，中间另有平行于东西墙的若干排书架，形成多条南北向窄过道；最后一排书架=最南侧、紧邻南墙窗台的一排，顶层摊开《县志》；门—过道—窗在同一南北中轴线上 |
| 机位坐标系约定 | 以古籍库入口双开木门为"北（N）"，库房纵深朝"南（S）"；门外走廊沿北墙东西向（E–W）延伸；每张图的机位用"位于空间何处、面朝哪个方向（N/S/E/W）"描述，全部分图共用此坐标系 |

---

# 第一部分：空间锚点图（1 条 · 文生图）

**用户操作**：复制本节提示词，用**文生图**单独生成，保存为"空间锚点图"。这张图是第二部分所有图的参考图，先生成并保存。

```
Watercolor / ink-wash painting style, Top-down isometric aerial view, architectural floor plan / site-map style, a top-down isometric floor plan of a third-floor archive room (古籍库) at night, clear spatial layout with numbered zones, room 8m wide (east-west) by 12m deep (north-south) with 3.4m ceiling, NORTH wall = double-leaf wooden entrance door slightly ajar with a doorplate reading "古籍库", an east-west corridor running outside along the north wall, SOUTH wall = old-style casement window + windowsill with rain drifting in, EAST wall and WEST wall = full-height wooden bookshelves, a central aisle running north-south from the door to the window, several parallel bookshelf rows forming narrow north-south aisles, the southernmost shelf row (最后一排书架) nearest the window with an open book 《县志》 on its top shelf, label N/S/E/W compass directions and a scale/ratio, number the 6 scene zones (1=door/corridor, 2=central aisle, 3=window/windowsill, 4=floor aisle footprints, 5=last shelf row top shelf, 6=space in front of last shelf row), this plan is the spatial reference for all other images, ink-wash rendering, soft ambient light, ultra HD, 8k.
```

---

# 第二部分：宏观图与全部特写（图生图 · 以锚点图为参考图）

**用户操作**：将"空间锚点图"作为**参考图/垫图**输入生图工具（支持 ControlNet 的工具优先用 Canny/Depth 结构约束）；以下每条提示词复制进文字框逐条生成。若工具允许调节参考强度，建议中等偏强（如 Midjourney `--iw 1.0-1.5`、SD img2img denoise 0.45-0.6），文字与参考图共同约束空间。每条均含"视角定位"与"画面锚定"两行，画面锚定写死左/中/右/纵深的标志物——即使参考图失效，文字也能摆正空间。

## 二、宏观整体图（1 条）

以空间锚点图为参考图（图生图）生成。

**视角定位**：机位位于中央过道北端（入口门内侧），面朝南（朝库房纵深、朝南墙窗）。

**画面锚定**：画面近端（身后）=北墙双开木门；画面左=西墙整排到顶书架；画面右=东墙整排到顶书架；画面中=南北贯通的中央过道（水磨石地面）；画面纵深=南墙老式推窗＋窗台（正对入口门）。

```
Watercolor / ink-wash painting style, architectural/environmental wide-angle shot of a third-floor archive room at night, deep depth of field, room 8m wide by 12m deep with 3.4m ceiling, camera at the north end of the central aisle just inside the entrance door, facing south; near foreground behind camera = north-wall double-leaf wooden door; left side = full-height wooden bookshelves along the west wall receding into darkness; right side = full-height wooden bookshelves along the east wall receding into darkness; center = the north-south central aisle on terrazzo floor; depth = south-wall old-style casement window + windowsill directly opposite the entrance, rain-night skylight drifting in; dim cool-blue rain-night skylight through the window, faint cool-green emergency-light accent, low-saturation ink-wash palette (deep umber wood, cool gray-blue, paper cream), soft ambient light, ink-wash color grading, 8k hyper-detailed.
```

## 三、各小场景特写（6 条）

### 场景1 - 三楼古籍库·门口（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。近景（平视略低）。

**视角定位**：机位位于北墙门外走廊东段，面朝西南（正对双开木门，走廊向画面左右两侧延伸）。

**画面锚定**：画面中=北墙双开木门（门牌"古籍库"、门虚掩留窄缝）；画面左=走廊向西的暗部（老周来向）；画面右=走廊向东的漆黑深处（应急指示灯冷绿微光）；画面纵深=门缝内的库房黑暗。

```
Watercolor / ink-wash painting style, night interior of a third-floor corridor outside the archive-room entrance, camera in the corridor east of the door facing southwest; center = the north-wall double-leaf wooden door, slightly ajar with a narrow gap, doorplate reading "古籍库"; left = the corridor receding west into shadow; right = the corridor receding east into darkness with a faint cool-green emergency-light; depth = darkness inside the archive room through the door gap; dim cool-blue rain-night light, low-saturation ink-wash palette, deep umber wooden door and dark frame, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

### 场景2 - 古籍库·书架间过道（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。中全景（平视）。

**视角定位**：机位位于中央过道北端（入口门内），面朝南。

**画面锚定**：画面近端（身后）=北墙入口双开木门；画面左=西墙整排到顶书架；画面右=东墙整排到顶书架；画面中=南北向中央过道（水磨石地面）；画面纵深=南墙老式推窗＋窗台。

```
Watercolor / ink-wash painting style, night interior of the archive-room central aisle, camera at the north end just inside the entrance facing south; near foreground behind camera = north-wall double-leaf wooden door; left = full-height wooden bookshelves along the west wall receding into darkness; right = full-height wooden bookshelves along the east wall receding into darkness; center = the north-south central aisle on terrazzo floor; depth = south-wall old-style casement window + windowsill; dim cool-blue rain-night skylight through the window, faint cool-green emergency-light accent, low-saturation ink-wash palette, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

### 场景3 - 古籍库·窗边（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。中全景（平视略仰）。

**视角定位**：机位位于中央过道南段，面朝南偏西（正对南墙推窗，窗置于画面右侧）。

**画面锚定**：画面右=南墙老式推窗＋窗台（窗开、雨丝斜飘入）；画面中=窗台上一小片湿脚印（光斑正中）；画面左=中央过道向北延伸的暗部留白＋西墙书架暗影；画面纵深=窗外雨夜天光（冷蓝）。

```
Watercolor / ink-wash painting style, night close view of the archive-room south wall, camera in the south section of the central aisle facing south-southwest; right side = south-wall old-style casement window open, rain slanting in as fine silver lines, rainwater running down the frame; center = a small wet footprint on the windowsill; left side = the central aisle receding north into dark negative space with west-wall bookshelf shadows; depth = rain-night sky beyond the window, cool-blue; dim cool-blue rain-night skylight, low-saturation ink-wash palette, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

### 场景4 - 古籍库·书架过道（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。近景（低角度）。

**视角定位**：机位低角度贴地，位于中央过道南段（近窗台），面朝北（回望入口门方向）。

**画面锚定**：画面近景=水磨石地面湿脚印起点（近窗台）；画面中=湿脚印向纵深渐淡延伸；画面左=西墙整排到顶书架；画面右=东墙整排到顶书架；画面纵深=北墙入口双开木门（远处暗部，冷绿应急光透入）。

```
Watercolor / ink-wash painting style, night low-angle view of the archive-room floor, camera near the floor in the south section of the central aisle near the windowsill, facing north; near foreground = the start of a trail of small wet footprints on the terrazzo floor; center = the footprints receding and fading into the dark; left = full-height wooden bookshelves along the west wall; right = full-height wooden bookshelves along the east wall; depth = the north-wall double-leaf entrance door in the far dark with faint cool-green emergency-light; dim cool-blue rain-night light, low-saturation ink-wash palette, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

### 场景5 - 古籍库·最后一排书架（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。近景（平视略仰）。

**视角定位**：机位位于中央过道南端（最后一排书架北侧），面朝南（正对最后一排书架顶层）。

**画面锚定**：画面中=最后一排书架顶层被抽出的《县志》（摊开、泛黄竖排字迹）；画面近端=过道地面；画面左=西侧书架排；画面右=东侧书架排；画面纵深=南墙老式推窗＋窗台（《县志》后上方，雨夜天光透入）。

```
Watercolor / ink-wash painting style, night close-up of the top shelf of the southernmost bookshelf row, camera in the south end of the central aisle north of the last shelf row facing south; center = an old county chronicle 《县志》 pulled out and lying open on the top shelf, yellowed vertical-print pages slightly moving; near foreground = aisle floor; left = western bookshelf rows; right = eastern bookshelf rows; depth behind and above the book = south-wall old-style casement window + windowsill with rain-night skylight drifting in; dim cool-blue rain-night light through the window, low-saturation ink-wash palette, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

### 场景6 - 古籍库·最后一排书架前（内景 · 夜）

以空间锚点图对应部位为参考（图生图）生成。中全景（平视）。

**视角定位**：机位位于中央过道南段（最后一排书架前），面朝南（正对最后一排书架与南墙窗）。

**画面锚定**：画面中=摊开的《县志》（纸页被风吹动）；画面右=南墙老式推窗＋窗台（风灌入、雨丝）；画面左=中央过道向北延伸的暗部留白＋西墙书架暗影；画面纵深=南墙窗与窗外雨夜。

```
Watercolor / ink-wash painting style, night wide shot of the space in front of the southernmost bookshelf row, camera in the south section of the central aisle facing south; center = the open 《县志》 with pages fluttering in the wind; right = south-wall old-style casement window + windowsill, wind and rain blowing in; left = the central aisle receding north into dark negative space with west-wall bookshelf shadows; depth = the south-wall window and rain-night sky beyond; dim cool-blue rain-night skylight, low-saturation ink-wash palette, soft ambient light, deep focus, 8k hyper-detailed, unified low-saturation ink-wash palette.
```

---

# 四、排版拼接方案

- **空间锚点图独立放置**：放大单列置于整页左上角（或置顶），不与特写混排——它是参考图，生成特写时需单独调用。
- **主区域**：宏观整体图单独占一行（全宽），作为空间总览。
- **特写排列**：6 张按空间动线排成两列三行，行序为 场景1(门口) → 场景2(书架间过道) → 场景3(窗边) → 场景4(书架过道·地面脚印) → 场景5(最后一排书架) → 场景6(最后一排书架前)。
- **图注文字**：
  - 空间锚点图（第一部分·文生图）
  - 宏观全景（图生图）
  - 场景1：三楼古籍库·门口·夜
  - 场景2：古籍库·书架间过道·夜
  - 场景3：古籍库·窗边·夜
  - 场景4：古籍库·书架过道·夜
  - 场景5：古籍库·最后一排书架·夜
  - 场景6：古籍库·最后一排书架前·夜

# 五、一致性提醒

- **光照一致性**：全图统一为"窗外雨夜天光微弱冷蓝（约6500K）＋走廊应急指示灯冷绿补光＋手电冷白光柱（约5000K）"；纯空景特写以窗天光与冷绿补光为主，不做与统一设定表冲突的暖光/天光。
- **建筑一致性**：主色调（墨褐木色＋冷灰蓝＋纸张米白）、材质（深褐旧木书架、水磨石地面、泛黄纸页、深色双开木门、老式铝合金窗框、青灰砖墙）、标志性结构件（双开木门、到顶书架、南墙推窗与窗台）统一。
- **空间一致性**：锚点图、宏观图、特写共用同一张空间基准表——尺寸（8m×12m×3.4m）、四面墙功能（北门/南窗/东西书架）、固定布局（南北中央过道、最后一排书架近南墙）、机位坐标系（门=北、纵深朝南）必须一致；每条特写与宏观图都带"视角定位"与"画面锚定"两行，锚点图标注 N/S/E/W 与比例。
- **生成顺序一致性**：第一部分锚点图先用文生图单独生成；第二部分宏观图与特写一律以锚点图为参考图（图生图）生成，不得脱离锚点图纯文生图（若工具不支持参考图，才退化为纯文生图，此时画面锚定句是空间不乱的主要保障）。
- **拍摄建议**：各图统一在同一"雨夜·内景"时间设定下生成，禁止出现相互冲突的天光/夜景/色调；小场景特写不描写人物（纯空景）。
