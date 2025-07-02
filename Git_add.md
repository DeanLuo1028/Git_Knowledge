# **git add 是什麼？**

`git add` 是用來**將變更的檔案加入暫存區（staging area）** 的指令。

在 Git 中，提交（commit）前，檔案需要先被 `git add` 加入暫存區，這樣 Git 才知道哪些變更需要被提交。

---

## **`git add` 作用**

1. **告訴 Git 你要追蹤哪些檔案的變更**（新檔案、修改的檔案）。
2. **將檔案從「未追蹤（untracked）」或「已修改（modified）」狀態變成「已暫存（staged）」**。
3. **下一次執行 `git commit` 時，只有被 `git add` 過的檔案才會被提交**。

---

## **怎麼使用？**

### 1️⃣ **加入單個檔案**

```sh
git add filename
```

例如：

```sh
git add test.txt
```

這樣 `test.txt` 會被加入暫存區。

---

### 2️⃣ **加入多個檔案**

```sh
git add file1 file2 file3
```

例如：

```sh
git add test.txt example.py
```

這樣兩個檔案都會被加入暫存區。

---

### 3️⃣ **加入所有變更的檔案**

```sh
git add .
```

這個 `.` 代表「當前資料夾內的所有變更」，意思是：

* **所有新檔案**
* **所有修改過的檔案**
* **不包括已刪除的檔案（除非你用 `git rm`）**

---

### 4️⃣ **加入特定類型的檔案**

```sh
git add *.txt
```

這樣會加入所有 `.txt` 檔案，例如 `test.txt`、`notes.txt`。

---

## **`git add` 的流程**

Git 的版本控制有三個主要區域：

1. **工作區（Working Directory）** → 你實際修改檔案的地方。
2. **暫存區（Staging Area）** → 用 `git add` 加入這裡，準備提交。
3. **儲存庫（Repository）** → 用 `git commit` 提交變更，存入 Git。

這個流程通常是：

```sh
git add file        # 把檔案加入暫存區
git commit -m "描述提交的變更"  # 提交變更到 Git 儲存庫
```

---

## **如何查看哪些檔案被加入暫存區？**

使用：

```sh
git status
```

* **紅色**：檔案還沒 `git add`（未追蹤或已修改）。
* **綠色**：檔案已 `git add`，準備提交。

---

## **常見問題**

❓ **為什麼 `git commit` 時沒有變更？**
👉 因為你還沒 `git add`，Git 只提交被加入暫存區的檔案。

❓ **`git add .` 和 `git add -A` 有什麼不同？**

* `git add .` 只會加入 **當前資料夾內的變更**。
* `git add -A` 會加入 **所有變更（包含刪除的檔案）**。

---

**總結：**

* `git add` 是 **把變更加入暫存區**，讓 Git 知道哪些變更要提交。
* `git commit` 只會提交 **已 `git add` 過的檔案**。
* `git add .` 是最常用的指令，會加入當前資料夾內的所有變更。

你可以試試：

```sh
echo "Hello Git" > test.txt  # 建立一個新檔案
git status  # 會顯示 test.txt 未被追蹤
git add test.txt  # 加入 test.txt
git status  # 這時 test.txt 會變成綠色（已暫存）
git commit -m "新增 test.txt"  # 提交變更
```

這樣就完成了一次 Git 提交！ 🚀
