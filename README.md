# first-skill

将小说片段一键转换为**短剧制作三件套**的开源 Agent Skill 项目。

## 一、项目解决什么问题

小说改编短剧的常规流程是三道割裂的工序：编剧写剧本、分镜师拆镜头、美术出场景设定。三道工序各自为政，常见痛点：

- **风格不统一**：剧本的视觉基调、分镜的机位语言、场景图的材质光照各说各话，拼在一起不像一部戏
- **重复劳动**：同一段剧情要分别给编剧、分镜、美术三拨人讲三遍
- **口述难落地**：小说里的心理描写、抽象叙述直接搬进剧本会变成"旁白剧"，观众看不到任何行动

本项目用一个 Agent Skill（[Novel-Switch-AI video prompts](skills/Novel-Switch-AI%20video%20prompts/SKILL.md)）把三段工序串成一条**共用同一套世界设定**的流水线：输入一段小说原文，依次产出剧本、分镜、场景提示词三份 Markdown，角色、场景、光线、材质全程一致。

## 二、主要功能

三阶段流水线，输出顺序固定，每阶段产出独立 `.md` 文件：

| 阶段 | 输入 | 输出 | 关键规则 |
|------|------|------|----------|
| 一 | 小说片段 | **横屏短剧剧本**（16:9） | 人物表+场景列表+统一设定表；逐场戏（场景/时长/镜头/画面内容/对白/环境音/运镜建议）；每集 6-12 场、每场 15-45 秒；心理描写 100% 外化为动作/表情/道具；环境音每场必标 |
| 二 | 剧本 | **视频生成分镜方案** | 按话轮/景别/机位/沉默反应拆分为独立镜头，单镜 ≤10 秒；每镜含起始帧构图（6 子项）+动态时间轴+语音时间轴+运镜+衔接说明；编号全局连续 |
| 三 | 剧本场景列表 | **AI 绘图场景提示词** | 统一设定表+空间基准表；**★空间锚点图（特殊列出、先生成）**+宏观整体图+各小场景空景特写（含空间定位行）+排版拼接方案+一致性提醒；特写纯空景无人物；英文画风后缀固定格式；光照/材质/空间可验证 |

核心特性：

- **写实铁律**：默认写实画风——拒绝舞台剧式表演、拒绝旁白式心理叙述，所有内心活动转化为观众能看到的动作与道具
- **🎨 自定义画风（v1.2.0 新增）**：默认输出写实（Photorealistic），用户说"动漫风""水墨风""3D 渲染""赛博朋克""像素风"等即可切换画风，画风贯穿三阶段——剧本视觉基调、分镜光线质感、场景提示词英文后缀全部一致（预设画风表见 SKILL.md"画风配置"小节）
- **共用世界设定**：阶段一输出"统一设定表"（光源方向/色温/主色调/材质清单/结构件）+ **空间基准表**（空间尺寸/四面墙功能/固定布局/机位坐标系），阶段二、三强制复用，保证三份文件像同一部戏
- **空间一致性（v1.4→v1.5）**：宏观图/布局图/特写共用同一坐标系——**空间锚点图特殊列出、最先单独生成**（★标记），随后宏观图与各特写**以锚点图为参考图（图生图/垫图/ControlNet）**生成；每条特写带"空间定位"行，宏观图带主视角方位，缓解生图 AI 跨图几何漂移
- **可直接投喂生成模型**：分镜每个镜头构图自洽独立，场景提示词带固定英文后缀，均可单独作为文生图/文生视频提示词
- **自动落盘**：三份产物自动写入当前工作目录

## 三、安装方法

### 1. 获取项目

复制本项目目录（或下载 ZIP）。项目位于 GitHub 公开仓库：https://github.com/InaPine/Novel-Switch-AI-video-prompts

```bash
git clone https://github.com/InaPine/Novel-Switch-AI-video-prompts.git
```

### 2. 安装到 Agent 框架

本 skill 是标准的 `SKILL.md` 目录包，支持任何识别 SKILL.md 的 Agent 框架（Claude Code、Codex、DeepSeek Harness 等）。把 `skills\Novel-Switch-AI video prompts` 目录放进框架的 skill 目录即可。

**DeepSeek Harness**（本机已验证）：

```powershell
# 同步到用户 skill 根目录（目录名用 kebab-case，与 SKILL.md 的 name 一致）
Copy-Item "skills\Novel-Switch-AI video prompts" "$env:USERPROFILE\.dsh\skills\novel-switch-ai-video-prompts" -Recurse
```

同步后重启/刷新会话，即可在 skill 工具目录中看到 `novel-switch-ai-video-prompts`。

**Claude Code**：

```bash
mkdir -p ~/.claude/skills
cp -r "skills/Novel-Switch-AI video prompts" ~/.claude/skills/novel-switch-ai-video-prompts
```

**Codex / OpenAI Agents SDK**：放入项目或用户的 `.agents/skills/`（或 Codex 配置的 skills 目录）。`agents/openai.yaml` 中的 `interface.display_name` 会在 skill 选择器中显示。

### 3. 校验环境（可选）

运行 `quick_validate.py` 校验 skill 格式需要 Python 3.8+ 与 PyYAML。Windows 下可用 winget 安装（本机已用此方式验证）：

```powershell
winget install --id Python.Python.3.12 -e --accept-source-agreements --accept-package-agreements
python -m pip install pyyaml
```

## 四、使用方法

### 方式一：Agent 会话中直接使用（推荐）

在已安装本 skill 的 Agent 会话中，直接粘贴小说片段并说"改编成短剧"（或"改成剧本"、"出分镜"、"生成场景提示词"）。Agent 自动触发本 skill，依次完成三阶段并保存三份 Markdown：

1. `<剧名或第X集>_剧本.md`
2. `<剧名或第X集>_视频生成分镜.md`
3. `<剧名或第X集>_场景AI绘图提示词.md`

**自定义画风**：在指令中带一句画风要求即可，例如：

- "用动漫风改编这段" → 三份输出全部为 Anime style
- "这段改成赛博朋克风格" → 后缀替换为 Cyberpunk style
- 不指定画风 → 默认写实（Photorealistic）

**优先级约定**：你的显式指令（指定路径/文件名/篇幅/画风）优先于 skill 默认写法；片段撑不满 6 场时按实际内容定场数，不会为凑数虚构剧情。

### 拿到场景提示词后的两步生图流程（v1.5.0）

场景提示词文件会把"空间锚点图"特殊列出（★标记），生图时请严格按两步走，否则宏观图/平面图/特写会各生成各的空间：

1. **第 1 步·先生成空间锚点图**：用"★ 空间锚点图"的提示词单独生成俯视平面布局图，保存为空间基准
2. **第 2 步·用锚点图图生图**：宏观图与每条特写，都把锚点图（或其局部裁剪）作为**参考图/垫图/ControlNet** 输入生图工具，文字提示词只描述该视角下与锚点图的差异

生图工具不支持参考图时才退化为纯文生图——此时提示词里的"空间基准表 + 空间定位行"只能降低空间漂移概率，无法完全消除。

### 方式二：手动按指令执行

直接阅读 [SKILL.md](skills/Novel-Switch-AI%20video%20prompts/SKILL.md)，把其中三阶段流水线作为提示词交给任意大模型。

### 校验 skill 格式

```powershell
# 中文 Windows 请先设置 PYTHONUTF8=1（否则 GBK 读 UTF-8 文件会报错）
$env:PYTHONUTF8 = "1"
python "skills\Novel-Switch-AI video prompts\scripts\quick_validate.py" "skills\Novel-Switch-AI video prompts"
# 输出：Skill is valid!
```

## 五、输入输出示例

以下示例取自真实测试产出（`examples/slice-of-life/`，默认写实画风），与 skill 实际行为一致。

### 输入（用户粘贴的小说片段）

> 早上六点四十。陈建国在厨房煎鸡蛋，油锅里"滋啦"一声，他手一抖，蛋液溅到灶台上。十六岁的女儿陈晨坐在餐桌边，面前摊着一本数学卷子，笔尖悬在最后一道大题上空，半天没落。陈建国把煎好的蛋铲进盘子，端过去，放在她手边，又往她杯子里续了牛奶。他张了张嘴，想说"不会做就先放着"，最后只说出一句："牛奶趁热喝。"陈晨"嗯"了一声，没抬头。……（原文约 400 字，此处省略）

### 输出 1：剧本（节选，完整见 `examples/slice-of-life/剧本.md`）

```markdown
## 人物表
| 角色 | 身份 | 备注 |
|------|------|------|
| 陈建国 | 陈晨的父亲，四十出头 | 中学后勤职工，沉默寡言，深蓝旧围裙上留着洗不掉的油渍 |
| 陈晨 | 陈建国的女儿，十六岁 | 高二学生，刘海微乱，考前熬夜的倦色 |

【场景：一】（内景，家中开放式厨房·灶台区，清晨 6:40）
【时长：25秒】
【镜头】：（中全景→近景递进）
【画面内容】：……他手一抖，蛋液溅到灶台瓷砖上，白色蛋液顺着浅米色瓷砖淌下一道。他瞥了一眼，没擦，继续用铲子压蛋黄。横屏左右各置一人，中间隔着操作台。
【对白】：无对白
【环境音】：油锅滋啦声（贯穿）；油星爆裂声；挂钟滴答（远景）；晨间小区楼下隐约的汽车发动声。
【运镜建议】：固定起幅交代空间；随后缓慢推近至陈建国手部。
```

> 注意心理描写的外化：原文"想说'不会做就先放着'"在剧本中化为"他张了张嘴，喉结动了动，终究没出声"。

### 输出 2：视频生成分镜（节选，完整见 `examples/slice-of-life/视频生成分镜.md`）

```markdown
**镜头1（时长：6秒）**
起始帧构图：
- 景别：中全景
- 视角：平视
- 画面人物：陈建国在画面右侧灶台前；陈晨在画面左侧餐桌边，同框
- 人物朝向：陈建国侧脸朝右（面向灶台）；陈晨3/4侧面朝左（面向卷子）
- 位置关系：两人隔操作台一右一左，空间平行
- 画面重心：油锅与陈建国磕蛋的手

动态时间轴：0-2秒 油锅冒烟，陈建国单手磕蛋，蛋液滑入油锅；2-4秒 油星四溅，他手一抖，蛋液溅上灶台瓷砖；4-6秒 白色蛋液沿浅米色瓷砖淌下一道，他瞥一眼，继续用铲子压蛋黄。
语音时间轴：0-6秒 无对白；0-6秒 环境音：油锅滋啦声与油星爆裂声贯穿。
运镜：固定（0-6秒），中全景定场。
衔接说明：开场镜头，确立"开放式厨房+餐桌"同一空间与左右人物位置，为镜头5的横向调度和正反打做机位铺垫。
```

### 输出 3：AI 绘图场景提示词（v1.5.0 结构节选，完整见 `examples/suspense-inkwash/场景AI绘图提示词_v1.5.0.md`）

场景提示词按"〇 统一设定+空间基准表 → ★ 空间锚点图 → 宏观图 → 特写 → 排版 → 一致性"组织，空间锚点图特殊列出：

```markdown
## ★ 一、空间锚点图（俯视平面布局图，1条提示词）—— 生成流程第 1 步，单独生成、特殊列出

> 本节是全份提示词中唯一"先生成、独立生成"的图：请先单独生成此图并保存为"空间锚点图"，
> 作为后续所有图的空间基准；之后生成宏观图与各特写时，把它（或其局部裁剪）作为参考图输入生图工具。
> 其余所有图的布局与方位以此图为准。

Top-down isometric aerial view of a rectangular third-floor archive reading room (古籍库), ...,
16m wide × 22m deep × 4m ceiling. N wall = double wooden entrance door; S wall = casement window;
E/W walls = five rows of floor-to-ceiling wooden bookshelves; central corridor runs north-south.
Label six shot positions as numbered zones ①-⑥ ... Mark N/S/E/W and the scale ratio;
this image is the spatial anchor — the layout and orientation of ALL other images must follow it.
`Watercolor / ink-wash painting style, Top-down isometric aerial view, ...`

## 二、宏观整体图 —— 生成流程第 2 步，以锚点图为参考图

> 以空间锚点图为参考图（图生图）生成。主视角方位：从北墙入口向内看，面朝南……

### 场景1 - 古籍库·门口 - 近景→中全景
**以空间锚点图对应部位为参考（图生图）**
空间定位：位于北墙入口双开木门外侧约1.5m处，面朝南（正对门扇）……
```

> 使用时先单独生成 ★ 锚点图，再以它为参考图生成宏观图与各特写（详见"两步生图流程"）。

### 画风切换示例（同一输入，两种画风）

同一段输入，指令加一句"改成动漫风"，阶段三的场景提示词后缀会从写实切换为动漫（预设画风表见 SKILL.md）：

```markdown
# 写实（默认）            # 动漫（用户指定）
Photorealistic, ...   →   Anime style, ...
```

画风同时影响阶段一剧本的视觉基调（动漫风允许夸张表情与明快配色）和阶段二的光线质感描述，三份文件开头均标注"画风：…"以便核对。

### 更多完整示例

- `examples/` —— 三种类型片段（默认写实画风）的完整输出：
  - `examples/romance/`（都市言情，咖啡店重逢，午后）
  - `examples/suspense/`（悬疑惊悚，深夜公寓，夜）
  - `examples/slice-of-life/`（家庭日常，清晨厨房，晨）
- `examples/` —— 三种画风切换的完整输出（v1.3.0 画风功能验证产物）：
  - `examples/romance-anime/`（都市言情·雨夜便利店 × 动漫风 Anime style）
  - `examples/suspense-inkwash/`（悬疑惊悚·雨夜档案馆 × 水墨风 Watercolor / ink-wash）
  - `examples/scifi-cyberpunk/`（科幻·赛博都市 × 赛博朋克风 Cyberpunk style）
- `examples/suspense-inkwash/` —— 空间一致性机制的两版对比产物：
  - `场景AI绘图提示词_v1.4.0.md`（空间基准表 + 空间定位行）
  - `场景AI绘图提示词_v1.5.0.md`（★空间锚点图特殊列出 + 两步生成流程，推荐参考）

## 测试与已知约束

- 开发阶段做了两轮端到端测试（每个测试由独立子代理加载 skill 完整执行）：
  - **写实风测试（v1.0→v1.1）**：言情/悬疑/日常三类型片段，修复 14 条规范缺陷（优先级规则、统一设定表等）
  - **画风切换测试（v1.2→v1.3）**：言情×动漫 / 悬疑×水墨 / 科幻×赛博朋克三组，验证画风切换生效（三阶段后缀与"画风：…"标注一致、核心功能无损），修复 5 条画风细则缺陷——布局图后缀句首补画风词、每镜字段计数口径（5 顶层字段）、光照措辞随画风适配（规则 6）、画风不改变剧情氛围（规则 7）、写实措辞残留处理
  - **空间一致性（v1.4→v1.5）**：新增"空间基准表"与"空间定位"机制（v1.4.0），v1.5.0 将**空间锚点图特殊列出**——先单独生成锚点图，再以锚点图为参考图（图生图/垫图/ControlNet）生成宏观图与特写，固定两步生成流程；已用雨夜档案馆（suspense-inkwash）两版验证（`场景AI绘图提示词_v1.4.0.md`、`_v1.5.0.md`），子代理确认 ★锚点图单独成节、宏观图/特写均标注"以锚点图为参考图"；已知局限——纯文生图模型无跨图空间记忆，文字约束只能降低漂移概率
- **名称约束**：SKILL.md 的 frontmatter `name` 必须是 kebab-case（`novel-switch-ai-video-prompts`）——这是官方校验器（quick_validate.py）与 DeepSeek Harness 的共同要求；文件夹名可保留空格展示名（`Novel-Switch-AI video prompts`）。
- **中文 Windows 校验**：运行 quick_validate.py 前需设置 `PYTHONUTF8=1`。
- 每次修改 SKILL.md 后建议重新运行校验并重新同步到 `$DSH_HOME/skills`。

## 许可

[MIT](LICENSE)

第三方声明：`skills/Novel-Switch-AI video prompts/scripts/quick_validate.py` 改编自 [anthropics/skills](https://github.com/anthropics/skills) 的官方 skill-creator 工具（Apache License 2.0），脚本头部保留了来源标注，详见 LICENSE 文件末尾的 Third-party notices。
