# 雨水フロー追跡ツール

Qiita記事で紹介した「雨水フロー追跡ツール」のソースコードです。
Google Maps上で起点を指定すると、道路中心線データと標高データを用いて、雨水が流れる経路を擬似的に計算・追跡します。

## 📖 操作説明書
以下のリンクから、インストール不要で説明書を閲覧できます。
**[👉 操作説明書を見る（HTML版）](https://architectJapan.github.io/rainwater-flow-tracker/README.html)**

---

## 🚀 使い方

このツールはHTMLファイル単体で構成されていますが、Google Maps APIを使用するため、ご利用には**APIキーの取得**と**ローカルサーバーの起動**が必要です。

### 1. ファイルの準備
右上の緑色のボタン [Code] > [Download ZIP] からファイルをダウンロードし、解凍してください。

### 2. APIキーの設定
`index.html` をメモ帳やテキストエディタで開き、**108行目付近**にある以下のコードを探し、ご自身のGoogle Maps APIキーに書き換えて保存してください。

```javascript
window.GMAPS_API_KEY = "ここにあなたのGoogle Maps APIキーを入れる";
```

> **⚠️ セキュリティに関する注意**
> APIキーの不正利用を防ぐため、Google Cloud Console側で**HTTPリファラー制限**を設定することを強く推奨します。
> * ローカルで使う場合: `http://localhost:8000/*`
> * Cloudflare Pages等で使う場合: `https://あなたのプロジェクト名.pages.dev/*`

### 3. ローカルサーバーの起動
セキュリティ制約（CORS）のため、HTMLファイルを直接ダブルクリックしても動作しません。
コマンドプロンプト（またはターミナル）でファイルのあるフォルダを開き、簡易サーバーを立ち上げてください。

**Windowsの場合:**
```bash
py -m http.server 8000
```
※ Pythonランチャーが動かない場合は `python -m http.server 8000` を試してください。

**Mac / Linuxの場合:**
```bash
python3 -m http.server 8000
```

### 4. ブラウザでアクセス
ブラウザのアドレスバーに以下を入力してアクセスしてください。

`http://localhost:8000`

---
Copyright (c) 2026 architectJapan
