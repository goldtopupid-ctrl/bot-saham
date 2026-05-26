# Telegram Market Bot BBCA BBRI Bitcoin USD IHSG

Bot Node.js untuk Render yang mengirim update market ke Telegram.

## Isi pantauan

- BBCA.JK
- BBRI.JK
- BTC-USD
- USD/IDR
- Berita Stockbit via Google News RSS query `site:stockbit.com`
- Berita IHSG / market Indonesia via Google News RSS
- Yahoo Finance news sebagai fallback tambahan

Catatan: Stockbit tidak disediakan sebagai API resmi di project ini. Bot mengambil berita Stockbit lewat Google News RSS dengan query `site:stockbit.com`, jadi hasil tergantung indeks Google News.

## ENV Render

```env
TELEGRAM_BOT_TOKEN=isi_token_bot_telegram
TELEGRAM_CHAT_ID=-100xxxxxxxxxx
TIMEZONE=Asia/Jakarta
NEWS_POLL_MINUTES=5
MARKET_SUMMARY_MINUTES=60
SEND_MARKET_SUMMARY=true
SEND_STARTUP_MESSAGE=true
RSS_NEWS_ENABLED=true
YAHOO_NEWS_ENABLED=true
```

Kalau mau matiin Yahoo dan pakai RSS Stockbit/IHSG aja:

```env
YAHOO_NEWS_ENABLED=false
RSS_NEWS_ENABLED=true
```

## Render

Build command:

```bash
npm install
```

Start command:

```bash
npm start
```

## Test Telegram

```bash
npm run test:telegram
```

## Disclaimer

Bot ini alat bantu pantauan, bukan nasihat keuangan dan bukan jaminan profit.


## v7 Fix
Versi ini tidak memakai package yahoo-finance2, jadi aman dari error `quote is not a function` / `search is not a function`. Data harga diambil langsung dari endpoint Yahoo Chart API.
