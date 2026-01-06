---
marp: true
theme: gaia
paginate: true
backgroundColor: #fff
style: |
  section {
    font-family: 'Helvetica Neue', Arial, sans-serif;
    padding: 40px;
    text-align: left;
  }
  h1 {
    color: #004080;
  }
  strong {
    color: #008080;
  }
---

# Hono × Cloudflare Workers
# DiscordのBotを作ってみた

---

## 1. 開発した内容

**URLを貼ると、AIが要約＆URLの短縮してくれるBot** を作ってみた。

- **機能:**
  - 記事のURLをDiscordに投稿
  - AIが日本語で箇条書き3行で要約
  - 短縮URLを自動発行してDBに保存<br>(やってみたかっただけであんまり意味はない)

![bg bottom right:25% fit bottom](../../images/20260107/discord.png)

---

## 2. 開発のきっかけ

- たまたまHonoの記事を読んでたら、discord-honoがあると知る
- Honoにも、DiscordのBotにも興味があったので試しに作ってみること
- **Cloudflare Workers** と **Hono** という構成を試してみたかった

---

## 3. 使用したライブラリ等

- **Framework:** Hono
- **Platform:** Cloudflare Workers
- **Database:** Workers KV 
- **AI Model:** Llama-3(Cloudflare Workers AI)
- **Libs:** discord-hono, cheerio

![bg left:35% fit](../../images/20260107/hono.png)

---

## 4. 実際の動作

1. Discordで `/summarize url:...` を入力
2. BotがWebサイトをスクレイピング
3. Llama-3 (AI) が日本語で要約を生成
4. 要約結果と短縮URLを返信

![bg right:40% width:400px fit](../../images/20260107/image.png)

---

## まとめ

- **Hono × Cloudflare** の開発はすごくお手軽にできた
- AI機能もAPIひとつで簡単に実装できる
- これだけの機能が **個人で利用する分には無料枠** で運用できる
