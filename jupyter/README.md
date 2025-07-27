## 📊 使用資料集

- **名稱**：CIC-DDoS2019
- **來源**：Canadian Institute for Cybersecurity（UNB）
- **連結**：[https://www.unb.ca/cic/datasets/ddos-2019.html](https://www.unb.ca/cic/datasets/ddos-2019.html)

## ⚙️ 執行方式

### 1. 安裝相依套件

```bash
pip install -r requirements.txt

## 🔧 模組功能簡述

- **Data Cleaning**：負責資料清洗與預處理，包括遺失值處理、欄位過濾與資料格式標準化，為後續特徵選擇與模型訓練建立乾淨資料基礎。
- **XGBoost**：作為特徵挑選工具，用以評估並篩選對分類結果具有高度影響力的欄位，降低維度並優化訓練效率。
- **LSTM**：為主要深度學習模型，適用於處理時間序列資料，可學習封包流量中的時間依賴性以進行 DDoS 攻擊分類。
- **LSTM Integrated Version**：LSTM 的進階版本，支援多次實驗與參數化設計，便於進行不同特徵組合或實驗設計下的模型訓練與結果比較。