# 伏地挺身教練

用手機鏡頭分析伏地挺身姿勢的網頁 App：計次、下壓深度、頂端伸直、塌腰／翹臀、節奏。
姿勢偵測在瀏覽器裡執行（Google MediaPipe Pose Landmarker），影片不會上傳。

- **錄影或選擇影片**：錄好一段側拍影片後逐格分析，顯示每一下的分數與問題，可重播看骨架
- **即時鏡頭**：手機架在身體側面，邊做邊計次，有語音提示
- iPhone Safari：分享 → 加入主畫面，就能像 App 一樣打開

## 檔案

| 檔案 | 用途 |
|---|---|
| `index.html` | 介面與判斷規則（與 Python 原型相同的門檻） |
| `vision_bundle.js`、`wasm/` | MediaPipe Tasks Vision 0.10.21（Apache-2.0） |
| `pose_landmarker_full.task` | MediaPipe 姿勢模型（Full） |
| `manifest.webmanifest`、`icons/` | 加入主畫面用 |

## 判斷標準

- 下壓深度：最低點手肘 ≤ 90°（90–105° 略淺）
- 頂端伸直：手肘 ≥ 155°
- 身體直線：肩-髖-踝 ≥ 165°（< 155° 明顯塌腰或翹臀）
- 節奏：一下至少 0.8 秒
