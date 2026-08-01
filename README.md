# marxist-classics-markdown

马克思主义经典著作的 Markdown 版本，共 134 部文献，约 152 MB 纯文本。

## 收录内容

| 文献 | 卷数 |
|------|------|
| 马克思恩格斯全集 | 第 1 至 50 卷（含上下册分卷） |
| 列宁全集 | 第 1 至 53 卷 |
| 斯大林全集 | 正卷、档案附卷 |
| 毛泽东选集 | 十卷合订本 |
| 建国以来毛泽东文稿 | 第 1 至 13 册 |
| 毛泽东军事文集 | 第 3 至 5 卷 |
| 辩证法唯物论（讲授提纲） | 单册 |
| 哲学小词典（上海哲学小辞典编写组） | 单册 |

文件按著作命名，一部一卷对应一个 `.md`，直接放在仓库根目录，没有子目录。

## 文本来源与处理

原始文本由 PDF 经 OCR 转换而来，已做过噪声清洗：

- 移除 HTML 标签残留（`<td rowspan=1 colspan=1>` 等网页拷贝痕迹）
- 移除失效的 Markdown 图片引用（`![](images/xxx.jpg)`，图片本体不存在）
- Markdown 链接 `[文字](说明)` 转为纯文字（说明部分多为注记编号）
- LaTeX 公式块保留原文

章节结构用 Markdown 标题（`#`、`##`）标记，段落以空行分隔。

## OCR 质量说明

文本来自 OCR，**存在识别错误**，个别字词、标点可能有误，少数文件含无法解码的字节。用于阅读和检索没问题，**引用请以纸质版或官方电子版为准**。

## 怎么用

直接下载：

```bash
git clone https://github.com/PrismScopes/marxist-classics-markdown.git
```

只要某一部：在 GitHub 页面上找到文件，点 Raw 下载即可。

### 配合 MarxLen 使用

本仓库是 [MarxLen（马列通）](https://github.com/PrismScopes/MarxLen) 的语料来源。MarxLen 是基于这些文献的智能问答系统，用自然语言提问，回答附带可追溯的原文出处。

把本仓库放到 MarxLen 项目的 `ww/` 目录下即可启用原文阅读器与来源跳转：

```bash
# 在 MarxLen 项目根目录执行
git clone https://github.com/PrismScopes/marxist-classics-markdown.git ww-tmp
mv ww-tmp/*.md ww/
rm -rf ww-tmp
```

详见 MarxLen 仓库的 README。

## 为什么单独放一个仓库

MarxLen 主仓库带的是预构建索引（二进制，约 1.2 GB，走 Git LFS）。语料是纯文本，更新节奏与索引不同，而且只做问答的用户并不需要这 152 MB。拆开各取所需。

## License

文本版权归原出版方所有，本仓库仅供学习研究使用，不作商业用途。
