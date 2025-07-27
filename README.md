## 📊 使用資料集

- **名稱**：CIC-DDoS2019
- **來源**：Canadian Institute for Cybersecurity（UNB）
- **連結**：[https://www.unb.ca/cic/datasets/ddos-2019.html](https://www.unb.ca/cic/datasets/ddos-2019.html)

## ⚙️ 執行方式

### 1. 安裝相依套件

```bash
pip install -r requirements.txt
```
## 2. 模組功能簡述

- **Data Cleaning**：負責資料清洗與預處理，包括遺失值處理、欄位過濾與資料格式標準化，為後續特徵選擇與模型訓練建立乾淨資料基礎。
- **XGBoost**：作為特徵挑選工具，用以評估並篩選對分類結果具有高度影響力的欄位，降低維度並優化訓練效率。
- **LSTM**：為主要深度學習模型，適用於處理時間序列資料，可學習封包流量中的時間依賴性以進行 DDoS 攻擊分類。
- **LSTM Integrated Version**：LSTM 的進階版本，支援多次實驗與參數化設計，便於進行不同特徵組合或實驗設計下的模型訓練與結果比較。

## 3 資料存檔方式
### 1. npy 方式存資料
```bash
#儲存
imagesavepath = "data/"
np.save(imagesavepath + "normalized_features.npy", normalized_features)
np.save(imagesavepath + "train_label_onehot.npy", train_label_onehot)

#載入
imagesavepath = "data/"
normalized_features = np.load(imagesavepath + "normalized_features.npy")
train_label_onehot = np.load(imagesavepath + "train_label_onehot.npy")
```
### 2. 模型和權重儲
```bash
#儲存
model.save("LSTM_for_DDOS.h5")
print("LSTM_for_DDOS.h5 模型儲存完畢!")
model.save_weights("LSTM_for_DDOS.weights.h5")
print("模型權重儲存完畢")   

#載入
model = load_model("LSTM_for_DDOS.h5")
print("模型載入成功")
model.load_weights("LSTM_for_DDOS.weights.h5")
print("載入權重成功, 繼續訓練模型")
```