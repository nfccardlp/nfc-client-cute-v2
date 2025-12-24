# 愛花 - Club Venus NFC名刺サイト V2（Video Enhanced）

六本木Club Venusのキャスト、愛花様のNFC名刺用ランディングページ **バージョン2.0**

## 🆕 V2の新機能

### ✨ ヒーロー動画（New!）
- **微動きらめき効果**: シャンデリアの輝き、照明の揺らぎ
- **シネマグラフ風**: 高級感のある「生きた写真」演出
- **軽量最適化**: 263KB（5秒ループ）
- **フォールバック対応**: 動画非対応ブラウザでは静止画表示

### 🚀 GitHub Actions自動デプロイ
- **Cloudflare Pages対応**: mainブランチへのpushで自動デプロイ
- **Vercel対応**: 代替デプロイオプション
- 詳細は `DEPLOY_GITHUB_ACTIONS.md` を参照

---

## 🎨 テーマ特性

- **テーマ**: Cute & Soft（キュート＆ソフト）
- **カラースキーム**: ソフトピンク基調、柔らかいグラデーション
- **フォント**: M PLUS Rounded 1c（丸ゴシック）
- **ターゲット**: 20代前後の若々しい雰囲気
- **特徴**: 大きな角丸、ふんわりした影、立体的なボタン

## 👤 クライアント情報（サンプル）

- **名前**: 愛花（Aika）
- **職業**: キャスト
- **店舗**: Club Venus
- **所在地**: 六本木
- **LINE**: https://line.me/ti/p/demo-aika

## ✨ 実装済み機能

### 1. ヒーローセクション（V2強化）
- 🎬 **背景動画**: きらめき効果付きループ動画
- 画面の75%を占める大型エリア
- 下部にグラデーションオーバーレイで名前表示

### 2. アバターセクション
- リッチなグラデーションボタン（ピンク系）
- クリックでモーダル表示
- 立体感のあるホバーエフェクト

### 3. ギャラリー（Swiper）
- Coverflowエフェクト（カード風の重なり表示）
- 自動再生（タッチ/スワイプ操作後も継続）
- 左右スワイプ対応
- クリックで画像をライトボックス拡大表示

### 4. CTAボタン
- 「保存してね💕」- ブックマーク案内モーダル表示
- 「LINEで話そ！」- LINEリンク（緑色、LINEブランドカラー）
- 両方とも大きく丸いボタンデザイン

### 5. レスポンシブ対応
- モバイルファースト設計
- 最大幅480pxのスマートフォン最適化

## 📁 ファイル構成

```
nfc-client-cute-v2/
├── index.html                  # メインHTML（動画対応）
├── style.css                   # CSS（動画スタイル追加）
├── script.js                   # JS（動画ロード検出追加）
├── gallery-swiper.js           # Swiperカルーセル設定
├── swiper-custom.css           # Swiper追加スタイル
├── hero-video-optimized.mp4    # 🆕 ヒーロー背景動画（263KB）
├── reina-hero-cute.jpg         # ヒーロー画像（フォールバック）
├── reina-avatar-cute.jpg       # アバター画像
├── slide-1.jpg ~ slide-5.jpg   # ギャラリー画像
├── favicon.svg                 # ファビコン
├── .github/
│   └── workflows/
│       ├── deploy-cloudflare.yml  # 🆕 Cloudflare自動デプロイ
│       └── deploy-vercel.yml      # 🆕 Vercel自動デプロイ
├── DEPLOY_GITHUB_ACTIONS.md    # 🆕 デプロイ設定ガイド
├── vercel.json                 # Vercelデプロイ設定
├── package.json                # プロジェクト情報
└── README.md                   # このファイル
```

## 🚀 デプロイ

### GitHub Actions（推奨）

詳細は `DEPLOY_GITHUB_ACTIONS.md` を参照。

```bash
# mainブランチへpushするだけで自動デプロイ
git push origin main
```

### 手動デプロイ

```bash
# Vercel CLI
vercel --prod

# Cloudflare Wrangler
npx wrangler pages deploy .
```

### ローカルプレビュー

```bash
# Python
python -m http.server 8080

# Node.js
npx http-server -p 8080
```

## 🔗 関連リポジトリ

- **V1（元テンプレート）**: [nfccardlp/nfc-client-cute-template](https://github.com/nfccardlp/nfc-client-cute-template)
- **V2（このリポジトリ）**: 動画対応 + GitHub Actions

## 📞 サポート

このサイトに関するお問い合わせ：
- 制作者: tsailink0611@gmail.com

---

© 2025 Aika - Club Venus. Built with AI. | V2.0 - Video Enhanced
