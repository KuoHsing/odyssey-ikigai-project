# Odyssey Life Coach

Odyssey Life Coach 是一個以 GitHub Copilot 為核心的生涯探索提示詞專案。它把 Copilot 設定成一位節奏溫和、一次只問一題的對話教練，透過 12 個問題協助使用者梳理三種 5 年後的人生版本，並在訪談結束後自動輸出本地 Markdown 摘要。

這個專案適合用在個人職涯盤點、轉職前思考、生活型態重整，以及低成本生涯原型測試的前期探索。

## 專案定位

這不是一套自動替你做決策的系統，而是一個把思考過程外顯化的對話流程。核心目標有三個：

1. 協助使用者看清楚「延續現況」、「被迫轉向」與「放開限制」三種版本。
2. 從三個版本中萃取重複出現的能力、節奏、關係與價值。
3. 把模糊的人生想像轉成一個 30 天內可執行的微測試。

## 主要功能

根據 [prompts/copilot_life_coach.md](prompts/copilot_life_coach.md)，Copilot 會：

1. 以固定順序進行 12 題一問一答訪談。
2. 每次只提出 1 個問題，避免一次拋出整串問卷。
3. 在每題之間給出一句簡短、低壓的回應。
4. 完成後整理三個版本的交集分析。
5. 產出一個 30 天內可執行的低成本微測試。
6. 將結果寫入 [my_plans](my_plans) 下的 `my_odyssey_summary.md`。

## 訪談架構

### Plan A：延續現況

1. 5 年後，你在哪裡工作與生活？
2. 那時你每天大多把時間花在哪裡？
3. 繼續走這條路，會讓你得到什麼？
4. 為了繼續走，你可能會放棄什麼？

### Plan B：重新改道

5. 假設原本的工作或產業消失了，你能先靠什麼既有能力重新開始？
6. 你可能會嘗試的 3 個方向是什麼？
7. 這 3 個方向中，你最想進一步了解哪一個？
8. 想到重新開始，你心裡最擔心什麼？

### Plan C：放開限制

9. 如果不用在意這件事看起來成不成功，你想把時間花在哪裡？
10. 你希望一週的工作與生活怎麼安排？
11. 你最想和哪些人一起工作或生活？
12. 你會用什麼標準判斷自己過得很好？

## 輸出內容

一次完整訪談結束後，應至少產出以下內容：

1. 12 題問答整理。
2. 三個版本的交集分析。
3. 能力、生活節奏、人際環境、核心價值四個面向的觀察。
4. 一個可在 30 天內完成的微測試方案。
5. 本地摘要檔 `my_plans/my_odyssey_summary.md`。

## 使用方式

1. 在 VS Code 開啟此工作區。
2. 讓 Copilot 使用 [prompts/copilot_life_coach.md](prompts/copilot_life_coach.md) 作為主要對話指令。
3. 從開場白開始，依序完成 12 題回答。
4. 對話結束後，到 [my_plans](my_plans) 查看自動生成的摘要檔。

### 推送前隱私檢查

`my_plans/` 內的私人摘要預設不會被 git 追蹤，但如果你曾手動強制加入檔案，或改過忽略規則，推送到 GitHub 前仍建議先執行 `git status` 檢查一次。

## 專案結構

```text
odyssey-ikigai-project/
├── README.md
├── my_plans/
├── prompts/
│   └── copilot_life_coach.md
└── templates/
    └── odyssey_light.md
```

## 對外說明與限制

1. 本專案為個人生涯探索與提示詞設計用途，並非心理治療、職涯諮商執照服務或醫療建議。
2. README 與 prompt 中提到的生涯設計、原型測試與 Ikigai，屬於啟發式方法，不應被視為保證結果的評量工具。
3. 本專案不是 Stanford 或任何 Ikigai 官方組織的正式產品。

## 隱私與存檔

1. 對話完成後，摘要預期會寫入 `my_plans/my_odyssey_summary.md`。
2. `my_plans/` 預設用來存放個人對話整理與私人探索內容。
3. 目前 repo 設定會忽略 `my_plans/` 內的個人內容，因此一般的 `git add`、`git commit`、`git push` 不會把這些私人摘要上傳到 GitHub。
4. 專案僅保留 `my_plans/.gitkeep` 作為資料夾占位檔，方便在版本庫中維持資料夾結構。
5. 若手動使用強制加入指令，或未來修改 `.gitignore` 規則，私人檔案仍可能被納入版控，推送前應自行再次確認。

## 來源出處

### 專案內直接來源

本 README 的功能描述、12 題流程、輸出要求與對話行為，直接整理自 [prompts/copilot_life_coach.md](prompts/copilot_life_coach.md)。

### 外部參考資料

1. Vogue Taiwan 文章〈你現在走的路，真的是自己選的嗎？史丹佛「奧德賽計畫 Odyssey Plan」用 3 個問題幫你找回人生主導權〉：https://www.vogue.com.tw/article/%E5%A5%A7%E5%BE%B7%E8%B3%BD%E8%A8%88%E7%95%AB
2. Designing Your Life 官方網站與相關方法資源：https://designingyour.life/

### 出處標註說明

本專案中的「12 題對話流程」是此專案 prompt 的整理版本；其中使用到的概念靈感，主要參考 Odyssey Plan / Designing Your Life 的生涯設計思路，以及上述 Vogue Taiwan 的中文整理文章。