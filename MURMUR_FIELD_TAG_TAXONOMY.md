# MURMUR_FIELD_TAG_TAXONOMY.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## Overview / 概要

Tags in Murmur Field are divided into two layers with distinct roles.  
マーマーフィールドのタグは、役割の異なる二層に分かれています。

**Layer 1 — Content Tags / コンテンツ系タグ**  
Used to define interests and distances at onboarding, and to categorize bookmarks.  
オンボーディング時に興味と距離を定義するために使用し、ブックマークの分類にも使います。

**Layer 2 — Emotional Tags / 感情系タグ**  
Used only at bookmarking time, to capture mood and resonance at the moment of saving.  
ブックマーク保存時のみ使用。保存した瞬間の気分や共鳴を記録するためのものです。

Tags do not carry time-of-day attributes visible to users.  
The algorithm holds an internal time × tag affinity table.  
タグはユーザーに見える時間帯属性を持ちません。  
時間帯×タグの相性テーブルはアルゴリズムが内部に保持します。

---

## Layer 1: Content Tags / コンテンツ系タグ

### Design Principle / 設計方針

- Used in onboarding Q1 (interests) and Q2 (distance preferences).  
  オンボーディング問1（興味）・問2（遠ざけたい気分）に使用。
- Q1 and Q2 share the same tag list — treated symmetrically.  
  問1と問2は同じタグリストを使用——対称的に扱います。
- Category names are used in onboarding UI. Individual tags appear at bookmarking.  
  オンボーディングUIではカテゴリ名を使用。個別タグはブックマーク時に表示。

---

### 1. 思索と精神 / Mind & Philosophy

| Tag (JA) | Tag (EN) |
|---|---|
| 哲学 | Philosophy |
| 心理 | Psychology |
| 生きかた | Ways of Living |

---

### 2. ことばと物語 / Words & Stories

*Merged from original categories 7 (Language) and 8 (Fiction & Imagination).*  
*元カテゴリ7（言語）と8（物語と空想）を統合。*

| Tag (JA) | Tag (EN) |
|---|---|
| ことば | Words |
| 詩 | Poetry |
| 小説 | Fiction |
| エッセイ | Essays |
| 民話 | Folklore |
| 都市伝説 | Urban Legends |

**Excluded / 除外:**  
- `ささやき` — reserved as a service feature name / サービス機能名として使用するため除外

---

### 3. 自然と宇宙 / Nature & Universe

| Tag (JA) | Tag (EN) |
|---|---|
| 宇宙 | Universe |
| 生き物のふしぎ | Wonders of Life |
| 科学 | Science |

**Time affinity note / 時間帯相性メモ:**  
Low time-of-day variance. Displayed consistently across all hours.  
時間帯による差が少ないカテゴリ。全時間帯で均等に浮上します。

---

### 4. テクノロジーとつくる / Tech & Craft

| Tag (JA) | Tag (EN) |
|---|---|
| テクノロジー | Technology |
| 工業 | Industry |
| つくる | Making |

---

### 5. 食と農 / Food & Farming

*Merged from 料理 (Cooking) in original category 5 and 農業 (Farming) in category 6.*  
*元カテゴリ5の「料理」と、カテゴリ6の「農業」を統合して新設。*

| Tag (JA) | Tag (EN) |
|---|---|
| 料理 | Cooking |
| 農業 | Farming |

---

### 6. 暮らしの知恵 / Living Wisdom

*林業 (Forestry) and 水産業 (Fisheries) excluded for MVP due to limited audience.*  
*「林業」「水産業」はMVPでは対象ユーザー層が限定的なため除外。*

| Tag (JA) | Tag (EN) |
|---|---|
| 暮らしの知恵 | Living Wisdom |
| 教育 | Education |
| コミュニティ | Community |
| 環境 | Environment |

---

### 7. いんたーねっとと雑学 / Web & Trivia

| Tag (JA) | Tag (EN) |
|---|---|
| いんたーねっと | Internet |
| 雑学 | Trivia |

---

### 8. 社会と時事 / Society & Current Events

*Newly added in session 4. Reflects the need to include — and optionally distance from — news and public affairs.*  
*セッション4で新設。ニュース・時事情報を含める、または意図的に遠ざけるニーズに対応。*

| Tag (JA) | Tag (EN) |
|---|---|
| 政治 | Politics |
| 経済 | Economy |
| 社会 | Society |
| 時事 | Current Events |
| 事件・事故 | Incidents & Accidents |

**Time affinity note / 時間帯相性メモ:**  
Intentionally dimmed after 20h. The field protects rest.  
20時以降は意図的に遠ざけられます。野原は休息を守ります。

---

## Layer 2: Emotional Tags / 感情系タグ

### Design Principle / 設計方針

- Shown only at bookmark save time. Never used in onboarding.  
  ブックマーク保存時のみ表示。オンボーディングには使用しません。
- Captures the emotional state or resonance at the moment of saving.  
  保存した瞬間の感情状態・共鳴を記録します。
- Multiple emotional tags may be applied to a single bookmark.  
  一つのブックマークに複数の感情タグを付けられます。

---

### Resonance Tags / 共鳴タグ

| Tag (JA) | Tag (EN) | Nuance / ニュアンス |
|---|---|---|
| 興味深い | Intriguing | Intellectual curiosity / 知的好奇心 |
| なるほどですね | I see | Quiet understanding / 静かな納得 |
| うんうん | Nodding | Gentle agreement / 穏やかな共感 |
| ぷんぷん | Upset | Mild frustration / 軽い苛立ち |
| 心が痛い | Heartache | Empathetic pain / 共感的な痛み |
| ほしい | I want this | Desire / 欲求 |
| これが恋かしら？ | Is this love? | Unexpected fascination / 思いがけない惹かれ方 |
| 愛してる | Love you | Deep affection / 深い愛着 |
| 読んだ | Read | Completion / 読了記録 |
| 読みたい | Want to read | Future intent / 未来の意図 |
| お得情報 | Good deal | Practical value / 実用的な価値 |

---

### Ambient Tags / 空気感タグ

*Playful, sound-like, or atmospheric — the untranslatable texture of the field.*  
*音感・雰囲気・翻訳不能な野原の質感。*

| Tag (JA) | Tag (EN equivalent) |
|---|---|
| ゆるゆる | Yuru-Yuru |
| ふにゃー | Funya- |
| ウェイウェイプー | Wei-Wei-Poo |
| ニャーンですね | Meow-esque |
| ウワー | Uwaa- |

---

### Special Tags / 特別枠タグ

| Tag (JA) | Tag (EN) | Note / 備考 |
|---|---|---|
| もふもふのいきもの | Fluffy Friends | Soft creatures / 柔らかい生き物への愛着 |
| あとで読む | Read Later | Quick capture / クイック・キャプチャ用 |
| ティータイム | Tea Time | Leisurely browsing / のんびり閲覧用 |
| ひとやすみ | Quiet Pause | Gentle rest / 静かな休憩 |
| リラックス | Relax | Unwinding / くつろぎ |
| おさかな | Fish | Transferred from content tags — affection rather than topic / コンテンツ系から移動。話題ではなく愛着 |

---

## Excluded Tags / 除外タグ

| Tag (JA) | Reason / 除外理由 |
|---|---|
| ささやき | Reserved as a service feature name / サービス機能名と重複 |
| 林業 | Niche audience — excluded from MVP onboarding / 対象ユーザー層が限定的——MVPのオンボーディングから除外 |
| 水産業 | Niche audience — excluded from MVP onboarding / 対象ユーザー層が限定的——MVPのオンボーディングから除外 |

*林業 and 水産業 may be reconsidered as user-generated tags in later phases.*  
*「林業」「水産業」は将来フェーズでユーザー生成タグとして再検討可能。*

---

## Onboarding Usage Summary / オンボーディングでの使用サマリー

| Onboarding Question / 問 | Tag layer used / 使用タグ層 | Granularity / 粒度 |
|---|---|---|
| Q1: Topics of interest / 興味のある話題 | Content tags — category level / コンテンツ系——カテゴリ単位 | 8 categories |
| Q2: Topics to keep distance from / 遠ざけたい気分の話題 | Content tags — category level / コンテンツ系——カテゴリ単位 | Same 8 categories |
| Bookmark time / ブックマーク時 | Content tags (individual) + Emotional tags / コンテンツ系（個別）＋感情系 | Full list |

---

*END OF DOCUMENT*
