# MURMUR_FIELD_VISUAL_INTERACTION.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## Overview / 概要

This document defines the visual behaviour and interaction design of the Murmur Field interface.  
All visual effects are derived from user needs — not applied as decoration.  
このドキュメントは、マーマーフィールドのインターフェースにおける視覚的な振る舞いとインタラクション設計を定義します。  
すべての視覚効果はユーザーが必要とする機能から逆算して定義されます——装飾として付加するものではありません。

---

## 1. Card Motion / カードの動き

### Principle / 原則

Cards are not static. The field breathes.  
But the field does not exhaust. Motion is occasional, not constant.  
カードは静止していません。野原は息をしています。  
しかし野原は疲れさせません。動きはときおり起こるものであり、常時ではありません。

### Normal Card Behaviour / 通常カードの振る舞い

- Cards rest in a near-static state by default.  
  カードはデフォルトでほぼ静止した状態にあります。
- A randomised wind event triggers a subtle sway on individual cards.  
  ランダムなタイミングで「風」が発生し、カードが微細に揺れます。
- Sway parameters:  
  揺れのパラメータ：
  - Amplitude / 振れ幅: 2–3px
  - Duration / 持続時間: approximately 0.3 seconds / 約0.3秒
  - Frequency / 発生頻度: random interval, 5–30 seconds per card / カードごとにランダム、5〜30秒間隔
  - Cards do not sway simultaneously — offsets are randomised. / 複数のカードが同時に揺れないよう、タイミングをずらす
- Implementation: CSS animation + randomised JavaScript timer. Lightweight; suitable for MVP.  
  実装：CSSアニメーション＋ランダムJavaScriptタイマー。軽量——MVPに適しています。

### Stone Card Behaviour / 石カードの振る舞い

- `animation: none` — stones do not move under any circumstance.  
  `animation: none`——石はいかなる状況でも動きません。
- The contrast between swaying cards and a still stone is the core visual metaphor of the field.  
  揺れるカードと静止した石のコントラストが、野原の核心的な視覚メタファーです。
- Stones remain still even during shake gestures (see section 4).  
  shakeジェスチャー中も石は動きません（セクション4参照）。

---

## 2. Place a Stone / 石を置く

### What it means / 意味

To place a stone is to mark something as permanently present in your field —  
not because it is popular, but because it matters to you.  
石を置くとは、何かを野原の中で永続的に存在させることです——  
人気があるからではなく、自分にとって大切だから。

### Trigger / トリガー

- Long press on a card / カードを長押し
- Confirmed with a single additional tap if desired (to prevent accidental placement) / 誤操作防止のため、確認タップを1回追加することも可（要検討）

### Visual Change / 視覚的変化

- The card takes on a visually heavier, more grounded appearance.  
  カードが視覚的に重く、地に足のついた外観になります。
- Subtle texture or shadow change to suggest physical weight.  
  物理的な重さを示唆する、わずかなテクスチャまたはシャドウの変化。
- Animation stops. The card becomes completely still among moving neighbours.  
  アニメーションが停止します。揺れる隣のカードの中で、完全に静止します。
- No number, label, or badge is added.  
  数字・ラベル・バッジは一切追加されません。

### Position in Field / フィールド内の位置

- Stones remain within the field flow — they are not pinned to the top of a list.  
  石はフィールドの流れの中にとどまります——リスト上部への固定ではありません。
- Their stillness within a moving field is what makes them findable.  
  動くフィールドの中での静止そのものが、石を見つけやすくします。

---

## 3. Release a Stone / 石をはずす

### Principle / 原則

Releasing a stone should be possible but not accidental.  
石をはずすことは可能でなければなりませんが、誤操作であってはなりません。

### Trigger / トリガー

- Long press on a stone card → button appears: **「石をはずす」**  
  石カードを長押し → ボタンが現れる：**「石をはずす」**
- Single tap on the button to confirm. No further confirmation dialog.  
  ボタンをシングルタップで確定。追加の確認ダイアログは不要。

### Visual Change / 視覚的変化

- The card gently resumes the normal sway behaviour.  
  カードがそっと通常の揺れの振る舞いを再開します。
- No dramatic animation. The stone simply becomes grass again.  
  劇的なアニメーションはありません。石は静かに、また草に戻るだけです。

---

## 4. Withered Grass / 枯れ草

### What it means / 意味

When a link dies, its card does not disappear.  
It becomes withered grass — present, textured, a record of something that once was.  
リンクが切れたとき、カードは消えません。  
枯れ草になります——存在し、質感を持ち、かつてあったものの記録として。

### Trigger / トリガー

Link survival check runs at two moments only:  
リンク生存確認は、以下の2つの瞬間にのみ実行されます：

1. On first bookmark save / 新規ブックマーク保存時
2. When the user presses「思い出す」to recall past cards / ユーザーが「思い出す」を押して過去のカードを呼び出したとき（オンデマンド方式）

### Visual Change / 視覚的変化

- Card texture shifts to suggest dryness, fading, or weathering.  
  カードのテクスチャが、乾燥・褪色・風化を示唆するものに変化します。
- Link is rendered non-interactive (not clickable).  
  リンクは非インタラクティブ（クリック不可）になります。
- The card continues to sway if it was a normal card, or remain still if it was a stone.  
  通常カードであれば引き続き揺れ、石であれば引き続き静止します。
- No error icon. No warning label. The visual texture speaks for itself.  
  エラーアイコンなし。警告ラベルなし。テクスチャが語ります。

### User Choice / ユーザーの選択

The withered card remains until the user decides.  
枯れ草カードはユーザーが決断するまで残ります。

| Choice / 選択 | Action / 操作 | Result / 結果 |
|---|---|---|
| Keep / 残す | Do nothing / 何もしない | Card stays as withered grass — a record of fading. / 枯れ草として残る——移ろいの記録。 |
| Forget / 忘れる | Tap「忘れる」button on card | Card quietly disappears. No confirmation dialog. / カードが静かに消える。確認ダイアログなし。 |

---

## 5. Forgetting / 忘れる

### Scope / 適用範囲

「忘れる」is the unified vocabulary for removing any card from the field.  
「忘れる」は、野原からカードを消去するための統一された語彙です。

| Context / 文脈 | Confirmation / 確認 |
|---|---|
| Normal card / 通常カード | 1 additional action required / 1アクション追加が必要 |
| Withered grass card / 枯れ草カード | No confirmation — loss has already occurred / 確認なし——すでに喪失は起きている |

The word 「削除」is not used anywhere in the interface.  
「削除」という言葉はインターフェースのどこにも使いません。

---

## 6. Shake Gesture / shakeジェスチャー

### What it means / 意味

Shaking the device reshuffles the visible field —  
bringing different cards to the surface through ambient rhythm and chance.  
端末を振ると、フィールドが再シャッフルされます——  
環境リズムと偶然によって、異なるカードが浮上してきます。

This is a pull-type interaction: the user initiates. The field responds.  
これはプル型のインタラクションです：ユーザーが起点になり、野原が応答します。

### Behaviour / 振る舞い

- Shake intensity maps to reshuffle depth.  
  振る強さが、かき混ぜの深さに対応します。
  - Gentle shake / 軽く振る: minor reshuffle, nearby cards surface / 軽いシャッフル。近くのカードが浮上
  - Strong shake / 強く振る: deeper reshuffle, more distant cards may appear / 深いシャッフル。より遠いカードが現れる可能性がある
- Stone cards do not move regardless of shake intensity.  
  石カードは振る強さに関わらず動きません。
- The gesture is available in field view only.  
  このジェスチャーはフィールド閲覧中のみ有効です。

### Conflict Avoidance / 衝突回避

- Shake gesture is automatically disabled when a text input field is focused.  
  テキスト入力フィールドにフォーカスがある場合、shakeジェスチャーは自動的に無効化されます。
- This prevents conflict with comment entry (「ささやき」input).  
  これにより、コメント入力（「ささやき」入力）との衝突を防ぎます。
- Implementation detail to be confirmed at development phase (OS/framework dependent).  
  実装の詳細は開発フェーズで確認が必要です（OS・フレームワーク依存）。

---

## 7. Presence Feedback / 気配フィードバック

*Defined in detail in MURMUR_FIELD_COMMENTS_DESIGN.md. Summary only.*  
*詳細はMURMUR_FIELD_COMMENTS_DESIGN.mdに記載。ここではサマリーのみ。*

### Three-Stage Meadow Feedback / 3段階草原フィードバック

| Stage / 段階 | Trigger / トリガー | Visual / 視覚表現 |
|---|---|---|
| 1st — Discovery / 発見 | First person to bookmark this URL / そのURLを最初にブックマークした人 | A single blade of grass sways quietly on the card / カード上で草が一本、静かに揺れる |
| 2nd — First follower / 最初の追っかけ | First other person bookmarks the same URL / 別の誰かが初めて同じURLをブックマーク | A second blade grows, or a small ripple appears. Shown once only. / 二本目の草が生える、または小さな波紋。一度だけ表示。 |
| 3rd — Continued presence / 継続的な気配 | Further bookmarks by others / その後の追っかけ | A persistent quiet icon at the edge of the card. Does not grow beyond this. / カード端に持続的で静かなアイコン。これ以上は増えない。 |

No numbers at any stage. No names. Presence only.  
どの段階でも数字なし。名前なし。気配だけ。

---

## 8. Pending Items / 未決事項

- Final visual direction for withered grass texture / 枯れ草テクスチャの最終的なビジュアル方向性
- Stone card visual treatment (texture / shadow specifics) / 石カードのビジュアル処理（テクスチャ・シャドウの具体的な仕様）
- Whether accidental stone placement warrants a confirmation step / 石の誤置き防止のための確認ステップの要否
- Shake gesture conflict resolution — implementation verification / shakeジェスチャー衝突回避の実装確認（開発フェーズ）
- Haptic feedback design for mobile (stone placement, 忘れる, shake) / モバイルでの触覚フィードバック設計（石を置く・忘れる・shake）

---

*END OF DOCUMENT*
