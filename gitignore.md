# **.gitignore是什麼？**

`.gitignore` 是 Git 用來**忽略你不想上傳到 Git 儲存庫的檔案或資料夾**的設定檔案。它的語法非常簡單明瞭，我這就為你說明。

---

## 📘 `.gitignore` 的基本語法：

| 語法                       | 意義                             |
| ------------------------ | ------------------------------ |
| `filename`               | 忽略某個檔案（如：`t.text`）             |
| `foldername/`            | 忽略某個資料夾（如：`build/`）            |
| `*.ext`                  | 忽略所有副檔名為 `.ext` 的檔案（如：`*.log`） |
| `!filename`              | **反向忽略**：強制追蹤某檔案，即使其他規則忽略了它    |
| `/filename` 或 `/folder/` | 僅在**專案根目錄**下忽略該檔案或資料夾          |
| `**/filename`            | 忽略任意子資料夾下的這個檔案                 |

---

## ✅ 範例：

### 1. 不要上傳 `t.text`

在 `.gitignore` 裡加上：

```
t.text
```

---

### 2. 不要上傳某個資料夾（假設叫做 `myfolder`）

```
myfolder/
```

如果你希望忽略所有叫做 `myfolder` 的資料夾（不管在哪層），可以加上：

```
**/myfolder/
```

---

## 📌 補充注意：

* `.gitignore` 只對**尚未被 Git 追蹤**的檔案有效。
* 如果某個檔案已經被 commit 過，再加進 `.gitignore` 不會生效，除非先用：

```bash
git rm --cached 檔案名
```

例如：

```bash
git rm --cached t.text
```

然後再 commit。

---

## 📌 `.gitignore` 的各種範例：

以下是幾個常見開發環境的 `.gitignore` 範例，你可以根據你開發的內容挑一個來使用，或做組合也行。

---

### 🐍 **Python 專案 `.gitignore` 範例**

```gitignore
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# VS Code 設定
.vscode/

# Virtual environment
venv/
.env/

# Jupyter Notebook checkpoints
.ipynb_checkpoints/

# macOS / Windows
.DS_Store
Thumbs.db
```

---

### 🌐 **Node.js 專案 `.gitignore` 範例**

```gitignore
# Node modules
node_modules/

# Log files
*.log

# Environment files
.env

# VS Code
.vscode/

# Build output
dist/
build/
```

---

### 🧰 **Visual Studio Code 專案 `.gitignore`（適合搭配其它語言）**

```gitignore
.vscode/
.history/
*.code-workspace
```

---

### ✨ 組合範例（Python + VS Code + 通用垃圾檔）

```gitignore
# Python
__pycache__/
*.py[cod]
*.pyc

# VS Code
.vscode/

# 虛擬環境
venv/
.env/

# macOS / Windows
.DS_Store
Thumbs.db

# Jupyter Notebook
.ipynb_checkpoints/
```

---
### ✅ `.gitignore` 範例：Java 專案
以下是一個適用於 **Java 專案** 的 `.gitignore` 範例，這個版本考慮了大多數 Java 開發環境（如 IntelliJ IDEA、Eclipse、VS Code），以及 Java 專案中常見的編譯產物。

---

```gitignore
# 忽略 Java 編譯產物
*.class

# 忽略 JAR / WAR / EAR
*.jar
*.war
*.ear

# 忽略日誌檔
*.log

# 忽略臨時檔
*.tmp
*.swp

# 忽略 IDE 設定檔

# IntelliJ IDEA
.idea/
*.iml
*.iws
out/

# Eclipse
.project
.classpath
.settings/
bin/

# VS Code
.vscode/

# Maven
target/

# Gradle
.gradle/
build/
!gradle/wrapper/gradle-wrapper.jar

# 忽略系統特定檔案
.DS_Store        # macOS
Thumbs.db        # Windows
```

---

### 補充說明：

* `.class` 是 Java 編譯後產生的檔案。
* `target/` 和 `build/` 是 Maven 和 Gradle 預設的輸出資料夾。
* `.idea/`、`.vscode/` 等是 IDE 的設定檔夾，跟程式碼無關。
* `*.jar` 等是打包後的可執行檔，通常也不需要加入版本控制。

