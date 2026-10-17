# screenwriting-coach

剧本创作助手 Skill（编剧教练）。用户给出一个影视或视频创意（哪怕只有一句话），Skill 会先诊断创意缺什么，为每个缺口给出至少 3 个具体方案，待用户选定后生成故事大纲，大纲锁定后再生成时长与集数严格一致的剧本。

## 支持的类别

| 类别 | 默认体量 | 参考文件 |
|---|---|---|
| 电影 | 100 分钟 | `references/film.md` |
| 电视剧 | 24 集 × 45 分钟 | `references/tv-drama.md` |
| 网络剧 | 12 集 × 20 分钟 | `references/web-series.md` |
| AI 短剧 | 30 集 × 1 分钟（竖屏） | `references/ai-short-drama.md` |
| 广告 | 30 秒 | `references/advertisement.md` |
| 微电影 | 10 分钟 | `references/micro-film.md` |
| 纪录片 | 单集 10 分钟 | `references/documentary.md` |
| MV | 与歌曲时长一致 | `references/mv.md` |

所有类别共同遵守 `references/common.md`。

## 工作流程

1. **锁定三参数**：类别、总时长（或集数 × 单集时长）、画幅。
2. **创意诊断**：指出最多 5 个缺口（分为致命、重要、可选），每个缺口给出 A/B/C 三个方向不同的具体方案及推荐项。
3. **生成大纲**：按用户选择生成完整大纲，经审查后锁定版本号。
4. **生成剧本**：严格遵循大纲的集数与时长，附时长校验表。

## 目录结构

```
screenwriting-coach/          # 仓库根目录即 skill 目录
├── SKILL.md              # 流程、诊断格式、文件路由
├── README.md             # 本文件
├── LICENSE               # MIT
└── references/
    ├── common.md         # 通用规则：创意引擎、大纲骨架、一致性协议
    ├── film.md
    ├── tv-drama.md
    ├── web-series.md
    ├── ai-short-drama.md
    ├── advertisement.md
    ├── micro-film.md
    ├── documentary.md
    └── mv.md
```

## 使用方法

把整个仓库 clone 或下载到你的 skill 目录，目录名保持 `screenwriting-coach`（WorkBuddy 为 `~/.workbuddy/skills/`，其他支持 skill 的 AI 编程环境同理）：

```bash
git clone https://github.com/rupillsss-sketch/screenwriting-coach.git ~/.workbuddy/skills/screenwriting-coach
```

使用时直接描述创意，例如：

> 我想做一个微电影：一个程序员发现自己可能是虚拟出来的程序。

Skill 会先确认类别与时长，再进入诊断。

## 设计原则

- **先诊断，后创作**：不直接替用户写完，而是指出缺口、让用户选择。
- **一致性优先**：大纲锁定后，剧本的集数、时长、主要情节不得擅自改动。
- **真实性（纪录片）**：不编造事实，无素材的内容标注【待核实】。
- **合规**：广告遵守极限词规定，不照搬在世作品的情节、台词或歌词。

## 注意

- 各类别的默认时长、字数换算（如每分钟约 250–400 字）属于经验估算，建议结合实际生成结果校准。
- 目前的规范中尚无分镜格式，分镜规范将作为独立 skill 另行开发。

## 许可证

MIT，见 [LICENSE](LICENSE)。
