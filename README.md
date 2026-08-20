# de-ai-feel：台灣繁中的去 AI 感檢查層

`de-ai-feel` 是一個寫完之後才上場的編輯 skill。它會檢查稿件裡的模板句、空話、失去作者立場的安全語氣、台灣讀者不自然的詞，以及發佈前不該留下的工具痕跡。

它不替作者虛構故事，也不把每篇文章改成同一種網路口吻。目標很單純：保住原意，讓文字更像這位作者真的會說出口的話。

## 它會檢查什麼

檢查分成五輪，順序固定：

1. **發佈清潔**：移除對話框殘句、引用代碼、模型追蹤參數，以及貼到社群後會露出的 Markdown 標記。
2. **資訊密度**：找出沒有增加事實、判斷或情緒的句子，決定要刪、併，還是請作者補資料。
3. **作者聲音**：檢查語氣是否過度安全、句型是否整齊到像模板、例子是否只有泛稱而沒有可核對的細節。
4. **台灣繁中**：依科技介面、工作場合、社群內容與日常口語分組校正用詞，不用單一詞表硬套所有情境。
5. **口讀驗收**：把稿件唸一遍，處理太長、轉折太多、氣口不自然的句子，再核對數字與承諾有沒有漂移。

## 三色保真標記

改稿前先替內容分級，避免越改越不準：

- `LOCK`：名稱、價格、日期、網址、逐字引言、法務與退款條款。原字保留。
- `CHECK`：數據結論、因果關係、比較結果、效益承諾。可以改句子，不能改強度或推論。
- `FREE`：轉場、贅字、段落順序、句長與語氣。可依平台大幅調整。

這套分級比「全部潤得更自然」更安全，也比較容易看出哪一處需要回頭確認作者。

## 安裝

```bash
git clone https://github.com/techtipstts-tech/de-ai-feel.git ~/.claude/skills/de-ai-feel
```

重開 Claude Code session 後即可使用。也可以把 `SKILL.md` 提供給其他支援自訂指令的 AI 工具。

## 使用方式

- 「用 de-ai-feel 檢查這篇 Threads 貼文」
- 「保留我的語氣，只抓 AI 感和中國用語」
- 「先標問題，不要直接改」
- 「這封客戶信可以直接改，但價格和退款條款不能動」

若沒有指定模式，skill 會先給問題清單與修改方向；使用者明確說「直接改」時，才輸出完整改寫版。

## 檔案結構

```text
de-ai-feel/
├── SKILL.md
└── references/
    └── taiwan-localization.md
```

`SKILL.md` 是完整的檢查流程；`references/taiwan-localization.md` 是台灣繁中用字與語境判斷卡。

## 授權

MIT License。

由 [techtips_scarlett（Threads）](https://www.threads.com/@techtips_scarlett) 整理維護；Instagram：[techtips_scarlett](https://www.instagram.com/techtips_scarlett/)。若遇到新的工具殘留、平台格式或台灣用語案例，歡迎開 issue。
