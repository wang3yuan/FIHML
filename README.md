# FIHML｜智慧醫療與機器學習基礎

臺北醫學大學 智慧醫療學士學位學程　1151 學期
授課教師：王三源（syw@tmu.edu.tw）
課程助教：古珉瑄（醫資所，m610115009@tmu.edu.tw）

本 repo 提供課程第 5–9 週 Python 實作單元的資料與 notebook，可直接在 Google Colab 開啟。

| 週次 | 主題 | Notebook |
|---|---|---|
| W5 | 長照數據處理 – pandas | `notebooks/W05_pandas.ipynb`　作業：`homework/W05_HW.ipynb` |
| W6 | 探索性資料分析 – Matplotlib | 即將公布 |
| W7 | 機器學習模型 – scikit-learn | 即將公布 |
| W9 | 醫療 AI 模型可解釋性 – SHAP | 即將公布 |

## 執行環境

- Google Colab（建議），或 Python 3.10 以上的 Jupyter 環境
- 本教材已在 **pandas 2.2.3** 與 **pandas 3.0.6** 測試通過（Python 3.12）
- pandas 3 的文字欄位型別顯示為 `str`，pandas 2 顯示為 `object`，不影響程式執行

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

### 長照模擬資料欄位說明

| 原始欄名 | 英文欄名 | 說明 |
|---|---|---|
| 住民編號 | resident_id | 住民代碼 |
| 姓名 | name | 模擬姓名（去識別化練習用） |
| 性別 | sex | 男／女（原始資料寫法不一致） |
| 出生日期 | birth_date | 西元或民國（原始資料格式不一致） |
| 機構 | facility | A／B／C 機構 |
| 入住日期 | admission_date | |
| 教育年數 | education_years | 年 |
| 身高、體重 | height_cm, weight_kg | 公分、公斤 |
| 血型、房號 | blood_type, room | |
| 高血壓、糖尿病、中風史、聽力障礙 | hypertension, diabetes, stroke, hearing_loss | 有／無 |
| 失智診斷 | dementia | 有／無（**預測目標**） |
| 評估日期 | assess_date | |
| SPMSQ錯誤題數 | spmsq_errors | 簡易心智狀態問卷，0–10，錯越多認知越差；99 = 未評估 |
| 巴氏量表 | adl_barthel | 日常生活活動功能，0–100，越高越獨立 |
| IADL | iadl | 工具性日常生活活動，0–8 |
| GDS15 | gds15 | 老人憂鬱量表簡式版，0–15 |
| 過去一年跌倒次數 | falls_past_year | |
| 夜間睡眠時數 | sleep_hours | 小時 |
| 每週社交活動次數 | social_per_week | 住民自主參與之社交活動（非因失智安排之認知活動） |
| 用藥品項數 | n_medications | 慢性病用藥品項數（**不含失智症用藥**） |

> 本資料刻意不收錄 CDR 分期、失智症用藥等「確診後才會產生」的資訊：用它們預測失智等於偷看答案。
