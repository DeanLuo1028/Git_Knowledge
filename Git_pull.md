# **git pull 是什麼？**

`git pull` 是一個 Git 指令，**用來從遠端儲存庫（remote repository）獲取最新的更改，並將這些更改合併到你的本地分支（local branch）**。

---

## **基本語法**

```sh
git pull <遠端名稱> <分支名稱>
```

* **`<遠端名稱>`**：通常是 `origin`，代表你的 GitHub/GitLab 等遠端儲存庫。
* **`<分支名稱>`**：你要同步的分支，通常是 `main` 或 `master`。

如果你不加參數，Git 預設會拉取 **當前分支** 的變更：

```sh
git pull
```

這相當於：

```sh
git pull origin <當前分支>
```

---

## **`git pull` 做了什麼？**

1. **從遠端儲存庫下載最新的提交（commits）**

   * 這部分相當於 `git fetch`，但 `git pull` **不只是下載**，還會直接合併（merge）。
2. **將遠端變更合併到你的本地分支**

   * 如果本地和遠端都有新的變更，可能會產生**合併衝突（merge conflict）**，需要手動解決。

---

## **範例**

### **1. 簡單的 `git pull`**

```sh
git pull origin main
```

這會從 `origin` 這個遠端儲存庫的 `main` 分支拉取最新的變更，並合併到你的本地 `main` 分支。

### **2. `git pull` 發生衝突時**

如果你本地的 `main` 分支也有修改，而遠端的 `main` 也有新的變更，執行 `git pull` 可能會發生合併衝突，例如：

```sh
Auto-merging file.txt
CONFLICT (content): Merge conflict in file.txt
```

這時候你需要：

1. 手動編輯衝突的檔案，解決衝突。
2. 執行：

   ```sh
   git add .
   git commit -m "解決合併衝突"
   ```

---

## **`git pull` vs `git fetch`**

* `git pull` = `git fetch` + `git merge`
* **`git fetch`** 只是下載最新的變更，但不會自動合併，你可以手動檢查變更後再決定如何處理：

  ```sh
  git fetch origin
  git merge origin/main
  ```

  這種做法可以避免直接合併造成的衝突，適合**想要先確認變更後再決定如何合併**的情況。

---

## **結論**

* `git pull` 是用來**同步遠端最新的程式碼並合併到本地分支**。
* 可能會發生合併衝突，需要手動解決。
* 如果不確定是否要直接合併，建議使用 `git fetch` 來先檢查變更。
