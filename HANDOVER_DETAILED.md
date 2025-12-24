# 🎀 NFC名刺サイト制作マニュアル - Cute & Soft Theme完全ガイド

このドキュメントは、**Cute & Soft Themeテンプレート**を使って新しいキャバ嬢・ホステス向けNFC名刺サイトを制作するための完全ガイドです。

---

## 📑 目次

1. [このテンプレートについて](#このテンプレートについて)
2. [命名規則とリポジトリ管理](#命名規則とリポジトリ管理)
3. [新規サイト制作フロー（全体像）](#新規サイト制作フロー全体像)
4. [ステップバイステップ手順](#ステップバイステップ手順)
5. [カスタマイズ詳細ガイド](#カスタマイズ詳細ガイド)
6. [画像生成ガイド](#画像生成ガイド)
7. [デプロイと公開](#デプロイと公開)
8. [トラブルシューティング](#トラブルシューティング)
9. [実例集](#実例集)

---

## 🎨 このテンプレートについて

### テーマ: Cute & Soft（キュート＆ソフト）

**対象**: 20代前後の若々しいキャバ嬢・ホステス向け

**デザインコンセプト**:
- 🌸 ソフトピンク基調の優しいカラーパレット
- 🔮 大きな角丸（30px）で可愛らしさを演出
- ✨ ふんわりした影と立体的なボタン
- 💕 ガラスモーフィズム（半透明効果）
- 🎈 浮遊するバブル風背景

**技術スタック**:
- HTML5
- CSS3（CSS変数使用）
- Vanilla JavaScript
- Swiper.js（カルーセル）
- Google Fonts（M PLUS Rounded 1c）

### 元のリポジトリ

- **テンプレートリポジトリ**: `nfc-client-cute-template`
- **GitHub URL**: https://github.com/tsailink0611/nfc-client-cute-template
- **作成日**: 2025-01-XX
- **バージョン**: v1.0.0

---

## 📛 命名規則とリポジトリ管理

### リポジトリ命名規則

すべてのプロジェクトは以下の命名規則に従います：

```
nfc-キャバ嬢の名前（ローマ字）-店舗名（省略形）
```

### 命名例

| キャバ嬢名 | 店舗名 | リポジトリ名 |
|----------|-------|------------|
| 愛花（あいか） | Club Venus | `nfc-aika-venus` |
| 美優（みゆ） | Club Rose | `nfc-miyu-rose` |
| さくら | Lounge Sakura | `nfc-sakura-lounge` |
| れいな | Diamond Ginza | `nfc-reina-diamond` |
| あやか | Club Platinum | `nfc-ayaka-platinum` |
| ゆい | Bar Crystal | `nfc-yui-crystal` |
| まりな | Club Brillante | `nfc-marina-brillante` |
| ももか | Lounge Peach | `nfc-momoka-peach` |
| ななみ | Club Seven | `nfc-nanami-seven` |

### 命名のポイント

1. **すべて小文字**: GitHubの慣例に従う
2. **ハイフン区切り**: 単語の区切りは `-` を使用
3. **わかりやすさ**: ファイル名だけで誰のサイトかすぐわかる
4. **一貫性**: すべてのプロジェクトで同じパターン

### ディレクトリ構造（推奨）

```
/home/user/webapp/
├── nfc-client-cute-template/     # マスターテンプレート（触らない）
├── nfc-aika-venus/               # 愛花さん（Club Venus）
├── nfc-miyu-rose/                # 美優さん（Club Rose）
├── nfc-sakura-lounge/            # さくらさん（Lounge Sakura）
└── nfc-reina-diamond/            # れいなさん（Diamond Ginza）
```

---

## 🚀 新規サイト制作フロー（全体像）

### タイムライン

| フェーズ | 作業内容 | 所要時間 |
|---------|---------|---------|
| **準備** | 情報収集、画像準備 | 30分 |
| **クローン** | テンプレートをクローン | 2分 |
| **カスタマイズ** | テキスト・画像差し替え | 15-30分 |
| **確認** | ローカルでプレビュー | 5分 |
| **デプロイ** | GitHubとVercelに公開 | 10分 |
| **テスト** | 全機能動作確認 | 10分 |
| **納品** | NFCカード書き込み | 5分 |

**合計**: 約1.5〜2時間

---

## 📝 ステップバイステップ手順

### 事前準備: 情報シート

新規プロジェクト開始前に以下の情報を収集してください：

#### ✅ 必須情報

```
キャバ嬢情報シート
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【基本情報】
・源氏名（漢字）: _________________
・源氏名（ひらがな）: _____________
・源氏名（ローマ字）: _____________
・本名（姓）: ___________________
・本名（名）: ___________________
・英語名（姓）: _________________
・英語名（名）: _________________

【店舗情報】
・店舗名（日本語）: ______________
・店舗名（英語）: ________________
・場所: ________________________
・住所: ________________________

【連絡先】
・LINE URL: https://line.me/ti/p/__________
・メールアドレス: _______________
・電話番号: ____________________ （任意）

【キャッチコピー・説明文】
・ヒーローエリアのキャッチコピー: 
  ________________________________

・自己紹介文: 
  ________________________________
  ________________________________

【サービスメニュー】
1. サービス1名: ______________
   説明: ____________________

2. サービス2名: ______________
   説明: ____________________

【SNS】
・Instagram URL: ______________
・Twitter/X URL: ______________
・TikTok URL: ________________
```

#### 📸 必須画像（7枚）

| # | 用途 | 推奨サイズ | 説明 |
|---|-----|----------|-----|
| 1 | ヒーロー画像 | 1080x1920px | 全身または上半身、華やかな衣装 |
| 2 | アバター画像 | 800x1200px | 顔アップ、笑顔 |
| 3 | ギャラリー1 | 800x1200px | ピンク系ドレス |
| 4 | ギャラリー2 | 800x1200px | 白系ドレス |
| 5 | ギャラリー3 | 800x1200px | カジュアル服 |
| 6 | ギャラリー4 | 800x1200px | 和装（浴衣など） |
| 7 | ギャラリー5 | 800x1200px | イベント・バースデー |

---

### STEP 1: 作業ディレクトリの準備

```bash
# 作業ディレクトリに移動
cd /home/user/webapp

# 現在のプロジェクト一覧を確認
ls -la
```

### STEP 2: テンプレートをクローン

```bash
# 新しいプロジェクト名を決める（例: nfc-miyu-rose）
PROJECT_NAME="nfc-miyu-rose"

# テンプレートをクローン
git clone https://github.com/tsailink0611/nfc-client-cute-template.git $PROJECT_NAME

# 新しいディレクトリに移動
cd $PROJECT_NAME

# 現在のディレクトリを確認
pwd
# 出力例: /home/user/webapp/nfc-miyu-rose
```

### STEP 3: Git履歴をリセット

```bash
# 既存のGit履歴を削除
rm -rf .git

# 新しいGitリポジトリとして初期化
git init

# ブランチ名をmainに設定
git branch -M main

# 確認
git status
```

### STEP 4: 情報を一括置換

#### 4-1. 環境変数を設定（置換を簡単にするため）

```bash
# キャバ嬢情報
OLD_NAME_JP="愛花"
NEW_NAME_JP="美優"

OLD_NAME_EN="Aika"
NEW_NAME_EN="Miyu"

OLD_LAST_NAME_JP="山本"
NEW_LAST_NAME_JP="佐藤"

OLD_LAST_NAME_EN="Yamamoto"
NEW_LAST_NAME_EN="Sato"

# 店舗情報
OLD_SHOP_JP="Club Venus"
NEW_SHOP_JP="Club Rose"

OLD_SHOP_EN="Club Venus"
NEW_SHOP_EN="Club Rose"

OLD_LOCATION="六本木"
NEW_LOCATION="銀座"

# LINE URL
OLD_LINE_URL="https://line.me/ti/p/demo-aika"
NEW_LINE_URL="https://line.me/ti/p/実際のID"

# メールアドレス
OLD_EMAIL="aika@club-venus.example"
NEW_EMAIL="miyu@club-rose.example"
```

#### 4-2. HTMLファイルを置換

```bash
# index.htmlの置換
sed -i "s/${OLD_NAME_JP}/${NEW_NAME_JP}/g" index.html
sed -i "s/${OLD_NAME_EN}/${NEW_NAME_EN}/g" index.html
sed -i "s/${OLD_SHOP_JP}/${NEW_SHOP_JP}/g" index.html
sed -i "s/${OLD_SHOP_EN}/${NEW_SHOP_EN}/g" index.html
sed -i "s/${OLD_LOCATION}/${NEW_LOCATION}/g" index.html
sed -i "s|${OLD_LINE_URL}|${NEW_LINE_URL}|g" index.html

# タイトルとメタディスクリプションの確認
grep "<title>" index.html
grep 'name="description"' index.html
```

#### 4-3. JavaScriptファイルを置換

```bash
# script.jsの置換
sed -i "s/firstName: '${OLD_NAME_JP}'/firstName: '${NEW_NAME_JP}'/g" script.js
sed -i "s/lastName: '${OLD_LAST_NAME_JP}'/lastName: '${NEW_LAST_NAME_JP}'/g" script.js
sed -i "s/firstNameEN: '${OLD_NAME_EN}'/firstNameEN: '${NEW_NAME_EN}'/g" script.js
sed -i "s/lastNameEN: '${OLD_LAST_NAME_EN}'/lastNameEN: '${NEW_LAST_NAME_EN}'/g" script.js
sed -i "s/company: '${OLD_SHOP_JP}'/company: '${NEW_SHOP_JP}'/g" script.js
sed -i "s/email: '${OLD_EMAIL}'/email: '${NEW_EMAIL}'/g" script.js
sed -i "s|url: '${OLD_LINE_URL}'|url: '${NEW_LINE_URL}'|g" script.js
sed -i "s/location: '${OLD_LOCATION}'/location: '${NEW_LOCATION}'/g" script.js

# 自己紹介文（note）も更新
sed -i "s/${OLD_LOCATION}${OLD_SHOP_JP}の${OLD_NAME_JP}/${NEW_LOCATION}${NEW_SHOP_JP}の${NEW_NAME_JP}/g" script.js
```

#### 4-4. gallery-swiper.jsを置換

```bash
# alt属性の置換
sed -i "s/alt: '${OLD_NAME_JP}/alt: '${NEW_NAME_JP}/g" gallery-swiper.js
```

#### 4-5. package.jsonを置換

```bash
# プロジェクト名と説明の置換
sed -i "s/\"name\": \"nfc-client-cute-template\"/\"name\": \"${PROJECT_NAME}\"/g" package.json
sed -i "s/${OLD_NAME_JP}/${NEW_NAME_JP}/g" package.json
sed -i "s/${OLD_SHOP_JP}/${NEW_SHOP_JP}/g" package.json
sed -i "s/${OLD_LOCATION}/${NEW_LOCATION}/g" package.json
```

#### 4-6. README.mdを置換

```bash
sed -i "s/${OLD_NAME_JP}/${NEW_NAME_JP}/g" README.md
sed -i "s/${OLD_NAME_EN}/${NEW_NAME_EN}/g" README.md
sed -i "s/${OLD_SHOP_JP}/${NEW_SHOP_JP}/g" README.md
sed -i "s/${OLD_LOCATION}/${NEW_LOCATION}/g" README.md
sed -i "s|${OLD_LINE_URL}|${NEW_LINE_URL}|g" README.md
```

#### 4-7. 置換結果を確認

```bash
# 主要ファイルで新しい名前が反映されているか確認
echo "=== index.html ==="
grep -E "${NEW_NAME_JP}|${NEW_SHOP_JP}" index.html | head -5

echo "=== script.js ==="
grep -E "firstName:|company:" script.js

echo "=== package.json ==="
cat package.json | head -10
```

### STEP 5: 画像を差し替え

#### 5-1. 古い画像を削除

```bash
# テンプレートの画像を削除
rm reina-hero-cute.jpg reina-avatar-cute.jpg slide-*.jpg

# 確認
ls -la *.jpg 2>/dev/null || echo "画像ファイルはすべて削除されました"
```

#### 5-2. 新しい画像を配置

**方法A: 既に画像ファイルがある場合**

```bash
# 画像をコピー（例）
cp /path/to/hero-image.jpg reina-hero-cute.jpg
cp /path/to/avatar-image.jpg reina-avatar-cute.jpg
cp /path/to/slide1.jpg slide-1.jpg
cp /path/to/slide2.jpg slide-2.jpg
cp /path/to/slide3.jpg slide-3.jpg
cp /path/to/slide4.jpg slide-4.jpg
cp /path/to/slide5.jpg slide-5.jpg
```

**方法B: AI画像生成を使う場合**

プロンプト例:

```
# ヒーロー画像
A young Japanese hostess [名前], [年齢] years old, cute and elegant style.
Wearing a [色] evening dress, holding a champagne glass, 
smiling sweetly in a luxury club setting.
Full body shot, photorealistic, 8k resolution, soft lighting.

# アバター画像
A young Japanese hostess [名前], [年齢] years old.
Close-up portrait, beautiful smile, looking at camera.
Wearing elegant makeup, soft pink background.
Photorealistic, 8k, professional portrait photography.

# ギャラリー画像1-5（それぞれ異なるシチュエーション）
```

#### 5-3. 画像サイズの確認と最適化

```bash
# ImageMagickがインストールされている場合
for img in *.jpg; do
    echo "$img: $(identify -format '%wx%h' $img)"
done

# サイズが大きすぎる場合は圧縮（オプション）
# mogrify -resize 1080x1920 -quality 85 reina-hero-cute.jpg
```

### STEP 6: ローカルでプレビュー

```bash
# Pythonでサーバー起動
python3 -m http.server 8080 &

# または Node.js
# npx http-server -p 8080 &

# プレビューURLを取得
echo "プレビュー: http://localhost:8080"
```

**確認項目**:
- [ ] ヒーロー画像が表示される
- [ ] 名前・店舗名が正しい
- [ ] アバターボタンをクリックで画像表示
- [ ] ギャラリーがスワイプできる
- [ ] LINEボタンが正しいURLにリンク

### STEP 7: 初回コミット

```bash
# すべてのファイルをステージング
git add .

# コミット
git commit -m "feat: Initial setup for ${NEW_NAME_JP} (${NEW_SHOP_JP})

- Updated all text content
- Replaced images (hero, avatar, gallery x5)
- Configured contact information
- Ready for deployment"

# 確認
git log --oneline
```

### STEP 8: GitHubリポジトリを作成

```bash
# GitHub CLIでリポジトリ作成（パブリック）
gh repo create $PROJECT_NAME --public --source=. --remote=origin

# プッシュ
git push -u origin main

# リポジトリURLを表示
gh repo view --web
```

**GitHub CLIが使えない場合**:

1. https://github.com/new にアクセス
2. リポジトリ名: `nfc-miyu-rose` （例）
3. Public を選択
4. Create repository

```bash
# 手動でリモート追加
git remote add origin https://github.com/tsailink0611/nfc-miyu-rose.git
git push -u origin main
```

### STEP 9: Vercelにデプロイ

#### 方法A: Vercel Dashboard（推奨）

1. https://vercel.com/dashboard にアクセス
2. 「Add New...」→ 「Project」をクリック
3. GitHub連携していない場合は連携
4. リポジトリ一覧から `nfc-miyu-rose` を選択
5. 「Import」をクリック
6. 設定はデフォルトのまま「Deploy」

**約1-2分で完了**

デプロイURL例: `https://nfc-miyu-rose.vercel.app`

#### 方法B: Vercel CLI

```bash
# Vercelにログイン
vercel login

# デプロイ
vercel --prod

# URLが表示される
```

### STEP 10: 動作確認

**デプロイ後のチェックリスト**:

```
[ ] ヒーロー画像が中央に表示
[ ] 名前・店舗名が正しく表示
[ ] アバターボタンをクリックで画像モーダル表示
[ ] ギャラリーが左右にスワイプ可能
[ ] ギャラリーが自動再生
[ ] 画像クリックでライトボックス表示
[ ] ライトボックス内で前後ナビゲーション
[ ] 「保存してね」ボタンでブックマーク案内表示
[ ] 「LINEで話そ」ボタンでLINE起動
[ ] スマホで表示確認（iPhoneとAndroid）
[ ] Instagram/ブログセクションが中央揃え
[ ] フッターが中央揃え
```

### STEP 11: NFCカードに書き込み

```bash
# デプロイURLをメモ
echo "https://nfc-miyu-rose.vercel.app"
```

NFCカード書き込みアプリ（例: NFC Tools）で上記URLを書き込み

---

## 🎨 カスタマイズ詳細ガイド

### カラースキームの変更

#### パターン1: ピンク系（デフォルト）

```css
/* style.css の :root セクション */
:root {
    --color-primary: #FF9EAA;       /* ソフトピンク */
    --color-primary-light: #FFD1D9; /* 薄いピンク */
    --color-secondary: #FFF0F5;     /* ラベンダーブラッシュ */
}
```

#### パターン2: ラベンダー系（上品）

```css
:root {
    --color-primary: #B19CD9;       /* ラベンダー */
    --color-primary-light: #D8BFD8; /* シスル */
    --color-secondary: #F0E6FF;     /* 薄紫 */
}
```

#### パターン3: ミントグリーン系（爽やか）

```css
:root {
    --color-primary: #98D8C8;       /* ミントグリーン */
    --color-primary-light: #C8F0E8; /* 薄いミント */
    --color-secondary: #E8FFF8;     /* ごく薄いミント */
}
```

#### パターン4: コーラル系（華やか）

```css
:root {
    --color-primary: #FF7F50;       /* コーラル */
    --color-primary-light: #FFA07A; /* ライトコーラル */
    --color-secondary: #FFE4E1;     /* ミスティローズ */
}
```

#### パターン5: ピーチ系（優しい）

```css
:root {
    --color-primary: #FFB6A3;       /* ピーチ */
    --color-primary-light: #FFDAB9; /* ピーチパフ */
    --color-secondary: #FFF5EE;     /* シーシェル */
}
```

### キャッチコピー・文言のカスタマイズ

#### ヒーローセクションのキャッチコピー

**index.html 149行目付近**:

```html
<p class="tagline-elegant">六本木で一番楽しい時間を♪</p>
```

**変更例**:
```html
<p class="tagline-elegant">一緒に特別な夜を過ごしませんか？</p>
<p class="tagline-elegant">あなたの笑顔が私の宝物💕</p>
<p class="tagline-elegant">銀座で最高のひとときを✨</p>
```

#### アバターセクションの文言

**index.html 159行目付近**:

```html
<p>私のアバターからご挨拶します♪</p>
```

**変更例**:
```html
<p>動画でご挨拶💕 タップしてね！</p>
<p>私からのメッセージがあります✨</p>
```

#### サービスカードの内容

**index.html 173-181行目付近**:

```html
<div class="cute-card">
    <div class="cute-card-icon">🥂</div>
    <h3 class="cute-card-title">指名してね</h3>
    <p class="cute-card-desc">VIPルームで盛り上がろう！</p>
</div>
```

**変更例**:

```html
<!-- カスタム例1: 同伴重視 -->
<div class="cute-card">
    <div class="cute-card-icon">🍽️</div>
    <h3 class="cute-card-title">同伴大歓迎</h3>
    <p class="cute-card-desc">美味しいお店ご一緒しましょ♪</p>
</div>

<!-- カスタム例2: 初心者向け -->
<div class="cute-card">
    <div class="cute-card-icon">🌟</div>
    <h3 class="cute-card-title">初めてでも安心</h3>
    <p class="cute-card-desc">優しくエスコートします💕</p>
</div>
```

### レイアウトの調整

#### ヒーローセクションの高さ変更

```css
/* style.css 88行目付近 */
.hero {
    height: 75vh; /* デフォルト */
}

/* より大きく */
.hero {
    height: 85vh;
}

/* より小さく */
.hero {
    height: 65vh;
}
```

#### ボタンの角丸調整

```css
/* style.css 15-17行目付近 */
:root {
    --border-radius-lg: 30px;  /* デフォルト */
    --border-radius-md: 20px;
    --border-radius-sm: 12px;
}

/* より丸く（可愛い） */
:root {
    --border-radius-lg: 40px;
    --border-radius-md: 30px;
    --border-radius-sm: 20px;
}

/* よりシャープに（クール） */
:root {
    --border-radius-lg: 20px;
    --border-radius-md: 15px;
    --border-radius-sm: 8px;
}
```

---

## 📸 画像生成ガイド

### AI画像生成プロンプト集

#### ヒーロー画像（全身）

```
A young Japanese hostess [名前], [年齢] years old, cute and elegant style.
Wearing a beautiful [色] evening dress, holding a champagne glass,
smiling sweetly in a luxury club VIP room setting.
Full body shot, standing pose, soft lighting, photorealistic, 8k resolution.
Background: luxury velvet sofa, dim ambient lighting with gold accents.
```

**変数**:
- `[名前]`: 英語名（例: Miyu）
- `[年齢]`: 年齢（例: 23）
- `[色]`: ドレスの色（pink, white, red, black など）

#### アバター画像（顔アップ）

```
A young Japanese hostess [名前], [年齢] years old.
Close-up portrait photo, beautiful smile, looking directly at camera.
Soft makeup with pink tones, glossy lips.
Wearing elegant jewelry (small earrings).
Soft pink gradient background, professional portrait lighting.
Photorealistic, 8k, high detail facial features.
```

#### ギャラリー画像1: ドレス姿

```
A young Japanese hostess [名前], [年齢] years old.
Wearing a stunning pink sequin evening dress, sitting on a luxury velvet sofa.
Elegant pose, one hand holding champagne glass, looking at camera with sweet smile.
Luxury club interior background with soft bokeh lights.
Photorealistic, 8k, fashion photography style.
```

#### ギャラリー画像2: カジュアル

```
A young Japanese hostess [名前], [年齢] years old.
Wearing casual but stylish outfit: pastel blouse and white skirt.
Walking in Roppongi/Ginza street at night, city lights bokeh background.
Natural smile, holding small handbag, fashionable and cute.
Photorealistic, 8k, street photography style.
```

#### ギャラリー画像3: 浴衣

```
A young Japanese hostess [名前], [年齢] years old.
Wearing a beautiful pink floral yukata (Japanese summer kimono).
Holding a paper fan, standing in a summer festival atmosphere.
Traditional Japanese setting, lanterns in background.
Sweet smile, photorealistic, 8k.
```

#### ギャラリー画像4: バースデー

```
A young Japanese hostess [名前], [年齢] years old.
Birthday celebration event, holding a birthday cake with lit candles.
Wearing a sparkling tiara and elegant dress.
Very happy and excited expression, balloons in background.
Photorealistic, 8k, party photography.
```

#### ギャラリー画像5: エレガント

```
A young Japanese hostess [名前], [年齢] years old.
Wearing an elegant white off-shoulder dress.
Sitting gracefully on a luxury chair, looking at camera.
Sophisticated and classy atmosphere, soft lighting.
Photoreactive, 8k, fashion magazine style.
```

### 画像生成時の注意点

1. **一貫性**: 同じモデルの顔を保つため、すべてのプロンプトで `[名前]` と `[年齢]` を統一
2. **解像度**: 必ず `8k` または `photorealistic` を指定
3. **ライティング**: `soft lighting` で優しい雰囲気に
4. **背景**: ぼかし効果（`bokeh`）で被写体を際立たせる
5. **表情**: `sweet smile` や `natural smile` で親しみやすさを

---

## 🚢 デプロイと公開

### Vercelの自動デプロイ設定

一度Vercelにデプロイすると、以降はGitHubにプッシュするだけで自動デプロイされます。

```bash
# 更新作業
vim index.html  # ファイルを編集

# コミット
git add .
git commit -m "update: キャッチコピー変更"

# プッシュ（自動でVercelがデプロイ）
git push origin main
```

約30秒〜1分で反映されます。

### カスタムドメインの設定

#### 手順

1. Vercel Dashboard → プロジェクト選択
2. Settings → Domains
3. Add Domain
4. ドメイン入力（例: `miyu.example.com`）
5. DNSレコード設定の指示に従う

#### DNSレコード例

```
Type: CNAME
Name: miyu
Value: cname.vercel-dns.com
```

---

## 🐛 トラブルシューティング

### 問題1: 名前が置換されていない箇所がある

**原因**: sed コマンドの対象ファイル漏れ

**解決策**:

```bash
# すべてのファイルで検索
grep -r "愛花" .

# 該当ファイルを個別に修正
sed -i 's/愛花/美優/g' ファイル名
```

### 問題2: 画像が404エラー

**原因**: ファイル名の不一致

**解決策**:

```bash
# ファイル名を確認
ls -la *.jpg

# HTMLで参照されている名前を確認
grep -E "\.jpg" index.html

# ファイル名を修正
mv wrong-name.jpg reina-hero-cute.jpg
```

### 問題3: LINEボタンが動かない

**原因**: URL形式が間違っている

**解決策**:

```bash
# 正しい形式
https://line.me/ti/p/実際のID

# 間違った形式例
line://ti/p/実際のID  # NG
https://lin.ee/xxxxx   # これもOK（短縮URL）

# script.jsで確認
grep "url:" script.js
```

### 問題4: ギャラリーが動かない

**原因**: Swiper.jsの読み込み失敗

**解決策**:

```bash
# ブラウザのコンソールでエラー確認
# F12 → Console タブ

# CDNが正しいか確認（index.html）
grep "swiper" index.html
```

### 問題5: モバイルで表示が崩れる

**原因**: 画像サイズが大きすぎる

**解決策**:

```bash
# 画像を圧縮
mogrify -resize 1080x1920 -quality 85 *.jpg

# または WebP形式に変換
for img in *.jpg; do
    cwebp -q 85 $img -o ${img%.jpg}.webp
done

# HTMLで参照を変更
sed -i 's/\.jpg/\.webp/g' index.html
```

---

## 💡 実例集

### 実例1: nfc-aika-venus（テンプレート元）

**基本情報**:
- 名前: 愛花（Aika）
- 店舗: Club Venus
- 場所: 六本木
- テーマ: Cute & Soft（ピンク）

**リポジトリ**: `nfc-client-cute-template`
**URL**: https://github.com/tsailink0611/nfc-client-cute-template

### 実例2: nfc-miyu-rose（架空の例）

**基本情報**:
- 名前: 美優（Miyu）
- 店舗: Club Rose
- 場所: 銀座
- テーマ: Cute & Soft（ラベンダー）

**カスタマイズ内容**:
```bash
# カラー変更
--color-primary: #B19CD9;  /* ピンク→ラベンダー */

# キャッチコピー
"銀座で最高のひとときを✨"

# サービスカード
1. 同伴大歓迎 - 美味しいお店ご一緒しましょ♪
2. アフターも♪ - 朝まで楽しく過ごせます💕
```

### 実例3: nfc-sakura-lounge（架空の例）

**基本情報**:
- 名前: さくら（Sakura）
- 店舗: Lounge Sakura
- 場所: 新宿
- テーマ: Cute & Soft（ピーチ）

**カスタマイズ内容**:
```bash
# カラー変更
--color-primary: #FFB6A3;  /* ピンク→ピーチ */

# ヒーロー高さ
height: 80vh;  /* 75vh→80vh */

# ボタン角丸
--border-radius-lg: 40px;  /* 30px→40px */
```

---

## 📚 参考資料

### 公式ドキュメント

- Swiper.js: https://swiperjs.com/
- Google Fonts: https://fonts.google.com/
- Vercel: https://vercel.com/docs

### 推奨ツール

- **画像編集**: Photoshop, GIMP, Canva
- **画像圧縮**: TinyPNG, Squoosh
- **AI画像生成**: Midjourney, Stable Diffusion, DALL-E
- **NFCカード書き込み**: NFC Tools (iOS/Android)

---

## ✅ クイックスタートコマンド集

新規プロジェクトを最速で立ち上げる場合、以下をコピペしてください：

```bash
#!/bin/bash
# NFC名刺サイト クイックスタートスクリプト

# ===== 変数設定 =====
PROJECT_NAME="nfc-新しい名前"
OLD_NAME_JP="愛花"
NEW_NAME_JP="新しい名前"
OLD_NAME_EN="Aika"
NEW_NAME_EN="NewName"
OLD_SHOP_JP="Club Venus"
NEW_SHOP_JP="New Shop"
OLD_LOCATION="六本木"
NEW_LOCATION="新しい場所"
OLD_LINE_URL="https://line.me/ti/p/demo-aika"
NEW_LINE_URL="https://line.me/ti/p/新しいID"

# ===== 作業開始 =====
cd /home/user/webapp
git clone https://github.com/tsailink0611/nfc-client-cute-template.git $PROJECT_NAME
cd $PROJECT_NAME
rm -rf .git
git init
git branch -M main

# ===== 一括置換 =====
for file in index.html script.js gallery-swiper.js package.json README.md; do
    sed -i "s/${OLD_NAME_JP}/${NEW_NAME_JP}/g" $file
    sed -i "s/${OLD_NAME_EN}/${NEW_NAME_EN}/g" $file
    sed -i "s/${OLD_SHOP_JP}/${NEW_SHOP_JP}/g" $file
    sed -i "s/${OLD_LOCATION}/${NEW_LOCATION}/g" $file
    sed -i "s|${OLD_LINE_URL}|${NEW_LINE_URL}|g" $file
done

# ===== 初回コミット =====
git add .
git commit -m "feat: Initial setup for ${NEW_NAME_JP}"

echo "✅ クイックスタート完了！"
echo "次のステップ:"
echo "1. 画像を差し替え（reina-hero-cute.jpg, reina-avatar-cute.jpg, slide-*.jpg）"
echo "2. プレビュー確認: python3 -m http.server 8080"
echo "3. GitHubリポジトリ作成: gh repo create ${PROJECT_NAME} --public --source=. --remote=origin --push"
echo "4. Vercelデプロイ: https://vercel.com/dashboard"
```

---

## 🎯 まとめ

このマニュアルに従えば、約1.5〜2時間で新しいNFC名刺サイトを制作・公開できます。

### 成功のポイント

1. **情報収集を徹底**: 事前に必要な情報・画像をすべて揃える
2. **命名規則を守る**: `nfc-名前-店舗` の形式で統一
3. **一括置換を活用**: sedコマンドで効率的に
4. **プレビュー確認**: デプロイ前に必ずローカルで確認
5. **チェックリスト**: 動作確認を漏れなく実施

### 次のステップ

- [ ] このマニュアルを保存
- [ ] 次のプロジェクトで実践
- [ ] カスタマイズパターンを増やす
- [ ] テンプレートの改善提案

---

**Happy Coding! 🎀**

© 2025 NFC Hostess Card Template Project
