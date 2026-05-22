# eduTool｜AI 輔助互動頁面建置

> 2026 eduTool — 以 API KEY 為核心的教育互動工具集

這個專案是為課堂設計的互動工具集，分為三個部分：

- **成果展示**：串接 Google Drive 的作品展示頁面
- **課堂應用**：以 Gemini API 驅動的 AI 互動工具，由老師設計、課堂中實際使用
- **上課工具**：純前端互動模擬，不需 API，開啟即用

---

## 目錄結構

```
/
├── index.html          ← 入口導覽頁
└── demo/
    │
    │  ── 成果展示（Google Drive）──
    ├── digital-music-player.html    ← 音樂播放器
    ├── digital-library.html         ← 數位圖書館
    ├── digital-photo.html           ← 數位相簿
    │
    │  ── 課堂應用（Gemini API）──
    ├── research-game.html           ← 獨立研究討論
    ├── travel-map.html              ← 人文踏查規劃
    ├── travel-prompt-generator.html ← 旅行 APP 產生器
    │
    │  ── 上課工具（純前端）──
    ├── ui-dashboard.html            ← 互動儀表板
    ├── css-cards.html               ← CSS 卡片排版
    ├── java-sim.html                ← 排序視覺化
    ├── js-science.html              ← JS 科學模擬
    ├── physics-lab.html             ← 拋體實驗
    └── markdown-viewer.html         ← Markdown 檢視工具
```

---

## 使用前準備

### 一、Gemini API（課堂應用工具）

以下三個頁面是老師為課堂設計的 AI 互動工具，需要 Gemini API Key 才能運作：

- `research-game.html`（獨立研究討論）
- `travel-map.html`（人文踏查規劃）
- `travel-prompt-generator.html`（旅行 APP 產生器）

**申請步驟：**

1. 前往 [Google AI Studio](https://aistudio.google.com/)，用 Google 帳號登入
2. 點選左側「Get API key」→「Create API key」
3. 複製產生的 API Key
4. 貼入對應頁面的 API Key 欄位即可使用

> **目前使用的模型為 Gemini 3.1 Flash Lite（`gemini-3.1-flash-lite`），在免費額度內可直接使用，不需要綁定信用卡。**
>
> 免費額度限制如下：
> - **RPM 15**：每分鐘最多 15 次請求
> - **RPD 500**：每天最多 500 次請求
>
> 課堂中學生分組使用，通常不會觸及上限。詳細說明請參考 [Google AI Studio 定價頁面](https://ai.google.dev/pricing)。

---

### 二、Google Drive API（成果展示頁面）

以下三個頁面用於展示學生成果，串接 Google Drive，需要額外開啟 API 授權：

- `digital-music-player.html`（音樂播放器）
- `digital-library.html`（數位圖書館）
- `digital-photo.html`（數位相簿）

**申請步驟：**

1. 前往 [Google Cloud Console](https://console.cloud.google.com/)
2. 建立新專案（或選擇現有專案）
3. 在左側選單選「API 和服務」→「程式庫」
4. 搜尋「Google Drive API」，點選後按「啟用」
5. 前往「憑證」→「建立憑證」→「OAuth 2.0 用戶端 ID」
6. 將核准的 JavaScript 來源設為你的網站網址
7. 複製用戶端 ID，貼入對應頁面的設定欄位

> Google Drive API 同樣有免費額度，教學情境下不會超用。

---

## 關於地圖功能

`travel-map.html`（人文踏查規劃）的地圖功能**並非使用 Google Maps API**。

Google Maps JavaScript API 需要綁定信用卡才能申請，且免費額度計算複雜，不適合直接用在教學工具上。因此改用 **[Leaflet.js](https://leafletjs.com/) + OpenStreetMap**，完全免費、不需要任何 API Key，功能足以支援踏查行程規劃的需求。

---

## 上課工具（不需 API）

以下頁面為純前端實作，不需要任何 API Key，開啟即可直接使用：

| 頁面 | 說明 |
|------|------|
| `ui-dashboard.html` | 指針儀表板，可接台股或感測器資料 |
| `css-cards.html` | CSS 卡片版型展示與教學 |
| `java-sim.html` | Bubble Sort 排序視覺化 |
| `js-science.html` | 重力井互動模擬 |
| `physics-lab.html` | 水平拋射拋物線實驗 |
| `markdown-viewer.html` | Markdown 即時預覽工具 |

---

## 注意事項

- API Key 請勿直接寫進程式碼後推送到公開 repo，建議使用輸入欄位讓使用者自行填入
- Gemini API Key 外洩可能導致額度被他人消耗，請妥善保管
- 本專案為教學用途設計

---

## 相關資源

- [Google AI Studio](https://aistudio.google.com/) — Gemini API 申請
- [Google Cloud Console](https://console.cloud.google.com/) — Google Drive API 設定
- [Gemini API 文件](https://ai.google.dev/docs)
- [Leaflet.js 文件](https://leafletjs.com/reference.html)
- [OpenStreetMap](https://www.openstreetmap.org/)
