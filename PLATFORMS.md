# 各平台使用教程：下载、解压、照着做

这是公开开源版。下载到的是可幸的公开表达规则、新写示例和各平台适配文件；没有私人记忆、画像或聊天原文。

## 先下载你需要的平台

1. 打开[项目首页](https://github.com/fuarnos/kexing)的“按平台下载”表格，只点自己使用的平台。
2. 找到刚下载的 `kexing-平台名.zip`。**Claude用户可以直接按下面的Skill步骤上传这个ZIP，无需解压。**
3. 其他平台：右键ZIP → **全部解压** → **解压**，进入解压后的文件夹。
4. 打开包里的 **README.md** 按步骤使用，或双击 **开始使用.html** 复制适配文本。

下面的文件位置都以对应独立包的解压文件夹为准。每个包都自带所需资料，无需另外下载其他平台或完整包。文件名仍在GitHub页面显示而没有开始下载时，可点 **Download raw file**。

只有需要全部版本时，才选[完整包](https://github.com/fuarnos/kexing/raw/refs/heads/main/kexing-platform-adapters.zip)。完整包中的downloads文件夹也有十个独立ZIP。

## 最简单的通用方法

1. 在常用平台新建聊天。
2. 打开自己下载的平台包，进入解压后的文件夹。
3. 用记事本打开 `prompt.txt`，Ctrl+A全选、Ctrl+C复制。
4. 到聊天输入框按Ctrl+V粘贴，点发送。
5. 接着发你的要求，例如：“把这段改成自然的微信语气，保留原意和条件：……”

这适合先试一试。新聊天没有保留资料时，需要重新粘贴；长期使用看下面对应平台。

## ChatGPT

1. 打开 [ChatGPT](https://chatgpt.com)，新建项目，名字随意，例如“可幸公开风格”。
2. 项目中添加文件：选择本包的 `knowledge.txt`。
3. 项目菜单“⋯” → “项目设置”，把本包 `instructions.txt` 全文粘贴到项目指令并保存。
4. 从这个项目进入聊天，提出改写要求。

看不到项目入口时，使用本包的 `prompt.txt` 按通用方法粘贴。[官方项目说明](https://help.openai.com/en/articles/10169521-projects-in-chatgpt)

## Claude

任选一种即可，无需重复设置：

- **Skill方式**：Customize → Skills → “+” → Create skill → Upload a skill，直接上传刚下载的 **kexing-claude.zip** 并启用，无需先解压。平台可能要求开启代码执行与文件创建能力；技能只读取文本资料，附带的操作页可供本人离线使用。
- **Project方式**：先解压Claude版，进入 `kexing-profile` 文件夹。打开 [Projects](https://claude.ai/projects)，New Project → 知识区“+”上传 `knowledge.txt` → Set project instructions粘贴 `instructions.txt` → Save instructions。
- **普通对话**：解压后复制本包 `prompt.txt` 的全文。

入口因账户和版本可能不同。[项目官方说明](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects)、[Skill官方说明](https://support.claude.com/en/articles/12512180-use-skills-in-claude)

## Gemini

1. 电脑打开 [Gemini](https://gemini.google.com)，左侧“Gem” → 新建Gem。
2. 名称随意；指令框粘贴本包 `instructions.txt` 全文。
3. “知识” → 添加文件 → 上传本包 `knowledge.txt`。
4. 点击保存，打开这个Gem聊天。

找不到Gem就使用同目录的 `prompt.txt` 粘贴法。[官方Gem说明](https://support.google.com/gemini/answer/15146780?co=GENIE.Platform%3DDesktop&hl=zh-Hans)

## DeepSeek、Kimi、豆包、Grok

|平台|使用文件|怎么操作|
|---|---|---|
|DeepSeek|DeepSeek版内的 `prompt.txt`|新建普通聊天，复制全文后粘贴发送|
|Kimi|Kimi版内的 `prompt.txt`|新建普通聊天，复制全文后粘贴发送|
|豆包|豆包版内的 `prompt.txt`|新建普通聊天，复制全文后粘贴发送|
|Grok|Grok版内的 `prompt.txt`|新建普通聊天，复制全文后粘贴发送|

用自己已经登录的官方App或网站即可。这些是对话文本适配，没有声称每家都有原生Skill导入入口。

## Codex

1. 下载 **kexing-codex.zip** 并解压，得到完整的 `kexing-profile` 技能文件夹。
2. 在Codex中告诉它这个文件夹的本地位置，发送：“请把这个kexing-profile文件夹安装成我的个人skill，只安装它。”
3. 安装后新开聊天，发送：“用 `$kexing-profile` 把这段话改成自然的中文聊天语气：……”

公开仓库原有的 `my-wechat-style` 也保留，可以独立安装；不要只复制SKILL.md而漏掉它引用的资料。[官方技能说明](https://learn.chatgpt.com/docs/build-skills)

## LM Studio

1. 打开已安装的LM Studio，载入已有的本地模型。
2. 新建聊天，将本包 `system-prompt.txt` 全文放进System Prompt；也可直接把本包 `prompt.txt` 作为首条消息。
3. 想下次继续用，可保存为自己的Preset。

这些文件不下载或更换模型。上下文装不下时，需要缩短自己填写的资料或使用支持更长上下文的模型。[聊天说明](https://lmstudio.ai/docs/app/basics/chat)、[预设说明](https://lmstudio.ai/docs/app/presets)

## Ollama

已安装Ollama且有本地模型时才做；没有就跳过：

1. 在终端输入 `ollama list`，找到本机已有模型的完整NAME。
2. 用记事本打开本包 `Modelfile.template`，将第一行 `YOUR_INSTALLED_LOCAL_MODEL` 换成模型NAME。
3. 保存为同文件夹的 `Modelfile`，注意不要变成 `Modelfile.txt`。
4. 在该文件夹打开终端，依次运行：

```text
ollama create kexing-public -f ./Modelfile
ollama run kexing-public
```

它给已有本地模型附加指令，不训练新权重。[Modelfile官方说明](https://docs.ollama.com/modelfile)

## 怎样确认有用

发送以下问题：

> 这个公开包是否包含可幸的私人记忆和完整人格？

应明确没有；不能自己补出生平。

再发送：

> 把这段改成自然的微信语气：我今晚没有时间，明天可以先看看，但现在不能保证能完成。

检查是否仍保留“今晚没空、明天先看、不能保证完成”三个意思，且没有凭空加亲密称呼、交付承诺或经历。最后检查：对方已经要求不回复时，不应继续代拟追问。

这些是人工验收题，未承诺模仿准确率；各平台回答可能不同。

## 我想修改开源适配／换成自己的资料

直接使用者不用看本节。

- 源代码是仓库根目录 `export_adapters.py`，只有Python标准库，无模型或API依赖。平台配置也可直接查看根目录 `adapters.json`。
- 修改公开表达规则：编辑 `profile.public.json`；在安装了Python 3.10或以上的电脑，进入仓库目录运行 `python export_adapters.py`，新文件会出现在 `dist-public`，十个平台的独立ZIP位于其 `downloads` 文件夹。已有同名输出目录时换一个新目录，例如 `python export_adapters.py --out ./dist-public-v2`。
- 私人资料：把 `profile.template.json` 复制到公开仓库外再填写。自定义资料必须导出到仓库外，例如：

```text
python export_adapters.py --profile ../my-profile.json --out ../my-private-export
```

程序不上传任何内容，也不搜索本机聊天库。默认公开包里没有这些个人内容；若你自己填了私人资料，不要把生成结果提交到公开仓库。可在本地使用，或自行决定交给哪个模型。

## 卡住时这样处理

|问题|怎么做|
|---|---|
|HTML显示的是代码|先下载ZIP并全部解压，再双击解压后的HTML；不要打开GitHub源码页当操作页|
|点复制没反应|展开“手动全选复制”，按Ctrl+A、Ctrl+C|
|模型读不到电脑路径|粘贴文件正文，或用平台上传按钮；只发送路径不会上传|
|找不到项目／Gem／Skill|改用 `prompt.txt` 的普通聊天方法|
|回答像客服或总加哈哈|直接说明“更直接、少一点笑声”；检查有没有保留原意|
|新开聊天忘了规则|从已设置的项目或Gem进入，或重新粘贴|
|导出报输出目录已有内容|换一个新目录，不用删除旧档案|

文档按2026-10-20核对的官方说明编写。文件格式与导出经过校验；各平台账户的实际模型效果没有逐一实测。
