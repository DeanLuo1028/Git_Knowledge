# **cd 是什麼？**

`cd` 其實不是 Git 的指令，而是**命令提示字元（Command Prompt）或 Bash（如 Git Bash）**的指令，用來**變更目前所在的資料夾（目錄）**。

## 用法

```sh
cd <資料夾名稱>
```

👉 切換到指定的資料夾。

```sh
cd ..
```

👉 回到上一層資料夾。

```sh
cd /
```

👉 回到根目錄（C: 或 /）。

```sh
cd ~
```

👉 回到使用者的主目錄（Windows 上通常是 `C:\Users\你的帳號`）。

---

## 舉例

假設你在 `C:\Users\jeff6\Desktop\`，然後你要進入 `test` 資料夾：

```sh
cd test
```

現在你的位置變成 `C:\Users\jeff6\Desktop\test`。

如果你想回到 `Desktop`：

```sh
cd ..
```

## 結論

`cd` 是**變更目錄的指令**，和 Git 本身無關，只是因為 Git 需要在某個資料夾中執行，所以你會在 Git Bash 或命令提示字元中用到它！ 🚀
