# IMPLEMENTATION_NOTES.md
# 実装ノート

---

## Purpose of this document / このドキュメントの目的

This document provides technical and UX implementation guidance for builders working with the ima-mode specification. It also records all items that are pending expert review or require implementor judgment.

このドキュメントでは、ima-mode仕様書をもとに実装するビルダーへの技術的・UX的なガイダンスを提供します。また、専門家の監修待ち、または実装者の判断が必要な項目をすべて記録します。

---

## Platform targets / プラットフォームターゲット

| Form / 形式 | Technology / 技術 | Status / ステータス |
|-------------|------------------|-------------------|
| Smartphone app / スマートフォンアプリ | React Native or Flutter / React NativeまたはFlutter | Planned / 予定 |
| PDF workbook / PDFワークブック | — | Planned / 予定 |
| Card kit / カードキット | — | Planned / 予定 |

---

## Data handling / データ取り扱い

| Rule / ルール | Detail / 詳細 |
|--------------|--------------|
| Storage / ストレージ | Local only / ローカルのみ |
| Encryption / 暗号化 | Required / 必須 |
| Analytics / 分析 | None / なし |
| Third-party SDKs / サードパーティSDK | None / なし |
| Default retention / デフォルト保持期間 | 1 day, then auto-delete / 1日後に自動削除 |
| User-selectable retention / ユーザー選択可能な保持期間 | Yesterday view; history view / 昨日表示；履歴表示 |

No data is transmitted outside the device. No third-party analytics or tracking SDKs may be included.

デバイス外へのデータ送信は行いません。サードパーティの分析・トラッキングSDKを含めることはできません。

---

## UX specifications / UX仕様

### Board / ボード
- **"Alone mode" (だれもいないモード)** is displayed at the visual center of the board.
  **「Alone mode」(だれもいないモード)** はボードの視覚的中心に表示されます。
- All modes are connected to the center with lines.
  すべてのモードは線で中心と接続されます。
- The phrase *"These are all part of you." / 「全部があなたの一部」* is displayed persistently on the board.
  「全部があなたの一部」というフレーズはボード上に常時表示されます。

### Visible modes / 表示モード数
- 5–7 cards visible on the board at any time.
  ボード上に常時5〜7枚のカードを表示。
- Up to 50–100 modes stored internally.
  内部には最大50〜100のモードを保存。

### Session completion UI / セッション完了UI
When a mode card entry is completed, the following sequence occurs:

モードカードへの入力が完了したとき、以下の順序で表示されます：

1. Haptic feedback / ハプティクスフィードバック
2. Completion message / 完了メッセージ："Saved" (残せました)
3. Two buttons / 2つのボタン：
   - "＋" → Next mode card / 次のモードカードへ
   - "That's enough for today" (今日はここまで) → Return to board / ボードに戻る

The completion message and button labels carry no punctuation, in keeping with the soft tone of the app.

完了メッセージとボタンラベルには句点をつけない。アプリの柔らかいトーンに合わせるためです。

Note: English translations of "残せました" and "今日はここまで" are provisional. Final copy should be verified by a native English speaker with knowledge of the project's tone.

注：「残せました」「今日はここまで」の英語訳は暫定です。最終的な文言はプロジェクトのトーンを理解した英語ネイティブによる確認を推奨します。

### Deletion / 削除
- One-tap full delete is always visible.
  ワンタップ全削除は常時表示。

### Panic dummy screen / パニックダミースクリーン
- Trigger: two-finger simultaneous tap / トリガー：2本指同時タップ
- No text on the dummy screen / ダミースクリーン上に文言なし
- Explained once during onboarding or in settings / オンボーディングまたは設定画面で一度だけ説明する
- Design principle: the dummy screen should look like a screen that anyone might ordinarily have open. A plain single-color screen is unnatural and should be avoided.
  設計方針：ダミースクリーンは誰でも日常的に開いている可能性がある画面に見えることが望ましい。単色の画面は不自然であり避けること。
- See TBD_FOR_IMPLEMENTORS for candidate screen types.
  候補画面の種類についてはTBD_FOR_IMPLEMENTORSを参照。

### Session flow / セッションフロー
- Entry: time-appropriate neutral greeting (morning / daytime / evening).
  開始：時間帯に応じた中立的な挨拶（朝・昼・夜）。
- Exit: user returns to board via "That's enough for today" (今日はここまで) and closes the app freely.
  終了：「今日はここまで」でボードに戻り、ユーザーが自由にアプリを閉じる。

### Mode suggestion / モード提案
- On demand only. No push notifications. No proactive suggestions.
  オンデマンドのみ。プッシュ通知なし。積極的な提案なし。

### Haptics / ハプティクス
- Triggered on successful mode card entry.
  モードカードへの記録完了時にトリガー。
- Quality target: gentle, satisfying — the feeling of having recorded safely, not the feeling of achievement.
  質感のターゲット：穏やかで心地よい——達成感ではなく、安全に記録できた安心感。
- Reference: Duolingo-style haptic feedback pattern.
  参考：Duolingo的なハプティクスフィードバックのパターン。

---

## Mode versioning / モードのバージョン管理

Mode name candidate lists are version-managed across all categories (e.g. v1.0, v2.0). When the list is updated, the version number is incremented. Previous versions are retained for reference.

モード名候補リストは全カテゴリを対象にバージョン管理されます（例：v1.0、v2.0）。リストが更新された場合はバージョン番号が増加します。以前のバージョンは参照用に保持されます。

---

## Child safety / 子どもの安全

- Parents and teachers do not have full data access to a child's records.
  親や教師は子どもの記録への完全なデータアクセスを持ちません。
- The panic dummy screen is particularly important in child and adolescent contexts.
  パニックダミースクリーンは、子ども・青年のコンテキストにおいて特に重要です。

---

## Expert review required / 専門家の監修が必要な項目

The following items must not be finalized without input from qualified professionals (mental health, crisis intervention, or related fields).

以下の項目は、資格を持つ専門家（メンタルヘルス、危機介入、または関連分野）の意見なしに確定させてはなりません。

| Item / 項目 | Detail / 詳細 |
|------------|--------------|
| Crisis threshold / クライシス閾値 | At what point, if any, should the app respond differently to user input? What response is appropriate? / アプリがユーザーの入力に対して異なる対応をすべき閾値はあるか？適切な対応は何か？ |
| "Wanting to speak with someone who is no longer here" mode / 「いまはもういない人と語りたいモード」 | Safety and ethical notes for this mode; UX considerations for grief and loss proximity; limits of the transparent mirror principle in this context. / このモードの安全・倫理的注記；悲嘆・喪失への近接性に関するUX上の配慮；このコンテキストにおける透明な鏡原則の限界。 |
| Grief and loss UX / 悲嘆・喪失のUX | General UX considerations when the tool is used in proximity to grief or bereavement. / ツールが悲嘆や死別に近接した形で使用される場合の全般的なUX配慮。 |

---

## To be determined by implementors / 実装者が判断する項目

The following items are left to implementor judgment, based on local context, user research, or post-launch data.

以下の項目は、地域の文脈・ユーザーリサーチ・ローンチ後のデータに基づき、実装者の判断に委ねられます。

| Item / 項目 | Detail / 詳細 |
|------------|--------------|
| Crisis threshold implementation / クライシス閾値の実装 | Once expert guidance is received, implementation details are left to the implementor. / 専門家のガイダンスを受けた後、実装の詳細は実装者に委ねる。 |
| mode vs. state A/B test / mode vs. state A/Bテスト | Whether to use "mode" or "state" in English-language UI copy should be tested post-launch. The specification uses "mode" as default. / 英語UIでmodeとstateのどちらを使うかはローンチ後にテストする。仕様書ではmodeをデフォルトとして使用。 |
| Locale-specific crisis hotline numbers / ロケール別クライシスホットライン番号 | Replace placeholder with local numbers during localization. / ローカライズ時にプレースホルダーを地域の番号に置き換える。 |
| Culture-specific mode names / 文化固有のモード名 | Add or adapt mode names to reflect local relational contexts. See CULTURAL_LAYER.md. / 地域の関係的文脈を反映するモード名を追加・適応させる。CULTURAL_LAYER.mdを参照。 |
| Panic dummy screen content / パニックダミースクリーンの中身 | The screen should resemble an app that anyone might ordinarily have open. Candidate types: note-taking app style / calendar style / weather app style. Final choice left to implementor. / 誰でも日常的に開いている可能性があるアプリに見える画面が望ましい。候補：メモ帳風 / カレンダー風 / 天気予報風。最終的な選択は実装者に委ねる。 |

---

## Non-goals reminder / NON_GOALSリマインダー

Any implementation of ima-mode must not:

ima-modeのいかなる実装も以下を行ってはなりません：

- Diagnose mental health conditions / 精神的な状態を診断すること
- Provide therapeutic advice / 治療的なアドバイスを提供すること
- Assign scores or ratings to relational states / 関係性の状態にスコアや評価を与えること
- Monitor users over time to draw conclusions / 時系列でユーザーをモニタリングして結論を出すこと
- Transmit user data outside the device / ユーザーデータをデバイス外に送信すること
- Include third-party analytics or tracking / サードパーティの分析・トラッキングを含めること
