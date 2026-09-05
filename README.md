# 视频风格蒸馏 (Video Style Distillation)

一个 TRAE 插件技能：拆解某位自媒体博主的视频风格，蒸馏成可复用的风格档案，再据此生成同款风格的新视频。

## 功能

- **风格分析**：从抖音等平台收集博主视频素材，用七维框架拆解风格
- **风格蒸馏**：把"感觉"转化为结构化参数（配色 Hex、BPM、单镜时长、字幕规范等），产出可复用的 `style-profile.md`
- **视频生成**：基于风格档案生成分镜脚本 + 视频 prompt，支持直接调用 GenerateVideo 出片或仅输出脚本

### 七维风格分析框架

| 维度 | 内容 |
|------|------|
| V1 视觉基因 | 配色、光影、画质风格、镜头语言 |
| V2 叙事结构 | 骨架类型、钩子方式、结构占比、转场 |
| V3 音频风格 | 人声、BGM、环境音、音画关系 |
| V4 字幕风格 | 字体、颜色、位置、动效、覆盖率 |
| V5 内容公式 | 选题模式、开头公式、结尾公式、话题标签 |
| V6 节奏与时长 | 平均时长、单镜时长、节奏曲线、信息密度 |
| V7 人格气质 | 人设定位、情绪基调、口头禅、与观众关系 |

## 安装

将本仓库克隆或下载，然后在 TRAE 中通过插件市场安装本地插件，或将 `.trae-plugin` 目录放入 TRAE 的插件目录。

## 使用

安装后，直接在对话中描述你的需求即可触发技能，例如：

- "帮我分析 @某博主 的视频风格"
- "模仿 @某博主 的风格做一个关于 XX 的视频"
- "把这个博主的风格蒸馏成模板"

技能会引导你走完四步流程：

1. **素材收集** — 提供博主主页链接或视频截图/文件
2. **风格分析** — 七维拆解，每维给出参数值和证据
3. **风格蒸馏** — 产出 `<博主>_style-profile.md` 风格档案
4. **风格应用** — 生成新视频的分镜脚本 + prompt，可选直接出片

## 目录结构

```
video-style-distillation/
├── .trae-plugin/
│   └── plugin.json          # 插件配置
├── assets/
│   └── icon.svg             # 插件图标
├── skills/
│   └── video-style-distillation/
│       ├── SKILL.md         # 技能主文件
│       └── references/
│           ├── style-profile-template.md   # 风格档案模板
│           └── storyboard-template.md      # 分镜脚本模板
└── README.md
```

## 配置

发布前请编辑 `.trae-plugin/plugin.json`，修改以下字段为你的真实信息：

- `author.name` / `author.email` / `author.url`
- `homepage` / `repository`
- `interface.developerName`
- `keywords`（可按需增减）

## License

MIT