# cinematic-image-prompt-builder

一个面向中文生图工作流的 Codex Skill。它的目标是把用户脑中比较模糊的画面想法，转换成结构完整、镜头语言清楚、光影色彩具体、可直接复制到生图模型里的中文提示词。

这套 Skill 主要服务单张图片生成，也考虑到这些图片后续可能会作为图生视频的第一步素材。

## 适合做什么

- 电影感大场景、战争、灾难、神话、末日、科幻城市
- 人物肖像、角色设定、古风人物、科幻人物、游戏角色
- 建筑空间、室内、街区、遗迹、未来基地
- 怪物、生物、神兽、异形、巨型生物
- 产品图、商业主视觉、科技产品、食品饮品
- 游戏概念图、世界观设定、载具、道具、服装设定
- 电影剧照、故事插画、关键事件、叙事瞬间

## 核心思路

它不是简单堆关键词，而是按画面任务组织提示词：

1. 判断这张图属于哪种画面任务。
2. 必要时追问 3-6 个问题。
3. 使用通用电影级提示词结构。
4. 用词库补全镜头角度、景别、构图、光线、色彩、材质。
5. 尽量使用正向表达，让 AI 明确知道“要生成什么”。

## 仓库结构

```text
docs/
  AI工作流说明.md
skills/
  cinematic-image-prompt-builder/
    SKILL.md
    agents/openai.yaml
    references/templates.md
    references/vocabulary.md
    references/examples.md
```

## 使用方式

把 `skills/cinematic-image-prompt-builder` 作为 Codex Skill 使用。调用时可以直接说：

```text
Use $cinematic-image-prompt-builder 帮我把“雨夜古城屋顶上的刺客”变成一份电影感生图提示词。
```

也可以把 `docs/AI工作流说明.md` 当作普通 AI 工作流说明，复制给 ChatGPT、Codex 或其他支持长上下文的 AI，让它按这套流程追问并生成提示词。

## 文件说明

- `SKILL.md`：Skill 主入口，说明何时触发、如何追问、如何输出。
- `references/templates.md`：万能主模板和画面任务分支模板。
- `references/vocabulary.md`：镜头、构图、光线、色彩、材质等可选词库。
- `references/examples.md`：完整示例和原始沙虫案例拆解。
- `docs/AI工作流说明.md`：给 AI 阅读的工作流说明，不依赖 Codex Skill 机制也能使用。
