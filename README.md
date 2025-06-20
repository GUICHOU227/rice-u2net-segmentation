# Rice U2Net Segmentation

本項目為基於 [U-2-Net](https://github.com/xuebinqin/U-2-Net) 模型的水穀叢去背處理系統，用於清除穀叢影像中的土壤、阿拉伯標示、陰影等非作物區域，以提升病蟲害分析、含水量判別、產量預測等之後續任務模型準確性。

---

## 系統概要

- **輸入**：穀種高範圖像 (UAV 與地面拍攝，航高4層不超過 4 米)
- **輸出**：已刪除背景的穀叢物體 mask 圖
- **應用**：前處理模型用於 GRVI 推測、蟲害 YOLO 分類、水分指標估算

---

## 供硬體與系統需求

- Nvidia GPU 相容系統 (CUDA 10.2 ~ 12.x)
- 已安裝 [Anaconda](https://www.anaconda.com/) (Python 3.7 ~ 3.10)

---

## 使用步驟

1. 使用 Anaconda 新建處理環境 (Python 3.7 ~ 3.10)
2. 根據 CUDA 版本，安裝相應 PyTorch
3. 安裝 U-2-Net 相關套件：
   ```bash
   pip install opencv-python torch torchvision
   ```
4. 開啟 `u2net_test.py` 程式
5. 將稍後要處理的穀種影像放入 `testimage/`
6. 在 `u2net_test.py` 中確認路徑，執行購面程式
7. 結果將轉出至 `results/` 或 `results_mask/`

---

## 使用結果示意

> 並附圖示示穀種影像前後轉化，可用於調用到病蟲害分類 / 水分預測等預處別程式中

---

## Acknowledgements

該項目基於開源項目 [U-2-Net by xuebinqin](https://github.com/xuebinqin/U-2-Net)。
