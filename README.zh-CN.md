<div align="center">

# 🎮 CS2 控制台指令速查

一键复制 · 分类齐全 · 中英双语 · 零依赖单文件

[English](README.md) · **简体中文**

</div>

纯静态的 **CS2（Counter-Strike 2）控制台指令速查页**。100 条常用指令按 11 个分类整理，点一下就能复制，粘进游戏控制台直接用。整个项目只有一个 `index.html`，无框架、无构建、无外部依赖。

## ✨ 功能特性

- 📋 **一键复制** — 每条指令右侧都有复制按钮，复制成功有视觉反馈
- 🗂 **11 个分类** — 从练习作弊、改刀到宠物鸡仔，分类 Tab 切换
- 🔗 **SteamID 转 `connect`** — 粘贴含 `[A:1:xxxx:xxxxx](xxxxxxxxxx)` 的文本（如 `status` 输出），自动生成 `connect` 指令
- 🌐 **中英双语** — 右上角「中文 / EN」切换，默认跟随浏览器语言，选择结果本地记忆
- 🎨 **拟态 UI** — Gemini 风格浅色拟态 + 粒子背景 + 液晶胶囊按钮
- 📱 **响应式** — 桌面与手机都能正常使用
- 🧩 **零依赖** — 纯原生 HTML / CSS / JavaScript，单个文件即开即用

## 🗂 指令分类

| 分类 | 条数 | 主要内容 |
| --- | :---: | --- |
| ⚡ 常用指令 | 7 | `status`、`bot_kick`、`mp_restartgame`、`sv_cheats`、`clear`、消音器模式 |
| 练习与作弊 | 8 | 无敌、穿墙飞行、无限弹药、手雷轨迹、弹着点 |
| 改刀指令 | 20 | 各类刀具模型切换 |
| 地图切换 | 20 | 常用练习地图 / 竞技地图快速切换 |
| 机器人管理 | 8 | 添加、踢出、难度、冻结机器人 |
| 对局控制 | 13 | 重开对局、冻结时间、回合时长、加时、友伤、C4 时间、重生 |
| 经济与物品 | 7 | 购买时间、随处购买、金钱上限、掉落设置 |
| 服务器与连接 | 2 | `status` 查看服务器与玩家信息、`disconnect` 断开连接 |
| 显示与界面 | 2 | `cl_draw_only_deathnotices` 只保留击杀提示（隐藏其余 HUD） |
| 语音通讯 | 6 | 全局语音、死亡语音、语音开关、屏蔽敌方语音 |
| 其他实用指令 | 3 | `kill` 自杀、`clear` 清屏、`kick` 踢人 |
| 宠物鸡仔 | 4 | `cl_ent_scale` 改变鸡仔模型大小 |

> 指令会随游戏更新变化，个别指令可能在特定版本或服务器上失效。

## 🚀 部署到 GitHub Pages

1. 新建一个 GitHub 仓库，把 `index.html`（建议连同 `README.md`、`README.zh-CN.md` 一起）上传到根目录
2. 进入仓库 `Settings → Pages`
3. `Source` 选择 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`，保存
4. 等一两分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`

**本地预览**：直接双击 `index.html` 即可；或在该目录执行

```bash
python -m http.server 8080
# 浏览器打开 http://localhost:8080
```

**游戏内开启控制台**：`设置 → 游戏 → 启用开发者控制台 → 是`，游戏中按 `~` 呼出。

## 🌐 中英切换机制

| 方式 | 说明 |
| --- | --- |
| URL 参数 | `?lang=en` 强制英文，`?lang=zh` 强制中文（便于分享给不同语言的玩家） |
| 右上角按钮 | 点「中文 / EN」，选择结果写入 `localStorage`（键名 `cs2_lang`） |
| 默认 | 未指定时跟随浏览器语言 `navigator.language` |

## ➕ 添加自己的指令

在对应分类的 `<div class="tab-content" id="...">` 里追加一段 `cmd-row`：

```html
<div class="cmd-row">
    <div class="cmd-text-wrapper">
        <code class="cmd-code">sv_cheats 1</code>
        <span class="comment">// 开启作弊指令</span>
    </div>
    <button class="copy-btn" data-cmd="sv_cheats 1">复制</button>
</div>
```

- `data-cmd` 才是真正被复制的内容，务必与 `<code>` 里的指令保持一致
- 想让英文模式下也显示英文注释，把中文注释原文加进页面脚本的 `DICT` 字典，例如 `"开启作弊指令": "Enable cheats"`
- 新增分类需要同时添加一个 `tab-btn` 和对应的 `tab-content`

## ⚠️ 注意事项

- 标注「仅本地 / 人机」的指令通常需要先执行 `sv_cheats 1`，在官方匹配中无效
- 在官方服务器使用作弊类指令可能触发 VAC 封禁，请自行判断风险
- 指令以当前 CS2 版本实测整理，游戏更新后可能失效
- 本项目与 Valve / Counter-Strike 官方无任何关联

## 📄 License

MIT — 随意使用、修改、分发。
