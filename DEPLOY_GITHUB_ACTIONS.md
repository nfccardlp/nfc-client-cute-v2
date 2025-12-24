# 🚀 GitHub Actions 自動デプロイ設定ガイド

## 📋 概要

このプロジェクトはGitHub Actionsを使用して、mainブランチへのpush時に自動デプロイされます。

---

## ☁️ Cloudflare Pages デプロイ（推奨）

### ステップ1: Cloudflareアカウント準備

1. https://dash.cloudflare.com にアクセス
2. アカウントを作成（または既存アカウントでログイン）
3. 左メニューから「Workers & Pages」を選択

### ステップ2: APIトークン取得

1. Cloudflare Dashboard右上のプロフィールアイコンをクリック
2. 「My Profile」→「API Tokens」を選択
3. 「Create Token」をクリック
4. 「Edit Cloudflare Workers」テンプレートを使用
5. 権限を以下に設定：
   - Account: Cloudflare Pages → Edit
   - Zone: なし（必要に応じて）
6. トークンを生成してコピー

### ステップ3: アカウントID取得

1. Cloudflare Dashboardの右サイドバーで「Account ID」を確認
2. コピーして保存

### ステップ4: GitHubシークレット設定

GitHubリポジトリで以下を設定：
1. 「Settings」→「Secrets and variables」→「Actions」
2. 「New repository secret」で以下を追加：

| シークレット名 | 値 |
|--------------|---|
| `CLOUDFLARE_API_TOKEN` | ステップ2で取得したAPIトークン |
| `CLOUDFLARE_ACCOUNT_ID` | ステップ3で取得したアカウントID |

### ステップ5: プロジェクト名設定（オプション）

カスタムプロジェクト名を使用する場合：
1. 「Settings」→「Secrets and variables」→「Actions」→「Variables」タブ
2. 「New repository variable」で以下を追加：

| 変数名 | 値 |
|-------|---|
| `CLOUDFLARE_PROJECT_NAME` | 任意のプロジェクト名（例: `nfc-aika-cute-v2`） |

### ステップ6: デプロイ実行

```bash
git add .
git commit -m "feat: Add GitHub Actions deployment"
git push origin main
```

これでmainブランチへのpush時に自動デプロイされます！

### デプロイURL

```
https://{プロジェクト名}.pages.dev
```

---

## 🔷 Vercel デプロイ（代替案）

Cloudflareが使えない場合の代替案です。

### ステップ1: Vercelトークン取得

1. https://vercel.com/account/tokens にアクセス
2. 「Create」をクリック
3. トークン名を入力して生成

### ステップ2: プロジェクトID取得

```bash
# ローカルでVercel CLIを使用
npm install -g vercel
vercel link
# プロジェクト設定後、.vercel/project.json を確認
cat .vercel/project.json
```

### ステップ3: GitHubシークレット設定

| シークレット名 | 値 |
|--------------|---|
| `VERCEL_TOKEN` | Vercel APIトークン |
| `VERCEL_ORG_ID` | project.jsonのorgId |
| `VERCEL_PROJECT_ID` | project.jsonのprojectId |

### ステップ4: ワークフロー有効化

`.github/workflows/deploy-vercel.yml` のコメントを外す：

```yaml
on:
  push:
    branches:
      - main
```

---

## 🔧 トラブルシューティング

### Q: デプロイが失敗する

**A1: シークレットを確認**
- GitHub Secrets に正しい値が設定されているか確認
- シークレット名のスペルミスに注意

**A2: 権限を確認**
- Cloudflare APIトークンに「Cloudflare Pages: Edit」権限があるか

### Q: プロジェクトが見つからない

**A: 初回デプロイ**
- 初回はCloudflare Pagesで自動的にプロジェクトが作成されます
- プロジェクト名は `CLOUDFLARE_PROJECT_NAME` 変数で指定可能

### Q: 動画が表示されない

**A: ファイルサイズ確認**
- Cloudflare Pagesの無料枠: 25MB/ファイル
- `hero-video-optimized.mp4` は約263KBで問題なし

---

## 📁 ワークフローファイル

```
.github/
└── workflows/
    ├── deploy-cloudflare.yml  # Cloudflare Pages用（推奨）
    └── deploy-vercel.yml      # Vercel用（代替）
```

---

## 🎯 デプロイフロー図

```
[ローカル開発]
     ↓
git push origin main
     ↓
[GitHub Actions 起動]
     ↓
[Cloudflare Pages デプロイ]
     ↓
✅ https://nfc-aika-cute-v2.pages.dev
```

---

作成日: 2024-12-24
