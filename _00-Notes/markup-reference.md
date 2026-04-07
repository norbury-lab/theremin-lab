# マークアップ・リファレンス

サイトには公開されない作業用メモ。
`_notes/markup-reference.md` に置くこと。

---

## Front Matter テンプレート

### 日記記事
```markdown
---
title: 2026/MM/DD タイトル（短め・サイドバー表示用）
layout: default
parent: 日記
nav_order: 9990  # 新しい記事を書くたびに10ずつ減らす
---
```

### 子ページ（例：intro/history.md）
```markdown
---
title: ページタイトル
layout: default
parent: はじめに  # 親ページのtitleと完全一致
nav_order: 2
---
```

### 親ページ（子を持つセクション）
```markdown
---
title: セクション名
layout: default
nav_order: 10
has_children: true
---
```

---

## Markdown 基本
```markdown
# 見出し1（ページタイトル用・1つだけ）
## 見出し2
### 見出し3

**太字**
*斜体*
~~取り消し線~~

> 引用

---（水平線）

- 箇条書き
- 箇条書き

1. 番号付きリスト
2. 番号付きリスト

`インラインコード`

[リンクテキスト](URL)

![画像の代替テキスト](../assets/images/ファイル名.jpg)
```

---

## HTML スニペット

### 画像（キャプション付き）
```html
<figure>
  <img src="../assets/images/ファイル名.jpg" alt="説明" style="max-width:100%; height:auto;">
  <figcaption style="font-size:0.85rem; color:#666; margin-top:0.4rem;">キャプションテキスト</figcaption>
</figure>
```

※トップページ（index.md）からは `assets/images/` （`../`不要）

### 画像（キャプションなし）
```html
<img src="../assets/images/ファイル名.jpg" alt="説明" style="max-width:100%; height:auto;">
```

### 外部リンクを別タブで開く（サイト全体に適用）

`_includes/head_custom.html` を作成し、以下を記述する。
```html
<script>
  document.addEventListener("DOMContentLoaded", function() {
    document.querySelectorAll('a[href^="http"]').forEach(function(link) {
      link.setAttribute('target', '_blank');
      link.setAttribute('rel', 'noopener noreferrer');
    });
  });
</script>
```

JSが無効な環境では同タブで開くだけで実害なし。

### YouTube埋め込み
```html
<div style="position:relative; padding-bottom:56.25%; height:0; overflow:hidden;">
  <iframe
    style="position:absolute; top:0; left:0; width:100%; height:100%;"
    src="https://www.youtube.com/embed/動画ID"
    frameborder="0" allowfullscreen>
  </iframe>
</div>
```

### 脚注（マウスオーバー＋クリックで飛ぶ）
```markdown
本文<span title="注釈の内容をここに書く">[^1]</span>

[^1]: 注釈の内容をここに書く
```

---

## Just the Docs：Callout
```markdown
{: .note }
> メモ・補足情報

{: .warning }
> 注意事項

{: .important }
> 重要ポイント

{: .tip }
> ヒント

{: .info }
> 情報
```

### タイトルを変えたいとき
```markdown
{: .warning-title }
> 独自タイトル
>
> 本文
```

---

## Just the Docs：Label（バッジ）
```markdown
[未完成](#){: .label .label-yellow }
[工事中](#){: .label .label-red }
[英語](#){: .label .label-blue }
[完成](#){: .label .label-green }
```

---

## テーブル
```markdown
| 項目 | 値 | 備考 |
|------|-----|------|
| 内容 | 内容 | 内容 |
```

---

## 参考リンクの書式
```markdown
- サイト名: [*記事タイトル（英語）*](URL)（日本語訳）日付
```

例：
```markdown
- BPR: [*Three months after InMusic acquisition, Moog cuts jobs*](https://www.bpr.org/bpr-news/2023-09-25/three-months-after-inmusic-acquisition-moog-cuts-jobs)（inMusic買収から3ヶ月、Moogが人員削減）2023年9月25日
```

外部リンクの別タブ化はJavaScriptで一括対応するため、個別に `target="_blank"` は不要。

---

## nav_order 現状

| セクション | nav_order |
|-----------|-----------|
| はじめに | 10 |
| 動作原理 | 20 |
| 演奏 | 30 |
| DIY | 40 |
| 一次資料 | 50 |
| リンク集 | 55 |
| 日記 | 60 |
| お問い合わせ | 70 |

日記のnav_orderは 9990 から始めて、新しい記事を書くたびに10ずつ減らす。

---

## ファイル・フォルダ命名ルール

- 英数字・ハイフンのみ（スペース・日本語・アンダースコア禁止）
- 小文字統一
- 例：`2026-03-30-etherwave-adapter.md`

## 画像ファイル命名ルール

- 英数字・ハイフンのみ・小文字
- 内容がわかる名前
- 例：`etherwave-front.jpg`、`series91a-cabinet.jpg`

## 画像サイズ目安

| 用途 | 幅 | 容量 |
|------|----|------|
| 記事内写真 | 1200px以下 | 200KB以下 |
| モデル写真 | 800px以下 | 150KB以下 |
| SVG図 | — | 50KB以下 |

圧縮ツール：https://squoosh.app

---

## 表記ルール

- **Etherwave**：英語・アッパーケース固定
- **テルミン / theremin**：日本語文中はテルミン、技術的文脈はtheremin
- **Léon Theremin**：人名は固定
- **人名**：すべて英語表記（Joe Richardson、Steve Dunnington 等）
- **句読点**：`、。`で統一
- **数字**：半角（3ピン、2ピン等）
- **製品名**：Standard、Plus（頭文字大文字）

---

*最終更新：2026年4月*