# CULTURAL_LAYER.md
# 文化レイヤー

---

## Purpose of this document / このドキュメントの目的

ima-mode was conceived in a Japanese cultural context, but is designed as an open specification for global implementation.

ima-modeは日本の文化的文脈の中で構想されましたが、グローバルな実装のためのオープンな仕様書として設計されています。

This document describes the cultural assumptions embedded in the default design, and provides guidance for localization implementors.

このドキュメントでは、デフォルト設計に埋め込まれた文化的前提を説明し、ローカライズ実装者へのガイダンスを提供します。

---

## Cultural assumptions in the default design / デフォルト設計における文化的前提

### Relational self / 関係的自己

The core model of ima-mode — that the self shifts depending on relational context — resonates particularly with cultures where the self is understood as relational rather than fixed and individual.

ima-modeのコアモデル——自己が関係的文脈によって変化するという考え方——は、自己が固定された個人としてではなく、関係的なものとして理解される文化と特に共鳴します。

This is not a claim that the model is culturally exclusive. Relational self-awareness is a human universal. However, implementors in cultures with a strong individualist self-model may wish to adjust framing.

これは、このモデルが文化的に排他的であるという主張ではありません。関係的な自己認識は人間に普遍的なものです。ただし、強い個人主義的自己モデルを持つ文化での実装者はフレーミングの調整を検討してもよいでしょう。

### Affective modifiers / Affective修飾子

The default affective modifiers (仮面 / 片思い / 防御 / 省エネ / 察し / 空気読み) are drawn from Japanese relational vocabulary. Some of these — particularly 察し (sensing others' feelings without words) and 空気読み (reading the atmosphere) — are culturally specific concepts that may not translate directly.

デフォルトのAffective修飾子（仮面 / 片思い / 防御 / 省エネ / 察し / 空気読み）は日本の関係的語彙から引き出されています。とくに察し（言葉なしに相手の気持ちを感じ取ること）と空気読み（場の雰囲気を読むこと）は、直接翻訳されない可能性のある文化固有の概念です。

Localization implementors are encouraged to replace or supplement these with affective vocabulary natural to the target culture.

ローカライズ実装者は、対象文化において自然なAffective語彙に置き換えるか、補足することを推奨します。

### Spatial and institutional modes / 空間的・制度的モード

Modes such as 役所にいるときモード (at a government office mode) reflect specific Japanese institutional contexts. Implementors should adapt these to locally relevant institutions.

役所にいるときモードのような一部のモードは、日本固有の制度的文脈を反映しています。実装者は地域に関連する機関に合わせて適応させてください。

---

## Localization guidance / ローカライズガイダンス

### What to localize / ローカライズすべきもの

| Item / 項目 | Guidance / ガイダンス |
|-------------|----------------------|
| Affective modifiers / Affective修飾子 | Replace or supplement with culturally natural vocabulary / 文化的に自然な語彙に置き換えるか補足する |
| Institutional modes / 制度的モード | Adapt to local institutions / 地域の機関に合わせて適応させる |
| Cultural modes / 文化固有モード | Add modes that reflect local relational contexts / 地域の関係的文脈を反映するモードを追加する |
| Crisis hotline numbers / 危機相談窓口番号 | Replace with local numbers / 地域の番号に置き換える |
| Tone and honorifics / トーンと敬語 | Adapt to local linguistic norms / 地域の言語規範に合わせて適応させる |

### What not to localize / ローカライズすべきでないもの

| Item / 項目 | Reason / 理由 |
|-------------|---------------|
| Core ontology / コアオントロジー | One self, many states — this is the foundation / ひとつの自分、多くの状態——これは基盤 |
| Alone mode as center / だれもいないモードを中心に | Structural; removing it breaks the model / 構造的；削除するとモデルが壊れる |
| Non-diagnostic principle / 非診断原則 | Safety and ethics; non-negotiable / 安全と倫理；変更不可 |
| Transparent mirror AI role / 透明な鏡のAIの役割 | Core design value / コアな設計価値 |
| Privacy and local-only storage / プライバシーとローカル保存 | User trust; non-negotiable / ユーザーの信頼；変更不可 |

---

## Cultural modes / 文化固有モード

The default mode list includes examples drawn from Japanese daily life. These are illustrative, not exhaustive.

デフォルトのモードリストには日本の日常生活から引き出した例が含まれています。これらは例示であり、網羅的なものではありません。

Localization implementors are invited to add modes that reflect relational contexts meaningful in their culture. Some examples of the kinds of contexts that might generate culture-specific modes:

ローカライズ実装者は、自分たちの文化において意味のある関係的文脈を反映したモードを追加することを歓迎します。文化固有のモードを生む可能性のある文脈の例：

- Extended family structures / 拡大家族の構造
- Religious or community gatherings / 宗教的・コミュニティの集まり
- Specific social rituals or ceremonies / 特定の社会的儀式や式典
- Workplace hierarchies with local character / 地域的特性を持つ職場のヒエラルキー

These additions should be contributed back to the specification where possible, to enrich the global mode library.

これらの追加は可能な限り仕様書に還元し、グローバルなモードライブラリを豊かにしていくことを推奨します。

---

## The title / タイトルについて

The title **ima-mode** is fixed across all languages.
**いまモード** is the Japanese subtitle.

タイトル**ima-mode**は全言語で固定です。
**いまモード**は日本語のサブタイトルです。

"ima" (いま) means "now" in Japanese. The word is short, soft, and carries a quality of present-moment awareness that translates intuitively across languages without requiring translation.

「いま」は日本語で「今」を意味します。この言葉は短く、柔らかく、翻訳を必要とせず直感的に伝わる、現在の瞬間への気づきという質を持っています。

---

## Digital modes and cultural change / デジタルモードと文化的変化

The Digital category is explicitly marked for periodic review, as the relational contexts of digital life evolve rapidly and vary significantly across cultures.

デジタルカテゴリは明示的に定期的な見直しの対象とされています。デジタルライフの関係的文脈は急速に変化し、文化によって大きく異なるためです。

Localization implementors should treat the Digital mode list as a starting point, not a fixed set.

ローカライズ実装者は、デジタルモードリストを出発点として扱い、固定されたセットとしてではなく捉えてください。
