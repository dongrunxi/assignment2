# 我的博客 · 上传操作说明

这个文件只给你自己看，`_config.yml` 里已经把它排除，不会出现在网站上。

---

## 一、上传前先改 3 个地方（用记事本打开就行）

**1. `_config.yml`**

- `title:` 后面换成你想叫的站名（比如「小党的笔记本」）
- `description:` 一句话介绍
- `url:` 改成 `https://你的用户名.github.io`
- `baseurl:` 保持 `/blog`（因为仓库准备叫 blog）
- `aux_links:` 里的地址换成你的 GitHub 主页

**2. `about.md`** 里两处：邮箱、GitHub 链接。

**3. 其他文章先不用改**，上传成功后再慢慢替换成自己的内容。

> 提醒：`url` 里别留「你的用户名」这几个字，否则分享出去的链接是坏的。

---

## 二、上传到 GitHub（一共点 6 下）

1. 打开 `github.com`，注册或登录
2. 右上角 `+` → **New repository**
3. Repository name 填 `blog`；可见性选 **Public**（不选 Public 就没有免费网址）；点 **Create repository**
4. 新仓库页面点 **uploading an existing file**
5. 把这个文件夹里的文件全选（6 个），直接拖进网页
6. 页面下方点 **Commit changes**

---

## 三、打开网站开关

1. 仓库顶部 **Settings**
2. 左侧 **Pages**
3. Source 选 **Deploy from a branch**
4. Branch 选 **main**，右边目录选 **/(root)**
5. 点 **Save**

等 1～2 分钟，刷新这个设置页，顶部会出现你的网址：

```
https://你的用户名.github.io/blog/
```

第一次打开可能是 404，别急，再等一两分钟。

---

## 四、怎么知道成没成功

- **成功**：网址打开后，左边一列目录（首页 / 第一篇 / 第二篇 / 关于我），右边是正文
- **失败**：仓库顶部 **Actions** 标签，最新那条如果是红叉，点进去看第一段红字，多半是 `_config.yml` 写错（冒号后面少了空格、缩进乱了、中文引号）

---

## 五、以后加一篇新文章

1. 仓库页面 **Add file** → **Create new file**
2. 文件名写 `third-post.md`（英文或拼音，别用中文，网址会好看很多）
3. 粘贴这段，改标题和正文：

```markdown
---
layout: default
title: "第三篇：标题"
nav_order: 5
---

2026 年 X 月 · 分类

## 小标题

正文……
```

4. 拉到最下面 **Commit changes**，等一分钟刷新网站

> `nav_order` 是它在左侧目录里的位置，1 是首页、2 和 3 已占用，新的从 4 往后排，别重复。

---

## 六、放图片

1. **Add file** → **Create new file**，文件名写 `assets/images/.gitkeep`，提交（这一步只是先把文件夹建出来）
2. 再点 **Add file** → **Upload files**，把图片拖进去，提交
3. 文章里这样引用：

```markdown
![图片说明]({{ '/assets/images/图片名.png' | relative_url }})
```

---

## 七、常见问题

| 现象 | 原因 | 怎么办 |
|---|---|---|
| 打开是 404 | 还没构建完，或 Pages 没开 | 等 2 分钟；检查 Settings → Pages 是否显示网址 |
| 页面没样式，全是白底黑字 | `baseurl` 写错 | 仓库叫 blog 就写 `/blog`，别写 `/Blog` 或漏斜杠 |
| 左侧目录是空的 | 文章没写 `nav_order` | 每篇的 front matter 补上 `nav_order: 数字` |
| 改完没变化 | 浏览器缓存 | Ctrl+F5，或换无痕窗口 |
| Actions 红叉 | 配置语法错 | 点进日志，多半是冒号后没空格、用了中文标点 |
| 上传时提示文件太大 | 单文件超 25MB | 图片先压缩，或改用图床 |

---

## 八、这套东西花多少钱

0 元。公开仓库 + GitHub Pages 免费，个人博客的量完全够用。
唯一要守的规矩是：仓库必须 Public，别把密码、身份证照片之类的东西传上去。
