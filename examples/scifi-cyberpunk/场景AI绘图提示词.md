画风：赛博朋克（Cyberpunk style）

# 《雾都新城》场景AI绘图提示词

（依据剧本场景列表：1 集装箱货场·集装箱顶 / 2 集装箱货场·集装箱内 / 3 集装箱货场·货场地面·墙根，均为夜）

## 零、统一设定表（复用阶段一，未重新发明）
| 项目 | 设定 |
|------|------|
| 主光源方向与色温 | 货场四周高层建筑的红/蓝/青紫霓虹广告牌（混光，约5000–9000K）低角度散射进雨幕；巡逻机冷白探照灯（约6500K）自上方间歇扫过 |
| 补光 | 集装箱锁扣红色指示灯（红光）；积水与雨幕的冷青色反光 |
| 主色调 | 深黑蓝底 + 霓虹红/蓝/青紫高光 + 冷灰雨雾（高对比、冷色调） |
| 材质清单 | 锈蚀波纹钢集装箱板、银白色冷藏箱（EX-7）、透明密封培养皿、雨水浸透的沥青地面、金属防雨棚、湿滑金属锁扣 |
| 标志性结构件 | 三层叠放的集装箱垛、防雨棚边缘、铁网围栏、货场墙根 |
| 关键道具 | 数据刀（带指纹识别锁扣）、EX-7冷藏箱、写有妹妹名字标签的培养皿、林澈的雨靴 |

## 一、宏观整体图（1条提示词）

```text
二十二世纪雨夜集装箱货场全景：三层叠放的锈蚀波纹钢集装箱垛向画面纵深延伸，冷灰雨雾弥漫；四周高层建筑的红/蓝/青紫霓虹广告牌光晕低角度散射进雨幕；地面沥青被雨水浸透、倒映流动的霓虹色斑；金属防雨棚边缘滴水成串，铁网围栏与远处巡逻机探照灯光柱若隐若现。Cyberpunk style, architectural/environmental wide-angle shot, deep depth of field, 8k hyper-detailed, neon lighting as per context, cinematic color grading, commercial photography style.
```

## 二、俯视平面布局图（1条提示词）

```text
集装箱货场俯视等轴测布局图：以编号色块标注三个区域——1号"集装箱顶"（货场东侧三层垛顶）、2号"集装箱内"（同一垛二层开启的箱体，霓虹光从门缝斜切入内）、3号"货场地面·墙根"（货场西侧围栏墙根与小径）；地面沥青与积水反光、成排集装箱几何块、铁网围栏清晰可辨。Cyberpunk style, Top-down isometric aerial view, architectural floor plan or site map style, clear spatial layout with numbered zones, realistic material textures, ultra HD, 8k.
```

## 三、各小场景特写（每个编号各1条，纯空景无人物）

### 场景1 - 集装箱顶 - 中近景平视（微俯）
```text
（纯空景，无人物）雨夜集装箱顶表面特写：锈蚀波纹钢顶面，雨水积成薄层并顺箱沿成串滴落；数据刀抵过的锁扣位置处，红/蓝霓虹光在湿金属上流动成高对比光斑；远景是雨幕中虚化的霓虹广告牌与成排集装箱垛轮廓，冷色调。Cyberpunk style, consistent lighting from surrounding high-rise red/blue neon billboards diffusing through rain, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景2 - 集装箱内 - 近景平视（门缝光斜切）
```text
（纯空景，无人物）集装箱内部特写：成排银白色冷藏箱（编号EX-7）整齐堆叠，箱面凝结水汽；霓虹光从半掩箱门缝斜切入内，在地面切出红蓝光带；冷气与雨雾交混，金属内壁与地面反光，冷色调高对比。Cyberpunk style, consistent lighting from surrounding high-rise red/blue neon billboards diffusing through rain, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

### 场景3 - 货场地面·墙根 - 中近景平视（低角度）
```text
（纯空景，无人物）货场墙根地面特写：雨水浸透的沥青地面与积水，倒映上方巨型霓虹灯牌的红蓝光斑；墙根锈蚀波纹钢与铁网围栏，防雨棚边缘滴水成串；远景探照灯光柱扫过雨幕，冷色调高对比。Cyberpunk style, consistent lighting from surrounding high-rise red/blue neon billboards diffusing through rain, same architectural materials, deep focus, 8k hyper-detailed, unified color palette.
```

## 四、排版拼接方案（纯文字描述）

- **顶部横幅**：放宏观整体图，横向通栏占满整幅宽度，图注文字"宏观全景：集装箱货场·夜"。
- **中段左下**：放俯视平面布局图，方形，图注文字"俯视布局：编号1/2/3区域相对位置"。
- **主区域**：3张特写按场景编号从左到右排成一行（1→2→3），图注文字依次为"场景1：集装箱顶·夜"、"场景2：集装箱内·夜"、"场景3：货场地面·墙根·夜"。
- **底部**：可选加一张统一设定表文字卡（光源方向与色温、主色调、材质清单），作为三张特写一致性的对照说明。

## 五、一致性提醒

- **光照一致性**：所有画面主光源为货场四周红/蓝/青紫霓虹广告牌（低角度散射 + 雨幕反光，约5000–9000K混光），冷白光探照灯（约6500K）自上方间歇扫过；人物与建筑受光方向、色温一致。
- **建筑一致性**：主色调统一为深黑蓝 + 霓虹红/蓝/青紫高光 + 冷灰雨雾；材质统一为锈蚀波纹钢、银白冷藏箱、透明培养皿、浸水沥青、金属防雨棚；标志性结构件（三层集装箱垛、防雨棚、铁网围栏、墙根）保持一致。
- **拍摄建议**：全部图统一在"夜·雨"设定下生成，禁止出现白天/晴天/暖色天光；小场景特写均为纯空景、不描写人物；宏观图与布局图可含远处巡逻机探照灯光柱，但不得出现角色特写。
