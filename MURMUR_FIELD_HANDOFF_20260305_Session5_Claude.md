# MURMUR_FIELD_HANDOFF_20260305_Session5_Claude.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## 0. このドキュメントについて / About This Document

This handoff is written for humans first, and AI second.  
If you are a developer, collaborator, or future contributor picking this up —  
welcome. Everything you need to understand this project is here and in the files listed below.  
このハンドオフは人間向けに書かれています。AIも読めます。  
開発者、協力者、または将来の貢献者として手に取ってくださった方——ようこそ。  
このプロジェクトを理解するために必要なことは、ここと以下のファイルに書かれています。

**Who built this / 誰が作ったか:**  
deadbody（鳩川カルキ / sukoyaka-dopeness）— independent creator, Japan-based.  
Not a developer. Not a company. Someone who got tired of the internet and decided to design the quiet place they wanted.  
開発者ではない。会社でもない。インターネットに疲れて、自分が欲しかった静かな場所を設計することにした人。

**Current status / 現在地:**  
MVP specification — design refinement. No code has been written yet.  
Everything here is design, philosophy, and specification.  
MVPの仕様定義——デザイン精緻化フェーズ。コードはまだ一行も書かれていない。  
ここにあるものはすべて、設計・思想・仕様だ。

---

## 1. Machine-Readable State / 機械可読ステート

```json
{
  "project_meta": {
    "name": "Murmur Field (マーマーフィールド)",
    "version": "2026.03.05-session5-claude",
    "current_mode": "linear",
    "core_priority": "思想継承優先"
  },
  "machine_readable_state": {
    "current_session_id": 5,
    "previous_actors": ["Gemini", "Copilot", "Perplexity", "Grok", "Claude", "Gemini", "Claude"],
    "current_actor": "next",
    "approval_required": true,
    "auto_loop_guard": true,
    "cost_mode": "zero_cost",
    "next_task": "Chain Reactionスコアの閾値を決める。その後、次フェーズへ。"
  },
  "compressed_state": "mode=linear;session=5;actor=next;approval=true;cost=zero;name=MurmurField"
}
```

---

## 2. What Murmur Field Is / マーマーフィールドとは何か

A social bookmarking service designed as an antithesis to overstimulating social media.  
炎上に疲れた人、数字に疲れた人、返信しなければという強迫に疲れた人のための、  
ソーシャルブックマークサービス。

**The three-line version:**  
You save what matters. The field breathes around you.  
Somewhere out there, someone found the same place. The grass stirs, just once.

**What makes it different:**
- No amplification — the architecture does not reward volume
- No notifications by default — presence instead of push
- Time-of-day rhythm — the field changes with your daily pace
- Fog of visibility — distant clusters are physically hard to see
- Vocabulary of care — no "delete", only "忘れる（forget）"

詳細は `README.md` を参照。

---

## 3. Document Map / ドキュメントマップ

このリポジトリのすべてのファイルと、読む順番の推奨。  
All files in this repository, with recommended reading order.

| 推奨順 | File | 内容 |
|---|---|---|
| 1 | `README.md` | プロジェクト概要。まずここから |
| 2 | `MURMUR_FIELD_PHILOSOPHY.md` | 設計思想。なぜこのサービスが存在するか |
| 3 | `MURMUR_FIELD_USER_STORY.md` | ユーザーの一日。体験のイメージ |
| 4 | `MURMUR_FIELD_VISUAL_INTERACTION.md` | カード・石・枯れ草・shakeの設計 |
| 5 | `MURMUR_FIELD_AMBIENT_RHYTHM_MODEL.md` | 時間帯×タグの相性テーブル。野原が時間とともに変わる仕組み |
| 6 | `MURMUR_FIELD_TAG_TAXONOMY.md` | タグの完全分類。コンテンツ系・感情系 |
| 7 | `MURMUR_FIELD_ONBOARDING_DESIGN.md` | オンボーディング設計 |
| 8 | `MURMUR_FIELD_COMMENTS_DESIGN.md` | ひとりごと・つぶやき・引用メモの設計 |
| 9 | `MURMUR_FIELD_CLUSTER_CONTRIBUTION.md` | クラスタ貢献度スコアの設計 |
| 10 | `MURMUR_FIELD_UNLOCK_DESIGN.md` | 段階的アンロックと「遠くまで散歩」モード |
| 11 | `MURMUR_FIELD_REVENUE_MODEL.md` | 収益モデルと価格設計 |
| 12 | このファイル | セッション5の決定事項と未決事項 |

---

## 4. Session 5 Decisions / セッション5の決定事項

| 決定内容 | WHY |
|---|---|
| 「引用メモ」の文字数上限：1200文字・多言語差は許容 | 引用メモは断片を書く場所であり長文を書く場ではない。英語圏でも「詰め込みすぎない上限」として機能する |
| 石カードの上限：5個・デバイス差なし統一 | 石の上限は認知的上限であり、PCの画面が広くても「大切なもの」は増えない |
| 厳選度比率：乗算→加算ボーナスに変更 | 乗算だと多保存ユーザーが構造的に不利になる。多様に保存するユーザーと厳選するユーザーの両方を平等に扱うため |
| 通知感度：じわじわ上昇（段階的） | 突然の気配にびっくりさせない。「気づいたら野原が少し賑やかになっていた」が理想 |
| 通知感度のトリガー：起動回数×スクロール時間の累計 | 起動だけでは「開いてすぐ閉じる」が稼げる。スクロールだけでは「放置」が稼げる。掛け合わせで「ちゃんと来て読んでいる」を計測 |
| 「遠くまで散歩」モード：解禁60日仮置き | 「つぶやき」解禁（30日）の2倍を感覚値として採用 |
| 「遠くまで散歩」にレジェンダリー層を統合 | 2つのモードボタンはメカニカルすぎる。「散歩に出ると古い記憶の場所に迷い込む」体験として自然に統合する |
| Q2カテゴリは「遠くまで散歩」でも踏み込まない | 散歩モードは安心して歩ける範囲を広げるものであって、霧を完全に消すものではない |
| GitHubトピックス10個確定 | social-bookmarking / bookmarking / slow-web / calm-technology / digital-wellbeing / ambient-social / anti-optimization / indie-web / no-notifications / resonance-over-reach |
| MVP期：無料のみ＋任意寄付 | プロダクトの価値を検証する前に誰かにお金を求めない |
| Phase 1+：300円／月（仮置き） | 「コーヒー一杯より安い」。疲れた人が躊躇なく払える金額 |
| 価格は円建て設定 | 現在の円安局面を海外ユーザー獲得の構造的優位として活用する |
| 収益余剰は寄付に回す | サービスの出発点の反映。コミュニティと透明性を持って寄付先を決定 |
| 石カードは課金軸にしない（永久） | 石は認知的上限であり課金の単位ではない。「お金を払えば大切なものが増える」設計はサービスの約束を破る |
| MURMUR_FIELD_PHILOSOPHY.md 新規作成完了 | セッション5の主要成果物 |
| MURMUR_FIELD_UNLOCK_DESIGN.md 新規作成完了 | セッション5の主要成果物 |
| MURMUR_FIELD_REVENUE_MODEL.md 新規作成完了 | セッション5の主要成果物 |

---

## 5. Pending Items / 未決事項

**Priority High / 優先度高：**
- Chain Reactionスコアの閾値——第二段階フィードバックのトリガー条件  
  （段階的アンロック閾値が先に固まったため、次のセッションで取り組める状態になった）

**Priority Medium / 優先度中：**
- 「つぶやき」猶予期間の最適値（7日・14日・30日でベータ検証推奨）
- 段階的アンロックの具体的な閾値（ベータ前の仮置き値）
- Type Bシグナルの具体的な倍率・キャップ値
- スクロール時間の計測方法（MVP実装フェーズで確認）
- レジェンダリー層の定義（「何ヶ月以上前」「共鳴スコアの閾値」）
- Phase 1ローンチ前の価格再検討プロセス
- 決済プラットフォームの選定
- AI庭師（Gardeners）のペルソナ詳細設計

**Priority Low / 優先度低・将来フェーズ：**
- 寄付先の具体的な選定基準
- 石カードのページアーカイブ（ストレージコスト検討）
- 星座・菌糸ビューの設計（Phase 1）
- 個人リズム学習アルゴリズム詳細（Phase 1）
- 年間プランの価格（導入する場合）

---

## 6. Philosophical Core / 設計思想コア（変更禁止 / DO NOT MODIFY）

- **増幅しない:** 設計は量を報酬にしない。最も大きな声を浮上させない。
- **霧の演出（Fog of Visibility）:** 遠いクラスタの声は物理的に不可視、または意味をなさない「ざわめき」として処理し、文脈の衝突を構造的に防ぐ。
- **バズより共鳴:** クラスタ内密度を価値の指標とする。
- **AI Gardeners:** AIは管理者ではなく「庭師」。良質な文化の種をまき、コミュニティが自走を始めたら存在感を消す。
- **ネガティブ・オンボーディング:** 「何が好きか」だけでなく「何から守られたいか（気分として）」を起点にフィルタリングを構築する。
- **静かに寄り添う:** サービスがユーザーの時間を支配するのではなく、ユーザーの時間のリズムにサービスが合わせる。
- **倫理ではなく物理を設計する:** 特定ユーザーを判定・排除するのではなく、増幅しない構造を作る。
- **静けさは逃避ではない:** ここで息を整えた人が、また外に出ていける。それだけを願っている。

---

## 7. For the Next Person / 次に手に取る人へ

Whether you are an AI or a human, a developer or a dreamer:  
AIであれ人間であれ、開発者であれ夢想家であれ：

This project was built by someone thinking out loud, one session at a time.  
The decisions are careful. The questions are honest.  
The things marked "pending" are genuinely unresolved — not forgotten.  
このプロジェクトは、一度のセッションずつ声に出しながら考えた人によって作られた。  
決定は丁寧だ。問いは誠実だ。「未決」と書かれているものは、忘れられたのではなく、本当にまだ解けていない。

If you build this: please keep it quiet.  
If you continue the design: please keep the questions open.  
If you just read it: thank you for spending time here.  
これを作るなら：静かなままでいてください。  
設計を続けるなら：問いを閉じないでください。  
ただ読んだなら：ここで時間を使ってくれてありがとう。

---

## 8. Rules for AI / AIへのルール

1. `approval_required: true` — アクション前に人間の承認を求める
2. Philosophical Core は変更しない
3. 未決事項の優先順位を人間と確認してから作業を始める
4. 決定事項を増やしたらSESSION_LOGに追記する
5. 全ドキュメントは英語・日本語の順で併記するバイリンガル形式で書く
6. コミットメッセージはConventional Commits形式を使う（`docs:` 等のプレフィックス）
7. このルールを次のAIにも引き継ぐこと

---

*The field is quiet. Come when you're ready.*  
*野原は静かです。準備ができたら、いつでも。*

---

*END OF DOCUMENT*
