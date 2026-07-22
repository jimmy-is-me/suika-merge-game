# 🍹 Suika Merge Game

HTML5 + Matter.js 製作的「掉落合併」遊戲，靈感來自 Suika Game / Juice Merge。  
**完全客製化**：換一份你自己的圖片就能改成任何主題。

---

## 📁 檔案結構

```
suika-merge-game/
├── index.html          ← 遊戲主檔，直接用瀏覽器打開就能跑
├── README.md           ← 說明文件
└── assets/
    └── images/
        ├── item-1.png  ← 等級 1（最小，建議 200×200px 以上圓形 PNG）
        ├── item-2.png  ← 等級 2
        ├── item-3.png  ← 等級 3
        ├── item-4.png  ← 等級 4
        └── item-5.png  ← 等級 5（最大）
```

---

## 🖼️ 圖片規格建議

| 項目 | 建議 |
|---|---|
| 尺寸 | **200×200px 以上**，正方形 |
| 格式 | **PNG（建議帶透明背景）** |
| 形狀 | 接近圓形，外圍留透明區域 |
| 命名 | `item-1.png` 到 `item-5.png` |
| 放置位置 | `assets/images/` 資料夾 |

> 💡 圖片不一定要是圓形，但如果是方形圖，碰撞時的視覺效果會比圓形稍差。  
> 建議把你的圖片裁成圓形或橢圓形，透明背景 PNG。

---

## ▶️ 本地執行方式

### 方法 1：直接開啟（最簡單）
```
直接雙擊 index.html，用 Chrome 或 Firefox 打開即可。
```

### 方法 2：本地伺服器（推薦，圖片路徑更穩）
```bash
# 如果你有 Python
python -m http.server 8080

# 然後瀏覽器打開
http://localhost:8080
```

---

## ✏️ 修改素材方式

打開 `index.html`，找到下方這段 `ITEMS` 陣列（約第 60 行），修改 `image`、`radius`、`score` 即可：

```js
const ITEMS = [
  { level: 0, radius: 22, score: 10, image: './assets/images/item-1.png' },
  { level: 1, radius: 30, score: 20, image: './assets/images/item-2.png' },
  { level: 2, radius: 40, score: 40, image: './assets/images/item-3.png' },
  { level: 3, radius: 52, score: 80, image: './assets/images/item-4.png' },
  { level: 4, radius: 66, score: 160, image: './assets/images/item-5.png' }
];
```

| 欄位 | 說明 |
|---|---|
| `level` | 等級編號，不需改 |
| `radius` | 碰撞半徑（px），決定物件大小，建議等比例遞增 |
| `score` | 合併時得分 |
| `image` | 圖片路徑，相對於 `index.html` |

---

## 🕹️ 操作方式

| 裝置 | 操作 |
|---|---|
| 桌機 | 滑鼠左右移動決定落點，**點擊**投放 |
| 手機 | 左右滑動決定落點，**點一下**投放 |

---

## 📦 技術棧

- **Matter.js 0.20** — 2D 物理引擎（CDN，不需安裝）
- 純 HTML + CSS + JavaScript，無任何框架依賴
- 支援桌機與手機觸控

---

## 🌐 GitHub Pages 部署

如果你想讓別人線上玩：

1. 到 GitHub Repo → **Settings → Pages**
2. Source 選 `main` branch，folder 選 `/ (root)`
3. 儲存後會生成網址：`https://jimmy-is-me.github.io/suika-merge-game/`
