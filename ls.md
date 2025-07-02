# **ls 是什麼？**

`ls` 是一個**列出目錄內容的指令**，可以用來查看目前資料夾（目錄）內有哪些檔案和資料夾。

---

## **基本用法**

```sh
ls
```

👉 列出目前資料夾中的所有檔案和資料夾。

```sh
ls -l
```

👉 顯示詳細資訊（如權限、擁有者、大小、修改時間）。

```sh
ls -a
```

👉 顯示**所有檔案**，包括隱藏檔（以 `.` 開頭的檔案，如 `.git`）。

```sh
ls -lh
```

👉 以**可讀性較高的方式**顯示檔案大小（如 KB、MB）。

---

## **舉例**

如果你在 Git Bash 中輸入：

```sh
ls
```

可能會得到：

```
test.txt  test2.txt  my_folder
```

表示目前資料夾中有兩個檔案 `test.txt`、`test2.txt`，還有一個資料夾 `my_folder`。

如果輸入：

```sh
ls -l
```

可能會顯示：

```
-rw-r--r--  1 jeff6  staff  1234 Apr 7 10:30 test.txt
-rw-r--r--  1 jeff6  staff  5678 Apr 7 10:32 test2.txt
drwxr-xr-x  5 jeff6  staff  4096 Apr 7 10:35 my_folder
```

這裡顯示了：

* 檔案權限 (`-rw-r--r--`)
* 擁有者 (`jeff6`)
* 檔案大小 (`1234` bytes)
* 最後修改時間 (`Apr 7 10:30`)
* 檔案名稱 (`test.txt`)

---

## **Windows 的對應指令**

如果你用的是 **Windows 命令提示字元（cmd）**，`ls` 可能無法使用（除非你用的是 Git Bash 或 WSL）。Windows 上對應的指令是：

```sh
dir
```

它的作用和 `ls` 類似，會列出目前資料夾中的內容。

---

## **結論**

`ls` 是查看當前資料夾內容的指令，在 **Git Bash、Linux、macOS** 都能用，但 Windows 的命令提示字元要用 `dir` 代替！ 🚀
