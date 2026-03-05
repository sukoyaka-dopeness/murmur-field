# murmur-field

**Murmur Field: slow social bookmarking.**  
Ambient rhythm. Gentle resonance. No noise.

**マーマーフィールド：ゆっくりとしたソーシャルブックマーク。**  
環境リズム。静かな共鳴。ノイズなし。

---

## What is this? / これは何？

Murmur Field is a social bookmarking service designed as an antithesis to overstimulating social media.  
Instead of notifications, counts, and engagement metrics, Murmur Field offers a quiet field —  
where information moves with your daily rhythm, not against it.

マーマーフィールドは、刺激過多な現代のSNSへのアンチテーゼとして設計されたソーシャルブックマークサービスです。  
通知、数字、エンゲージメント指標の代わりに、静かな野原を提供します——  
情報はあなたの日常のリズムとともに動きます。あなたの時間を支配しません。

You save what matters. The field breathes around you.  
Somewhere out there, someone found the same place. The grass stirs, just once.

大切なものを保存する。野原はその周りで息をする。  
どこかで誰かが、同じ場所を見つけた。草が、ほんの一度だけそっと揺れる。

---

## Core Philosophy / 設計思想

- **Ambient Social** — always-on connection is not required. The field is there when you arrive.  
  **Ambient Social** — 常時接続を強いない。野原は、あなたが来たときそこにある。

- **Rhythm over engagement** — information surfaces according to time of day and personal pace, not viral momentum.  
  **エンゲージメントよりリズム** — 情報は拡散の勢いではなく、時刻と個人のペースに従って浮上する。

- **Resonance over reach** — value is measured within your cluster, not across the entire platform.  
  **リーチより共鳴** — 価値はプラットフォーム全体ではなく、自分のクラスタ内で測られる。

- **No amplification** — the architecture does not reward volume. It rewards depth.  
  **増幅しない** — 設計は量を報酬にしない。深さを報酬にする。

- **Physical over ethical** — rather than judging behavior, the structure simply does not amplify it.  
  **倫理ではなく物理を設計する** — 特定の行動を判定・排除するのではなく、増幅しない構造を作る。

---

## Key Concepts / 主要概念

### 🌿 The Field / 野原
Your personal bookmark space, rendered as a living meadow. Cards breathe gently with occasional wind. Connections form quietly at the edges.  
個人のブックマーク空間を、生きた草原として描画します。カードはときおり吹く風にそっと揺れます。つながりは静かに、縁の方から生まれます。

### 🪨 Place a Stone / 石を置く
Pin a card that matters. While other cards drift with the ambient rhythm, stones stay still.  
To remove a pin: *石をはずす.*  
大切なカードに石を置く。他のカードが環境リズムに揺れる中、石は静止し続ける。  
ピンを外すには：*石をはずす。*

### 🌾 Withered Grass / 枯れ草
When a link dies, its card becomes withered grass — visible, textured, present.  
Information fades. That fading is part of the record. You may *忘れる* it when you're ready.  
リンクが切れると、カードは枯れ草になる——見える、質感がある、存在する。  
情報は移ろう。その移ろいも記録の一部です。準備ができたら *忘れる* ことができます。

### 🔔 Presence, Not Notification / 通知ではなく気配
Push notifications are off by default.  
When you return to the field, a card may sway — someone else found this place too.  
No number. No name. Just a presence.  
プッシュ通知はデフォルトでオフです。  
野原に戻ったとき、カードが揺れているかもしれない——誰かが同じ場所を見つけた。  
数字はない。名前もない。気配だけがある。

### 🗣️ Whisper / ささやき
A comment left on your own bookmarked card. Not a reply. Not a thread.  
A fragment of thought at the moment you read it.  
自分のブックマークカードに残すコメント。返信ではない。スレッドでもない。  
読んだその瞬間の、思考の断片。

---

## Interaction Design / インタラクション設計

| Action / 操作 | Method / 操作方法 | Platform / 対応環境 |
|---|---|---|
| Save a bookmark / ブックマーク保存 | Share sheet → 1 tap / 共有シート → 1タップ | Mobile / PC |
| Browse the field / 野原を眺める | Scroll / スクロール | Both |
| Shake the field / 野原をかき混ぜる | Shake device / 端末を振る | Mobile |
| Place a stone / 石を置く | Long press card / カードを長押し | Both |
| Release a stone / 石をはずす | Button on card / カード上のボタン | Both |
| Remove a card / カードを消去 | Button on card / カード上のボタン | Both |
| Recall the past / 過去を呼び出す | Dedicated button / 専用ボタン | Both |

Shake intensity affects how much the field is shuffled. Stones do not move, regardless of shake intensity.  
振る強さによって、かき混ぜの程度が変わります。石は、振る強さに関わらず、動きません。

---

## Ambient Rhythm Model / 環境リズムモデル

The field changes with time. Individual rhythm is learned gradually from access patterns — never declared, never displayed.  
野原は時間とともに変化します。個人のリズムはアクセスパターンから徐々に学習されます——ユーザーに宣言されることも、表示されることもありません。

| Time / 時間帯 | Field character / 野原の性質 |
|---|---|
| Deep night 0–5h / 深夜 | Contracts. Close things become closer. / 収縮。近いものがより濃くなる |
| Morning 6–9h / 朝 | Standard. Fresh start. / 標準。新しい始まり |
| Midday 10–14h / 昼 | Practical content rises. / 実用的なコンテンツが浮上 |
| Afternoon 15–17h / 午後 | Steady focus. / 落ち着いた集中 |
| Evening 18–20h / 夕方 | The field begins to quiet. / 静かになり始める |
| Night 21–23h / 夜 | Reflective content surfaces. / 思索的なコンテンツが浮上 |

Social & current events are intentionally dimmed after 20h. The field protects rest.  
社会・時事カテゴリは20時以降に意図的に遠ざけられます。野原は休息を守ります。

---

## Tag Structure / タグ構造

Tags are divided into two layers:  
タグは二層に分かれています：

### Content Tags / コンテンツ系タグ
*Used at onboarding and bookmarking / オンボーディング時・ブックマーク時に使用*

| Category / カテゴリ | Tags / タグ |
|---|---|
| 思索と精神 / Mind & Philosophy | 哲学 / 心理 / 生きかた |
| ことばと物語 / Words & Stories | ことば / 詩 / 小説 / エッセイ / 民話 / 都市伝説 |
| 自然と宇宙 / Nature & Universe | 宇宙 / 生き物のふしぎ / 科学 |
| テクノロジーとつくる / Tech & Craft | テクノロジー / 工業 / つくる |
| 食と農 / Food & Farming | 料理 / 農業 |
| 暮らしの知恵 / Living Wisdom | 暮らしの知恵 / 教育 / コミュニティ / 環境 |
| いんたーねっとと雑学 / Web & Trivia | いんたーねっと / 雑学 |
| 社会と時事 / Society & Current Events | 政治 / 経済 / 社会 / 時事 / 事件・事故 |

### Emotional Tags / 感情系タグ
*Used at bookmarking only — not shown at onboarding / ブックマーク時専用——オンボーディングには表示しない*

Resonance, mood, and ambient tags:  
共鳴・気分・空気感のタグ：  
うんうん / 心が痛い / これが恋かしら？ / もふもふのいきもの / あとで読む / ひとやすみ / ゆるゆる / ふにゃー …

---

## Cluster Contribution Score / クラスタ貢献度スコア

Unlocks and notification sensitivity increase gradually. Contribution is never displayed as a number. Its effect is felt, not seen.  
アンロックと通知感度は段階的に上昇します。貢献度は数値として表示されません。その効果は感じられるものであり、見えるものではありません。

| Factor / 要素 | Description / 説明 | Cap / 頭打ち |
|---|---|---|
| 利用継続期間 | Time in the field / 野原にいた時間 | None / なし |
| タグ採用率 | % of your cluster using tags you introduced / 自分のタグがクラスタ内で使われた比率 | Yes / あり |
| インポート数 | External bookmarks brought in / 外部ブックマークの持ち込み数 | Yes / あり |
| タグ多様性スコア | Unique tag variety × selectivity ratio / ユニークタグ数 × 厳選度比率 | Yes / あり |

Tag adoption is measured by **cluster adoption rate, not absolute count** — preventing early-adopter advantage.  
タグ採用は**絶対数ではなくクラスタ内採用率**で評価されます——先行者利益を緩和するため。

---

## Revenue Model / 収益モデル

Subscription only. No advertising. No data sales.  
The service's interests must be aligned with the user's peace of mind.

サブスクリプションのみ。広告なし。データ販売なし。  
サービスの利益は、ユーザーの安心と一致していなければならない。

---

## Development Status / 開発状況

**Phase:** MVP Specification — Design Refinement  
**フェーズ：** MVP仕様定義——デザイン精緻化

**Multi-AI relay / マルチAIリレー:** Claude / Gemini / Perplexity / ChatGPT / Grok / Copilot  
**Human oversight / 人間による監督:** approval required at each session boundary / 各セッション境界で承認が必要

---

*The field is quiet. Come when you're ready.*  
*野原は静かです。準備ができたら、いつでも。*
