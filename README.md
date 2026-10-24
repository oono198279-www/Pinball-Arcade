# Nebula Strike — Pinball Arcade

外部ライブラリ・CDN・APIを使用しない、Canvas 2D製のオリジナルPWAピンボールゲームです。

## 操作

- Windows: `←` / `→` で左右フリッパー、`↓` で同時、`Space` で発射
- iPhone: 下部左右ボタン。設定で片手（どちらを押しても同時）／左右独立を切替

## ローカル起動

Service Workerの確認にはHTTP配信が必要です。

```sh
python3 -m http.server 4173
```

その後 `http://localhost:4173/` を開きます。

## 構成

- `index.html`: UI、描画、ゲームロジック、固定時間ステップ物理
- `manifest.webmanifest`: PWAメタデータ
- `sw.js`: バージョン付きアプリシェルキャッシュ
- `icons/`: PWAアイコン

ハイスコア、操作モード、効果音設定はブラウザの `localStorage` に保存されます。
