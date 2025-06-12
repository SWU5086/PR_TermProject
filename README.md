# PR_TermProject

## YOLOv3

由於 GitHub 對檔案大小有限制，**訓練與測試的圖片檔需自行加入**。

### 📁 資料集分配如下：
- 測試集：`001496.png ~ 002991.png`
- 訓練集：
  - `000000.png ~ 001495.png`
  - `002992.png ~ 007480.png`

---

# 📊 Object Detection Metrics 使用教學
## Object Detection Metrics 環境架設

1. 從老師給的網址下載 zip 檔  
   [https://github.com/rafaelpadilla/review_object_detection_metrics](https://github.com/rafaelpadilla/review_object_detection_metrics)

2. 解壓縮下載的 zip 檔

3. 點進解壓後的資料夾，直到看到 `environment.yml` 檔案

4. 在該資料夾空白處右鍵，選擇「打開終端機」（這樣終端機的路徑會直接在此資料夾）  
   > **注意**：如果你直接在外層開終端機，要自己用 `cd` 指令切換到此資料夾路徑

5. 執行以下指令創建 conda 環境並安裝依賴：
   ```bash
   conda create -n object_detection_metrics python=3.9
   conda activate object_detection_metrics
   conda env update --file environment.yml
   python setup.py install
   python run.py 

    #跑完上述架好環境後，下次要用來評估模型只需要到該資料夾，右鍵開啟終端機，輸入
    conda activate object_detection_metrics
    python run.py
    ```


##Object Detection Metrics 設定

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
