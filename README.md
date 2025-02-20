## 使い方

### 1. 必要なライブラリをインストール

このスクリプトを実行するために、必要な Python ライブラリをインストールしてください。

python3 -m pip install --upgrade pip

python3 -m pip install nfcpy gspread pygame requests python-dotenv google-auth

それぞれNFC、スプレッドシートAPI、音声ファイルの読み込み、HTTPリクエスト、envファイルの読み込み、Google Cloudのサービスへのアクセス、をするためのライブラリ

### 2. 認証情報の設定

Google スプレッドシート API を使用するために、認証情報 (`credentials.json`) を用意してください。

（ここの用意の仕方あとでもっと細かく追記する）

- `credentials.json` は Google Cloud Console で取得できます。

### 3. `.env` の設定

`.env.example` を参考に `.env` を作成し、必要な情報を記載してください。

### 4. スクリプトの実行

スクリプトを実行して、スプレッドシートにデータを書き込むことができます。

実行時に標準入力で時刻を"HH:MM"方式で入力

例：python3 attendance.py 13:00

## 動作の流れ

1. `.env` から **スプレッドシート ID** を読み込む
2. `credentials.json` を使用して Google API に認証
3. 指定されたスプレッドシートを開く
4. 学生証を読み込んで，不正なカードならエラー音を出力
5. 学籍番号や時刻を参照してデータを書き込む
6. 4に戻る

## 注意点

- `.env.example` を参考に `.env` を正しく設定してください。
- `credentials.json` および`.env` を誤って Git にアップロードしないように注意してください。
- Google Cloud Console で API キーと認証情報の設定が正しく行われていることを確認してください。
