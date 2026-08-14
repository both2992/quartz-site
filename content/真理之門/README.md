# 資料整理系統 README

## 這個專案是做什麼的
這是一套以 Markdown 為核心的資料整理系統，用來把外部資料逐步整理成可累積的知識庫。它不是單純放筆記的地方，而是一套可持續操作的工作流程，讓資料可以從原始材料一路走到可寫作、可教學、可研究的形式。

核心流程如下：

`inbox -> raw -> card -> opinions -> digest / outline / draft`

這套系統同時考慮 Obsidian 的閱讀與連結需求，但主資料仍保持為通用 Markdown。

## 各資料夾功能
- `inbox/`：尚未整理的輸入
- `raw/`：原始內容、逐字稿、摘錄、來源證據
- `card/`：單筆資料整理卡
- `opinions/`：主題母筆記、方法論、長期觀點
- `digest/`：週期回顧與趨勢整理
- `outline/`：文章、簡報、教學或研究的大綱
- `draft/`：草稿
- `rules/`：規則與驗收標準
- `templates/`：可直接複用的模板
- `moc/`：主題導覽頁
- `scripts/`：抓取、轉檔、整理工具

## 日常使用流程
1. 把新資料提供給 Codex  
   可以是網址、貼文、文章內容、逐字稿、PDF 摘錄、自己的筆記。

2. 先進 `raw/`  
   保留盡量完整的來源內容與證據，不急著先壓縮成摘要。

3. 再建 `card/`  
   將單筆資料轉成可吸收、可引用、可採取行動的整理卡。

4. 優先更新 `opinions/`  
   先把新資訊納入既有主題與方法論，而不是不停新增小筆記。

5. 累積到一定程度後，再產出 `digest/`、`outline/`、`draft`

## 文章貼進來後，會不會自動出現在 Obsidian
會，但前提是 Obsidian 直接開啟這個 workspace，或你的 Vault 與這個資料夾同步。

在這個前提下，當你把文章全文、摘錄或逐字稿貼給 Codex 時，Codex 會直接在這個 workspace 內建立或更新：
- `raw/`：保存原始內容與來源資訊
- `card/`：建立整理卡
- `opinions/`：更新既有主題母筆記

因為這些都是直接寫入 Markdown 檔，所以 Obsidian 會直接看到更新後的內容，不需要你再人工複製貼上一次。

如果你只提供網址，是否能完全自動要看來源網站能不能取得內容。若抓不到全文，Codex 會標示限制，並請你補貼全文或重點摘錄。

## 每次新增資料時，Codex 應如何處理
收到資料後，Codex 應固定執行：

1. 判斷資料類型與用途
2. 建立或更新 `raw`
3. 建立 `card`
4. 先找既有 `opinions` 是否可更新
5. 視情況補上 `[[內部連結]]` 或更新 MOC
6. 若主題已成熟，再產出 `digest`、`outline` 或 `draft`
7. 最後依 `rules/review-checklist.md` 做基本驗收

## 使用者應如何提供資料
建議用以下格式提供：

```md
- 資料類型：
- 來源網址或內容：
- 我的觀點：
- 我現在最關心的用途：
```

如果資訊不完整也沒關係，Codex 應先用現有資訊開始整理，並在結果中誠實標註缺漏與假設。

也可以直接使用 [source-intake-template.md](C:\Users\both2\Documents\Codex\2026-04-22-1-markdown-2-3-obsidian-notion\templates\source-intake-template.md) 這份模板來貼資料。

## 如何在 Obsidian 中使用這套系統
- 直接把整個 workspace 當作 Vault 打開即可
- `card/` 與 `opinions/` 會是最常閱讀與回顧的區域
- `moc/` 可作為主題入口頁
- 透過 YAML frontmatter、`[[內部連結]]`、標籤與資料夾共同整理
- 不為了圖譜而製造空洞頁面，仍以內容與主題累積為主

## 如何進行基本驗收
每次整理後，至少檢查：
- `raw` 是否保留足夠完整來源
- 是否清楚記錄來源與日期
- `card` 是否有結合使用者觀點
- 是否優先更新既有 `opinions`
- 是否誠實標註缺漏與不確定性
- 標籤與 `[[內部連結]]` 是否一致且有意義
- 結果是否能支援之後的寫作、回顧與串聯

詳細清單請看 [review-checklist.md](C:\Users\both2\Documents\Codex\2026-04-22-1-markdown-2-3-obsidian-notion\rules\review-checklist.md)。

## 第一次使用建議流程
1. 先貼 3-5 筆你最近真的想整理的資料，不要一次丟太多。
2. 讓系統先長出第一批 `raw`、`card` 與 1-2 篇核心 `opinions`。
3. 觀察哪些標籤與主題真的會重複出現，再逐步穩定命名。
4. 等同主題卡片累積起來後，再建立第一個 MOC 或 digest。

## 建議的啟動方式
你現在可以直接貼第一批資料，我會依規則開始整理，而不是只做摘要。
