# [`poteto`](https://x.com/poteto) 的 pstack 安裝手冊
[source](https://github.com/cursor/plugins/tree/main/pstack)

## 內容
### 1. pstack（作者：Lauren Tan @poteto，Cursor / React 核心工程師）：
- 專注於 SDLC 生命週期與驗證（Prove It Works）。
- 解決 AI Agent 缺乏系統化流程、不找根因就打 Monkey patch、宣稱「修好了」卻根本沒在終端跑過測試。
- 它的核心武器是 /poteto-mode 與完整的 Playbooks 庫。

### 2. ponytail（作者：Dietrich Gebert）：
- 專注於 代碼極簡主義（YAGNI & Anti-Boilerplate）。
- 它是獨立的開源準則，專門抑制初中階工程師與 AI 愛寫多層抽象、無用包裝類、廢話註解（如 # loop）的壞習慣。這不是 Lauren Tan 的專案範疇。

### 3. minimal-diff-reversibility：
- 專注於 Git Diff 與回滾安全性。
- 雖然 pstack 的 bug-fix 劇本裡有提到「最小修復」，但它沒有獨立的頂層規則來約束大規模格式重排與保障原子化原地可逆性。

### 4. in-your-own-words（作者：Austin Smith）：
- 先前看到的 mdsmithaustin/pstack 是 Austin Smith 個人的擴充工具箱，他將意圖回放門禁稱為 in-your-own-words。而 Cursor 官方倉庫的 cursor/plugins/pstack 採用的則是總調度器 /poteto-mode。

## 安裝流程
### 1. 確保全域插件目錄存在
```
mkdir -p ~/.gemini/config/plugins
```

### 2. 將插件 clone 至暫存並安裝（或直接 clone 到指定資料夾軟連結）
```
git clone git@github.com:kaierhyeh/antigravity-plugins.git /tmp/my-plugins
```

### 3. 使用 Antigravity CLI 一鍵全域安裝
```
~/.gemini/bin/agy plugin install /tmp/my-plugins/in-your-own-words
~/.gemini/bin/agy plugin install /tmp/my-plugins/minimal-diff-reversibility
~/.gemini/bin/agy plugin install /tmp/my-plugins/ponytail
~/.gemini/bin/agy plugin install /tmp/my-plugins/pstack
```

### 4. 清理暫存
```
rm -rf /tmp/my-plugins
```