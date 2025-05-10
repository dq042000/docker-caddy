# docker-caddy

本專案使用 [Caddy](https://caddyserver.com/) 官方 Docker 映像，快速建構現代化網站伺服器，支援自動 HTTPS、靜態檔案服務與反向代理等功能。

## 目錄結構

```
.
├── Caddyfile.dist         # Caddy 預設設定檔範本
├── docker-compose.yml.dist # docker-compose 範本
├── caddy_config/          # Caddy 設定資料夾(持久化)
│   └── .gitkeep
├── caddy_data/            # Caddy 執行資料(持久化)
│   └── .gitkeep
├── site/                  # 網站靜態檔案目錄
│   └── .gitkeep
└── README.md              # 本說明文件
```

## 快速開始

1. 複製設定檔：

   ```sh
   cp Caddyfile.dist Caddyfile
   cp docker-compose.yml.dist docker-compose.yml
   ```

2. 編輯 `Caddyfile` 以設定你的網站網域、靜態目錄或反向代理規則。

3. 啟動服務：

   ```sh
   docker-compose up -d
   ```

4. 將你的網站檔案放到 site 目錄下。

## 設定說明

- `Caddyfile`：Caddy 的主要設定檔，可設定網站網域、靜態檔案路徑、反向代理等。
- `docker-compose.yml`：定義 Caddy 服務、網路、資料卷等。
- caddy\_data、caddy\_config：分別用於儲存 Caddy 的執行資料與設定，確保重啟後資料不遺失。
- site：放置要對外服務的靜態網站檔案。

## 常見指令

- 啟動服務：`docker-compose up -d`
- 停止服務：`docker-compose down`
- 查看日誌：`docker-compose logs -f`

## 參考資訊

- [Caddy 官方文件](https://caddyserver.com/docs/)
- [Caddy Docker Hub](https://hub.docker.com/_/caddy)

---

如需更進階設定，請參考 Caddy 官方文件。