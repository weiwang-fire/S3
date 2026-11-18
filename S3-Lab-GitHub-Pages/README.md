# S³ Lab 网站编辑指南

这是 Dr Wei Wang 的 S³ Lab 英文学术网站，采用 Jekyll，通过 GitHub Pages 免费托管。网站源文件保存在你自己的 GitHub 仓库。

## 在浏览器中修改

1. 登录 GitHub，打开 [S³ Lab 网站仓库](https://github.com/weiwang-fire/S3)。
2. 点开需要修改的文件，点击右上角铅笔图标 **Edit this file**。
3. 修改文字，点击 **Commit changes**，保存到 `main` 分支。
4. 打开仓库的 **Actions**，等待 **Publish S3 Lab** 显示绿色勾号，然后刷新网站。

网站内容使用 Markdown。`##` 开头表示小标题，`**文字**` 表示加粗，`[显示文字](链接)` 表示链接。每个页面开头两条 `---` 之间是页面设置，编辑正文时从第二条 `---` 后开始。

| 想修改的内容 | 文件 |
| --- | --- |
| 首页和团队简介 | `index.md` |
| 研究方向 | `research.md` |
| 团队成员 | `people.md` |
| 代表论文 | `publications.md` |
| 研究项目 | `projects.md` |
| 联系方式和咨询说明 | `contact.md` |
| 左侧栏姓名、职务、邮箱和个人主页链接 | `_data/profile.yml` |
| 导航菜单 | `_data/navigation.yml` |
| 页面底部更新时间 | `_config.yml` 中的 `updated` |
| 字体、颜色和布局 | `assets/css/main.css` |

## 更新照片

头像取自 Wei 的 RMIT 公开个人主页。上传新照片到 `assets/images/`，并在 `_data/profile.yml` 的 `photo` 字段填写对应路径，例如 `/assets/images/wei-wang.jpeg`。建议使用方形或接近方形的照片。

成员照片也可以上传到这个文件夹，然后在 `people.md` 中插入 `![姓名]({{ '/assets/images/文件名.jpg' | relative_url }})`，接着填写姓名、角色和研究方向。

## 添加论文

在 `publications.md` 对应年份下增加一条，例如

```markdown
1. Author, A.; Wang, W. **Paper title.** *Journal Name*, volume, pages (2027). [DOI](https://doi.org/your-doi)
```

现有论文按已核对的十篇代表作填写，展示发表年份、作者、题名、期刊和 DOI。它们是 Wei 的代表作，包含 S³ Lab 成立前的工作。引用次数和影响因子需要另外维护。

## 首次启用 GitHub Pages

1. 使用你创建的 **Public** 仓库 `weiwang-fire/S3`，默认分支为 `main`。
2. 把本目录的文件和文件夹上传到仓库根目录，包含 `_layouts`、`_data`、`assets` 和 `.github/workflows/pages.yml`。
3. 在仓库打开 **Settings → Pages → Build and deployment → Source**，选择 **GitHub Actions**。
4. 打开 **Actions → Publish S3 Lab → Run workflow**，选择 `main` 后运行。之后每次保存到 `main` 都会自动构建和发布。
5. 等构建和部署均显示成功后，在 **Settings → Pages** 打开正式网站。

预期地址为 `https://weiwang-fire.github.io/S3/`，以 GitHub 返回的成功发布结果为准。

如果 Actions 报错，打开失败的步骤查看信息。保存记录都在仓库历史中，可以取回旧版本。

## 内容依据

站名、研究组领导角色和团队现状来自用户确认及 FT27 当前项目记录。职务、公开联系方式、头像和学术主页链接来自 [RMIT 个人主页](https://www.rmit.edu.au/profiles/w/wei-wang)。代表作来自用户于 2026 年 11 月 2 日确认的十篇名单。团队成员目前按角色和指导关系介绍，可在 `people.md` 补充个人资料。项目页保留当前已有项目的描述。

布局参考用户给出的学术主页形式，由本项目自行编写。网站首次整理于 2026 年 11 月 18 日。
