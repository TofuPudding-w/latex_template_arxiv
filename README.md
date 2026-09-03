# arXiv LaTeX 模板使用说明

## 下载内容

- 模板来源：<https://github.com/kourgeorge/arxiv-style>
- 下载日期：2026-08-07
- 授权协议：MIT License（见 `arxiv-style/License.txt`）
- 原始压缩包：`arxiv-style-master.zip`
- 压缩包 SHA-256：`EBC60796732A6EE338E0B5E679B7E4D0FB51A511CE55A5BC0DDA2E0FA516187B`

该模板是社区维护的单栏预印本模板，并非 arXiv 官方指定版式。arXiv 规定的是 TeX 源文件的处理与上传要求，而不是统一的论文排版样式。量子计算/物理类论文正式投稿时，应优先采用目标期刊的官方模板；若目标为 Physical Review 系列，通常使用 REVTeX 4.2。

## 主要文件

- `arxiv-style/template.tex`：示例主文件
- `arxiv-style/arxiv.sty`：自定义样式，提交时必须一并上传
- `arxiv-style/references.bib`：示例参考文献库
- `arxiv-style/template.pdf`：示例或本地验证生成的 PDF

## 本地编译

在 `arxiv-style` 目录运行：

```powershell
latexmk -pdf -interaction=nonstopmode -halt-on-error template.tex
```

本机已使用 TeX Live 2023 完成编译验证，生成 3 页 PDF。仅出现 Times 字体小型大写斜体回退的非致命警告，不影响生成。

## arXiv 上传注意事项

1. 上传主 `.tex`、全部被引用的图片、`arxiv.sty` 及其他自定义样式或宏文件。
2. 当前 arXiv 支持上传 `.bib` 或相应 `.bbl`；上游模板 README 中“必须把参考文献手工粘贴进 `.tex`”的说法已经过时，应以 arXiv 官方文档为准。
3. 不要上传 `.aux`、`.log`、`.out`、`.fls`、`.fdb_latexmk` 等编译中间文件，也不要混入未使用的图片和旧稿。
4. 上传前应在 arXiv 生成的预览 PDF 中逐页核对公式、图表、引用和字体。

官方说明：

- <https://info.arxiv.org/help/submit_tex.html>
- <https://info.arxiv.org/help/submit/index.html>
