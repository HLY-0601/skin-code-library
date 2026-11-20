# 超自然 · 皮肤代码库（苹果风改版）

《超自然行动组》皮肤代码查询工具的静态站点，前端原生 JS 单页，认证接 Supabase 邮箱注册 / 登录。

## 目录结构

```
├── index.html    # 站点入口（皮肤查询 / 云间音乐 / 设置 / 关于）
└── README.md
```

> 皮肤数据已内嵌在 `index.html` 中，仓库不提供原始 JSON / TXT 下载，仅站内查询。

## 功能

- **皮肤代码查询**：员工皮肤 19 组 152 款、道具皮肤 32 组 239 款，一键复制、批量导出
- **云间音乐**：4 条线路（网易云完整版 / 全球曲库 / Apple 曲库 / 全线路聚合），6 个第三方接口
- **整套设置**：深浅色主题、配色、背景图、粒子数量 / 形态、鼠标光晕、点击音效、播放器音量 / 循环 / 频谱
- **更新日志**：内置最新新增记录
- **认证**：Supabase 邮箱注册 / 登录 / 退出，会话持久化

## 接入 Supabase（必做）

1. 在 [supabase.com](https://supabase.com) 新建项目，等待数据库初始化完成。
2. 进入 **Authentication → Providers**，开启 **Email**；如需免验证可关闭 "Confirm email"。
3. 进入 **Settings → API**，复制 `Project URL` 和 `anon public` key。
4. 打开 `index.html`，替换顶部两处占位：

```js
var SUPABASE_URL = "https://YOUR-PROJECT.supabase.co";
var SUPABASE_ANON_KEY = "YOUR-ANON-KEY";
```

> `anon key` 是设计为公开的前端密钥；数据安全靠 Supabase Row Level Security (RLS) 策略保障。

## 本地运行

静态文件，无构建步骤。直接用浏览器打开 `index.html`，或起一个本地静态服务：

```bash
python3 -m http.server 8080
# 访问 http://localhost:8080
```

## 部署到 GitHub Pages

1. 新建公开仓库，把本目录内容推送到仓库根分支。
2. 仓库 **Settings → Pages**，分支选 `main`（或 `master`）、根目录 `/ (root)`，保存。
3. 等待发布后通过 Pages 域名访问即可。

## 备注

- 页脚 `沪ICP备2026088888号-1` 为占位示例；若在中国大陆境内正式上线，需替换为真实备案号，未备案请勿对外商用。
- 皮肤资源仅供个人学习交流，请遵守游戏用户协议与当地法律法规。

## 许可证

本项目基于 [MIT License](./LICENSE) 开源。
