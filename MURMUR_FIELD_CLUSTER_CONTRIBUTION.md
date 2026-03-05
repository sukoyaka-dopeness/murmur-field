# MURMUR_FIELD_CLUSTER_CONTRIBUTION.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## Overview / 概要

The Cluster Contribution Score measures the depth and quality of a user's presence in their cluster — not their volume of activity.  
クラスタ貢献度スコアは、クラスタ内でのユーザーの存在の深さと質を測るものです——活動の量ではありません。

It is used as the primary axis for gradual unlock of notification sensitivity and features.  
通知感度と機能の段階的アンロックの主要軸として使用されます。

**The score is never shown to users as a number.**  
Its effect is felt through changes in the field — not read from a dashboard.  
**スコアはユーザーに数値として表示されません。**  
その効果は野原の変化として感じられるものであり、ダッシュボードで読むものではありません。

---

## Design Principles / 設計方針

- **Quality over quantity / 量より質** — volume of bookmarks is not a factor. Diversity and selectivity are.  
  ブックマーク数は評価対象外。多様性と厳選度を見る。

- **No early-adopter advantage / 先行者利益を排除** — tag adoption is measured by cluster adoption rate, not absolute count.  
  タグ採用は絶対数ではなくクラスタ内採用率で評価。

- **Caps prevent gaming / 頭打ちで恣意的な操作を防ぐ** — capped factors cannot be gamed by bulk actions.  
  頭打ちのある要素は大量操作によるスコア水増しを防ぐ。

- **Time cannot be faked / 時間は偽れない** — tenure is the only uncapped factor, and it accumulates naturally.  
  継続期間だけが頭打ちのない要素であり、自然に積み重なる。

---

## Score Composition / スコアの構成要素

### 1. 利用継続期間 / Tenure
*Time spent as a member of the field.*  
*野原のメンバーとして過ごした時間。*

| Property / 属性 | Value / 値 |
|---|---|
| Cap / 頭打ち | None / なし |
| Weight / 重み | Baseline — all other factors layer on top / ベースライン——他の要素はここに積み重なる |
| Rationale / 理由 | Time cannot be rushed or manufactured. It is the most honest signal of commitment. / 時間は急かしたり作り出したりできない。継続の意志を示す最も誠実なシグナル。 |

---

### 2. タグ採用率 / Tag Adoption Rate
*Percentage of your cluster that uses tags you introduced.*  
*自分が持ち込んだタグが、クラスタ内で使われている割合。*

| Property / 属性 | Value / 値 |
|---|---|
| Cap / 頭打ち | Yes / あり |
| Measurement / 計測方法 | Cluster adoption rate (%) — not absolute user count / クラスタ内採用率（%）——絶対ユーザー数ではない |
| Rationale / 理由 | A tag adopted by 30% of a small cluster is equally valued as one adopted by 30% of a large cluster. Late arrivals can contribute as meaningfully as early adopters. / 小さなクラスタで30%に採用されたタグは、大きなクラスタで30%に採用されたタグと同等に評価される。後から参加したユーザーも先行者と同様に貢献できる。 |

A tag "introduced" means: you were among the first users in your cluster to apply it.  
タグを「持ち込んだ」とは：そのクラスタ内で最初にそのタグを使ったユーザーの一人であることを指します。

---

### 3. インポート数 / Import Count
*Number of bookmarks imported from external services.*  
*外部サービスからインポートしたブックマーク数。*

| Property / 属性 | Value / 値 |
|---|---|
| Cap / 頭打ち | Yes / あり |
| Rationale / 理由 | Importing brings existing context and vocabulary into the cluster. Bulk importing beyond the cap adds no further contribution value. / インポートは既存の文脈と語彙をクラスタに持ち込む行為。頭打ちを超えた大量インポートはそれ以上の貢献価値を持たない。 |

Imported bookmarks are treated the same as manually saved bookmarks in all other respects.  
インポートされたブックマークは、その他の点ではすべて手動保存のブックマークと同等に扱われます。

---

### 4. タグ多様性スコア / Tag Diversity Score
*A composite of unique tag variety and selectivity.*  
*ユニークタグ数と厳選度の複合スコア。*

| Property / 属性 | Value / 値 |
|---|---|
| Cap / 頭打ち | Yes / あり |
| Formula (conceptual) / 計算式（概念） | Unique tag count × selectivity ratio |
| Selectivity ratio / 厳選度比率 | Stones placed ÷ total bookmarks / 石を置いた数 ÷ 総ブックマーク数 |

**Why selectivity? / なぜ厳選度を使うのか？**  
Users who bookmark everything score the same as users who bookmark nothing.  
Users who carefully mark what truly matters to them score higher.  
This rewards curation, not accumulation.  
すべてをブックマークするユーザーと、何もブックマークしないユーザーは同じスコアになります。  
本当に大切なものを丁寧にマークするユーザーが高く評価されます。  
これは蓄積ではなく、編纂を報酬にする設計です。

**Why unique tag count? / なぜユニークタグ数を使うのか？**  
A cluster benefits from diverse vocabulary, not repeated use of the same few tags.  
クラスタは同じタグの繰り返しではなく、多様な語彙から恩恵を受けます。

---

## Summary Table / サマリーテーブル

| Factor / 要素 | Cap / 頭打ち | Anti-gaming property / ゲーミング耐性 |
|---|---|---|
| 利用継続期間 / Tenure | None / なし | Time cannot be manufactured / 時間は作り出せない |
| タグ採用率 / Tag Adoption Rate | Yes / あり | Rate-based; late adopters equally valued / 率ベース；後発も平等 |
| インポート数 / Import Count | Yes / あり | Bulk import beyond cap has no value / 大量インポートは無効 |
| タグ多様性スコア / Tag Diversity Score | Yes / あり | Rewards curation not volume / 編纂を報酬にする |

---

## What the Score Unlocks / スコアが解放するもの

Specific thresholds are to be determined in beta testing.  
具体的な閾値はベータテストで決定します。

| Unlock / アンロック内容 | Rationale / 理由 |
|---|---|
| 通知感度の段階的上昇 / Gradual increase in notification sensitivity | New arrivals don't yet know how to read the wind. / 野原に来たばかりの人は、まだ風の読み方を知らない。 |
| 「つぶやき」の開放 / Enabling "つぶやき" comments | Requires 30-day onboarding grace period to pass first. / まずオンボーディング猶予期間（30日）の通過が必要。 |
| 将来的な機能アンロック / Future feature unlocks | To be defined in later phases. / 将来フェーズで定義。 |

---

## Pending Items / 未決事項

- Specific cap values for each capped factor / 各頭打ち要素の具体的な上限値
- Specific unlock thresholds / アンロックの具体的な閾値
- Exact formula weighting across all four factors / 4要素の具体的な重み付け
- Definition of "first users in cluster" for tag introduction / タグ持ち込みにおける「クラスタ内最初のユーザー」の定義

All numeric values are delegated to beta verification.  
すべての数値はベータ検証に委任します。

---

*END OF DOCUMENT*
