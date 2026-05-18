# 更新日誌 — wicalyu.com

## 2026-05-18 — 界面優化 + 安全加固（諸葛統籌，UU spec / Lucy 方案）

- **Metadata schema 升級**：`PROJECTS` 每項改為 `{slug, title, desc, url, status, tags[], added}`。
- **狀態三態**：`live`(上線) / `wip`(整緊) / `archived`(已封存)；落架 = 直接由 array 移除（連 DNS 一齊清，防 subdomain takeover）。
- **渲染**：按 status 分組（live→wip→archived），組內 `added` 倒序；archived 組前加分隔 + 「封存」標。
- **三態 badge** = 色點 dot + 文字 label 雙編碼（唔淨靠顏色，色盲/灰階都分到）。
- **archived 降權唔靠 opacity**：標題 weight 500、hover 唔變 accent、scale(.99) — 多重訊號兼保 WCAG 對比。
- **a11y 補窿**：`:focus-visible` 焦點環、每卡 `aria-label`、dot/arrow `aria-hidden`、`prefers-reduced-motion` 關動效。
- **meta row**：tags（最多 3，`#` 前綴，最低 emphasis）+ added 靠右。
- **空態**：`PROJECTS` 為空顯置中提示（全 archived 唔算空）。
- **安全（Lucy T2-2）**：加 `<meta name="robots" content="noindex">`（unlisted）+ `referrer:no-referrer`。
- 維持 single-file、無 build、無外部依賴。node 模擬 DOM 12 項斷言全綠。
