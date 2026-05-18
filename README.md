# wicalyu.com

`wicalyu.com` 嘅個人主頁 — 一啲一次性、非產品嘅小工具同手帳嘅入口。

## 架構

- 單檔 `index.html`，無 build、無 dependency。
- `CNAME` = `wicalyu.com`（GitHub Pages apex 自訂 domain）。
- 各 misc project 各自一個 repo + subdomain（`<name>.wicalyu.com`）。

## 加新項目

1. 喺 `index.html` 嘅 `PROJECTS` array 加一個 object（`status: "live" | "soon"`）。
2. 嗰個 project repo 入面加 `CNAME` = `<name>.wicalyu.com`，GitHub Pages 設 custom domain。
3. GoDaddy DNS 加 `CNAME  <name> → wical112.github.io`，等傳開後剔 Enforce HTTPS。

## 部署（GitHub Pages，apex domain）

GoDaddy DNS：

```
A      @     185.199.108.153
A      @     185.199.109.153
A      @     185.199.110.153
A      @     185.199.111.153
CNAME  www   wical112.github.io
```

GitHub repo → Settings → Pages → custom domain `wicalyu.com` → 等 DNS 傳開後剔 Enforce HTTPS。
