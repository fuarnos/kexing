# 可幸 · 22岁存档

**可幸的数字永生计划：开源的多平台适配与公开表达层。**

为22岁这一阶段保留一个有时间边界的版本，让相同资料可以在不同平台使用。公开仓库提供表达规则、新写示例、适配程序和教程；私人记忆、人物画像与原始聊天另行保存。

## 不写代码，直接使用

1. 打开 [多平台下载包](kexing-platform-adapters.zip)，点 **Download raw file** 下载。
2. 右键ZIP → **全部解压**，进入 `kexing-platform-adapters` 文件夹。
3. 双击 **开始使用.html**，选平台，点“复制适配文本”，粘贴到新聊天。

每一步点哪里、选哪个文件、如何检查是否生效，都写在 [逐步教程](PLATFORMS.md) 中。也可下载仓库根目录的 [开始使用.html](开始使用.html)，在本地打开；不要把GitHub的HTML源码页当作操作页。

## 各平台适配

|平台|下载包里的文件|使用方式|
|---|---|---|
|ChatGPT|`platforms/chatgpt/instructions.txt`、`knowledge.txt`|Project指令＋项目资料；也提供普通对话文本|
|Claude|`platforms/claude/`|Project版、原生Skill ZIP、普通对话文本|
|Gemini|`platforms/gemini/instructions.txt`、`knowledge.txt`|Gem指令＋知识资料；也提供普通对话文本|
|DeepSeek|`platforms/deepseek/prompt.txt`|普通聊天中粘贴全文|
|Kimi|`platforms/kimi/prompt.txt`|普通聊天中粘贴全文|
|豆包|`platforms/doubao/prompt.txt`|普通聊天中粘贴全文|
|Grok|`platforms/grok/prompt.txt`|普通聊天中粘贴全文|
|Codex|`native/kexing-profile/` 或 `platforms/codex/kexing-profile-skill.zip`|安装Skill后用 `$kexing-profile` 调用|
|LM Studio|`platforms/lm-studio/system-prompt.txt`|系统提示或普通聊天首条消息|
|Ollama|`platforms/ollama/Modelfile.template`|替换成本机模型名后创建本地预设|

没有专用Skill入口的平台使用可复制文本，不要求安装额外插件。不同模型的回答效果可能不同；教程附人工验收题，没有准确率承诺。

## 源码与二次修改

- [export_adapters.py](export_adapters.py)：离线导出程序，只用Python标准库，不调用模型、不上传资料。
- [profile.public.json](profile.public.json)：当前公开表达规则。
- [profile.template.json](profile.template.json)：空白的自有资料模板。
- [adapters.json](adapters.json)：十个平台的可查看、可修改配置与文本。
- [LICENSE](LICENSE)：MIT许可证，可使用、修改和分发本开源内容。

安装Python 3.10及以上后，在仓库目录运行：

```text
python export_adapters.py
```

生成结果在 `dist-public`。已有输出目录时换一个新目录，避免覆盖旧版本。自定义私人资料请放在仓库外，并导出到仓库外；详见[教程](PLATFORMS.md)。

## 原有技能继续可用

`my-wechat-style/` 保留为独立的中文聊天风格Skill：

```text
用 $my-wechat-style 把这段话改成自然的微信语气，保留我的原意和承诺范围：……
```

它采用自然口语、短句和具体补充，按对象调整语气。已有同名技能时保留自己的版本，避免覆盖个人设置。

## 时间与资料边界

“22岁”是存档标签，不表示所有历史素材都发生在22岁。后来成长另建阶段，历史错误保留旧版并附更正，不静默覆盖。

公开包没有真实聊天原句、联系人资料、消息编号、原文证据索引或私人画像。所有示例都是新写演示，不是历史发言。表达规则不代表完整本人，也不代表安装者的经历。

本项目交付资料与适配代码，没有训练新模型权重，不自动联系他人或发送消息。源码、格式与打包已经检查；未在各平台账号逐一实测模型效果。
