# Git 用於 Minecraft

我幫你設計一個 **Minecraft 存檔 Git 管理方案**，讓你能用 Git 來管理遊戲世界，就像一個「版本控制的存檔系統」。

---

## 🚀 1. 初始化 Git 專案

假設你的世界在 `saves/first_world/`，進入該資料夾：

```bash
cd saves/first_world
git init
```

---

## 📝 2. 建立 `.gitignore`

Minecraft 世界資料夾裡其實有很多暫存檔（例如快取、日誌），完全沒必要放進 Git。
建議在 `first_world/` 內建立 `.gitignore`：

```gitignore
# 不需要的暫存檔
session.lock
*.log
*.tmp

# 玩家暫存資料（可選，通常不重要）
playerdata/
stats/

# 自動生成的快取
datapacks/
generated/

# 其他非必要檔案
*.bak
*.dat_old
```

這樣就只會追蹤「地圖檔案」和關鍵的 `level.dat`。

---

## 📦 3. 第一次提交

```bash
git add .
git commit -m "Initial commit: created first_world"
```

---

## 🎮 4. 建立遊玩流程

* 每到一個 **里程碑**（找到村莊、打敗Boss、蓋完城堡…）：

  ```bash
  git add .
  git commit -m "Day 10: found the village"
  ```
* 如果想測試不同發展，可以用 **branch**：

  ```bash
  git checkout -b no_death_run
  ```
* 如果想回到舊狀態：

  ```bash
  git checkout <commit_hash>
  ```

  （或是直接 reset，不過 checkout 比較安全）

---

## ☁️ 5. 跨電腦同步（可選）

想在不同電腦上繼續玩，可以推送到 GitHub / GitLab：

```bash
git remote add origin <your-repo-url>
git push -u origin main
```

⚠️ 建議搭配 **Git LFS**（處理大檔案）：

```bash
git lfs install
git lfs track "*.mca"
git add .gitattributes
git commit -m "Track Minecraft chunks with LFS"
```

---

## 📖 6. 最佳玩法（故事感）

* Commit message 當作「冒險日記」

  ```bash
  git commit -m "Day 15: built my first house"
  git commit -m "Day 40: defeated the Ender Dragon"
  git commit -m "Day 120: built Nether highway"
  ```
* `git log --oneline` 就能像看你的冒險歷史一樣。

甚至可以 `git tag` 重要事件：

```bash
git tag ender_dragon
```

然後隨時回去：

```bash
git checkout ender_dragon
```

---

✅ 結果就是：
你會得到一個 **可回溯、可分支、可分享的 Minecraft 存檔系統**，比遊戲內建存檔更有彈性，還能拿來講故事。

---
