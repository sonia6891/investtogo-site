# 投資袋著走 官網

投資袋著走（App 內與商店名稱「ETF 袋著走」）的介紹網頁。這是 Pocket Joy Studio 的產品，預計用 GitHub Pages 公開在 https://investtogo.pocketjoystudio.com/ （`CNAME` 檔不要刪）。這個 repo 只放網頁檔案（HTML、CSS、圖片），沒有 App 的程式。

| 網址 | 內容 |
|---|---|
| `/` | 首頁（只有繁體中文，App 只有 zh-Hant） |
| `/privacy/` | 隱私權政策（原本在 `https://sonia6891.github.io/etftogo/privacy`） |
| `/support/` | 支援與常見問題（原本在 `https://sonia6891.github.io/etftogo/support/`） |

- 樣式都在 `assets/style.css`，顏色取自 App 的「黑金」外觀主題（`PocketCore/Sources/PocketCore/Resources/skins.json`）；沒有外部字型、沒有追蹤碼、不需要 build。
- 截圖是 App repo `marketing/appstore/` 的商店圖縮小成 600 寬 JPEG；圖示是 `App/Assets.xcassets/Skins/blackgold/` 的 3D 圖。商店圖換新時這裡也要換。
- 隱私權政策、支援頁的文字是從 `sonia6891/etftogo` repo 原封不動搬過來的（2026-11-14 版），只換了外框樣式。要改政策內容時，App 裡的隱私權連結（`App/Membership/MemberView.swift` 的 `MemberView.privacy`）和商店說明的網址也要一起改成這裡。
- 使用條款用 Apple 標準許可協議（和支援頁、商店說明一致）。聯絡管道是 GitHub 問題回報頁。

## 數字從哪裡來

| 網頁上的數字 | 來源 |
|---|---|
| 口袋會員 NT$120／月 | App repo `App/Membership/MemberView.swift:21`（`PlanPrice.demoStore`，註解寫是 App Store Connect 台灣的價格）；Android 設計文件 `docs/superpowers/specs/2026-11-22-android-app-design.md` A3 也確認月費 NT$120 |
| 四套外觀主題（黑金、像素、縫線、手繪） | `PocketCore/Sources/PocketCore/Resources/skins.json`、`marketing/listing/description.txt` |
| 會員七項功能 | `PocketCore/Sources/PocketCore/Models/MemberFeature.swift`、`marketing/listing/description.txt` |

年費（Android 文件提到 NT$1,190）iPhone 版還沒有賣，所以網頁沒寫。App 改價或加年費時，這裡要一起改。

## App 上架後要改的地方

- `index.html` 裡兩組商店按鈕（首屏和最下面）：`class="store soon"` 改成 `class="store"`，拿掉 `aria-disabled="true"` 和 `<span class="tag">即將上架</span>`，加上 `href`（App Store 的 `https://apps.apple.com/app/id…`、Google Play 的 `https://play.google.com/store/apps/details?id=…`）。
- 「iPhone 和 Android 版即將在商店上架。」那句改掉。
- 如果 Android 晚一點才上，Google Play 按鈕先保留「即將上架」。Android 上架前，隱私權政策要補 Android 的說法（現在只寫 iPhone、iOS 鑰匙圈、Apple 付款）。
