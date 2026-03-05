# MURMUR_FIELD_COMMENTS_DESIGN.md

Version: 0.2 | Created: 2026-03-04 | Updated: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 0.2 | 作成: 2026-03-04 | 更新: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

Changes v0.1 → v0.2: three-stage meadow feedback model; comment notation support added; presence detection button and gradual unlock added.  
Changes v0.2 → bilingual: converted to English-first, Japanese-second format. No content changes.  
変更点 v0.1→v0.2: 連鎖フィードバックを3段階草原モデルに更新；コメント記法対応追加；気配察知ボタン・段階的アンロック追加。  
変更点 v0.2→バイリンガル版: 英語・日本語の順で併記する形式に変換。内容変更なし。

---

## 1. Comment Types / コメント種別の定義

Comments are categorised at the time of posting. **The category cannot be changed after posting.**  
コメントは投稿時に種別を選択します。**種別は投稿後に変更できません。**

| Type / 種別 | Display name / 表示名 | Reach / 到達範囲 | Notes / 備考 |
|---|---|---|---|
| Fully private / 完全私的 | ひとりごと | Self only / 自分のみ | Completely invisible to others / 外から一切見えない |
| Cluster-facing / クラスタ向け | つぶやき | Same cluster with distance decay / 同クラスタ・距離減衰あり | Clearer when close; foggy when far / 近いほど明瞭、遠いほど霧 |
| Content-attached / コンテンツ添付 | 引用メモ | Tied to content with distance decay / コンテンツに紐づく・距離減衰あり | No replies; not shown as a collection / 返信不可・集合非表示 |

---

## 2. Post-Publish Category Policy / 投稿後の種別変更ポリシー

**Comments are fixed at the privacy setting at time of writing.**  
**コメントは書いた時点の公開設定で固定します。**

- Converting「ひとりごと」to「つぶやき」requires an explicit individual operation.  
  「ひとりごと」→「つぶやき」への変換は、個別に明示的な操作が必要。
- Changing global settings does **not** retroactively apply to past comments.  
  設定をグローバルに変更しても、**過去のコメントには遡及しない**。
- Reason: to prevent accidental publication of「ひとりごと」. The sense of safety is the foundation of the service.  
  理由：意図せず「ひとりごと」が公開される事故を防ぐため。安心感がサービスの根幹。

### Per-comment Category Selection / コメントごとの種別選択

In the bookmarking UI, the user can select「ひとりごと／つぶやき／引用メモ」per comment.  
ブックマーク時のUI上で、コメントごとに「ひとりごと／つぶやき／引用メモ」を選択できる。  
The default follows the user's global settings, but can be overridden per post.  
デフォルトはユーザー設定に従うが、投稿単位でオーバーライド可能。

---

## 3. Default Settings and Onboarding / デフォルト設定とオンボーディング

### Onboarding Grace Period / オンボーディング猶予期間（検証対象仮説）

> A design with no precedent in other services. Beta verification required.  
> 他サービスに前例のない設計。ベータで検証が必要。

- During the **first 30 days** after registration, all comments are forced to「ひとりごと」.  
  登録後 **最初の30日間**、全コメントが「ひとりごと」に強制固定。
- From day 31, a switch to "allow つぶやき" appears.  
  31日目以降に「つぶやきを許可する」スイッチが現れる。
- Intent: designed so the user first becomes comfortable safely, then voluntarily finds the courage to open up.  
  意図：まず安全に慣れてから、自発的に勇気を出す設計。

**Verification items / 検証項目：**
- Percentage of users who transition to「つぶやき」after the grace period / 猶予期間後に「つぶやき」に移行するユーザーの割合
- Retention rate during the grace period / 猶予期間中の定着率
- Optimal length of grace period (is 30 days appropriate?) / 猶予期間の長さの最適値（30日が適切か）

---

## 4. Comment Notation / コメント記法

Creating an environment where people who write longer comments (those who read carefully) can write comfortably.  
Excessive formatting does not suit the quietness of Murmur Field, so only the minimum notation is supported.  
長めのコメントを書く人（じっくり読んだ人）が書きやすい環境を整える。  
装飾過多はマーマーフィールドの静けさと合わないため、最小限の記法のみ対応する。

**Supported / 対応記法：**
- `> quotation` / `> 引用`（クォーテーション）
- `**bold**` / `**太字**`
- Bullet list / 箇条書き（`-`）
- Code block / コードブロック（技術系クラスタ向け）

**Not supported / 非対応：** All HTML tags / HTMLタグ全般

---

## 5. Chain Feedback — No-number Notification Design / 連鎖フィードバック（数字を出さない通知設計）

### Principle / 原則

- No notification of "reached ◯ people" / 「◯人に届きました」という数値通知は出さない
- No notification of "who it reached" / 「誰に届いたか」も出さない
- **Only presence and meadow phenomena are returned. / 気配と草原の現象だけを返す。**

### Three-Stage Meadow Feedback Model / 3段階草原フィードバックモデル

#### Stage 1: First Bookmark / 第一段階：最初のブックマーク（発見者）
When you are the first person to save a page that nobody has bookmarked yet.  
誰もブックマークしていないページを最初に保存したとき。

> A single blade of grass sways quietly on the card.  
> 草が一本、静かに揺れる。

A thin blade of grass sways gently on the card — a single animation.  
No number. No words. "You were the first to find this place."  
カード上に細い草が一本だけそっと揺れるアニメーション。  
数字なし、言葉なし。「あなたが最初にここを見つけた」という意味。

#### Stage 2: First Following Bookmark / 第二段階：最初の追っかけブックマーク
The most important feedback. Communicated clearly.  
最も重要なフィードバック。はっきり伝える。

> "There are signs that someone has also come to the place you found."  
> 「あなたが見つけた場所に、誰かも来た気配があります」

A second blade of grass grows on the card, or a small ripple appears. **Shown once only.**  
カード上に二本目の草が生えるアニメーション、または小さな波紋。**一度だけ表示。**

When the reaction comes from outside the cluster: the grass colour or texture differs slightly.  
"A somehow different kind of presence" — only enough difference to convey that.  
クラスタ外からの反応の場合：草の色や質感がわずかに異なる。  
「なにか違う種類の気配」が伝わる程度の差分にとどめる。

#### Stage 3: Subsequent Following / 第三段階：その後の追っかけ
A persistent, quiet icon at the edge of the card on the user's page.  
マイページの隅に、持続的で静かなアイコン。  
The grass increases slightly, or a faint light stays on. Does not move frequently. Shows no count.  
草が少しずつ増える、または淡い光が点灯したまま。頻繁に動かない。数を示さない。

**Even if 100 people have bookmarked it, the display does not change.** By design, that information does not exist in the system.  
**100人超えても表示は変わらない。** 仕様上、その情報は存在しないことにする。

---

## 6. Presence Detection — Notification Design / 気配察知（通知設計）

### Pull-type Notification / プル型通知
Presence drifts in only when the "sense presence" button is pressed.  
「気配を察知」ボタンを押したときだけ、気配が漂ってくる。  
Not push-type — only those who actively come receive it.  
プッシュ型ではなく能動的に来た人だけが受け取れる設計。

### Push Notification / プッシュ通知
- Default: **Off / オフ**
- The user may optionally turn it on. / ユーザーが任意でオンにできる

### Gradual Unlock / 段階的アンロック
Notification sensitivity is set low at the start of the service. Sensitivity rises as the user becomes accustomed.  
サービス開始直後は通知感度を低く設定する。慣れてきた頃に感度が上がっていく。

> People who have just arrived in the meadow do not yet know how to read the wind.  
> 草原に来たばかりの人は、まだ風の読み方を知らない。

Unlock axes (pending / to be verified): tenure / bookmark count / cluster contribution score  
アンロックの軸（未決・要検証）：利用期間 / ブックマーク数 / クラスタへの貢献度

---

## 7. No Replies, No Collections / 返信・集合の非生成

- No reply function / 返信機能なし
- No comment collection page / コメント集合ページなし
- No "◯ comments" display / 「◯件のコメント」表示なし
- Quote comments are tied to the target content but not shown as a collection / 引用コメントは対象コンテンツに紐づくが、集合として見せない

---

## 8. UI Enjoyment / UIの楽しみ（spec追記用メモ）

Areas currently thin in the spec, to be incorporated into Phase design:  
現行specに薄い部分として、以下をPhase設計に組み込む。

| Item / 項目 | Platform / 対応環境 | Phase |
|---|---|---|
| Keyboard navigation (J/K to move etc.) / キーバインドナビゲーション（J/Kで移動等） | PC | Phase 0 |
| Haptic feedback on bookmark / ブックマーク時の触覚フィードバック | Mobile / スマートフォン | Phase 0 |
| Meadow animation (chain feedback) / 草原アニメーション（連鎖フィードバック） | Both / 両方 | Phase 0 |
| Constellation / mycelium view (own cluster visualisation) / 星座・菌糸ビュー（自クラスタの可視化） | Both / 両方 | Phase 1 |
| Monthly feedback visual representation / 月次フィードバックのビジュアル表現 | Both / 両方 | Phase 1 |

The joy of touch and UI rhythm prevents dropout. Tumblr's keybindings and the snappy feel of RSS readers create an experience where "rhythm emerges in the act of reading." Smartphone haptics ritualise the act of bookmarking.  
触る楽しみ・UIのリズムが離脱を防ぐ。Tumblrのキーバインド、RSSリーダーのサクサク感は「読む行為にリズムが生まれる」体験。スマートフォンのhapticはブックマークという行為を儀式化する。

---

## 9. Pending Items / 未決事項

- Character limit for「引用メモ」/「引用メモ」の文字数制限
- Detailed UI for individual conversion from「ひとりごと」to「つぶやき」/「ひとりごと」から「つぶやき」への個別変換UIの詳細
- Trigger conditions for Stage 2 feedback (Chain Reaction score threshold) / 第二段階フィードバックのトリガー条件（Chain Reactionスコアの閾値）
- Optimal length of onboarding grace period (30 days provisional, requires verification) / オンボーディング猶予期間の長さ（30日仮置き・要検証）
- Determination of gradual unlock axes / 段階的アンロックの軸の決定

---

*END OF DOCUMENT*
