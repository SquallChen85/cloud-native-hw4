# 2025cloud Docker Demo
---

## 🔧 如何 Build Docker 映像檔

請先進入本專案資料夾，執行以下指令來建立 image：

```bash
docker build -t 2025cloud-local .
```
這會建立一個local的image，接下來執行

```bash
docker run --rm 2025cloud-local
```
你應該會看到
```bash
Hello 2025cloud
```

---

## 🛠️ 自動產生 Docker Image 與 Tag 的設計說明

### 🔄 產生時機
每次當我將 main 分支更新時，GitHub Actions 會自動執行：
1. 透過 `docker build` 建立映像檔
2. 將其 `push` 到 Docker Hub 上的 `squallchen85/2025cloud` 專案

### 🏷️ Tag 選擇邏輯
- `v1`：我自己手動測試的版本，先在本地成功 build & run 過。
- `gh-action`：由 GitHub Actions 自動產生並上傳的 tag，方便區分是哪一次自動化流程上去的。
- `local`（例如 `2025cloud-local`）：我本地測試用的 tag，不會推送到 Docker Hub。

這樣的設計可以讓我清楚知道：
- 哪些是穩定版本（v1）
- 哪些是 CI 自動化產物（gh-action）
- 哪些是我開發測試中使用的版本（local）

---
