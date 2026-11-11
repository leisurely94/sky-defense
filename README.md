# 苍穹防线 · GitHub Pages 上传包

这是一个可直接部署到 GitHub Pages 的单文件网页游戏。

## 文件说明

| 文件 | 用途 |
|---|---|
| `index.html` | 游戏本体，单文件自包含，图片、脚本、样式均已内嵌 |
| `.nojekyll` | 告诉 GitHub Pages 不要用 Jekyll 处理，避免静态文件被改动 |
| `README.md` | 本说明 |

不需要 `assets/`、`save/`、Node.js 或任何服务器，上传后即可运行。

## 上传步骤

1. 在 GitHub 新建一个仓库，例如 `sky-defense`。
2. 把本目录中的 `index.html`、`.nojekyll`、`README.md` 上传到仓库**根目录**。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment** 中选择：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/(root)`
5. 保存后等待 GitHub Pages 构建完成，访问：
   `https://你的用户名.github.io/sky-defense/`

如果使用命令行：

```bash
git init
git add index.html .nojekyll README.md
git commit -m "deploy 苍穹防线"
git branch -M main
git remote add origin https://github.com/你的用户名/sky-defense.git
git push -u origin main
```

## 存档说明

游戏进度保存在浏览器的 `localStorage`，按当前浏览器和当前网址隔离：

- 在同一浏览器、同一 GitHub Pages 地址下刷新或重进，进度会保留。
- 换浏览器、换网址、清理浏览器数据或使用无痕模式，进度不会跟过去。
- 这个 GitHub 包不包含任何本地 `save/skydefense_save.json` 进度文件。

## 兼容性

- 推荐使用桌面版 Chrome / Edge / Firefox 最新版本。
- 游戏使用 960×600 逻辑画布，页面会按窗口自动缩放适配。
