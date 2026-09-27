# html-deck-to-pptx

把 HTML 演示文稿/课件的版式与视觉系统一比一复刻成 `.pptx`。

## 安装到 MiMo Desktop / Claude Code

```powershell
# 全局 skill
git clone https://github.com/oystero/html-deck-to-pptx.git "$env:USERPROFILE\.claude\skills\html-deck-to-pptx"
```

或解压后将本仓库内容放到 `~/.claude/skills/html-deck-to-pptx/`。

## 触发示例

- 「请按该 html 风格与格式输出完全一致的 pptx」
- 「把 outputs 里的网页课件做成同款 PPT」
- 「HTML 转 PPTX，保持色板和版式」

## 内容

| 路径 | 说明 |
|------|------|
| `SKILL.md` | 工作流：解析 tokens → 单位换算 → CJK 字体 → 组件映射 → QA |
| `references/mapping.md` | 色板/字阶/组件几何对照表 |
| `scripts/extract_html_tokens.py` | 从 HTML 抽取 CSS tokens 与 slide 清单 |
| `scripts/export_slides.ps1` | PowerPoint COM 导出 1920×1080 PNG（LibreOffice 崩溃时的备选） |

## 方法摘要

1. 解析 HTML `:root` 色板与 slide DOM  
2. `in = px × 13.333/1920`，`pt = px × 0.5`  
3. CJK 写入 `a:latin` / `a:ea` / `a:cs`  
4. 逐组件映射：sequence / choice-list / case-quote / rule-frame / pill / seal-ring…  
5. 结构诊断 + 关键短语 + 渲染 chrome 抽查  

## License

MIT
