# 个人简历网站更新说明

这个更新包适用于 `Misaeon/my-cv` 仓库。它完成两项修改：

1. 在 **About me**（`/cv/`）页面加入 **Service** 部分。
2. 在 **Teaching** 后加入 **Supervision** 页面，并提供 Doctoral thesis、Master thesis 两个区域以及可点击的 thesis 详情页。

## 一、放置文件

把压缩包内除本说明文件外的所有目录和文件复制到 `my-cv` 仓库根目录。出现提示时选择覆盖同名文件。

需要覆盖的现有文件：

- `_config.yml`
- `_data/cv.yml`
- `_layouts/cv.liquid`
- `assets/css/main.scss`

需要加入的新文件或目录：

- `_includes/cv/service.liquid`
- `_includes/supervisions.liquid`
- `_layouts/thesis.liquid`
- `_pages/supervision.md`
- `_sass/_supervisions.scss`
- `_supervisions/doctoral-thesis-template.md`
- `_supervisions/master-thesis-template.md`

## 二、Service 内容

Service 的文字已写入 `_data/cv.yml`，不需要再次修改。页面会显示：

- Academic Editor
  - Indoor Air, Wiley
- Peer-reviewer
  - Building and Environment, Journal of Building Engineering, Indoor Air, Indoor Environments, Sustainable Cities and Society, Case Studies in Thermal Engineering

如需以后修改，只编辑 `_data/cv.yml` 中的 `Service:` 部分即可。

## 三、加入一篇 Doctoral thesis

1. 复制 `_supervisions/doctoral-thesis-template.md`。
2. 把复制件改为有意义的英文文件名，例如：
   `_supervisions/physics-informed-indoor-climate.md`。
3. 编辑复制件中的标题、学生、学校、时间、状态、导师、论文和正文。
4. 删除最后的 `published: false`，或者把它改成 `published: true`。

必须保留：

```yaml
layout: thesis
thesis_type: doctoral
```

`thesis_type` 必须为小写的 `doctoral`，该记录才会自动进入 **Doctoral thesis** 区域。

## 四、加入一篇 Master thesis

操作与上面相同，但复制 `_supervisions/master-thesis-template.md`，并保留：

```yaml
layout: thesis
thesis_type: master
```

`thesis_type` 必须为小写的 `master`，该记录才会自动进入 **Master thesis** 区域。

## 五、填写相关发表论文

一篇 thesis 可以填写多篇 related publications。每篇论文按下面的格式加入：

```yaml
publications:
  - title: Paper title 1
    authors: Author One, Author Two, and Sen Miao
    journal: Journal name
    year: 2026
    url: https://doi.org/your-doi-1
    note: Published

  - title: Paper title 2
    authors: Author One and Sen Miao
    journal: Journal name
    year: 2027
    url: https://doi.org/your-doi-2
    note: Accepted
```

如果暂时没有相关论文，写成：

```yaml
publications: []
```

`note` 可以删除；`url` 也可以删除。没有 URL 时，论文标题会显示为普通文字而不是链接。

## 六、更新并发布

把所有文件提交到仓库的 `main` 分支后，现有 GitHub Actions 会重新生成并部署网站。因为 `_config.yml` 新增了 collection，这次更新必须触发一次完整构建。

如果使用 Git 命令：

```bash
git add _config.yml _data/cv.yml _layouts/cv.liquid assets/css/main.scss \
  _includes/cv/service.liquid _includes/supervisions.liquid \
  _layouts/thesis.liquid _pages/supervision.md _sass/_supervisions.scss \
  _supervisions
git commit -m "Add service and supervision pages"
git push origin main
```

## 七、本地检查（可选）

在仓库根目录运行：

```bash
npm ci
npx prettier . --check
docker compose up --build
```

然后访问：

- `http://localhost:8080/cv/`
- `http://localhost:8080/supervision/`

每次修改 `_config.yml` 后，应停止并重新启动 Jekyll/Docker，而不只是刷新浏览器。

## 注意

两个模板文件默认含有 `published: false`，因此示例文字不会出现在正式网站。创建真实 thesis 文件后，必须删除该行或设为 `true`，记录和详情页才会生成。
