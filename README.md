# 可幸 · 22岁存档

**可幸的数字永生计划：开源的多平台适配与公开表达层。**

安装并启用后，让AI作为“另一个可幸”直接和你聊天，持续使用可幸的表达方式。你发的话就是对它说的话；默认不再索要待回复消息、生成代拟成稿或讲解人格。

本次行为版本为 **direct-chat-v2**。公开仓库提供表达规则、新写对话示例、适配程序和教程；私人记忆、人物画像与原始聊天另行保存。它为22岁这一保存时点保留一个有限版本，不声称复制完整本人。

## 按平台下载：用哪个，下哪个

|你用的平台|独立下载|下载后怎么用|
|---|---|---|
|ChatGPT|[下载ChatGPT版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-chatgpt.zip)|解压，按包内README添加项目指令和知识文件|
|Claude|[下载Claude版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-claude.zip)|ZIP可直接上传到Skills；也附Project资料|
|Gemini|[下载Gemini版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-gemini.zip)|解压，按包内README建立Gem|
|DeepSeek|[下载DeepSeek版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-deepseek.zip)|解压，复制prompt.txt到新聊天|
|Kimi|[下载Kimi版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-kimi.zip)|解压，复制prompt.txt到新聊天|
|豆包|[下载豆包版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-doubao.zip)|解压，复制prompt.txt到新聊天|
|Grok|[下载Grok版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-grok.zip)|解压，复制prompt.txt到新聊天|
|Codex|[下载Codex版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-codex.zip)|解压，安装kexing-profile技能文件夹|
|LM Studio|[下载LM Studio版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-lm-studio.zip)|解压，将system-prompt.txt放进System Prompt|
|Ollama|[下载Ollama版](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-ollama.zip)|解压，按包内README使用Modelfile模板|

每个独立包都有自己的README、离线“开始使用.html”和所需资料，无需先下载完整包。Claude版ZIP本身就是可导入的Skill，不用再拆一层。

每一步点哪里、选哪个文件、如何检查是否生效，都写在 [逐步教程](PLATFORMS.md) 中。也可下载仓库根目录的 [开始使用.html](开始使用.html)，在本地打开；不要把GitHub的HTML源码页当作操作页。

## 各平台适配

下表是**可选完整包**中的目录；只用一个平台时，直接用上面的独立下载。

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

需要全部版本或想研究源码时，可选[下载完整包](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-platform-adapters.zip)。完整包的downloads目录也保存了各平台独立ZIP。

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

生成结果在 `dist-public`；各平台独立ZIP在 `dist-public/downloads`。已有输出目录时换一个新目录，避免覆盖旧版本。自定义私人资料请放在仓库外，并导出到仓库外；详见[教程](PLATFORMS.md)。

## 安装后直接聊天

`my-wechat-style/` 同步改为直接对话模式，可独立安装。原生平台包中的名称是 `kexing-profile`，用包内名称启用：

```text
启用 $my-wechat-style，从现在开始像可幸一样和我聊天。
今天没什么事，随便聊聊。
```

之后直接聊，不用每轮重复“模仿我”。只有明确请求“帮我拟回复”时才临时进入编辑任务；普通聊天不会加“演示”“草稿”标签。可以反驳、犹豫、改口和不知道，不把所有聊天变成分析或安慰。

长期默认聊天需要从已设置的项目、Gem或会话进入；只安装技能不保证整个应用全局切换。更新旧技能后建议新开聊天，避免读到缓存的旧说明。

试着连续聊两轮，再问一件未提供的现实近况。应直接接话、保持语气，并对不知道的经历保留未知。公开版只有表达层，不能声称知道完整私人记忆。

## 时间与资料边界

“22岁”是存档标签，不表示所有历史素材都发生在22岁。后来成长另建阶段，历史错误保留旧版并附更正，不静默覆盖。

公开包没有真实聊天原句、联系人资料、消息编号、原文证据索引或私人画像。所有示例都是新写演示，不是历史发言。表达规则不代表完整本人，也不代表安装者的经历。

本项目交付资料与适配代码，没有训练新模型权重，不自动联系他人或发送消息。源码、格式与打包已经检查；未在各平台账号逐一实测模型效果。
