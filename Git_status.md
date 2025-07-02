# **git status 是什麼？**

`git status` 是用來**檢查目前 Git 儲存庫的狀態**的指令。

這個指令不會更改任何內容，它只是讓你知道目前有哪些檔案：

* **已修改但尚未 `git add`**
* **已 `git add` 但還沒 `git commit`**
* **未被 Git 追蹤的檔案**
* **目前所在的分支**
* **是否有需要推送（push）的變更**

---

## **`git status` 作用**

1. **確認哪些檔案已修改，哪些還沒被追蹤**
2. **檢查哪些檔案已 `git add` 但還沒 `git commit`**
3. **查看目前所在的分支**
4. **確認是否有尚未推送的變更**

---

## **怎麼使用？**

直接輸入：

```sh
git status
```

如果你剛初始化 Git (`git init`)，但還沒建立任何檔案，你可能會看到：

```
On branch master
No commits yet
nothing to commit (create/copy files and use "git add" to track)
```

這表示目前沒有可提交的內容。

---

### **狀態解釋**

假設你新增了一個檔案 `test.txt`，但還沒 `git add`，`git status` 可能會顯示：

```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.txt
```

這表示 `test.txt` 是未追蹤的（Git 目前不管理這個檔案）。

現在如果你執行：

```sh
git add test.txt
git status
```

你可能會看到：

```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.txt
```

這表示 `test.txt` 已經被 `git add`，但還沒 `git commit`。

最後，當你執行：

```sh
git commit -m "新增 test.txt"
git status
```

Git 會回應：

```
On branch master
nothing to commit, working tree clean
```

這表示 **所有變更都已提交，Git 版本庫是乾淨的**。

---

## **`git status` 的常見狀態**

### 1️⃣ **未追蹤的檔案（Untracked files）**

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test.txt
```

👉 這些檔案尚未被 Git 追蹤，需要 `git add`。

---

### 2️⃣ **已修改但未 `git add`**

```
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   test.txt
```

👉 這些檔案已修改但還沒 `git add`，所以 Git 還沒準備提交它們。

---

### 3️⃣ **已 `git add` 但尚未 `git commit`**

```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test.txt
```

👉 這些檔案已 `git add`，但還沒 `git commit`，你可以 `git commit -m "訊息"` 來提交。

---

### 4️⃣ **已提交但尚未推送**

```
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
```

👉 這表示你有新的提交，但還沒推送到遠端儲存庫（如 GitHub）。
執行 `git push` 來上傳變更。

---

## **總結**

* `git status` 是用來**檢查 Git 儲存庫的狀態**，但不會修改任何東西。
* 它可以幫助你了解：

  * 哪些檔案已修改但未 `git add`
  * 哪些檔案已 `git add` 但未 `git commit`
  * 目前是否有未推送的提交
  * 你所在的 Git 分支

這是一個 Git 初學者 **最常用** 的指令之一！ 🚀
