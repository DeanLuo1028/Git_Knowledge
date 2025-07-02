# **git commit 是什麼？**

`git commit` 是 Git 裡最核心、最重要的指令之一。以下是**完整但簡單易懂**的介紹：

---

## 🔹 什麼是 `git commit`？

`git commit` 的作用是：
👉 **把你暫存區（staging area）中的變更，正式記錄到 Git 的版本歷史中**。

你可以把它想像成：
📝「**儲存一次專案的快照**，並寫下這次修改的備註說明。」

---

## 🔹 `git commit` 的使用流程

Git 的典型使用步驟如下：

```bash
git add 檔案          # 將變更放進暫存區（staging area）
git commit -m "說明"  # 將暫存區的變更提交（commit）到歷史紀錄
```

這個流程可以重複無限次，每次都像是在專案歷史中寫下「這是我做了什麼改變」。

---

## 🔹 常見用法和選項

### ✅ 1. 基本用法：寫一段 commit message

```bash
git commit -m "新增登入頁面功能"
```

### ✅ 2. 自動加入修改的檔案（等同 `git add` + `commit` 一起做）

```bash
git commit -a -m "修正錯字"
```

這個只會包含**已經追蹤的檔案**，不包含新檔案（要先用 `git add` 加入）。

### ✅ 3. 修改最近一次的 commit 訊息

```bash
git commit --amend -m "修正訊息：登入頁面功能"
```

👉 通常用來修補剛剛 commit 的錯字或補漏的內容。

### ✅ 4. 使用預設編輯器輸入 commit message

```bash
git commit
```

Git 會開啟一個編輯器（通常是 Vim 或 VS Code），讓你輸入多行訊息。

---

## 🔹 commit message 的好習慣

建議 message 要簡潔明確，例如：

* ✅ `新增使用者註冊功能`
* ✅ `修正按鈕點擊無反應的問題`
* ❌ `Update`（太模糊）
* ❌ `1234`（完全沒意義）

---

## 🔹 額外技巧與補充

### 🔸 多行 commit message（更詳細說明）

```bash
git commit -m "新增報表匯出功能" -m "可匯出 CSV 及 PDF 格式，支援篩選條件"
```

### 🔸 查看 commit 記錄

```bash
git log
```

---

## 🧠 小知識：為什麼叫 commit？

英文中 `commit` 的意思是「承諾、提交」，在 Git 中就是：
👉「**我確認這些變更，請幫我記錄到版本歷史裡！**」

---