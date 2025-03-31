# Git 教學專案 README

## 📌 介紹
這是一個簡單但完整的 Git 教學專案，幫助初學者理解從基本操作到進階技巧，包括：版本回溯、歷史重寫、分支管理、Submodule 以及 Git Internals。

本專案搭配教學課程使用，包含一份 `notes.txt` 作為所有實作示範的基礎檔案。

---

## 📂 專案結構
```
├── README.md       # 專案說明文件
├── Git 指令表.md    # 指令參考文件
├── 測試檔案.txt     # 課堂上使用的檔案
└── 上課資料/        
    └── 版本開發與高效工作流 (全).pptx # 簡報
```

---

## 🔧 安裝與設定
### 1️⃣ 安裝 Git
前往 [Git 官方網站](https://git-scm.com/) 下載對應版本。

### 2️⃣ 初始化 Git 專案
```sh
git init
```
建立 Git 儲存庫。

---

## 🚀 教學操作流程（精華指令）

### 🔹 基本操作
```sh
git add .
git commit -m "初始 commit"
git branch -b feature/login
```

### 🔹 合併與整理歷史
```sh
git merge feature/login
# 或使用 rebase
git rebase main
```

### 🔹 回朔與錯誤處理
```sh
git reset --soft HEAD~1
git reflog
git revert <commit>
```

### 🔹 常用輔助指令
```sh
git commit --amend
git stash / git stash pop
git cherry-pick <commit>
git tag -a v1.0 -m "說明"
```

---

## 📦 Submodule 實作指令
```sh
git submodule add <repo-url> submodule-folder
git submodule init
git submodule update
```
重新 clone 時記得：
```sh
git submodule update --init --recursive
```

---

## 🧠 Git Internals：深入理解
```sh
echo "hi" > a.txt
git hash-object a.txt
git cat-file -t <SHA>
git cat-file -p <SHA>
git rev-parse HEAD
```
這些指令用來觀察 Git 的儲存結構，協助理解 commit、blob、tree 與 HEAD 的實際關係。

---

## 📖 延伸學習資源
- [Git 官網](https://git-scm.com/)

---

祝你成為真正能駕馭 Git 的全端開發者！🔥

