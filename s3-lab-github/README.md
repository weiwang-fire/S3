# S³ Lab 网站编辑指南

这是 Dr Wei Wang 的 S³ Lab 英文学术网站，采用 Jekyll，通过 GitHub Pages 免费托管。网站源文件保存在你自己的 GitHub 仓库。

## 在浏览器中修改

1. 登录 GitHub，打开 [S³ Lab 网站仓库](https://github.com/weiwang-fire/S3)。
2. 进入 `s3-lab-github` 文件夹，点开需要修改的文件，点击右上角铅笔图标 **Edit this file**。
3. 修改文字，点击 **Commit changes**，保存到 `main` 分支。
4. 打开仓库的 **Actions**，等待 **Publish S3 Lab** 显示绿色勾号，然后刷新网站。

About 和 Contact 正文使用 Markdown。`##` 开头表示小标题，`**文字**` 表示加粗，`[显示文字](链接)` 表示链接。每个页面开头两条 `---` 之间是页面设置，编辑正文时从第二条 `---` 后开始。Research、People、Publications、Projects 从 `_data` 文件夹中的 JSON 文件读取资料并自动排版。

| 想修改的内容 | 文件 |
| --- | --- |
| 首页和团队简介 | `index.md` |
| 五个研究方向及各自的代表作编号 | `_data/research.json` |
| 博后、博士生、人数和个人主页 | `_data/people.json` |
| 论文清单 | `_data/publications.json` |
| 研究项目和资助方标识 | `_data/projects.json` |
| 各栏目标题和引言 | 对应的 `research.md`、`people.md`、`publications.md`、`projects.md` |
| 联系方式和咨询说明 | `contact.md` |
| 左侧栏姓名、职务、邮箱和个人主页链接 | `_data/profile.yml` |
| 导航菜单 | `_data/navigation.yml` |
| 页面底部更新时间 | `_config.yml` 中的 `updated` |
| 字体、颜色和布局 | `assets/css/main.css` |

## 更新照片

头像取自 Wei 的 RMIT 公开个人主页。上传新照片到 `assets/images/`，并在 `_data/profile.yml` 的 `photo` 字段填写对应路径，例如 `/assets/images/wei-wang.jpeg`。建议使用方形或接近方形的照片。

成员照片放在 `assets/people/`，并在 `_data/people.json` 中对应成员的 `photo` 字段填写 `/assets/people/文件名.jpg`。博后使用 `postdocs` 数组，RMIT 博士生使用 `rmit_phd` 数组，UNSW 博士生使用 `unsw_phd` 数组。每位成员可填写 `name`、`research`、`url`、`photo`。

博士生人数由 `rmit_count` 和 `unsw_count` 控制，目前为用户于 2026 年 11 月 18 日确认的 5 与 2。个人侧栏只在 About 显示；People 页负责人位于正文内。

## 添加论文

在 `_data/publications.json` 数组开头增加一个对象，例如

```json
{
  "id": "W198",
  "title": "Paper title",
  "authors": "Author, A.; Wang, W.",
  "year": 2027,
  "journal": "Journal Name",
  "doi": "10.xxxx/example",
  "url": "https://doi.org/10.xxxx/example",
  "volume": "1",
  "pages": "1–10"
}
```

相邻对象之间用英文逗号分隔，数组最后一个对象后面不加逗号。页面会按 `year` 自动从新到旧分组，同一年内保留文件中的论文顺序，因此最新文章请加在数组开头。

要把文章加入某个研究方向，在 `_data/research.json` 中该方向的 `publication_ids` 里填入文章的 `id`。每个方向目前展示 3–5 篇。

现有 197 篇来源于用户本地论文台账，并逐篇核对 Crossref DOI、题名和作者。正式出版年份优先使用已登记的印刷年份。Google Scholar 实时页面无法完整读取，清单与实时 Scholar 的覆盖差异仍待确认。Research 和 Publications 均使用对应期刊的真实独立封面，共 68 种期刊、覆盖 197 篇论文。封面来自官方出版社页面或原PDF中独立嵌入的封面位图，按期刊配图。

代表作优先考虑本人第一作者、通讯作者或末位作者，必要时选择第二作者及其他共同作者成果。作者角色保留在内部资料中供选文核对。Research 卡片展示期刊、论文题名、完整作者列表与文章链接。当前 22 个展示条目中 20 个已核实第一或通讯作者身份，另外两个补充电池整包实验和传播模拟。封面文件放在 `assets/journal-covers/`，各论文的 `image` 指向对应文件。

## 首次启用 GitHub Pages

1. 使用你创建的 **Public** 仓库 `weiwang-fire/S3`，默认分支为 `main`。
2. 当前网站源文件位于仓库的 `s3-lab-github/` 子目录。根目录的 `.github/workflows/pages.yml` 已配置 `source: ./s3-lab-github`。更新时保留这一层文件夹。
3. 在仓库打开 **Settings → Pages → Build and deployment → Source**，选择 **GitHub Actions**。
4. 打开 **Actions → Publish S3 Lab → Run workflow**，选择 `main` 后运行。之后每次保存到 `main` 都会自动构建和发布。
5. 等构建和部署均显示成功后，在 **Settings → Pages** 打开正式网站。

预期地址为 `https://weiwang-fire.github.io/S3/`，以 GitHub 返回的成功发布结果为准。

如果 Actions 报错，打开失败的步骤查看信息。保存记录都在仓库历史中，可以取回旧版本。

## 内容依据

Lab 全称为用户本轮确认的 **Safe, Smart, Sustainable Materials & Systems**。团队人数和两个 CRC-P 的当前状态来自 2026 年 11 月 18 日用户确认及所提供的 B4 表。About 的跨领域宗旨用于团队网站，不改变 FT27 申请的研究范围。

职务、联系方式及 Wei 的头像来自 [RMIT 个人主页](https://www.rmit.edu.au/profiles/w/wei-wang)。成员照片采用用户本轮提供的照片，Jiyuan Zhang 和 Claire Xiaowen Wan 的照片按用户要求整理为竖版构图。RMIT 五名博士生为 Mingjie Guo、Xuqi Yang、Meng Zhou、Jiyuan Zhang、Claire Xiaowen Wan。项目页列出 BPC、SSP3、两个 CRC-P 和 DECRA，并区分团队项目中的本人职责。资助方标识来自其公开官方资源，按原比例展示。DECRA 题名采用 RMIT 当前主页和项目记录中的 Fire Hazards 版本；旧 ARC 表存在 Fine Fibres 版本差异，仍需项目原始记录核准。

## 标识和配色

页眉采用用户确认的深蓝主体、红色上标与流线 S³ Lab 标识，透明 PNG 位于 `assets/branding/s3-lab-logo.png`。Logo 右侧为小号红色 RMIT University。个人头衔显示 Group Lead，现职简写 Lecturer。全站使用亮蓝、暖橙和深海军蓝的鲜明配色；五个 Research 主题分别有独立强调色，均在 CSS 中维护。

布局参考用户给出的学术主页形式，由本项目自行编写。网站首次整理于 2026 年 11 月 18 日。
