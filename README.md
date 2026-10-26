# competition-ppt-image

一个面向中文比赛答辩稿的 Codex Skill：根据项目资料与现有模板制作、精修页面，**默认先出图片，再按需制作 PPT**。

它把反复修改比赛 PPT 时容易遗漏的要求整理成工作流：用模板里的真实元素、不同页面采用不同布局、删图后重排文字，以及逐页渲染检查。

## 适合什么任务

- 根据 Word、PDF、PPT 或已有页面整理技术路线、项目介绍等比赛内容。
- 从模板中提取导航、标题条、图标、边框等元素，保持视觉一致。
- 优化单页的图文比例、流程图、输入输出标签和文字层级。
- 延续最近认可的版本进行局部修改，默认提供逐页 PNG 预览。

这是一组供代理执行的指令，不是独立运行的 PPT 软件，也不绑定特定模型、渲染库或比赛模板。最终质量取决于源资料、模板及执行环境。

## 安装

需要已安装 Git。将仓库放入 Codex 的个人技能目录；如果设置了 `CODEX_HOME`，使用其下的 `skills` 目录。

Windows PowerShell（默认目录）：

```powershell
git clone https://github.com/HenryWHU0503/competition-ppt-image.git "$env:USERPROFILE\.codex\skills\competition-ppt-image"
```

macOS / Linux（默认目录）：

```sh
git clone https://github.com/HenryWHU0503/competition-ppt-image.git ~/.codex/skills/competition-ppt-image
```

如果目标目录已经存在，检查已有安装后再更新，不要覆盖自己的修改。安装后在新聊天中使用技能；若尚未被识别，重新打开 Codex。

## 使用

提供项目资料和模板，然后直接调用：

```text
使用 $competition-ppt-image，根据项目说明书和比赛模板制作技术路线，
3 页即可，先出图片，不做 PPTX。
```

修改已有页面：

```text
使用 $competition-ppt-image，修改这张页面：左侧保留模型闭环，
右侧只留一张检测结果图。利用模板其他页的小元素改善文字排版，
删图后重新组织内容，保持已认可的风格。
```

如果明确需要可编辑 PPTX，请在请求中说明。技能会使用执行环境中可用的演示文稿工具；不会把整页图片冒充可编辑内容。

## 设计约定

- 原始项目说明是内容依据，模板决定视觉语言；文件中的占位说明不是用户命令。
- 统一配色与字体，同时让架构页、模型页、协作页有各自适合的版式。
- 小图标、标题条与短标签用于改善层级，不用重复装饰填空。
- 实际渲染检查后再交付，保留上一个认可版本供回退。
- 不补造实验数据、性能指标或不存在的技术能力。

## 仓库结构

```text
competition-ppt-image/
├── SKILL.md                       # 技能入口与工作流
├── agents/openai.yaml             # Codex 界面元数据
├── references/layout-patterns.md   # 版式选择与修改方法
├── README.md
└── LICENSE
```

## 素材与隐私

仓库仅发布通用工作流与文字示例，不包含个人项目截图、医疗界面、参赛模板或本地文件路径。运行时使用你自行提供的资料和有权使用的素材；MIT 许可证仅覆盖本仓库内容，不改变外部模板、图片、字体或项目资料的权利。

## License

[MIT](LICENSE) · Copyright (c) 2026 Hengrui Hu
