# **git merge 是什麼？**

這是 Git 最重要的操作之一，幫助你把不同的分支合併起來。以下是 **`git merge` 的完整介紹**

---

## ✅ `git merge` 是什麼？

`git merge` 是用來**把另一個分支的更動合併到你目前所在的分支**。

例如：
你在 `main` 分支上，想把 `feature/login` 分支的內容合併進來，就會使用：

```bash
git merge feature/login
```

這樣你就把 `feature/login` 的更動套用到 `main` 上了。

---

## 📌 基本語法

```bash
git merge <分支名稱>
```

這會把 `<分支名稱>` 的內容合併到你目前所在的分支。

---

## 🧱 常見情境步驟

### 情境：你在 main 分支上，想合併另一個分支的更動

```bash
git switch main         ← 先切換到 main
git merge featureX      ← 把 featureX 的內容合進來
```

合併完成後，`main` 就會擁有 `featureX` 的更動。

---

## 🔄 合併類型（背後發生的事）

### 1. **Fast-forward（快轉合併）**

如果目前的分支沒有新的 commit，Git 會自動「快轉」到那個分支上，就像直接接上去一樣，沒有產生新的合併紀錄。

### 2. **Merge commit（真正合併）**

如果兩邊都有各自的 commit，Git 會自動產生一個「合併紀錄（merge commit）」，表示兩條歷史合併在一起了。

---

## ⚠️ 發生衝突怎麼辦？

如果兩邊更動了同一段程式碼，就會發生「衝突（conflict）」，Git 會叫你手動解決。

步驟如下：

1. Git 會標記衝突的地方，像這樣：

   ```
   <<<<<<< HEAD
   你目前分支的內容
   =======
   要合併進來分支的內容
   >>>>>>> featureX
   ```

2. 你要手動改成你要的版本。

3. 然後做 commit：

   ```bash
   git add .
   git commit
   ```

---

## 🔄 和 `rebase` 有什麼不同？

* `git merge` 保留兩條分支的歷史。
* `git rebase` 是把分支歷史「改寫」成一條線。

如果你想保留每個人的貢獻與時間軸，就用 `merge`
如果你想歷史乾淨清楚，就用 `rebase`（但比較危險一點）

---

## 📌 常見錯誤或提醒

* 你要先切到「你想合併到的分支」，再執行 `git merge`
* 合併會改變你目前的分支，請先 `commit` 或 `stash` 當前更動，以免 Git 不讓你合併
* 合併過後會產生一個新的 commit，除非是 fast-forward 合併

---

## 🧠 小總結

* `git merge` 把另一個分支合併到你目前的分支
* 沒有衝突時會自動完成，有衝突要手動解決
* 是團隊協作時很常用的指令，讓大家的工作匯集在一起
* 合併後記得 `push` 到 GitHub 分享給其他人

---

如果你正在開發一個新功能，可以開一個分支，開發完後用 `git merge` 把它合回 `main`。這就是專業開發的日常操作！
