# **git push 是什麼？**

`git push` 是用來把你本地的 Git commit 推送到遠端儲存庫（例如 GitHub）的指令。

當你在本地寫完程式並 `commit` 之後，這些更動只存在你的電腦。
你需要用 `git push` 把它們送到 GitHub 等平台，別人才能看到或合作。

---

## 🧱 基本語法

```bash
git push <遠端名稱> <分支名稱>
```

例如：

```bash
git push origin main
```

這行意思是：
把本地 `main` 分支的內容，推送到遠端 `origin` 的 `main` 分支。

---

## 🔹 最常見的範例指令

```bash
git push -u origin main
```

這是第一次推送時最常見的指令，`-u` 的意思是：
**以後就記住這個遠端與分支的關係**，之後你只要輸入 `git push`，Git 就會知道推去哪裡。

---

## 📌 常見選項解釋

* `git push`
  把當前分支的更新推送到預設的遠端分支（必須先用 `-u` 記住過）

* `git push origin main`
  明確指定要把 `main` 推送到 `origin`

* `git push -u origin main`
  推送並且建立 tracking（之後可直接用 `git push`）

* `git push --force` 或 `git push -f`
  **強制推送**（⚠️ 小心使用，會覆蓋遠端的歷史）

* `git push origin --delete <branch>`
  刪除遠端的某個分支（例：`git push origin --delete old-branch`）

---

## ❓常見問題

### Q: 為什麼會出現「rejected」錯誤？

A: 通常是因為遠端分支比你本地的更新，這時你要先：

```bash
git pull
```

取得最新遠端變更，合併後再 `push`。

---

### Q: 可以推送多個分支嗎？

A: 可以。例如：

```bash
git push origin dev
git push origin feature/login
```

---

### Q: 我可以推送到多個遠端嗎？

A: 可以。你可以這樣新增多個遠端：

```bash
git remote add backup https://github.com/yourname/backup.git
git push backup main
```

---

## 📘 你學到的關鍵概念

* `git commit` 是把更動記錄在你本地的 Git 裡
* `git push` 是把那些更動推送到遠端（像 GitHub）
* 搭配 `-u` 可以記住推送的目標，之後操作更方便

---