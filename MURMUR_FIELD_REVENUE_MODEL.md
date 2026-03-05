# MURMUR_FIELD_REVENUE_MODEL.md

Version: 1.0 | Created: 2026-03-05 | Author: Claude (Project-Relay-Hub AI relay)  
バージョン: 1.0 | 作成: 2026-03-05 | 記述者: Claude（Project-Relay-Hub AIリレー）

---

## Overview / 概要

This document defines the revenue model and pricing philosophy for Murmur Field.  
このドキュメントは、マーマーフィールドの収益モデルと価格設計の思想を定義します。

### Non-negotiable principles / 変更不可の原則

- No advertising. 広告なし。
- No data sales. データ販売なし。
- The service's interests must be aligned with the user's peace of mind.  
  サービスの利益は、ユーザーの安心と一致していなければならない。
- Core experience is equal for all users regardless of plan.  
  コア体験はプランに関わらずすべてのユーザーに平等である。

---

## 1. Phase Structure / フェーズ別収益構造

### MVP Phase / MVPフェーズ

**Model: Free only + voluntary donation**  
**モデル：無料のみ＋任意の寄付**

- All features available at no cost.  
  全機能を無料で提供。
- A donation button is placed unobtrusively in the interface.  
  インターフェースの目立たない場所に寄付ボタンを置く。
- No pressure, no guilt, no "please support us" banners.  
  プレッシャーなし、罪悪感なし、「応援してください」バナーなし。
- Intent: validate the product before asking anyone to pay.  
  意図：誰かにお金を求める前に、プロダクトの価値を検証する。

### Phase 1 and beyond / Phase 1以降

**Model: Freemium — free plan + paid plan**  
**モデル：フリーミアム——無料プラン＋有料プラン**

See `MURMUR_FIELD_UNLOCK_DESIGN.md` for the full breakdown of what is free and what is paid.  
無料と有料の詳細な内訳は `MURMUR_FIELD_UNLOCK_DESIGN.md` を参照。

---

## 2. Pricing / 価格設定

All prices are set in Japanese Yen.  
価格は日本円建てで設定する。

| Plan / プラン | Price / 価格 | Notes / 備考 |
|---|---|---|
| Free / 無料プラン | 0円 | Core experience, full and equal / コア体験フル・平等 |
| Paid / 有料プラン | 300円／月（仮置き） | Additional depth features / 深さの追加機能 |

**WHY 300円 / なぜ300円か:**  
「コーヒー一杯より安い」という感覚で設定できる価格帯。  
疲れた人が躊躇なく払える金額として設定した。  
"Cheaper than a cup of coffee." Set at a price a tired person can pay without hesitation.

---

## 3. International Pricing / 海外ユーザーへの価格

Prices are set in JPY and converted at the prevailing exchange rate at time of payment.  
価格は円建てで設定し、支払い時の為替レートで換算する。

| Currency / 通貨 | 300円の目安（2026年3月時点） |
|---|---|
| USD | 約2ドル |
| EUR | 約1.8ユーロ |
| GBP | 約1.5ポンド |

**円安戦略 / Yen depreciation strategy:**  
Murmur Field's bilingual design (English-first, Japanese-second) targets both Japanese and international users.  
During the current period of yen weakness, the JPY price point is exceptionally accessible for international users.  
This is not an intentional discount — it is a structural advantage to be used while it lasts.  
Early international user acquisition during this period builds a user base that persists when exchange rates normalise.

マーマーフィールドのバイリンガル設計（英語優先・日本語併記）は、国内外のユーザーを対象としている。  
現在の円安局面において、円建て価格は海外ユーザーにとって非常に手が届きやすい水準にある。  
これは意図的な値引きではなく、今のうちに活用すべき構造的な優位性だ。  
この局面での海外ユーザー獲得は、為替が正常化したあとも残るユーザーベースを形成する。

**Price revision policy / 価格改定ポリシー（仮置き）:**  
- Price revision is considered only when server costs consistently exceed paid revenue.  
  サーバーコストが有料収益を継続的に上回った場合にのみ、価格改定を検討する。
- Price revision is not triggered by exchange rate movements alone.  
  為替変動のみを理由とした価格改定は行わない。
- Any price revision must be announced at least 60 days in advance.  
  価格改定は最低60日前に告知する。

---

## 4. Cost Structure / コスト構造

| Phase / フェーズ | 想定サーバー費用／月 | 損益分岐ユーザー数（有料） |
|---|---|---|
| MVP | 3,000〜10,000円 | 10〜35人 |
| Phase 1（ML追加） | 20,000〜50,000円 | 70〜170人 |
| スケール後 | 要再試算 | 要再試算 |

**Phase 1 risk note / Phase 1のリスク:**  
Ambient Rhythm's individual learning model (Phase 1) introduces machine learning inference costs  
that are difficult to predict at MVP stage. Pricing should be reviewed before Phase 1 launch.  
Ambient Rhythmの個人学習モデル（Phase 1）はML推論コストを発生させる。  
このコストはMVP段階では予測が難しいため、Phase 1ローンチ前に価格を再検討する。

---

## 5. Surplus Revenue Policy / 収益余剰の方針

If monthly revenue consistently exceeds operational costs, the surplus is directed to donation.  
月次収益がランニングコストを継続的に上回った場合、余剰分を寄付に回す。

- Donation recipients and amounts will be decided transparently with the community.  
  寄付先と金額はコミュニティと透明性を持って決定する。
- This policy reflects the service's origins: built by someone who felt the weight of the internet,  
  for people who feel the same weight.  
  このポリシーはサービスの出発点を反映している：インターネットの重さを感じた人が、  
  同じ重さを感じる人のために作ったサービス。

---

## 6. What This Model Does Not Do / このモデルがしないこと

- Does not create pressure to upgrade. アップグレードのプレッシャーを生まない。
- Does not gate quietness behind a paywall. 静けさを有料の壁の後ろに置かない。
- Does not use engagement metrics to drive conversion. エンゲージメント指標をコンバージョンに使わない。
- Does not send "you're missing out on paid features" notifications.  
  「有料機能を使い損ねています」通知を送らない。

**WHY / なぜか:**  
A revenue model that creates anxiety in the user to extract payment  
is structurally identical to the problem this service exists to solve.  
ユーザーに不安を生じさせて課金を引き出す収益モデルは、  
このサービスが解決しようとしている問題と構造的に同一だ。

---

## 7. Pending Items / 未決事項

- Specific donation recipients and selection criteria / 寄付先の具体的な選定基準
- Phase 1 pricing review process / Phase 1ローンチ前の価格再検討プロセス
- Payment platform selection / 決済プラットフォームの選定
- Annual plan pricing (if introduced) / 年間プランの価格（導入する場合）
- Definition of "consistently exceeds" for surplus policy / 余剰方針における「継続的に上回る」の定義

---

*END OF DOCUMENT*
