# 歐洲旅遊景點數據分析報告 
# European_Travel_Analysis
### European Travel Destinations: Data Analysis, K-Means Clustering & Recommendation Engine

[![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)](https://www.r-project.org/)
[![Quarto](https://img.shields.io/badge/Quarto-4752B2?style=for-the-badge&logo=quarto&logoColor=white)](https://quarto.org/)
[![Observable JS](https://img.shields.io/badge/Observable_JS-000000?style=for-the-badge&logo=observable&logoColor=white)](https://observablehq.com/)

## 專案概述
本專案透過數據分析解決旅客在面對歐洲眾多景點時的決策困境。透過分析 21 個國家、209 個指標性景點的數據（包含遊客量、生活成本、安全風險），識別了市場中隱藏的消費規律，並利用機器學習（K-Means Clustering）建立目的地人格標籤。

---

## 關鍵數據洞察 (Executive Summary)
* **市場主導地位**：超過 **60%** 的熱門景點屬於「人文城市」，且呈現強烈的春秋雙峰走訪趨勢。
* **消費地景反直覺**：受瑞士與北歐國家影響，**非歐元區**的高消費景點比例（64%）顯著高於歐元區（57%）。
* **自然景觀優勢**：數據顯示歐洲的自然景觀景點具備極高的安全性，是「低風險偏好者」的首選。

---

## 技術流程與核心方法

### 1. 資料清洗與特徵工程 (Data Engineering)
* **複合鍵處理 (Composite Key)**：利用「景點+國家」複合鍵解決如冰島與馬爾他同名 "Blue Lagoon" 的重複匹配問題，確保 209 筆數據的唯一性。
* **偏態校正**：對遊客量進行 **Log10 轉換**，以消除極端離群值（如巴黎 38M vs 一般景點 0.1M）對模型距離計算的影響。
* **文本探勘**：從半結構化的安全備註中提取關鍵風險頻率。

### 2. 機器學習分群 (Clustering)
* **演算法**：K-Means Clustering。
* **維度優化**：透過 PCA (主成分分析) 進行降維視覺化，模型在二維空間下的解釋力高達 **83.5%**。

### 3. 市場人格標籤 (Destination Personas)
| 群組 | 命名 | 數據特徵 | 適合客群 |
|:---:|:---|:---|:---|
| **C1** | **Hidden Premium Gems** | 人流極低、高消費、極安全 | 高端避世、預算充足者 |
| **C2** | **Budget-Friendly Havens** | 中人流、物價最低、極安全 | 背包客、高 CP 值追求者 |
| **C3** | **Elite Tourist Hotspots** | 高人流、高消費、極安全 | 熱門名勝愛好者、大眾富裕階層 |
| **C4** | **Iconic Metropolitan Hubs** | 最高人流、高消費、具潛在風險 | 一線大城收集者、經驗豐富旅客 |

---

## 📂 檔案結構
* `European_Travel.qmd`: 核心分析、可視化與 OJS 工具開發腳本。
* `cleaned_df_final.csv`: 經過清洗與 K-means 標籤化後的最終數據。
* `European_Travel.html`: 數據報告。

## 🚀 如何運行
1. 安裝 [RStudio](https://rstudio.com/) 與 [Quarto](https://quarto.org/docs/get-started/)。
2. 執行 R 指令安裝必要套件：請參考qmd檔。
3. 下載本專案後，開啟 `.qmd` 檔案並點擊 **"Render"** 即可生成包含互動工具的 HTML 報告。

---
