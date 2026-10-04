# FIHML｜智慧醫療與機器學習基礎

臺北醫學大學 智慧醫療學士學位學程　1151 學期
授課教師：王三源（syw@tmu.edu.tw）

本 repo 提供課程第 5–9 週 Python 實作單元的資料與 notebook，可直接在 Google Colab 開啟。

| 週次 | 主題 | Notebook |
|---|---|---|
| W5 | 長照數據處理 – pandas | `notebooks/W05_pandas.ipynb` |
| W6 | 探索性資料分析 – Matplotlib | 即將公布 |
| W7 | 機器學習模型 – scikit-learn | 即將公布 |
| W9 | 醫療 AI 模型可解釋性 – SHAP | 即將公布 |

## 資料

### `data/ltc/`：長照機構住民失智評估資料（教學用模擬資料）

> ⚠️ **所有資料皆由程式隨機生成，姓名、日期、數值都不對應任何真實個人或機構。**
> 資料中刻意放入缺值、格式不一致、單位錯誤等問題，供資料清理練習使用。

- `residents_raw.csv`：住民基本資料（每人一列，含少量重複列）
- `assessments_raw.csv`：評估紀錄（每人 1–4 次評估）

### `data/hw/`：作業資料

改編自 Kaggle [Alzheimer's Disease Dataset](https://www.kaggle.com/datasets/rabieelkharoua/alzheimers-disease-dataset)
（Rabie El Kharoua, 2024，授權 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)）。
本課程將原始資料拆成兩張表，移除 `DoctorInCharge` 欄位，並加入缺值、編碼不一致、重複列等髒資料供練習使用；原資料本身亦為合成資料。

- `patients_raw.csv`：病人基本資料與生活型態
- `clinical_raw.csv`：臨床量測與診斷
