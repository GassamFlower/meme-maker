# 你的第一个练手站：Memefy（在线表情包生成器）

这是一个**单页小工具站**，走通了哥飞套路最核心的"建站 → 上线 → 提交搜索 → 拿流量"闭环。
代码就在这个文件夹里，只有一个文件 `index.html`，零依赖，可以直接部署。

---

## 这个站演示了哪些「养网站防老」要点

| 你要学的套路 | 在这个站里怎么体现 |
|---|---|
| 一个关键词一个站 | 全站围绕 `meme generator`（表情包生成器） |
| 语义化结构 | `header / main / section / footer`，有 TDK（title/description） |
| 首页 + 工具页落位 | 首页=工具，下面是 FAQ / 介绍区撑长尾关键词 |
| 单页可上线 | 一个 HTML 就是全站，最省事 |
| 静态可托管 | 不需要服务器，免费托管即可上线 |

---

## 三步上线（约 15 分钟）

### 0. 先把代码拉到头（可选）
如果你把 `index.html` 放进了 github，浏览器直接打开即可本地预览这个页面本来就是一个现成 index。

### 1. 推到 GitHub
在 GitHub 上新建一个 repository（仓库），名字就叫 `meme-maker`（公开）。
然后在电脑上这个文件夹里打开终端（git bash），执行：

```bash
git init
git add index.html
git commit -m "first meme generator site"
git branch -M main
git remote add origin https://github.com/你的用户名/meme-maker.git
git push -u origin main
```

> 把命令行里的 `你的用户名` 换成你的 GitHub 用户名。第一次 push 会让你登录授权 GitHub。

### 2. 用 Vercel 一键上线（免费，推荐）
1. 打开 https://vercel.com 并用 GitHub 账号登录
2. 点 **New Project** → 选择你刚建的仓库 `meme-maker`
3. Framework 选 **Other**，什么都不改，点 **Deploy**
4. 等 1 分钟，它会给你一个 `https://meme-maker.vercel.app` 的网址 —— **你的站已经上线了！**

> 不想用 Vercel 也可以：GitHub 仓库里 Settings → Pages → 选 main 分支 → Save，会给你 `https://你的用户名.github.io/meme-maker/`。两条任选一条。

---

## 3. 提交 Google Search Console（让 Google 知道你来收录）

1. 打开 https://search.google.com/search-console 用 Google 账号登录
2. 添加资源 → 选 **网址前缀**，粘贴你上线的网址（如 `https://meme-maker.vercel.app`）
3. 它有几种验证方式，最简单是 **HTML 标签** 方式：
   - 复制 Google 给的一串 `<meta name="google-site-verification" content="xxxx">`
   - 把这串塞进 `index.html` 的 `<head>` 里（就在 `<title>` 上面几行），重新 push / 部署
   - 点「验证」
4. 验证后，在左侧 **Sitemap** 里提交你的 sitemap。

### 生成 sitemap
再放一个 `sitemap.xml` 文件到项目里：
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://meme-maker.vercel.app/</loc>
  </url>
</urlset>
```
（把网址换成你真实的那个）

逐篇推后，在 GSC 里就能看到"被收录的页面数"和"从 Google 来的点击"。

---

## 4. 用 GA4 统计（可放到上线后做）
这套路第一步不一定要 GA，但建议尽快加。注册 Google Analytics 会给你一段 `<script>`，塞进 `index.html` 的 `<head>`，就能看到访问量。

---

## 接下来你可以做的升级（一次只做一件）
- 加几个相关页面（比如「meme maker for WhatsApp」「funny meme text」）练内链
- 换一个更贴合真实需求、`KDRoi` 更高的词再做一个站（矩阵开始复制）
- 给高流量页面做成付费版 / 接广告
- 参考 `哥飞学习手册` 里「入门某步」的动作清单继续练

---

这就是「第一单站跑通」的最小路径，做到这里你就摸到了整套哥飞套路的实战手感。
下一步可以在这 SiteFolder 里继续加页，或者我们一起选下一个词去开第二个站。