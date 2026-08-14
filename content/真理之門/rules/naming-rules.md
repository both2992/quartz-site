# 檔案命名規則

## 預設命名格式
- `raw/`：`YYYY-MM-DD - raw - {title}.md`
- `card/`：`YYYY-MM-DD - {title}.md`
- `opinions/`：`{topic}.md`
- `digest/`：`YYYY-WW - digest.md`
- `outline/`：`YYYY-MM-DD - outline - {topic}.md`
- `draft/`：`YYYY-MM-DD - draft - {topic}.md`
- `moc/`：`{topic} - MOC.md`

## 命名原則
- 日期預設以整理日為主，不用原文日期取代檔名日期。
- 原文日期另外記錄於 YAML frontmatter 與內文欄位。
- `{title}` 與 `{topic}` 優先使用可讀中文名稱。
- 保留辨識度，避免 `想法1`、`筆記整理`、`未命名` 之類模糊名稱。
- 若原標題過長，可在不失真的前提下縮短。
- 同主題盡量維持穩定命名，避免同義重複。

## 標題縮寫建議
- 保留主詞與關鍵動作
- 移除贅詞與過長副標
- 優先讓未來搜尋時容易找到

## 檔名與內文的分工
- 檔名負責辨識與檢索
- 內文與 frontmatter 負責完整描述
- 不要把所有資訊都塞進檔名
