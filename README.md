# Tako CHANG — mypage

個人作品集網站，同時收錄網頁前端課堂練習成果。

## 專案結構

```
mypage/
├── index.html                         # 個人作品集首頁
├── 20260205-ch05-table_opendata.html  # Ch05｜響應式表格 × 開放資料 API
├── 20260210-ch6_practice2.html        # Ch06｜Bootstrap 切版練習
├── 20260212-1.html                    # Ch06 延伸｜地方美食卡片列表
├── 20260305-ch11-practice.html        # Ch11｜表單驗證與 AJAX 送出
├── SPA.html                           # 綜合｜WonderLand 單頁網站
├── 20260417-SPA-API.html              # 綜合｜派對公司 SPA × Axios API 串接
├── 20260423-SPA-API-controlPanel.html # 綜合｜派對公司後台控制台
├── 20260428-OSM.html                  # OSM 地圖 × 旅遊資料標記
├── 20260428-OSM-hotel.html            # OSM 地圖 × 觀光署旅館資料 × Marker Cluster
├── css/
│   ├── bootstrap.min.css
│   ├── mycss02.css                    # 自訂 cork 色票變數與通用樣式
│   └── table-rwd.css
├── js/
│   ├── bootstrap.bundle.min.js
│   ├── jquery-4.0.0.js
│   ├── travelData.js
│   └── json/
│       └── ODwsvTravelFood.json
└── images/
```

## 頁面說明

### index.html — 個人作品集首頁

個人介紹頁面，包含技術能力、作品集連結與聯絡方式。

- **Hero**：姓名、職稱（Full Stack Developer）與個人簡介
- **Skills**：前端（HTML/CSS/JS、React、Bootstrap）、後端（Node.js、Python、RESTful API）、資料庫（MySQL）、工具（Git、GitHub、Sourcetree）
- **Portfolio**：連結至下方四個課堂練習作品
- **Contact**：GitHub、LinkedIn 連結

---

### 20260205-ch05-table_opendata.html — 響應式表格 × 開放資料

**章節：Ch05 表格**

使用 jQuery AJAX 呼叫農業部開放資料 API，動態產生地方美食店家列表。

- RWD 響應式表格：桌面版顯示完整欄位，手機版轉為區塊堆疊並以 `data-th` 顯示欄位標題
- 串接 API：`data.moa.gov.tw` 農業部旅遊美食資料
- 欄位：店家名稱、圖片、地址、聯絡電話、食物特色
- 樣式：Playfair Display 字型、漸層表頭、斑馬紋列、hover 圖片縮放、fadeUp 入場動畫

---

### 20260210-ch6_practice2.html — Bootstrap 切版練習

**章節：Ch06 Grid 切版**

練習 Bootstrap Grid 系統進行 RWD 版面配置。

- Hero Banner（md 以上才顯示）
- 4 欄選單按鈕（sm:2欄 / md:4欄），hover 有彈跳與陰影效果
- 6 張飲品卡片（md:2欄 / lg:3欄），套用 `roller-r / roller-l / roller-t / roller-b` 滑入遮罩效果

---

### 20260212-1.html — 地方美食卡片列表

**章節：Ch06 延伸 × AJAX 本地 JSON**

讀取本地 JSON 檔案，以卡片 Grid 動態渲染地方美食店家資料。

- 以 `$.ajax` GET 讀取 `js/json/ODwsvTravelFood.json`
- 響應式卡片排版（md:2 / lg:3 / xl:4 欄）
- 每張卡片含封面圖、店家名稱、電話、地址、簡介
- 套用 `roller-r` 滑入覆蓋按鈕效果

---

### 20260305-ch11-practice.html — 飲料訂購表單

**章節：Ch11 表單驗證**

完整的飲料訂購表單，包含前端驗證與 AJAX 送出。

- **輸入欄位**：訂購者名稱（floating label）、產品名稱（datalist 建議選項）、冰塊、甜度、配料（checkbox）、數量（range slider）、備註
- **即時計算**：勾選配料與調整數量時即時更新單價與總價
- **驗證規則**：名稱 2–5 字、產品名稱 2–6 字、冰塊甜度必選，以 Bootstrap `is-valid / is-invalid` 視覺回饋
- **送出**：驗證通過後顯示訂單明細，並以 `$.ajax POST` 送至 `http://localhost:3000/orders`

---

### SPA.html — WonderLand 奇幻樂園（單頁網站）

**綜合練習：SPA 切版 × Modal × SweetAlert2 驗證**

以遊樂園主題製作的單頁網站，整合多個前端技術。

- **s01**：社群連結列（Facebook、LINE、Instagram、YouTube）
- **s02**：響應式 Navbar，含 Dropdown 票價選單、登入 / 註冊按鈕
- **s03**：全螢幕 Hero，Parallax 背景圖、CTA 按鈕
- **s04**：遊樂設施介紹卡片（雷霆雲霄、星光摩天輪、夢幻旋轉木馬）
- **s05**：三種票價方案（兒童票 / 成人票 / 家庭套票）
- **s06**：近期活動公告列表
- **s07**：開放時間與聯絡資訊（Parallax 背景、毛玻璃卡片）
- **登入 / 註冊 Modal**：以 localStorage 儲存使用者，SweetAlert2 提供完整驗證提示（格式、長度、重複帳號）

---

### 20260428-OSM.html — OSM 地圖 × 旅遊資料標記

**綜合練習：Leaflet.js × OpenStreetMap × 農業部旅遊資料**

以 Leaflet.js 整合 OpenStreetMap 地圖，將農業部旅遊美食資料標記於地圖上。

- 使用 Leaflet.js 建立全螢幕互動式地圖，以台灣中心座標初始化
- 讀取 `travelData.js` 旅遊資料，過濾無座標項目後以 `L.marker` 逐筆標記
- 每個標記點開啟 Popup，內含店家圖片、名稱、地址（縣市＋鄉鎮＋地址）、電話與官網連結
- 底圖：OpenStreetMap 標準磚塊圖層

---

### 20260417-SPA-API.html — 派對公司官方網站

**綜合練習：SPA × Axios × 後端 API 串接**

以派對公司為主題製作的多頁段單頁網站，整合 Axios 串接後端 RESTful API。

- **s01**：社群連結列（Facebook、LINE、X）
- **s02**：響應式 Navbar，含服務項目 Dropdown、登入 / 註冊按鈕、登入後顯示會員名與「後台管理」連結
- **s03**：全幅 Carousel 幻燈片（WOW.js bounceInLeft 入場動畫），含企業活動方案文字說明
- **s05**：時間軸（Timeline）版型介紹公司沿革
- **s08**：團隊成員卡片，hover 圓角＋縮放動畫
- **登入 / 註冊**：以 `axios.post` 串接 `http://127.0.0.1:5000/api/register` 與 `/api/login`；`/api/me` 驗證 Token 並還原登入狀態；SweetAlert2 提供驗證提示
- **後台連結**：登入後顯示「後台管理」按鈕，導向 `20260423-SPA-API-controlPanel.html`

---

### 20260423-SPA-API-controlPanel.html — 後台控制台

**綜合練習：後台管理介面**

派對公司網站的後台管理頁面，搭配 `20260417-SPA-API.html` 使用。

- 獨立頁面，Navbar 含「首頁」連結返回前台
- 登入 / 註冊 Modal，以 Axios + SweetAlert2 處理驗證
- 使用 `counterup2` 數字滾動計數效果

---

### 20260428-OSM-hotel.html — OSM 地圖 × 觀光署旅館資料 × Marker Cluster

**綜合練習：Leaflet.js × MarkerCluster × 觀光署旅館 JSON**

以 Leaflet.js 整合 OpenStreetMap 地圖，載入觀光署旅館資料並以叢集（Cluster）方式呈現。

- 使用 Leaflet.js 建立全螢幕地圖，初始化座標置於台灣中部
- 以 Axios 讀取 `js/json/HotelList.json`，透過 `normalize()` 函式標準化欄位（名稱、地址、電話、圖片、座標、官網）
- 過濾無圖片或無座標資料後，以 `leaflet.markercluster` 外掛合併標記，減少大量 Marker 的視覺雜亂
- 叢集分三級（small / medium / large）以不同顏色區分；每個標記點 Popup 含旅館圖片、名稱、地址、電話與官網連結

## 技術

| 類別 | 使用技術 |
|---|---|
| 版面 | Bootstrap 5、自訂 CSS（cork 色票）|
| 互動 | jQuery 4、原生 JS |
| 資料 | AJAX（遠端 API / 本地 JSON）、Axios |
| 地圖 | Leaflet.js × OpenStreetMap、Leaflet.MarkerCluster |
| 驗證 | Bootstrap Validation、SweetAlert2 |
| 動畫 | WOW.js × Animate.css、CounterUp2 |
| 字型 | Google Fonts（Noto Serif TC、Playfair Display、Noto Sans TC）|
