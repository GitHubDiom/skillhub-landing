# SkillHub Landing Page

这是一个可直接部署的静态 Landing Page，目录内只有一个 `index.html`，不依赖构建工具。

## 文件位置

- 页面文件：`skillhub-landing-page/index.html`

## 本地预览（10 秒）

直接双击打开 `index.html`，或在项目根目录执行：

```bash
open skillhub-landing-page/index.html
```

## DMG 下载文件配置（必做）

页面中的“下载 mac 版 .dmg / 立即下载 .dmg”按钮，默认指向：

`./downloads/SkillHub-Manager-mac.dmg`

请在发布前把你的安装包放到这个路径：

```text
skillhub-landing-page/downloads/SkillHub-Manager-mac.dmg
```

如果文件名不同，改 `index.html` 里这 3 处链接即可（当前是同一个地址）：

- 顶部导航下载按钮
- Hero 下载按钮
- 底部 CTA 下载按钮

> 当前页面文案已明确：仅 macOS 版本完成测试；源码暂不开放；高级功能后续收费。

## 国内可访问 + 最快上线（推荐：EdgeOne Pages 一键部署）

> 适合“怎么快怎么来”的场景：接入 Git 仓库后，点击即部署，后续可自动跟随仓库更新。

### 1. 先把代码推到 GitHub 或 Gitee（可用私有仓库）

确保仓库中已包含 `skillhub-landing-page/index.html`。

### 2. 打开一键部署链接（替换成你的仓库地址）

把下面链接中的 `ENCODED_REPO_URL` 换成“URL 编码后”的仓库地址（官方文档要求参数使用 `encodeURIComponent`）：

```text
https://edgeone.ai/pages/new?repository-url=ENCODED_REPO_URL&project-name=skillhub-landing&root-directory=skillhub-landing-page
```

示例（仓库是 `https://github.com/your-name/SkillsManager` 时）：

```text
https://edgeone.ai/pages/new?repository-url=https%3A%2F%2Fgithub.com%2Fyour-name%2FSkillsManager&project-name=skillhub-landing&root-directory=skillhub-landing-page
```

快速生成编码 URL（复制即用）：

```bash
REPO_URL='https://github.com/your-name/SkillsManager'
ENCODED_REPO_URL=$(node -e "console.log(encodeURIComponent(process.argv[1]))" "$REPO_URL")
echo "https://edgeone.ai/pages/new?repository-url=${ENCODED_REPO_URL}&project-name=skillhub-landing&root-directory=skillhub-landing-page"
```

也可以直接用按钮（同样替换为编码后的仓库地址）：

```md
[![Deploy with EdgeOne](https://edgeone.cloud.tencent.com/pages/deploy/button)](https://edgeone.ai/pages/new?repository-url=ENCODED_REPO_URL&project-name=skillhub-landing&root-directory=skillhub-landing-page)
```

### 3. 控制台确认并发布

在 EdgeOne Pages 控制台中：

- 选择仓库分支（一般 `main`）
- Root Directory 确认是 `skillhub-landing-page`
- 发布（Deploy）

发布完成后会得到一个可访问域名（例如 `*.edgeone.app`）。

## 备选：命令行一条命令部署

如果你不想走控制台，也可以：

```bash
npx edgeone pages deploy ./skillhub-landing-page
```

## 上线前建议（1 分钟）

- 确认 `skillhub-landing-page/downloads/SkillHub-Manager-mac.dmg` 已上传
- 如需企业官网域名，绑定自定义域名并按平台要求完成备案配置（如果使用中国大陆节点）

## 参考文档（官方）

- EdgeOne Pages 国内访问与免费版说明（FAQ）：https://edgeone.cloud.tencent.com/pages/document/162935477619350528
- EdgeOne Pages 一键部署按钮参数（官方文档）：https://cloud.tencent.com/document/product/1552/118069
- EdgeOne Pages 部署方式（Git 导入 / 直接上传 / CLI）：https://pages.edgeone.ai/zh/document/162936870006199296
