# **Git 中的 branch 是什麼？**

在 Git 中，**branch（分支）** 是一種**獨立開發的線路**，用來讓開發者在不影響主線 (`main` 或 `master`) 的情況下，進行新的功能開發或修正錯誤。

每個 `branch` 就像是時間軸上的一條獨立路線，讓開發者可以同時進行多項開發，最後再**合併 (`merge`)** 回主分支。

---

## **為什麼要使用 branch？**

1. **開發新功能**：你可以創建一個新的 `branch` 來開發功能，而不會影響原本的程式碼。
2. **修復 Bug**：當主分支 (`main`/`master`) 運作正常時，你可以建立一個 `bugfix` 分支來修正問題。
3. **多人協作**：不同開發者可以在不同 `branch` 上開發，最後合併，避免互相干擾。
4. **測試新想法**：如果你想嘗試新功能但不確定效果，可以開一個 `branch` 來測試。

---

## **Git 分支的基本指令**

1. **查看當前分支**

   ```bash
   git branch
   ```

   * 會顯示所有分支，`*` 代表目前所在的分支。

2. **建立新的分支**

   ```bash
   git branch 新分支名稱
   ```

   * 例如：`git branch feature-x` 會建立 `feature-x` 分支。

3. **切換到某個分支**

   ```bash
   git checkout 分支名稱
   ```

   * 例如：`git checkout feature-x` 會切換到 `feature-x` 分支。

   **(新版 Git 推薦使用 `git switch`)**

   ```bash
   git switch 分支名稱
   ```

4. **建立並切換到新分支**

   ```bash
   git checkout -b 新分支名稱
   ```

   或

   ```bash
   git switch -c 新分支名稱
   ```

5. **合併分支**

   * 切換到 `main`，然後合併 `feature-x`：

   ```bash
   git checkout main
   git merge feature-x
   ```

6. **刪除分支**

   ```bash
   git branch -d 分支名稱
   ```

   * 例如：`git branch -d feature-x` 會刪除 `feature-x`。

---

## **範例：使用 `branch` 進行開發**

假設你在開發一個新功能：

1. **創建並切換到新分支**

   ```bash
   git checkout -b feature-login
   ```
2. **寫程式、提交變更**

   ```bash
   git add .
   git commit -m "新增登入功能"
   ```
3. **回到主分支並合併**

   ```bash
   git checkout main
   git merge feature-login
   ```
4. **刪除已合併的分支**

   ```bash
   git branch -d feature-login
   ```

---

## **結論**

* `branch` 是 Git 用來支援**平行開發**的重要機制。
* 你可以透過 `branch` 開發新功能、修正錯誤，而不影響主程式碼。
* 最終可以使用 `merge` 把分支合併回主線。

這讓 Git 成為一個強大又靈活的版本控制系統！

---

# git switch 和 git checkout 差在哪？

`git switch` 和 `git checkout` 都可以用來切換分支，但 `git switch` 是 Git 2.23（2019 年）引入的新指令，目的是讓 Git 操作更直覺。兩者的主要差異如下：

## 1. **語意清楚**

* `git switch` 主要用來 **切換分支**，如果要創建新分支，也有明確的 `-c` 選項。
* `git checkout` 除了 **切換分支**，還能 **檢出特定的 commit 或檔案**，功能較雜。

## 2. **語法差異**

* **切換到已有的分支**

  ```sh
  git switch my-branch
  ```

  ```sh
  git checkout my-branch
  ```

* **創建並切換到新分支**

  ```sh
  git switch -c new-branch
  ```

  ```sh
  git checkout -b new-branch
  ```

* **還原檔案**

  ```sh
  git checkout -- file.txt  # 這是 git checkout 的功能，git switch 無法這樣做
  ```

## 3. **推薦使用**

Git 官方建議 **使用 `git switch` 來切換分支**，因為 `git checkout` 的用途太廣，可能導致誤解。例如：

* `git checkout my-branch` 可能讓人誤以為是「檢出某個 commit」而不是「切換分支」。
* `git switch` 更直觀地表達「切換分支」的概念。

## **結論**

* 如果你的 Git 版本是 **2.23 以上**，建議用 **`git switch`** 來切換分支，語法更清楚。
* 如果是 **舊版本 Git**（或還不熟悉 `git switch`），那就用 **`git checkout`**。
