# MURMUR_FIELD_AMBIENT_RHYTHM_MODEL.md

Version: 1.1 | Created: 2026-03-04 | Updated: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.1 | 作成: 2026-03-04 | 更新: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

Changes v1.0 → v1.1: bilingual format applied; noise ratio rule added; time × tag affinity table added.  
変更点 v1.0→v1.1: バイリンガル形式に変換；ノイズ比率一定ルールを追記；時間帯×タグ相性テーブルを追記。

---

## 1. Overview / 概要

The **Ambient Rhythm Model** is the design philosophy and implementation policy for "fluctuating distance" in Murmur Field.  
**Ambient Rhythm（環境リズム）モデル**とは、マーマーフィールドにおける「揺らぎ距離」の設計思想および実装方針です。

Based on the CORE PHYSICS principle that "distance does not fix — it fluctuates," the model dynamically changes the distance between clusters. There are two types of fluctuation:  
「距離は固定せず揺らぐ」というCORE PHYSICSに基づき、クラスタ間の距離を動的に変化させます。揺らぎには2種類あります。

- **Meaningful fluctuation / 有意な揺らぎ:** changes derived from user behaviour and environment.  
  ユーザーの行動・環境に由来する意味のある変化。
- **Random fluctuation (noise) / 無作為な揺らぎ（ノイズ）:** small random component to prevent echo chambers.  
  エコーチェンバー予防のための小さなランダム成分。

"Ambient" is like ambient music — not assertive, but certainly present.  
Closer to what Brian Eno meant by "music as environment" than to a notification system.  
「アンビエント」は音楽で言えば環境音——主張せず、でも確かにそこにある。  
Brian Enoが「空気のような音楽」と言ったのに近い感覚をアルゴリズムに込める。

---

## 2. Core Principle / 基本方針

> **"Fluctuation toward silence is strong. Fluctuation toward expansion is weak."**  
> **「静かにする方向への揺らぎは強く、広げる方向への揺らぎは弱く」**

Murmur Field's philosophy is not to amplify. Therefore the force pushing fluctuation toward "showing more" is always kept small. An asymmetric mixing ratio.  
マーマーフィールドの思想は増幅しないことであるため、揺らぎが「より多くを見せる」方向に働く力は常に小さく保つ。非対称な混合比。

---

## 3. Distance Symmetry / 距離の対称性

A being close to B does not mean B is close to A. Asymmetry is permitted.  
AがBに近くても、BからAが遠いという非対称を許容します。

Permitting asymmetry creates "directionality" within clusters. This is an intentional design feature.  
非対称を許容するとクラスタに「方向性」が生まれます。これは意図的な設計として活用します。

---

## 4. Meaningful Fluctuation — Layer Structure / 有意な揺らぎのレイヤー構造

### Layer 1: Time Axis / 時間軸

**Phase 0: Time-of-day and day-of-week based (fixed values)**  
**Phase 0：時刻・曜日ベース（固定値）**

| Time / 時間帯 | Distance fluctuation / 距離の揺らぎ | Experience / 体験 |
|---|---|---|
| Deep night 0–5h / 深夜 | Far becomes farther; near becomes denser / 遠くが遠くなる・近くが濃くなる | Quiet, introspective; cluster condenses / 静かで内省的、クラスタが凝縮する |
| Morning 6–9h / 朝 | Standard / 標準 | Normal distance / 通常の距離感 |
| Midday 10–14h / 昼 | Slightly expands / やや広がる | Distant things become faintly visible / 少し遠いものが薄く見える |
| Afternoon 15–17h / 午後 | Standard / 標準 | Steady focus / 落ち着いた集中 |
| Evening 18–20h / 夕方 | Begins to contract slowly / ゆっくり収縮し始める | Quieting toward end of day / 一日の終わりに向けて静かになる |
| Night 21–23h / 夜 | Contracted; reflective content surfaces / 収縮；思索的コンテンツが浮上 | Calm, contemplative / 穏やかで思索的 |

Day-of-week / 曜日:
- Sunday / 日曜日: Distances expand broadly; distant clusters sink deeper into fog. A gentle feed. / 全体的に距離が広がり、遠いクラスタが深く霧に沈む。穏やかなフィード。
- Friday night / 金曜夜: Fluctuation increases slightly. Chance encounters marginally increase. / 揺らぎがわずかに大きくなる。偶発的な出会いがわずかに増える。

**Phase 1: Individual access rhythm learning**  
**Phase 1：個人のアクセスリズム学習**

Access history is used to infer "is this person's late night an active or resting period?" and applied accordingly.  
アクセス履歴から「この人の深夜は活動時間か休息時間か」を推定して適用する。  
Night-shift users have their late night treated as "active hours."  
夜型ユーザーには深夜を「活動時間」として扱う。

> The service adapts to the user's rhythm. It does not colonise the user's time.  
> サービスがユーザーの時間を支配するのではなく、ユーザーの時間のリズムにサービスが合わせる。

---

### Layer 2: Behaviour Axis / 行動軸

- **Session length / 滞在時間の長さ:** Reading slowly → distance contracts; cluster becomes denser. / じっくり読んでいる日は距離が収縮し、クラスタが濃くなる
- **Bookmark frequency / ブックマーク頻度:** Saving many things in rapid succession → slight expansion (counter-intuitive by design). / 連続して大量保存しているときは少し広げる（逆張り）
- **Time since last access / 最後のアクセスからの経過時間:** Long absence → show slightly farther content on return ("welcome back" experience). / 久しぶりに来た人には少し遠くまで見せる（「おかえり」的体験）

---

### Layer 3: Content Axis / コンテンツ軸

- **Tag diversity / タグの多様性:** If today's saved articles have tags different from usual, expand fluctuation slightly. / その日読んだ記事のタグが普段と違うなら、揺らぎを少し広げる
- **Seasonal or limited-period tag resonance / 季節・期間限定タグとの共鳴度**

---

### Layer 4: Environment Axis / 環境軸（将来・推測扱い）

- **Device type / 端末の種類:** Smartphone = possibly in transit or resting → expand distance slightly. PC = settled in → contract distance. / スマートフォン＝移動中か休憩中として距離をやや広げる、PC＝腰を据えているとして収縮させる
- Based on inference; handle with care. Implementation from Phase 1 onwards. / 推測に基づくため扱いは慎重に。実装はPhase 1以降。

---

## 5. Time × Tag Affinity Table / 時間帯×タグ相性テーブル

This table is held internally by the algorithm. It is not exposed to users in any form.  
Language labels (e.g. "Active", "Relax") are internal only — the user experiences the result as visual and haptic changes in the field, not as labels.  
このテーブルはアルゴリズムが内部に保持します。いかなる形でもユーザーには表示されません。  
言語ラベル（例：「Active」「Relax」）は内部専用です——ユーザーはその結果を野原のビジュアルと振動の変化として体験します。ラベルとしてではありません。

★★★ = surfaces readily / 浮上しやすい  
★★ = standard / 標準  
★ = slightly receded / やや遠ざかる  
☆ = intentionally dimmed / 意図的に遠ざける

| Category / カテゴリ | Deep night 深夜 0–5h | Morning 朝 6–9h | Midday 昼 10–14h | Afternoon 午後 15–17h | Evening 夕方 18–20h | Night 夜 21–23h |
|---|---|---|---|---|---|---|
| 思索と精神 | ★★★ | ☆ | ★ | ★ | ★★ | ★★★ |
| ことばと物語 | ★★★ | ★ | ★ | ★★ | ★★ | ★★★ |
| 自然と宇宙 | ★★ | ★★ | ★★ | ★★ | ★★ | ★★ |
| テクノロジーとつくる | ★ | ★★ | ★★★ | ★★★ | ★★ | ★ |
| 食と農 | ☆ | ★★★ | ★★★ | ★★ | ★★★ | ★ |
| 暮らしの知恵 | ☆ | ★★★ | ★★★ | ★★ | ★★★ | ★ |
| いんたーねっとと雑学 | ★ | ★★ | ★★★ | ★★ | ★★ | ★★ |
| 社会と時事 | ☆ | ★★★ | ★★★ | ★★ | ★ | ☆ |

**Notes / 備考:**
- 自然と宇宙 is the lowest time-variance category — it surfaces consistently across all hours. / 自然と宇宙は時間帯による差が最も少ないカテゴリ——全時間帯で均等に浮上します。
- 社会と時事 is intentionally dimmed from 20h onward. The field protects rest. / 社会と時事は20時以降に意図的に遠ざけられます。野原は休息を守ります。
- All ★ values are relative weights, not absolute scores. Beta testing will calibrate. / すべての★は相対的な重みです。絶対スコアではありません。ベータテストで調整します。

---

## 6. Random Fluctuation (Noise) / 無作為な揺らぎ（ノイズ）

A small random component is applied to all users at all times.  
小さなランダム成分をすべてのユーザーに常時適用します。

**Purpose / 目的:** Prevent the distances of users with stable tags and follow relationships from becoming completely fixed. A preventive measure against echo chambers.  
タグ・フォロー関係が安定したユーザーの距離が完全固定化するのを防ぐ。エコーチェンバーの予防注射。

**Direction / 方向:** Noise operates only in the expanding direction. Noise toward silence is not needed.  
ノイズは「広げる方向」にのみ働かせます。静かにする方向へのノイズは不要。

**Ratio rule / 比率ルール:**  
As individual rhythm learning (Phase 1) becomes more precise, the noise ratio is held constant.  
個人リズム学習（Phase 1）の精度が上がっても、ノイズ比率は一定に保ちます。

> More precise learning does not mean a more perfectly predicted field.  
> The noise is a permanent structural feature, not a temporary compensation for imprecision.  
> 学習が精緻化しても、野原がより完璧に予測されることにはなりません。  
> ノイズは精度不足の一時的な補正ではなく、恒久的な構造的特徴です。

Mixing ratio (specific value): delegated to beta verification.  
混合比（具体的な数値）：ベータ検証に委任。

---

## 7. Mixing Ratio Design Policy / 混合比の設計方針

Specific weights for each layer are determined by beta testing. The following policies are fixed:  
各レイヤーの重みはベータ検証によって決定します。以下の方針のみ固定します：

1. Fluctuation toward silence > fluctuation toward expansion (asymmetry principle) / 静かにする方向の揺らぎ ＞ 広げる方向の揺らぎ（非対称原則）
2. The time axis layer carries the greatest weight (most intuitively understandable to users) / 時間軸レイヤーの重みが最も大きい（ユーザーが直感的に理解しやすいため）
3. Do not maximise all layers simultaneously (avoids becoming unpredictable) / 全レイヤーを同時に最大化しない（予測不能になりすぎることを避ける）
4. Users do not need to fully understand why something is visible, but they should be able to accept why something is not visible / ユーザーが「なぜこれが見えるのか」を完全に理解できなくてよいが、「なぜこれが見えないのか」には納得できる設計にする
5. Noise ratio remains constant regardless of learning precision / ノイズ比率は学習精度に関わらず一定に保つ

---

## 8. Rhythm Detection Signals / リズム検知シグナル

Signals used to learn individual access rhythm (Phase 1):  
個人のアクセスリズムを学習するために使用するシグナル（Phase 1）：

| Signal / シグナル | Adopted / 採否 | Rationale / 理由 |
|---|---|---|
| Access time distribution / アクセス時刻の分布 | ✅ | Core signal / コアシグナル |
| Session length / セッション長 | ✅ | Directly feeds Layer 2 behaviour axis / レイヤー2行動軸に直結 |
| Device type / デバイス種別 | ✅ | Low precision but useful auxiliary signal / 精度は低いが補助信号として有効 |
| Tag time-of-day pattern / タグの時間帯別傾向 | ✅ | Cross-learns with time × tag affinity table / 時間帯×タグ相性テーブルと相互学習 |
| Timezone / タイムゾーン | ❌ | Redundant when access time distribution is available / アクセス時刻分布があれば冗長 |

Learned rhythm is never declared or displayed to the user.  
学習されたリズムはユーザーに宣言されることも表示されることもありません。

---

## 9. Connection to「気分」Settings /「気分」設定との連動

When the user updates "adjust current mood" settings, Ambient Rhythm parameters update in real time.  
ユーザーが「いまの気分を調整する」設定を変更した場合、Ambient Rhythmのパラメータもリアルタイムに更新されます。

Settings change cost must be kept low. The button must be placed in a visible location on the user's page.  
設定変更のコストは低く保つ。マイページのわかりやすい場所に「いまの気分を調整する」ボタンを置く。

> If the word "mood" is used, the UI must reflect that change is a light action.  
> 「気分」という言葉を使う以上、変更が軽い動作であることがUIに表れていなければならない。

---

## 10. Pending Items / 未決事項

- Specific weights for each layer / 各レイヤーの具体的な重み（ベータ検証委任）
- Noise mixing ratio / ノイズの混入率（ベータ検証委任）
- Individual rhythm learning algorithm details / 個人リズム学習のアルゴリズム詳細（Phase 1設計時に決定）
- Adoption or rejection of Layer 4 (environment axis) / レイヤー4（環境軸）の採否

---

*END OF DOCUMENT*
