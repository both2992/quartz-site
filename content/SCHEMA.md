# 論文研究與撰寫知識庫維護指引 (Schema)

這份文件是讓 LLM（如我）參考的維基運作指引，用來確保在此知識庫中長期的資料一致性與品質。

## 🎯 知識庫目標

這個知識庫（Wiki）專注於**學術論文研究與撰寫**，主要目的是：
1. 長期累積文獻回顧的知識點，避免每次都重新閱讀論文。
2. 建立論文之間的對話與脈絡（誰反對誰、誰沿用了什麼方法）。
3. 提供撰寫文獻探討（Literature Review）與研究方法（Methodologies）的結構化素材。

## 🗂️ 目錄結構與分類規則

- `raw/`：存放您收集來、不應被竄改的原始論文、PDF文字檔或原始筆記。
- `raw/assets/`：存放論文原圖、圖表下載等本地資源。
- `wiki/`：由 LLM 負責新增、更新與維護的 Markdown 檔案。
  - `wiki/concepts/`：紀錄學術概念、理論模型、專有名詞（如 `Cognitive_Load_Theory.md`）。
  - `wiki/methods/`：紀錄研究方法、演算法、實驗設計、使用的資料集（如 `Semi_Structured_Interview.md`）。
  - `wiki/authors/`：紀錄重要學者、研究團隊及其主要貢獻（如 `John_Doe.md`）。
  - `wiki/comparisons/`：紀錄文獻對比、不同方法的優劣分析、文獻探討總結（如 `Literature_Review_on_LLM_Agents.md`）。

## 📝 Obsidian YAML 前置資料 (Frontmatter) 規範

為了配合 Obsidian 與 Dataview 操作，在建立或更新 `wiki/` 中的**任何一篇文章**時，**必須**在檔案開頭加入以下格式的 YAML Frontmatter：

```yaml
---
aliases: []
tags:
  - type/concept  # 或 type/method, type/author, type/comparison
  - status/draft  # status 可以是 draft, reviewed, synthesized
date_created: {{YYYY-MM-DD}}
date_modified: {{YYYY-MM-DD}}
sources:
  - "[[Paper_A_2023]]" # 連結到的來源文獻或原始檔
---
```

## ⚙️ 核心操作流程 (Workflows)

### 1. 攝取 (Ingest)
當使用者在 `raw/` 放入新論文（或指定新資訊）並要求處理時：
1. 讀取原始資料。
2. **總結核心貢獻**，並將這份論文的主要貢獻連結到對應的 `concepts/` 和 `methods/`。
3. 如果出現我們從未見過的新概念、新方法或重要作者，請在對應目錄建立新頁面，並套用 YAML 前置資料規範。
4. **更新現有頁面**：若該論文的觀點支持或反對現有百科內容，請導航到該頁面並更新，明確標示 `[Source: 新論文]`。
5. 更新 `index.md` 列出所有被建立或修改的頁面。
6. 在 `log.md` 產生一筆時間戳記紀錄。

### 2. 查詢與生成 (Query & Synthesis)
當使用者提問，或要求產出文獻回顧段落時：
1. 優先查閱 `index.md` 找出相關的 Wiki 頁面，並閱讀它們。
2. 在回答時，標註出處。
3. 若使用者的提問引發了有價值的新觀點或兩篇論文的有意義對比，將這個答案整理後儲存到 `wiki/comparisons/` 成為新頁面。

### 3. 健康檢查 (Lint)
定期尋找：
- 沒有其他內部連結指向的孤兒頁面（Orphan pages）。
- 內容互相矛盾但未被註記的頁面。
- 缺少特定 Metadata（如 `sources` 或 `tags`）的檔案。

## 🔗 內部連結 (Wikilinks)
請隨時使用 `[[Page Name]]` 語法來進行關聯，這樣在 Obsidian 的關聯圖（Graph View）中才能產生豐富的節點連接。
