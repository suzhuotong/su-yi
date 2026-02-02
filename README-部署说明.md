# 苏壹网站 · suyi.com 部署说明

本文件夹即你的网站根目录，部署后访问首页即为 **suyi.com**，五子棋为 **suyi.com/gomoku.html**。

## 一、把网站放到网上（任选一种）

### 方式 1：Vercel（推荐，免费且简单）

1. 打开 [vercel.com](https://vercel.com)，用 GitHub 登录。
2. 点击 **Add New → Project**，把本文件夹（或整个仓库）导入。
3. 直接点 **Deploy**，会得到类似 `xxx.vercel.app` 的地址。
4. 在 Vercel 项目里：**Settings → Domains**，添加 **suyi.com**，按提示到域名商处添加解析（见下方「绑定 suyi.com」）。

### 方式 2：GitHub Pages

1. 在 GitHub 新建一个仓库（如 `suyi-site`）。
2. 把本文件夹里的 **index.html** 和 **gomoku.html** 上传到仓库根目录（或把整个「文件」文件夹里的内容放到仓库根目录）。
3. 仓库 **Settings → Pages**：Source 选 **main** 分支、根目录，保存。
4. 会得到 `https://你的用户名.github.io/suyi-site/`。若想用 **suyi.com**，在 Pages 设置里填 Custom domain：**suyi.com**，再到域名商添加解析。

### 方式 3：Netlify

1. 打开 [netlify.com](https://netlify.com)，注册/登录。
2. 把本文件夹拖到 **Drag and drop your site** 区域，或通过 Git 连接仓库部署。
3. 部署完成后在 **Domain settings** 里添加 **suyi.com**，并按提示做 DNS 解析。

---

## 二、绑定域名 suyi.com

你需要在**购买 suyi.com 的域名商**（如阿里云、腾讯云、GoDaddy、Cloudflare 等）里做解析，把 suyi.com 指到你部署的平台。

### 若用 Vercel

在域名商添加：

| 类型 | 主机记录 | 记录值 |
|------|----------|--------|
| A    | @        | 76.76.21.21 |
| CNAME | www      | cname.vercel-dns.com |

（具体以 Vercel 里 Domains 页面显示的为准。）

### 若用 GitHub Pages

在域名商添加：

| 类型 | 主机记录 | 记录值 |
|------|----------|--------|
| A    | @        | 185.199.108.153（或 Pages 提供的 IP） |
| CNAME | www      | 你的用户名.github.io |

### 若用 Netlify

在 Netlify 的 Domain settings 里会显示要你添加的 A 记录或 CNAME，按页面提示在域名商填写即可。

---

## 三、当前网站结构

```
你的网站根目录/
├── index.html      ← 首页（suyi.com）
├── gomoku.html     ← 苏壹五子棋（suyi.com/gomoku.html）
└── README-部署说明.md
```

部署完成后，别人打开 **https://suyi.com** 会看到你的首页，点击「苏壹五子棋」即可进入游戏并分享链接在线对战。
