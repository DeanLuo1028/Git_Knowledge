# **在另一台電腦上使用Git和GitHub**

之前用Git都是在一台電腦上用的，然後有把一些之前就寫好的程式上傳到GitHub，你想要在其他電腦上修改那些程式，然後測試執行，該怎麼做？

你應該先在另一台電腦上安裝 Git。安裝完成後，請按照以下步驟操作：

1. **打開終端機（Terminal）或 Git Bash**
   在 Windows 上可以使用 Git Bash，在 macOS 和 Linux 上可直接使用終端機。

2. **設定 Git 使用者資訊（如果還沒設置過）**

   ```sh
   git config --global user.name "你的GitHub使用者名稱"
   git config --global user.email "你的GitHub電子郵件"
   ```

3. **從 GitHub 下載你的程式（clone repository）**
   使用 `git clone` 來下載你在 GitHub 上的程式碼：

   ```sh
   git clone https://github.com/你的GitHub帳號/你的倉庫名稱.git
   ```

   這會建立一個新的資料夾，裡面包含你上傳的程式。

4. **進入專案資料夾**

   ```sh
   cd 你的倉庫名稱
   ```

5. **檢查當前狀態（可選）**

   ```sh
   git status
   ```

6. **開始修改與測試**
   現在你可以在這台電腦上修改程式並測試執行。

7. **提交修改並推送回 GitHub**
   當你完成修改並測試後，可以使用以下指令將修改提交回 GitHub：

   ```sh
   git add .
   git commit -m "更新說明，例如：修正錯誤或新增功能"
   git push origin master  # 假設你是在 master 分支
   ```

這樣你的修改就會同步回 GitHub，之後如果要在原本的電腦上取得最新版本，則只需在那台電腦執行：

```sh
git pull origin master
```

這樣就能獲取最新的程式碼。
