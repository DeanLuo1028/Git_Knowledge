# GitHub 中 repo 的 Public 和 Public archive 差在哪？

它們的差異其實是在 **repo 的「狀態」**，下面是簡單的說明：

---

## 🔹 Public（公開）

這是最常見的 repo 狀態，意思是：

* **任何人都可以看到這個 repo 的內容**
* 可以繼續更新、修改、提交程式碼
* 你或其他協作者都可以照常使用 Git 進行 `push`、`pull`、發 Pull Request、開 Issue 等操作

---

## 🔹 Public archive（公開封存）

這表示這個 repo 是「**公開的，但已封存（archived）**」，意思是：

* 內容還是**任何人都可以看到**
* 但：這個 repo **已經停止維護，不再更新**
* 所有人（包括擁有者）都無法：

  * `push` 新的 commit
  * 開新的 Issue 或 Pull Request
  * 編輯專案的任何東西（除非先取消封存）

封存一個 repo，通常是因為這個專案已經完成、過時、不再維護，或被其他東西取代了。

---

## ✅ 總結差異

| 狀態             | 誰可以看 | 是否能修改/更新 | 用途與情境說明           |
| -------------- | ---- | -------- | ----------------- |
| Public         | 所有人  | ✅ 可以     | 正常使用中的公開專案        |
| Public archive | 所有人  | ❌ 不可以    | 停止維護的專案，僅供參考或保存歷史 |

---

如果你看到某個 repo 是「Public archive」，代表：

* 這個專案雖然還看得到，但它已經「退役」了
* 通常不建議你 fork 它來用在新專案（因為不再更新）

---

你也可以在自己的 GitHub repo 頁面中進入：
`Settings → Danger Zone → Archive this repository` 來封存任何你想停用的 repo。

需要我教你怎麼封存或取消封存一個 repo 嗎？
