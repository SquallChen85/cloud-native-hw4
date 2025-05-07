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

aaa