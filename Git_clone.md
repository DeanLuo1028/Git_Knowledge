# **git clone 是什麼？**

`git clone` 是 Git 中用來\*\*複製遠端儲存庫（repository）\*\*到本地端的指令。

---

## **基本語法**

```sh
git clone <遠端儲存庫網址>
```

這會將指定的 Git 儲存庫完整下載到你的電腦上，包括所有的程式碼、歷史紀錄、分支等。

---

## **範例**

如果你要複製 GitHub 上的某個專案，例如：

```sh
git clone https://github.com/DeanLuo1028/test.git
```

這會執行以下動作：

1. 下載 `test` 這個 Git 儲存庫的完整內容。
2. 在你的電腦中建立一個 `test` 目錄。
3. 把該儲存庫的 Git 歷史紀錄也下載下來。

如果成功，終端機可能會顯示：

```
Cloning into 'test'...
remote: Enumerating objects: 10, done.
remote: Counting objects: 100% (10/10), done.
remote: Compressing objects: 100% (5/5), done.
Receiving objects: 100% (10/10), done.
```

這表示 Git 已成功下載該專案。

---

## **克隆到指定資料夾**

如果你不想讓 Git 自動用專案名稱建立資料夾，可以指定資料夾名稱：

```sh
git clone https://github.com/DeanLuo1028/test.git my_project
```

這會把 `test` 儲存庫下載到 `my_project` 這個資料夾內，而不是 `test`。

---

## **克隆特定分支**

如果你只想下載特定分支，而不是整個專案，使用 `-b`（branch）：

```sh
git clone -b dev https://github.com/DeanLuo1028/test.git
```

這只會下載 `dev` 分支的內容，而不會下載其他分支。

---

## **與 `git pull` 的區別**

| 指令          | 作用                         |
| ----------- | -------------------------- |
| `git clone` | **第一次** 下載整個專案（含 Git 歷史紀錄） |
| `git pull`  | **已經有專案時**，更新最新的變更         |

如果你第一次使用 Git，或是要取得別人的專案，應該用 **`git clone`**。
如果你已經有專案了，想要取得最新的變更，應該用 **`git pull`**。

---

## **總結**

* `git clone` 是用來**從遠端儲存庫下載專案**。
* 下載的內容包含所有的程式碼、歷史紀錄與分支。
* 可以用 `git clone -b <分支名稱>` 來克隆特定分支。
* `git clone` 主要用在第一次下載專案，而 `git pull` 則用來更新已下載的專案。
