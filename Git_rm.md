# **git rm 是什麼？**

`git rm` 是 Git 中用來 **刪除版本控制中的檔案** 的指令。

簡單來說，它會：

1. 把指定的檔案 **從 Git 的追蹤（tracking）中移除**。
2. 並且（預設情況下）**從工作目錄中也刪除這個檔案**。

---

### 語法：

```bash
git rm 檔案名
```

### 範例：

```bash
git rm old_code.py
```

這會從 Git 追蹤中移除 `old_code.py`，而且會把實體檔案從資料夾中刪掉。

---

### 如果你只想從 Git 中移除，但保留實體檔案怎麼辦？

使用 `--cached` 選項：

```bash
git rm --cached notes.txt
```

這樣 Git 就不會再追蹤 `notes.txt`，但檔案會保留在你的資料夾中。

---

這常用在 `.gitignore` 之後：
你加入某個檔案到 `.gitignore`，但它之前已經被 Git 追蹤了，這時就用 `git rm --cached` 把它移除追蹤。
