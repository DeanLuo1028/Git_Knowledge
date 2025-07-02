# **修改GitHub 的 Default branch（預設分支）**

要修改 GitHub 上的 **Default branch（預設分支）**，請按照以下步驟操作：

## **方法 1：透過 GitHub 網頁設定**

1. **進入你的 GitHub Repository（倉庫）**

   * 例如：`https://github.com/你的帳號/你的倉庫`

2. **進入「Settings」**

   * 在倉庫的上方選單中，點擊 **「Settings」**。

3. **找到「Branches」設定**

   * 在左側的選單中，點擊 **「Branches」**。

4. **修改 Default branch**

   * 在 **「Default branch」** 區塊，點擊 `Change default branch` 按鈕。
   * 選擇你想要設為預設的分支，然後點擊 **Update**。

5. **確認變更**

   * 這樣你新的 Default branch 就生效了！

---

## **方法 2：透過 Git 指令修改 Default branch**

如果你想在本地端用 Git 修改分支名稱，然後同步到 GitHub，可以這樣做：

1. **切換到要設為預設的分支**

   ```sh
   git switch <新分支名稱>
   ```

2. **將新的分支推送到 GitHub**（如果該分支還沒推送過）

   ```sh
   git push -u origin <新分支名稱>
   ```

3. **進入 GitHub 設定 Default branch**（請參考「方法 1」步驟）

4. **刪除舊的 Default branch**（可選）
   如果你不再需要舊的分支，可以刪除它：

   ```sh
   git push origin --delete <舊的 Default branch 名稱>
   ```

這樣 Default branch 就成功修改了！ 🎉
