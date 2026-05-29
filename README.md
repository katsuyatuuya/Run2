# システムスマホ

iPhone / Android のブラウザで使える、1ページ型の簡易顔入れ替えツールです。

GitHub Pages に `index.html` を置くと、スマホからURLを開いてそのまま使えます。画像と動画はブラウザ内で処理され、素材をサーバーへアップロードしません。

## GitHub Pagesで公開する

1. GitHubで新しいリポジトリを作る
2. このフォルダの `index.html`、`README.md`、`.nojekyll` をアップロードする
3. GitHubのリポジトリで `Settings` → `Pages` を開く
4. `Build and deployment` を `Deploy from a branch` にする
5. `Branch` を `main` / `/root` にして保存する
6. 数分後に表示されるURLをiPhoneのSafariで開く

公開URLの例:

```text
https://ユーザー名.github.io/リポジトリ名/
```

初回だけ MediaPipe FaceMesh をCDNから読み込みます。iPhoneで使う場合は、まず5秒から10秒の短い動画、出力幅480または640で試してください。

## 使い方

1. 入れ替えたい顔画像を選ぶ
2. 元動画を選ぶ
3. 出力幅や画質を選ぶ
4. 実行する
5. 完成後、保存ボタンから動画を保存する

## 注意

- デスクトップ用AI顔入れ替えアプリと同等の品質ではありません
- できるだけ明るい動画、正面に近い顔、短い動画で使ってください
- iPhone Safari の動画書き出し仕様により、音声が入らない場合があります
- 長い動画や高解像度動画は処理が重くなります
- 本人の同意、権利、公開範囲を確認して使ってください

## PCでローカル確認する

Pythonが使える場合:

```bash
python -m http.server 8767
```

ブラウザで開きます。

```text
http://127.0.0.1:8767/index.html
```

## Python版について

`mobile_faceswap.py` と `web_app.py` はPCやAndroid/Termux向けのローカル処理版です。GitHub PagesではPythonは動かないため、スマホから公開URLで使う場合は `index.html` のブラウザ版を使います。
