# Git 指令對照表（基礎 + 進階版）

本文件為 Git 指令對照表，涵蓋 Git 的初始化、提交變更、分支管理、合併、版本回朔、歷史重寫、Submodule 與 Git Internals 等操作，適用於本次 Git 課程與進階應用。

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

- 提交追蹤變更。
- 若要一次 `add` + `commit`：
  ```sh
  git commit -am "提交訊息"
  ```

---

## **📌 分支管理**

### **5️⃣ 建立新分支**

```sh
git branch <分支名稱>
```

### **6️⃣ 切換分支**

```sh
git checkout <分支名稱>
```

### **7️⃣ 建立並切換新分支**

```sh
git checkout -b <分支名稱>
```

### **8️⃣ 查看所有分支**

```sh
git branch
```

### **9️⃣ 刪除分支**

```sh
git branch -d <分支名稱>
# 強制刪除：
git branch -D <分支名稱>
```

---

## **📌 遠端操作與 GitHub**

### **🔟 連結遠端倉庫**

```sh
git remote add origin <URL>
```

### **1️⃣1️⃣ 推送分支**

```sh
git push -u origin main
# 強制推送：
git push -f origin main
```

### **1️⃣2️⃣ 拉取與複製專案**

```sh
git pull origin main
git clone <URL>
```

---

## **📌 提交歷史與版本控制**

### **1️⃣3️⃣ 修改上一筆 commit**

```sh
git commit --amend
```

### **1️⃣4️⃣ 快速暫存 / 回復暫存內容**

```sh
git stash
git stash pop
```

### **1️⃣5️⃣ 版本回朔（Reset）**

```sh
git reset --soft HEAD~1
# 清除暫存：
git reset --mixed HEAD~1
# 全部清除（⚠️危險）：
git reset --hard HEAD~1
```

### **1️⃣6️⃣ 找回歷史（Reflog）**

```sh
git reflog
git reset --hard HEAD@{n}
```

### **1️⃣7️⃣ 安全回退（Revert）**

```sh
git revert <commit-hash>
```

---

## **📌 Rebase 與整合歷史**

### **1️⃣8️⃣ 重整歷史（Rebase）**

```sh
git rebase <分支>
# 互動式：
git rebase -i HEAD~n
```

### **1️⃣9️⃣ Rebase 衝突處理**

```sh
git add .
git rebase --continue
# 中止：
git rebase --abort
```

---

## **📌 補充實用指令**

### **2️⃣0️⃣ 選擇性套用 commit**

```sh
git cherry-pick <commit>
```

### **2️⃣1️⃣ 建立 / 推送 Tag**

```sh
git tag -a v1.0 -m "說明"
git push origin --tags
```

### **2️⃣2️⃣ 比較差異 / 檢視歷史**

```sh
git diff HEAD~1 HEAD
git log --oneline --graph
```

---

## **📌 Submodule 管理**

### **2️⃣3️⃣ 加入 Submodule**

```sh
git submodule add <repo-url> <資料夾>
```

### **2️⃣4️⃣ 初始化與更新**

```sh
git submodule init
git submodule update
# clone 後一行完成：
git submodule update --init --recursive
```

### **2️⃣5️⃣ 更新 submodule 並提交**

```sh
cd submodule
<修改內容>
git commit -am "更動"
cd ..
git add submodule
git commit -m "更新 submodule commit"
```

---

## **📌 Git Internals 常用工具**

### **2️⃣6️⃣ 內容轉 blob 與檢視物件**

```sh
echo "Hello" > a.txt
git hash-object a.txt
git cat-file -t <SHA>
git cat-file -p <SHA>
```

### **2️⃣7️⃣ HEAD 與 SHA 查詢**

```sh
git rev-parse HEAD
```

---