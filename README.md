# 🌟 Git 教學專案 README

## 📌 介紹
這是一個簡單的 Git 教學專案，旨在幫助初學者熟悉 Git 的基本操作，包括 **初始化 Git、提交變更、分支管理、合併、衝突解決、遠端協作等**。本專案可用於個人練習或課堂演示。

---

## 📂 專案結構
```
├── README.md       # 專案說明文件
├── Git 指令表.md    # 指令參考文件
├── 測試檔案.txt     # 課堂上使用的檔案
└── 上課資料/        
    └── 版本開發與高效工作流-1.pptx # 簡報
```

---

## 🔧 安裝與設定
### **1️⃣ 安裝 Git**
請先確保你的電腦已安裝 Git。
- **Windows**：可從 [Git 官方網站](https://git-scm.com/) 下載安裝。
- **macOS** / **Linux**：可使用終端機安裝：
  ```sh
  sudo apt install git  # Ubuntu / Debian
  brew install git      # macOS
  ```

### **2️⃣ 初始化 Git 儲存庫**
```sh
git init
```
這會在專案目錄下建立 `.git/` 資料夾，讓該目錄變成 Git 儲存庫。

---

## 🚀 Git 基本操作

### **🔹 檢視 Git 狀態**
```sh
git status
```

### **🔹 追蹤檔案**
```sh
git add notes.txt
```

### **🔹 提交變更**
```sh
git commit -m "Initial commit"
```

### **🔹 建立並切換分支**
```sh
git checkout -b feature-branch
```

### **🔹 合併分支**
```sh
git checkout main
git merge feature-branch
```

### **🔹 推送到遠端倉庫**
```sh
git remote add origin <GitHub 倉庫 URL>
git push -u origin main
```

---

## ❌ Merge Conflict 解決
當 Git 無法自動合併變更時，可能會遇到 Merge Conflict。
### **🔹 解決衝突步驟**
1. **開啟衝突的檔案**，手動選擇要保留的變更。
2. **移除 Git 標記**（`<<<<<<<`, `=======`, `>>>>>>>`）。
3. **提交修正後的檔案**：
   ```sh
   git add notes.txt
   git commit -m "解決合併衝突"
   ```

---

## 🛠 .gitignore 使用
### **🔹 忽略特定檔案**
建立 `.gitignore` 並添加忽略的檔案類型：
```sh
echo "*.log" >> .gitignore
git rm -r --cached .gitignore
git commit -m "新增 .gitignore"
```

---

## 📖 更多 Git 指令
📌 你可以參考完整的 **[Git 指令對照表](./Git_指令表.md)**，獲得更詳細的 Git 指令說明。

📌 Git 官方文件：[Git 官方指南](https://git-scm.com/doc)


