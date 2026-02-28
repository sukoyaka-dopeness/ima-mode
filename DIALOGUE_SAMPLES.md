# DIALOGUE_SAMPLES.md
# ダイアログサンプル

---

## About this document / このドキュメントについて

This document is a supplementary appendix to DIALOGUE_ENGINE.md and IMPLEMENTATION_NOTES.md. It collects concrete dialogue examples, UX copy, and question pool samples to convey the tone and texture of ima-mode in practice.

このドキュメントはDIALOGUE_ENGINE.mdおよびIMPLEMENTATION_NOTES.mdの補足付録です。ima-modeの実際のトーンと質感を伝えるための、具体的なダイアログ例・UX文言・質問プールサンプルを収録します。

**Language note / 言語について**
Dialogue samples in this document are provided in Japanese only. The tone and relational nuance of these samples are culturally specific and do not translate directly. For localization, machine translation is a practical starting point, but cultural adaptation is strongly recommended. See CULTURAL_LAYER.md.

このドキュメントのダイアログサンプルは日本語のみで記載されています。これらのサンプルのトーンと関係的ニュアンスは文化固有のものであり、直訳には適しません。ローカライズにはAI翻訳を出発点として使用できますが、文化的な再作成を強く推奨します。CULTURAL_LAYER.mdを参照。

---

## 1. Time-based greetings / 時間帯別挨拶

| Time / 時間帯 | English (provisional) / 英語（暫定） | Japanese / 日本語 |
|--------------|--------------------------------------|-----------------|
| Morning / 朝 | Good morning | おはよう |
| Daytime / 昼 | Hello | こんにちは |
| Evening / 夜 | Good evening | こんばんは |

No personalization. No reference to previous sessions.
パーソナライズなし。前回のセッションへの言及なし。

*(Time-based greetings are subject to localization. Some cultures do not distinguish greetings by time of day. See CULTURAL_LAYER.md.)*
*(時間帯別挨拶はローカライズの対象です。時間帯で挨拶を変える習慣が薄い文化圏もあります。CULTURAL_LAYER.mdを参照。)*

---

## 2. Onboarding copy / オンボーディング文言

### Concept cards / コンセプトカード

| # | English / 英語 | Japanese / 日本語 |
|---|---------------|-----------------|
| 1 | "You don't have to be the same person all the time." | 「あなたは、いつも同じじゃなくていい。」 |
| 2 | "A place to simply see yourself, right now." | 「ただ、いまの自分を見る場所。」 |
| 3 | "We don't give you answers." | 「答えは出しません。」 |

### Privacy card / プライバシーカード

**Heading (plain language) / 見出し（平易）**
- EN: "Your records belong to you alone."
- JP:「あなたの記録は、あなただけのものです。」

**Detail (formal) / 詳細（正式）**
- EN: "This app uses local storage only and is encrypted. No data is transmitted to third parties or used for analysis. Records are automatically deleted after one day by default."
- JP:「本アプリはローカルストレージのみを使用し、暗号化されています。第三者への送信、分析への使用は一切行いません。デフォルトで1日後に自動削除されます。」

### Crisis card / クライシスカード

**Entry (plain language) / 入口（平易）**
- EN: "If you are feeling very distressed right now."
- JP:「もし今、とてもつらい気持ちがあれば。」

*Crisis contact: localized by implementor. / 危機相談窓口：ローカライズ実装者に委ねる。*

---

## 3. Tone confirmation dialog / トーン確認ダイアログ

*Shown once during onboarding, and available via settings. / オンボーディング時に一度だけ表示。設定からも変更可能。*

| Tone / トーン | Japanese / 日本語 |
|--------------|-----------------|
| Easy / 易しい | 「この話し方でいい？変えられるよ」 |
| Standard / ふつう | 「話し方、今のままでいい？」 |
| Adult / 大人向け | 「口調を変えましょうか？」 |

---

## 4. Layer 2 suggestion dialog / Layer 2提案ダイアログ

*Offered once only, in response to a single-session signal. / 単発セッションシグナルへの反応として一度だけ提案。*

| Tone / トーン | Japanese / 日本語 |
|--------------|-----------------|
| Easy / 易しい | 「このモード、〇〇なときとも似てる？」 |
| Standard / ふつう | 「このモード、〇〇のときと近い気がする。分けてみる？」 |
| Adult / 大人向け | 「このモードに〇〇という側面もありますか。」 |

---

## 5. Mode name suggestion dialog / モード名提案ダイアログ

*Offered on demand when the user describes a context. / ユーザーが文脈を説明したときにオンデマンドで提案。*

### A: User describes a person / ユーザーが人物を説明するとき

**User input example / ユーザー入力例：**「最近よく会う職場の先輩がいて…」

| Tone / トーン | Japanese / 日本語 |
|--------------|-----------------|
| Easy / 易しい | 「その先輩といるときモード、作ってみる？」 |
| Standard / ふつう | 「その先輩といるときモード、名前にしてみますか？」 |
| Adult / 大人向け | 「その方といるときの状態に、名前をつけてみましょうか。」 |

### B: User describes a place or situation / ユーザーが場所・状況を説明するとき

**User input example / ユーザー入力例：**「週末ひとりでカフェにいることが多くて…」

| Tone / トーン | Japanese / 日本語 |
|--------------|-----------------|
| Easy / 易しい | 「カフェでひとりのときモード、どう？」 |
| Standard / ふつう | 「カフェでひとりでいるときモード、作りますか？」 |
| Adult / 大人向け | 「カフェでひとりでいるときの状態を、ひとつのモードとして置いてみましょうか。」 |

### C: User describes an emotional state / ユーザーが感情・状態を説明するとき

*In this case, the AI offers a choice: create a new mode, or place it inside an existing mode. / このケースではAIが選択肢を提示する：新しいモードとして作るか、既存のモードの内側に置くか。*

**User input example / ユーザー入力例：**「なんか気をつかってばかりいる時間があって…」

| Tone / トーン | Japanese / 日本語 |
|--------------|-----------------|
| Easy / 易しい | 「気をつかってるときモード、名前にしてみる？　それとも、今あるモードの内側に置く感じにする？」 |
| Standard / ふつう | 「ひとつのモードとして名前にしますか？それとも、今あるモードの内側に置きますか？」 |
| Adult / 大人向け | 「ひとつのモードとして置くか、既存のモードの内側に置くか。どちらにしますか。」 |

---

## 6. Session completion UI / セッション完了UI

*Shown after a mode card entry is completed. / モードカードへの入力完了後に表示。*

| Element / 要素 | English (provisional) / 英語（暫定） | Japanese / 日本語 |
|---------------|--------------------------------------|-----------------|
| Completion message / 完了メッセージ | Saved | 残せました |
| Button A / ボタンA | ＋ | ＋ |
| Button B / ボタンB | That's enough for today | 今日はここまで |

- 「＋」→ Next mode card / 次のモードカードへ
- 「今日はここまで」→ Return to board / ボードに戻る

*No punctuation on any element. English translations are provisional; final copy should be verified by a native English speaker with knowledge of the project's tone. / すべての要素に句点なし。英語訳は暫定。最終的な文言はプロジェクトのトーンを理解した英語ネイティブによる確認を推奨します。*

---

## 7. Question pool / 質問プール

*1–2 questions are drawn from this pool per mode card session. Questions rotate; the same question is not shown every time. / モードカードのセッションごとにこのプールから1〜2問が選ばれる。ローテーションされ、毎回同じ質問は表示されない。*

*Questions are provided in Japanese only. For other languages, machine translation is a practical starting point, but cultural adaptation is strongly recommended — some questions carry nuance that does not translate directly. Localization implementors are encouraged to rewrite the pool from scratch with local relational vocabulary in mind. See CULTURAL_LAYER.md.*

*質問は日本語のみで記載されています。他言語への翻訳はAI翻訳を出発点として使用できますが、直訳では伝わりにくいニュアンスを含む質問もあるため、文化的な再作成を推奨します。CULTURAL_LAYER.mdを参照。*

### Physical sensation / 身体感覚系
- 肩の力が抜けていましたか？
- 自分のペースでいられましたか？
- 疲れましたか？
- 呼吸が楽でしたか？
- リラックスできていましたか？

### Sense of presence / 存在感覚系
- その場にいてよかったと思いましたか？
- 静かな気持ちでいられましたか？
- ここにいる自分が、しっくりきましたか？
- 自然体でいられましたか？

### Relational sensation / 関係感覚系
- 安心できましたか？
- 笑顔になれましたか？
- たくさん話せましたか？
- 相手のことを考える余裕がありましたか？
- 黙っていられる時間がありましたか？
- 気をつかいましたか？
- 話を聞いてもらえた気がしましたか？
- 一緒にいて、時間が経つのが早かったですか？
- また会いたいと思いましたか？
- 本音が出ましたか？

---

## 8. Panic dummy screen / パニックダミースクリーン

*Triggered by two-finger simultaneous tap. / 2本指同時タップでトリガー。*

**Design principle / 設計方針**
The dummy screen should look like a screen that anyone might ordinarily have open. A plain single-color screen is unnatural and should be avoided.

ダミースクリーンは誰でも日常的に開いている可能性がある画面に見えることが望ましい。単色の画面は不自然であり避けること。

**Candidate screen types (TBD for implementors) / 候補画面の種類（実装者に委ねる）**
- Note-taking app style / メモ帳風
- Calendar style / カレンダー風
- Weather app style / 天気予報風

**No text is shown on the dummy screen itself.**
**ダミースクリーン上に文言は表示しない。**

*The two-finger tap gesture is explained once during onboarding or in settings. / 2本指タップのジェスチャーはオンボーディングまたは設定画面で一度だけ説明する。*
