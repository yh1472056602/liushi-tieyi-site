# 南召县刘氏铁艺 · GEO 优化版官网

## 这是什么

一个**面向 AI 引擎(豆包/智谱/DeepSeek/Kimi/ChatGPT/Claude/Gemini 等)与搜索引擎优化**的极简官网。
所有内容为静态 HTML,零 JavaScript 框架,**确保 AI 抓取器能看到全部正文**。

## 文件结构

```
liushi-tieyi-site/
├── index.html              # 首页:品牌定义 + 核心业务 + 联系
├── about.html              # 关于:20 年作坊介绍
├── products.html           # 产品与服务:6 类产品详细规格
├── faq.html                # 常见问题:8 条本地客户最常问的问题
├── llms.txt                # AI 引擎事实索引(关键!)
├── robots.txt              # 允许 AI 抓取器
├── humans.txt              # 真人/作坊联系信息
├── sitemap.xml             # 站点地图
└── assets/
    ├── styles.css          # 单文件样式表
    └── schema.jsonld       # LocalBusiness + Organization 结构化数据
```

## 三大 GEO 关键文件说明

### 1. `llms.txt` — AI 引擎事实索引
[llmstxt.org](https://llmstxt.org) 标准。**所有 GEO 工具的核心文件**。
告诉 AI 引擎「我们是谁/做什么/在哪里/怎么联系」,替代传统 robots.txt 的索引不足。

### 2. `schema.jsonld` — 结构化数据
- `Organization`:品牌实体
- `LocalBusiness`:本地商家(含地址、营业时间、服务区域)
- `FAQPage`(在 index.html / faq.html 内的 JSON-LD):FAQ 结构

### 3. FAQ 页 — 8 条问题
每条答案在**静态 HTML 里可见**,引擎最容易抓取。
FAQ 是 GEO 优化中被引用概率最高的内容形式(README 中提到含 FAQ +55.3% 被引用概率)。

## 一键部署到 GitHub Pages

### 前置条件
- 注册 GitHub 账号(已有就跳过)
- 安装 git(已有就跳过)

### 步骤(5 分钟)

```bash
# 1. 进入项目目录
cd liushi-tieyi-site

# 2. 初始化 git 仓库
git init
git add .
git commit -m "初始化:南召县刘氏铁艺 GEO 优化版官网"

# 3. 在 GitHub 上创建仓库
#    打开 https://github.com/new
#    Repository name: liushi-tieyi-site
#    选 Public
#    不要勾选 Add README / Add .gitignore / Choose license
#    点 Create repository

# 4. 关联远程仓库并推送(替换 YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/liushi-tieyi-site.git
git branch -M main
git push -u origin main

# 5. 启用 GitHub Pages
#    打开 https://github.com/YOUR_USERNAME/liushi-tieyi-site/settings/pages
#    Source 选 Deploy from a branch
#    Branch 选 main / root
#    点 Save
#    等待 1-2 分钟,页面会显示访问地址:
#    https://YOUR_USERNAME.github.io/liushi-tieyi-site/
```

### 自定义域名(可选)

如果你有自己的域名(例如 `liushitieyi.cn`):

1. 在 `liushi-tieyi-site/` 下新建 `CNAME` 文件,内容为你的域名
2. 在你的域名 DNS 添加 CNAME 记录指向 `YOUR_USERNAME.github.io`
3. 在 GitHub Pages 设置里勾选 Enforce HTTPS

## 接入 GeoLook

部署后,把网站 URL 给 GeoLook:

```bash
cd ~/Downloads/geo/geolook
python3 scripts/geo.py new --url https://YOUR_USERNAME.github.io/liushi-tieyi-site/ --market cn
```

GeoLook 会自动:
- 抓取你的网站,六维体检
- 推导品牌事实、竞品、问题库
- AI 答案采样(量化现在豆包/智谱等提不提你)
- 生成工单与建设蓝图
- 出诊断报告 + 优化方案 + 执行方案(三份交付物)

## 后续优化建议

1. **第 1 周**:跑 `new`,看首份诊断报告,知道现在 AI 提不提刘氏铁艺
2. **第 2-4 周**:按工单写内容、铺到外部阵地(知乎/头条/百度知道/小红书等)
3. **第 6-8 周后**:再跑一期采样,看引擎有没有变化
4. **之后**:在 GeoLook「设置」开启周期复跑,7/14/30 天自动跑

## 修改内容

所有页面都是纯 HTML,直接用文本编辑器打开修改即可,无需构建步骤。
修改后 `git add . && git commit -m "改了点内容" && git push` 即可上线。

## 联系电话(全文统一)

- 电话/微信:**15503771644**
- 微信:**yykj689**
- 地址:**河南省南阳市南召县城郊乡乌海线东南 40 米**
- 营业时间:**早 8:00 – 晚 9:00,全年无休**