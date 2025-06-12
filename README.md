# PR_TermProject

## YOLOv3

由於 GitHub 對檔案大小有限制，**訓練與測試的圖片檔需自行加入**。

### 📁 資料集分配如下：
- 測試集：`001496.png ~ 002991.png`
- 訓練集：
  - `000000.png ~ 001495.png`
  - `002992.png ~ 007480.png`

---

## 📊 Object Detection Metrics 設定

請依以下說明進行測試與評估：

- **Annotation**：使用**轉換後的 YOLO 格式 labels**
- **Images**：放置**測試圖檔**的資料夾
- **\*class 檔案**：使用 `kitti.names` 的內容，但**副檔名需改為 `.txt`**

### 偵測結果格式：

- **Detection Annotation**：`output_txts` 資料夾（由 `test_for_metric.py` 產生）
- **class 名稱檔案**：同上需`*.txt` （來自 `kitti.names`）

---

## 📂 評估輸出

執行 Object Detection Metrics 工具後，會產生完整的評估資料夾，包含：

- 每類別的 Precision / Recall / AP
- mAP（mean Average Precision）
- 可視化結果（如提供）
