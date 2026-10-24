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

## iPhoneの効果音

最初の `LAUNCH` またはフリッパー操作でWeb Audioを有効化します。設定画面の「状態」が「再生可能」になれば、ブラウザ側では再生できる状態です。音量は「小・中・大」から選択でき、設定は保存されます。

iPhone本体の音量がゼロの場合は聞こえません。また、iOSのバージョン、Safari／ホーム画面PWAの状態、端末の消音モードによって音声出力が制限される場合があります。その場合は本体音量を上げ、消音モードを解除してから、ゲーム内の効果音を一度OFF→ONにしてください。
