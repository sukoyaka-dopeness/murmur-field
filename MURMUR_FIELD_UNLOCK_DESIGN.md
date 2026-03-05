# MURMUR_FIELD_UNLOCK_DESIGN.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## Overview / 概要

This document defines the gradual unlock system for Murmur Field —  
what unlocks, when, and why.  
このドキュメントは、マーマーフィールドの段階的アンロックシステムを定義します——  
何が、いつ、なぜアンロックされるか。

### Core Principle / 設計原則

> People who have just arrived in the meadow do not yet know how to read the wind.  
> 草原に来たばかりの人は、まだ風の読み方を知らない。

Unlocks are not rewards for performance. They are a gradual introduction to the depth of the field.  
アンロックはパフォーマンスへの報酬ではない。野原の深さへの、段階的な招待だ。

**Non-negotiable constraints / 変更不可の原則：**

- The core experience is equal for all users, regardless of plan or contribution score.  
  コア体験はすべてのユーザーに平等である。プランや貢献度スコアに関わらず。
- Stone card limit (5) is never a paid feature. Stones are a cognitive limit, not a product tier.  
  石カードの上限（5個）は有料機能にしない。石は課金の単位ではなく、認知的な上限だ。

---

## 1. Unlock Items / アンロック項目一覧

| Item / 項目 | Free / 無料 | Paid / 有料 | Unlock trigger / アンロック条件 |
|---|---|---|---|
| ブックマーク保存 | 無制限 | 無制限 | 登録直後から |
| 石カード（上限5個） | ✅ | ✅ | 登録直後から |
| ひとりごと（完全私的コメント） | ✅ | ✅ | 登録直後から |
| 「遠くまで散歩」モード | ✅ | ✅ | 貢献度スコア閾値（60日仮置き） |
| つぶやき（クラスタ向けコメント） | ✅ | ✅ | 猶予期間経過（30日仮置き） |
| 通知感度の段階的上昇 | ✅ | ✅ | 起動回数×スクロール時間の累計 |
| 石カードのページアーカイブ | ❌ | ✅ | 有料プラン加入 |
| 星座・菌糸ビュー（Phase 1） | ❌ | ✅ | 有料プラン加入 |
| ブックマークのエクスポート | 制限あり | 無制限 | 有料プラン加入 |
| 個人リズムの詳細レポート（Phase 1） | ❌ | ✅ | 有料プラン加入 |

---

## 2. Trigger Axes / トリガー軸

アンロックのトリガーは2種類ある。  
There are two types of unlock trigger.

### Type A: Time-based / 時間ベース

- **利用継続期間（日数）** がメイン軸。時間は偽れない。  
  **Tenure (days)** is the primary axis. Time cannot be manufactured.
- すべてのアンロックはこの軸を基準に動く。  
  All unlocks move against this axis as baseline.

### Type B: Engagement-based / エンゲージメントベース

メイン軸に対して低倍率で加味する。頭打ち（キャップ）あり。  
Applied at low multiplier on top of the time axis. All capped.

| Signal / シグナル | Role / 役割 | Cap / キャップ |
|---|---|---|
| 起動回数 × スクロール時間の累計 | 通知感度のトリガー | あり |
| タグ多様性スコア | アンロックを若干早める補助信号 | あり |
| タグ採用率（クラスタ内） | アンロックを若干早める補助信号 | あり |
| インポート数 | アンロックを若干早める補助信号 | あり |

**設計意図 / Rationale:**  
時間を積み重ねれば最低限アンロックされる。良い使い方をしていれば少し早く開く。  
Anyone who stays long enough will unlock. Good usage opens things a little sooner.

---

## 3. Unlock Timeline / アンロックのタイムライン（仮置き値）

All numeric values are provisional. Beta verification required.  
すべての数値は仮置き。ベータ検証が必要。

```
登録
  │
  ├─ Day 0       コア体験フル開放（ブックマーク・石・ひとりごと）
  │
  ├─ Day 30      「つぶやき」解禁スイッチが現れる
  │              （7日・14日・30日の三段階でベータ検証推奨）
  │
  ├─ Day 30〜    通知感度がじわじわ上昇
  │              （起動回数×スクロール時間の累計に連動）
  │
  └─ Day 60      「遠くまで散歩」モード解禁
                 （「つぶやき」解禁期間の2倍を仮置き値として採用）
```

---

## 4. 「遠くまで散歩」モード / Wander Mode

### What it is / 概要

A pull-type interaction — the user initiates, the field responds.  
プル型インタラクション——ユーザーが起点になり、野原が応答する。

When activated, the field temporarily extends its visible range beyond the user's usual cluster,  
surfacing content from nearby clusters and occasionally from the Legendary layer.  
起動すると、フィールドは通常のクラスタを超えて一時的に可視範囲を広げ、  
近隣クラスタのコンテンツ、そしてときおりレジェンダリー層のコンテンツを浮上させる。

### What it shows / 何を見せるか

| Layer / 層 | Description / 説明 |
|---|---|
| 近隣クラスタ | 普段より少し遠いが、Q2（遠ざけたい話題）には抵触しないクラスタ |
| レジェンダリー層 | 過去に共鳴を集め、今は静かに沈んでいるブックマーク。「野原の古い記憶」 |

### What it never shows / 絶対に見せないもの

- Q2「少し遠ざけておきたい気分の話題」として設定されたカテゴリ  
  Categories the user designated as "topics to keep distance from" in onboarding Q2
- 全く未知の遠方クラスタ（霧は完全には晴れない）  
  Completely unknown distant clusters — the fog never fully lifts

### Design rationale / 設計意図

> 散歩に出ると、たまに古い記憶の場所に迷い込む。  
> When you go for a walk, you sometimes wander into a place from old memory.

「遠くまで散歩」と「野原の古い記憶」は別モードではなく、同一体験の中に統合する。  
These are not two separate modes — the Legendary layer surfaces naturally within the wander experience.

---

## 5. Notification Sensitivity / 通知感度

### Principle / 原則

Sensitivity rises gradually. Users are not startled by sudden presence.  
感度はじわじわ上がる。突然の気配にびっくりさせない。

「気づいたら野原が少し賑やかになっていた」という体験が理想。  
The ideal is: "I noticed the field had become a little more alive."

### Trigger / トリガー

```
通知感度 ∝ 起動回数の累計 × スクロール時間の累計
```

**実装メモ / Implementation note:**  
「スクロール時間」の計測はMVPでは実装コストが高い場合、  
セッション長（ログインからログアウトまでの時間）で代替可。  
If measuring scroll time is costly in MVP, session length may substitute.

### What sensitivity unlocks / 感度が上がると何が変わるか

感度が低い：Chain Reactionの第二段階フィードバック（誰かが同じ場所に来た気配）がほぼ届かない  
感度が高い：他者の気配を受け取れる範囲が広がる

数値による表示は一切なし。変化は野原の視覚的・触覚的フィードバックとして感じられる。  
No numerical display at any level. Changes are felt through visual and haptic field feedback.

---

## 6. What Is Never Unlocked by Money / お金でアンロックされないもの

以下は有料プランでも変わらない。価格改定時も不変。  
The following do not change with any paid plan. Non-negotiable in all future iterations.

- 石カードの上限数（5個）  
  Stone card limit (5)
- コメント種別の選択権（ひとりごと・つぶやき・引用メモ）  
  Comment type selection (ひとりごと / つぶやき / 引用メモ)
- Q2「遠ざけたい話題」の設定が尊重されること  
  Respect for Q2 "topics to keep distance from" settings
- フィールドの静けさそのもの  
  The quietness of the field itself

**WHY / なぜか:**  
「お金を払えば静けさが増す」という設計は、  
「疲れた人が平等に息をできる場所」という約束を破る。  
A design where "paying buys more quietness" breaks the promise  
of "a place where tired people can breathe equally."

---

## 7. Pending Items / 未決事項

- 「つぶやき」猶予期間の最適値（7日・14日・30日でベータ検証）
- 「遠くまで散歩」解禁の具体的な閾値（60日は仮置き）
- 通知感度の段階数（何段階でじわじわ上げるか）
- Type Bシグナルの具体的な倍率・キャップ値（ベータ検証委任）
- スクロール時間の計測方法（MVP実装フェーズで確認）
- レジェンダリー層の定義（「何ヶ月以上前」「共鳴スコアの閾値」など）

---

*END OF DOCUMENT*
