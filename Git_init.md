# **git init 是什麼？**

`git init` 是用來**初始化 Git 儲存庫（repository）**的指令。

當你在一個資料夾內執行 `git init`，Git 會在該資料夾建立一個隱藏的 `.git` 目錄，這個目錄是 Git 用來管理版本控制的地方。

---

## **`git init` 作用**

1. **讓資料夾變成 Git 儲存庫**（開始使用 Git 追蹤這個資料夾的變更）。
2. **建立 `.git` 資料夾**（裡面包含 Git 需要的設定、歷史紀錄等）。
3. **不會影響原本的檔案**，只是新增 Git 版本控制的功能。

---

## **怎麼使用？**

假設你有一個新專案，想要用 Git 來管理它：

```sh
mkdir my_project      # 建立一個新資料夾
cd my_project         # 進入這個資料夾
git init              # 初始化 Git 儲存庫
```

初始化成功後，你可以輸入：

```sh
ls -a
```

會發現 `.git` 這個隱藏資料夾，這表示 Git 儲存庫已經建立。

---

## **如何確認目前資料夾是否已經是 Git 儲存庫？**

你可以執行：

```sh
git status
```

如果 Git 回應：

```
fatal: not a git repository (or any of the parent directories): .git
```

表示這個資料夾還不是 Git 儲存庫，你需要先執行 `git init`。

如果 `git status` 正常顯示分支狀態，表示這個資料夾已經是 Git 儲存庫了。

---

## **`git init` 什麼時候要用？**

* **建立新專案** 時，第一次初始化 Git。
* **已存在的專案但還沒用 Git**，想開始使用 Git 來管理版本時。
* **如果 `.git` 目錄不小心刪除**，想要重新初始化 Git 儲存庫。

---

## **注意**

* `git init` **不會刪除你的檔案**，但會讓該資料夾開始使用 Git 來追蹤變更。
* `git init` 只需要執行一次，之後這個資料夾就會一直是 Git 儲存庫，直到你手動刪除 `.git` 資料夾。
