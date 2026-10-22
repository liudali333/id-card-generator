# 工作证生成器

单文件网页工具，用于快速生成工作证、员工证、样机证的预览图片。

无需安装后端，直接用浏览器打开 `工作证生成器.html` 即可使用。页面输入、上传和导出默认都发生在本地浏览器中；导出 PNG 时依赖在线 CDN 加载 `html2canvas`，如需离线使用可改为本地脚本。

## 功能

- 左侧填写单位、编号、证卡标题、自定义字段等信息；
- 支持上传 Logo 和证件照；
- 支持自定义字段增删；
- 支持圆形印章样式和水印；
- 支持品牌色、标题色、印章色调整；
- 右侧实时预览；
- 一键导出高清 PNG；
- 一键导出干净版 HTML。

## 使用

1. 克隆仓库：

   ```bash
   git clone <repo-url>
   cd <repo-name>
   ```

2. 用浏览器打开：

   ```bash
   xdg-open 工作证生成器.html
   # 或 Windows 下双击 工作证生成器.html
   ```

3. 在左侧填写信息，右侧实时预览。
4. 点击「导出 PNG」下载图片。
5. 如需保留可编辑版本，点击「导出 HTML」。

## 文件说明

```text
.
├── 工作证生成器.html
├── README.md
└── LICENSE
```

仓库入口为单文件 `工作证生成器.html`，没有构建步骤。

## 公开使用建议

- 仓库内可直接保留该单文件工具；
- 公开演示或分享导出图时，建议使用中性示例文字，避免附带真实员工证件照、真实证件编号或真实公司信息；
- 涉及企业正式证件、印章、员工身份或对外证明用途时，以公司正式材料和合规要求为准。

## 隐私与安全

- 上传的照片和 Logo 仅通过 `FileReader` 转成 `dataURL`，用于本地预览和导出，不会上传到服务器；
- 页面内容默认保存在浏览器内存中，刷新后可能丢失；
- 不要把真实员工个人信息和真实证件材料提交到公开仓库。

## 离线化建议

如果需要在无网络环境使用，可把外部依赖下载到本地：

```bash
wget https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js
```

然后在 `工作证生成器.html` 中将：

```html
<script src="https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js"></script>
```

改为：

```html
<script src="./html2canvas.min.js"></script>
```

## License

本项目采用 [MIT License](./LICENSE) 发布。
