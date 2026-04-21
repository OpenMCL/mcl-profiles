# MCL Profiles

一個用來練習 Git 基本操作的小專案。每個人建立自己的個人詳細介紹頁面，並在首頁加上自己的連結卡片。

核心目標：練習 Branch 操作、Commit 規範、Pull Request 流程，以及處理 Git 衝突 (Conflicts)。

## 快速開始

### Step 1：Clone 專案

```bash
git clone git@github.com:OpenMCL/mcl-profiles.git
cd mcl-profiles
```

### Step 2：開一個新的 branch

```bash
git checkout -b add/your-name
```

### Step 3：建立個人詳細介紹頁面

1. 複製模板：`cp profiles/template.html profiles/yourname.html`
2. 打開 `profiles/yourname.html`：
   - 修改頁面標題、名字、自我介紹。
   - 確保大頭照路徑正確（例如使用 DiceBear 或上傳照片至 assets/photos）。
   - 此頁面為個人介紹頁，可自由調整排版。

### Step 4：同步到首頁 index.html

1. 打開個人頁面檔案，參考內文結構。
2. 打開根目錄的 `index.html`。
3. 找到 `MEMBER_CARDS_START` 註解標記，將自己的卡片 HTML 貼在下方。
4. 修改卡片中的連結，確保其連向 `profiles/yourname.html`。

### Step 5：Commit 並 Push

```bash
git add .
git commit -m "feat: add yourname profile and card"
git push origin add/your-name
```

## 如何處理衝突 (Conflict Resolution)

當多名成員同時修改 index.html 的同一區塊時，會發生衝突。請依照以下步驟處理：

1. 在本地更新 main 分支：
   ```bash
   git checkout main
   git pull origin main
   ```
2. 回到個人分支並合併 main：
   ```bash
   git checkout add/your-name
   git merge main
   ```
3. 打開 index.html，手動決定要保留的內容（通常為保留他人的卡片並加上自己的內容）。
4. 存檔後提交：
   ```bash
   git add index.html
   git commit -m "fix: resolve conflict with main"
   git push origin add/your-name
   ```

## 檔案結構

```
mcl-profiles/
├── index.html              # 團隊首頁
├── styles.css              # 共用樣式
├── profiles/
│   ├── template.html       # 個人頁面模板
│   └── yourname.html       # 個人詳細介紹頁面
├── assets/photos/          # 大頭照存放目錄
└── README.md
```
