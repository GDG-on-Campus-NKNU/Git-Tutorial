# Git 指令對照表（基礎版）

本文件為 Git 基礎指令對照表，涵蓋 Git 的初始化、提交變更、分支管理、合併、衝突解決與遠端協作等操作，適用於本次 Git 課程 (以有提及過的為主)。

---

## **📌 Git 初始化與基本操作**

### **1️⃣ 初始化 Git 專案**
```sh
git init
```
- 讓目前的資料夾變成 Git 儲存庫。

### **2️⃣ 檢查當前 Git 狀態**
```sh
git status
```
- 檢視哪些檔案被修改、尚未提交，或是未被追蹤。

### **3️⃣ 追蹤檔案**
```sh
git add <檔案名稱>
```
- 開始追蹤某個檔案。
- 追蹤所有變更：
  ```sh
  git add .
  ```

### **4️⃣ 提交變更**
```sh
git commit -m "提交訊息"
```
- 將已追蹤的變更提交至 Git。
- 若要一次 `add` + `commit` 可使用：
  ```sh
  git commit -am "提交訊息"
  ```
  （**注意**：這僅適用於已被追蹤的檔案）

---

## **📌 分支管理**

### **5️⃣ 建立新分支**
```sh
git branch <分支名稱>
```
- 建立新分支。

### **6️⃣ 切換分支**
```sh
git checkout <分支名稱>
```
- 切換至指定分支。

### **7️⃣ 建立並切換新分支**
```sh
git checkout -b <分支名稱>
```
- 建立新分支並立即切換過去。

### **8️⃣ 查看所有分支**
```sh
git branch
```
- 顯示目前所有本地分支。

### **9️⃣ 刪除分支**
```sh
git branch -d <分支名稱>
```
- 刪除已合併的分支。
- 若要強制刪除（即使未合併）：
  ```sh
  git branch -D <分支名稱>
  ```

---

## **📌 遠端倉庫與 GitHub 操作**

### **1️⃣2️⃣ 連結遠端倉庫**
```sh
git remote add origin <GitHub 倉庫 URL>
```
- 讓本地端 Git 儲存庫與 GitHub 遠端倉庫連結。

### **1️⃣3️⃣ 推送到遠端倉庫**
```sh
git push -u origin main
```
- 將 `main` 分支的變更推送到遠端倉庫。
- 若遇到推送錯誤，可強制推送：
  ```sh
  git push -f origin main
  ```
  （**⚠️ 注意**：`-f` 會覆蓋遠端歷史，請謹慎使用！）

### **1️⃣4️⃣ 拉取遠端變更**
```sh
git pull origin main
```
- 從 GitHub 倉庫下載最新變更。

### **1️⃣5️⃣ 複製遠端專案（Clone）**
```sh
git clone <GitHub 倉庫 URL>
```
- 下載遠端專案到本地端。

---

## **📌 其他常用 Git 指令**

### **1️⃣6️⃣ 查看 Git 提交歷史**
```sh
git log --oneline --graph
```
- 以簡潔方式顯示 commit 歷史。

### **1️⃣7️⃣ 比較兩個 commit 之間的變更**
```sh
git diff HEAD~1 HEAD
```
- 查看最近一次 commit 的變更。
- 在merge中用git diff可以直接比較來源和傳入。


## **📌 總結**
這份指令表涵蓋了 Git 的核心操作，包括：
✅ 初始化 Git 倉庫 (`init`)
✅ 基本版本控制 (`add`, `commit`, `status`)
✅ 分支管理 (`branch`, `checkout`, `merge`, `branch -D`)
✅ 遠端協作 (`push`, `pull`, `clone`, `push -f`)
✅ 解決 Merge Conflict (`merge`, `status`, `add`, `commit`)
✅ `.gitignore` 與清除快取 (`rm --cached`)
✅ 進階操作 (`reset`, `stash`, `diff`, `commit --amend`)

這份文件可以作為日常開發的參考手冊，希望能幫助你熟練 Git！🚀

