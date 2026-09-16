# 奧德賽計畫 × Ikigai 生涯設計框架 (Odyssey-Ikigai Framework)

結合**史丹佛大學設計思考（Designing Your Life）**與**沖繩長壽哲學 Ikigai（生之意義）**，打造一套可迭代、可測試的 5 年人生探索工具。

搭配 **VS Code + GitHub Copilot**，讓 AI 擔任你的個人生涯教練，透過一問一答梳理出 3 種平行人生版本，並以最小成本的原型測試驗證假設。

---

## 專案結構

```text
odyssey-ikigai-project/
├── templates/                 # 空白範本
│   ├── 01_ikigai_audit.md       # Ikigai 四向度盤點表
│   ├── 02_odyssey_plan_1.md     # 版本一：現有軌道延續
│   ├── 03_odyssey_plan_2.md     # 版本二：轉向與替代方案
│   ├── 04_odyssey_plan_3.md     # 版本三：狂想探索
│   └── 05_prototype_tracker.md  # 原型測試追蹤表（對話與微實驗）
├── prompts/                   # AI 指令集
│   └── copilot_life_coach.md    # 供 GitHub Copilot 引導對話的角色指令
├── my_plans/                  # 個人填寫區（已加入 .gitignore，不外洩）
├── .gitignore                 # 隱私防護設定
└── README.md                  # 專案說明文件