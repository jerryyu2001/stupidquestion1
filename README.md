# stupidquestion1.strnetwork.cc

靜態網站，由 GitHub Pages 部署，DNS 由 Cloudflare 代管。

## 怎麼更新網站

1. 把新的 HTML 內容存成 `index.html`（覆蓋舊的）
2. 執行：

```bash
git add -A
git commit -m "更新網頁內容"
git push
```

推上去後約 1–2 分鐘，https://stupidquestion1.strnetwork.cc 就會顯示新版本。
（瀏覽器如果還是舊的，用無痕視窗或強制重新整理 Cmd+Shift+R。）

## 檔案說明

| 檔案 | 用途 |
| --- | --- |
| `index.html` | 網站首頁，**要更新的就是這個檔** |
| `CNAME` | 告訴 GitHub Pages 自訂網域是什麼。**不要刪除或修改** |
| `.nojekyll` | 停用 Jekyll 處理，讓底線開頭的資料夾也能正常載入 |
| `.gitignore` | 排除不該上傳的檔案（金鑰、系統檔等） |

## 注意事項

- 這是 **public repo**，任何人都看得到。不要放金鑰、密碼、`.env`、內部未公開資料。
- 圖片、CSS、JS 等附加檔案直接放在同一層或子資料夾，用相對路徑引用即可。
- 如果要改子網域，需同時修改 `CNAME`、GitHub Pages 設定、以及 Cloudflare 的 DNS 記錄。
