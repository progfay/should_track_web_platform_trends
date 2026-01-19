---
title: FE エンジニアは Web Platform 動向を追うべきか？
titleTemplate: "%s | progfay"
author: progfay
theme: ./
class: text-center
transition: null
mdc: true
duration: 12min
colorSchema: dark
---

<h1 style="font-size: 3rem">
  FE エンジニアは
  <span style="display: inline flow-root">
    Web Platform 動向を追うべきか？
  </span>
</h1>

<p style="color: #A5A5A1">
  2026.01.20 |
  <a href="https://findy.connpass.com/event/380541/" target="_blank" rel="noreferrer" style="color: #A5A5A1">Findy TECH BATON</a> |
  <a href="https://x.com/progfay" target="_blank" rel="noreferrer" style="color: #A5A5A1">@progfay</a>
</p>

---
layout: self-intro
preload: true
---

- Web Frontend Engineer
- 趣味で Web の動向を追っかけている
- 🆕 趣味: スマホのアプリを消す

---
layout: statement
---

## Web Platform の動向、追ってますか？

---
layout: default-with-message
---

## Web 動向って何だっけ？

※個人的な定義です。

- **Proposal**: どのような機能が提案されているのか
- **Discussion**: どのような議論がされているか
- **Shipment**: どのような機能がブラウザに実装されるか

プロダクト開発に一番影響するのは **Shipment**

---

## Shipment

新しく公開された API などがプロダクトで使える！

<div style="display: flex; justify-content: center">
  <a href="https://developer.chrome.com/blog/new-in-chrome-144?hl=ja" target="_blank" rel="noreferrer">
    <img
      src="/Chrome144.png"
      alt="Chrome 144 から `::search-text`, `<geolocation>`, Temporal API が利用可能になった。"
      style="height: 25rem" />
  </a>
</div>

---
layout: default-with-message
---

## Major Browsers

- Apple Safari (macOS / iOS)
- Google Chrome (desktop / Android)
- Microsoft Edge (desktop)
- Mozilla Firefox (desktop and Android)
- etc...

これらの Shipment をそれぞれ追うのは大変...

---
layout: statement
tile: Introduce Baseline
---

<a href="https://web-platform-dx.github.io/web-features/" target="_blank" rel="noreferrer">
  <img
    src="/Baseline.png"
    alt="Shipment を追うのに便利な Baseline について紹介します。"
    style="margin: auto; height: 5rem" />
</a>

---

## What's Baseline?

> Baseline （ベースライン）は、ブラウザー間で動作するウェブプラットフォームの機能を確認します。
>
> Baseline は、サイトの訪問者に互換性の問題を引き起こす可能性が低くなった時期を示すことで、その機能を使用するタイミングを決定するのに役立ちます。

ref. [Baseline (compatibility) - Glossary | MDN](https://developer.mozilla.org/ja/docs/Glossary/Baseline/Compatibility)

---

## Baseline Status

![Limited availability](https://developer.mozilla.org/ja/docs/Glossary/Baseline/Compatibility/low.png)

![Newly Available](https://developer.mozilla.org/ja/docs/Glossary/Baseline/Compatibility/limited.png)

![Widely Available](https://developer.mozilla.org/ja/docs/Glossary/Baseline/Compatibility/high.png)

ref. [Baseline (compatibility) - Glossary | MDN](https://developer.mozilla.org/ja/docs/Glossary/Baseline/Compatibility#baseline_badges)

---

## どのタイミングから使う？

- 一部の Major Browser でのみ Ship された
  - 流石に時期尚早感がある
  - 将来、機能が消える可能性もある

- 全 Major Browser で Ship された
  - 「最新 ver. に更新して」が可能に
  - とはいえ、まだ多くの環境では使えない

- 全 Major Browser で Ship されてだいぶ経った
  - どれくらい時間が経てばいい？
  - 古いブラウザはサポートしない？

---

## 基準を定めている現場もあるかも

- サポートするブラウザについて公開していたり
- 内部では、より広いブラウザをサポートしようとしていたり
  - [Browserslist](https://github.com/browserslist/browserslist)

```json
{
  "browserslist": [
    "last 1 version",
    "> 1%",
    "not dead"
  ]
}
```

---

## どうやって基準を設定する？

- プロダクトの特性を見極めて設定するのがベスト
  - ユーザーが使うブラウザと version の分布は？
  - 未実装のブラウザではどれくらい困る？
  - etc...

- でも見極めってめっちゃ難しい
  - リリース前では判断するための情報が足りない
  - そもそもあんまり詳しくない
  - (ぶっちゃけめんどくさい...)

---
layout: statement
tile: Re-introduce Baseline
---

<a href="https://web-platform-dx.github.io/web-features/" target="_blank" rel="noreferrer">
  <img
    src="/Baseline.png"
    alt="そんなあなたには Baseline がオススメ！"
    style="margin: auto; height: 5rem" />
</a>

---

## Baseline: Newly → Widely

Newly Available になってから 30 ヶ月後に Widely Available になる。

> この広く利用されている線が、すべての人にとって正確であるとは限らないことは承知しています。
>
> しかし、ブラウザ バージョンの導入に関する利用可能なデータを調べたところ、 **ほとんどの機能は、世界中の約 95% のユーザーが利用できるようになるまでに 30 か月もかからないことがわかりました。**
> この期間よりもずっと早く機能をご使用になっても問題ないかもしれませんが、相互運用から 30 か月が経過すると、その機能を使用できなくなる可能性は低くなります。

ref. [ベースラインの定義の更新  |  Blog  |  web.dev](https://web.dev/blog/baseline-definition-update?hl=ja)

---

## Baseline in your project

> Baseline を使用すると、以下のことが可能になります。
> - **サイトやアプリケーションで使用する Web プラットフォーム機能に関する意思決定**
> - 他の人に、機能がブラウザ間で動作するかどうかを伝える

ref. [Baseline in your project | Baseline](https://web-platform-dx.github.io/web-features/use-baseline/) (Translated by [Nani Translate](https://nani.now))

<hr style="border-color: #A5A5A1; margin: 3rem 0" />

```json {2}
{
  "browserslist": ["baseline widely available"]
}
```

ref. [Browserslist でベースラインを使用する  |  Articles  |  web.dev](https://web.dev/articles/use-baseline-with-browserslist?hl=ja)

---

## どうやって Web Platform 動向を追えばいい？

プロダクト開発においては **Baseline を追うだけでも十分**

- [Baseline 2025](https://web.dev/baseline/2025)
- [New to the web platform in December](https://web.dev/blog/web-platform-12-2025)
- [November 2025 Baseline monthly digest](https://web.dev/blog/baseline-digest-nov-2025)

---

## Baseline 以外は追わなくて良い？

Shipment には 3 パターンある

1. 何も影響しない Shipment

2. 対応すると嬉しい Shipment
   - Baseline を追うことで発見できる

3. **対応しないとヤバい Shipment**
   - Breaking Change: [3rd Party Cookie Deprecation](https://blog.chromium.org/2019/05/improving-privacy-and-security-on-web.html) (`SameSite=Lax`)
   - Security Updates: [Spectre / Meltdown](https://developer.chrome.com/blog/meltdown-spectre)
   - etc...

---

## Don't Break the Web

> オープンなウェブ標準の周りで耳にするもう一つの言葉は「ウェブを壊さない」です。
>
> この考えは、導入される新しいウェブ技術は、過去に行われたものが下位互換性を持ち（つまり、古いウェブサイトも引き続き動作する）、上位互換性がある（将来の技術は、現在あるものと互換性がある）べきだというものです。

ref. [ウェブ標準モデル - ウェブ開発の学習 | MDN](https://developer.mozilla.org/ja/docs/Learn_web_development/Getting_started/Web_standards/The_web_standards_model#%E3%82%A6%E3%82%A7%E3%83%96%E3%82%92%E5%A3%8A%E3%81%95%E3%81%AA%E3%81%84)

<hr style="border-color: #A5A5A1; opacity: 0; margin: 1.5rem 0" />

- しかし実際には Breaking Change が起きる
- これは「ユーザーの安全性」を毀損すると判断された場合に起きる
- Breaking Change は十分に議論された上で Ship される

---
layout: default-with-message
---

## Web 動向って何だっけ？

<p style="position: absolute; margin: 0; top: 1rem; right: -3.25rem; background-color: #A5A5A1; padding: 0.6rem 0.5rem 0.4rem; width: 12rem; text-align: center; vertical-align: middle; transform: rotate(35deg); font-weight: bold; font-size: 1.35rem">
  再掲
</p>

※個人的な定義です。

- **Proposal**: どのような機能が提案されているのか
- **Discussion**: どのような議論がされているか
- **Shipment**: どのような機能がブラウザに実装されるか

Proposal, Discussion から Web Platform が進む方向性が予測できる

---

## まとめ

- Web Platform 動向はまず Baseline を追うところから始めよう
  - [Baseline 2025](https://web.dev/baseline/2025)
  - [New to the web platform in December](https://web.dev/blog/web-platform-12-2025)
  - [November 2025 Baseline monthly digest](https://web.dev/blog/baseline-digest-nov-2025)

- 新機能を利用するかの判断基準はプロダクトの特性を見極めて設定するのがベスト

- でも、大変なら Baseline Widely Available を活用するのも良い

- Baseline に加えて提案や議論も追うと Web Platform が進む方向性が予測できる
  - [`@progfay`](https://x.com/progfay) はこれを趣味として楽しんでいます！

---

## おまけ: [`@progfay`](https://x.com/progfay) の新機能利用基準

- 基本戦略: 不要な挑戦はしない
  - Feature Detection での分岐は fallback との二重管理になってしまう
  - Transpile や Polyfill で Bundle Size 増やしてもユーザーは嬉しくない
  - 開発効率の向上やバグの低減につながるなら要検討

- リリースした後でも、使えないユーザーが多そうなら修正する
  - `Array.prototype.at` や `OffscreenCanvas` は Widely Available
  - しかし Sentry などに "OffscreenCanvas is not defined" などのエラーが上がってくる
  - 数が多そうならユーザーの不利益になるので即修正

- 新しい機能を使いたい気持ちをグッと抑えて Widely Available を虎視眈々と待っている
  - [`field-sizing: content`](https://developer.mozilla.org/ja/docs/Web/CSS/Reference/Properties/field-sizing) と [Navigation API](https://developer.mozilla.org/en-US/docs/Web/API/Navigation_API) 早く来てくれ...！
