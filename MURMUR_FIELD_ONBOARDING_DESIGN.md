# MURMUR_FIELD_ONBOARDING_DESIGN.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

Supersedes: MURMUR_FIELD_ONBOARDING_DESIGN.md (prior session v0.1). Fully rewritten in bilingual format with session 4 decisions incorporated.  
前バージョン: MURMUR_FIELD_ONBOARDING_DESIGN.md（前セッション v0.1）を置き換えます。セッション4の決定事項を反映し、バイリンガル形式で全面改訂。

---

## 1. Design Principles / 設計方針

### Core Principles / 原則

- 2–3 questions are enough. More causes dropout.  
  質問は2〜3問で十分。多いと離脱する。

- Make it explicit that skipping is allowed. Tell users from the start that they can use the service without answering.  
  スキップ可を明示する。答えなくても使えることを最初に伝える。

- Use the language of **"mood"** rather than "what you dislike." Mood is allowed to change.  
  「何が嫌いか」ではなく**「気分」**という言語を使う。気分は変わってよい。

### The Meaning of "Mood" / 「気分」という言語の意味

Defined not as a fixed "like/dislike" but as a state that is allowed to change.  
固定的な「好き嫌い」ではなく、変化してもよい状態として定義する。

This connects directly to the Ambient Rhythm Model's philosophy of "distance does not fix."  
これはAmbient Rhythmモデルの「距離は固定しない」思想と直接つながる。

---

## 2. Onboarding Questions / オンボーディング質問

### Q1: Topics you are interested in right now? / いま興味のある話題は？

Multiple selection + free text input  
複数選択 ＋ 自由入力

→ Sets initial cluster position / クラスタの初期位置を決める

### Q2: Topics you feel like keeping a little distance from? / 少し遠ざけておきたい気分の話題は？

Multiple selection + free text input + **skippable**  
複数選択 ＋ 自由入力 ＋ **スキップ可**

→ Sets initial fog thickness / 霧を厚くする方向の初期値

This phrasing has a freshness rarely seen in web services — that quality is itself a feature.  
この文言はウェブサービスであまり見かけない表現であり、その斬新な手触り感は設計上の特徴として活かします。

### Q3: What time of day do you think you will mainly use Murmur Field? / マーマーフィールドを主に使いそうな時間帯は？

Single selection: 朝 / 昼 / 夜 / 深夜 / バラバラ  
（Morning / Midday / Night / Deep night / Varies）

→ Sets initial Ambient Rhythm parameters / Ambient Rhythmの初期パラメータに使う

The word "mainly" lowers the psychological barrier to choosing "Varies."  
「主に」という言葉が入ることで、「バラバラ」を選ぶ心理的ハードルが下がります。

---

## 3. Category Presets for Q1 and Q2 / 問1・問2のカテゴリプリセット

Q1 and Q2 share the same category list and are treated symmetrically.  
問1と問2は同じカテゴリリストを使用し、対称的に扱います。

Category names in onboarding are **softened display names** — distinct from the formal category names in TAG_TAXONOMY. Individual tags within each category appear only at bookmark time.  
オンボーディングでのカテゴリ名は**やわらかい表示名**を使用します——TAG_TAXONOMYの正式カテゴリ名とは区別します。各カテゴリ内の個別タグはブックマーク時にのみ表示されます。

### Display Order and Names / 表示順と表示名

| Order / 順 | Onboarding display name / オンボーディング表示名 | TAG_TAXONOMY name / TAG_TAXONOMY正式名 |
|---|---|---|
| 1 | ことば・物語 | ことばと物語 |
| 2 | 哲学・こころ | 思索と精神 |
| 3 | 自然・宇宙 | 自然と宇宙 |
| 4 | ウェブ・雑学 | いんたーねっとと雑学 |
| 5 | テクノロジー・ものづくり | テクノロジーとつくる |
| 6 | 料理・食・農 | 食と農 |
| 7 | 暮らし・教育 | 暮らしの知恵 |
| 8 | ニュース・時事 | 社会と時事 |

### Rationale for Order / 並び順の根拠

Arranged from psychologically close to psychologically distant, with the heaviest category last.  
心理的に近いものから遠いものへ。最後に重いカテゴリを置く。

- 「ニュース・時事」is placed last so that users who want to skip it can do so without it dominating the list.  
  「ニュース・時事」を最後に置くことで、遠ざけたいユーザーがリストに支配されることなくスキップできる。
- 「社会と時事」→「ニュース・時事」: removing the word "社会" reduces the heaviness in the context of Q2 ("topics to keep distance from").  
  「社会と時事」→「ニュース・時事」：「社会」という言葉を外すことで、問2（遠ざけたい話題）の文脈での重さが消えます。

---

## 4. Ease of Changing Settings / 設定の変更しやすさ

If the word "mood" is used, the UI must reflect that change is a light action.  
「気分」という言葉を使う以上、設定変更が**軽い動作**であることがUIに表れていなければならない。

- Place an "adjust current mood" button in a clearly visible location on the user's page.  
  マイページのわかりやすい場所に「いまの気分を調整する」ボタンを置く。
- Do not bury it deep inside "profile settings."  
  「プロフィール設定」の奥深くに埋めない。
- No "are you sure?" confirmation required when changing settings.  
  変更のたびに「本当によいですか？」確認は不要。

---

## 5. Meadow Explanation at End of Onboarding / オンボーディング最後の草原説明

Shown once only at the end of onboarding. Concise.  
オンボーディングの最後に一度だけ、簡潔に説明する。

> "When someone finds the same place as you, the grass stirs softly. No numbers appear. Only a presence."  
> 「誰かがあなたと同じ場所を見つけたとき、草がそっと揺れます。数字は出ません。気配だけです。」

This explanation is necessary because without understanding the meadow animations and "presence" signals, the feedback system does not function for the user.  
ユーザーが草原のアニメーションや「気配」通知の意味を理解していないと、フィードバックが機能しない。そのためこの説明が必要です。

---

## 6. Gradual Unlock / 段階的アンロック

### Onboarding Grace Period / オンボーディング猶予期間

During the **first 30 days** after registration, all comments are forced to「ひとりごと」.  
登録後 **最初の30日間**、全コメントが「ひとりごと」に強制固定。

From day 31, a switch to "allow つぶやき" appears.  
31日目以降に「つぶやきを許可する」スイッチが現れる。

> People who have just arrived in the meadow do not yet know how to read the wind.  
> 草原に来たばかりの人は、まだ風の読み方を知らない。

Starting with too many "presences arriving" from the beginning risks creating the same psychological dependency as number-based metrics. Sensitivity increases naturally as the user becomes accustomed.  
最初から「気配がたくさん来る」状態にすると、数字依存と同じ心理が発生するリスクがある。慣れてきた頃に感度が上がっていく。

Unlock axes (to be determined in beta testing):  
アンロックの軸（ベータテストで決定）：
- 利用継続期間 / Tenure
- タグ多様性スコア / Tag diversity score
- タグ採用率 / Tag adoption rate

See `MURMUR_FIELD_CLUSTER_CONTRIBUTION.md` for full specification.  
詳細は `MURMUR_FIELD_CLUSTER_CONTRIBUTION.md` を参照。

---

## 7. First-time「忘れる」Notice / 初回「忘れる」予告

When a user uses「忘れる」for the first time, a notice is shown once only — then never again.  
ユーザーが初めて「忘れる」を使ったとき、一度だけ予告メッセージを表示します——2回目以降は表示しません。

### Notice Text / メッセージ文案

> "This card will be forgotten from your field. This cannot be undone."  
> 「このカードを野原から忘れます。取り消しはできません。」

　［忘れる］　　［やめておく］

### Scope / 適用範囲

| Context / 文脈 | First-time notice / 初回予告 | Subsequent / 2回目以降 |
|---|---|---|
| Normal card / 通常カード | ✅ Shown once | No confirmation |
| Withered grass card / 枯れ草カード | ✅ Shown once (independently) | No confirmation |

The「初回」count is tracked independently for normal cards and withered grass cards.  
「初回」のカウントは通常カードと枯れ草カードで独立して管理します。

**Implementation note / 実装メモ:** Whether to unify or separate the two counts is to be confirmed at development phase.  
2つのカウントを統一するか独立させるかは開発フェーズで確認が必要です。

---

## 8. Visual Tone / ビジュアルトーン

Delegated to the UI design phase. Not defined in this document.  
UIデザインフェーズに委任します。本ドキュメントでは定義しません。

---

## 9. Pending Items / 未決事項

- Optimal length of onboarding grace period (30 days provisional — requires beta verification) / オンボーディング猶予期間の長さ（30日仮置き・要検証）
- Specific unlock thresholds for gradual unlock axes / 段階的アンロックの軸の具体的な閾値
- Whether the first-time「忘れる」count is unified or independent across card types / 初回「忘れる」カウントの統一・独立の判断（開発フェーズ）

---

*END OF DOCUMENT*
