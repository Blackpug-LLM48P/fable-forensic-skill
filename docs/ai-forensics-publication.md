# AI鑑識学・公開理論稿の案内と引用

| 項目 | 内容 |
|---|---|
| 著者 | 黒パグ（Blackpug-LLM48P） |
| 記事名 | AI鑑識学の公開理論：関係・機能・保留を監査する |
| 原稿版 | 公開理論稿 v0.2 |
| Zenn公開日 | 2026年10月16日 |
| 公開記事 | [Zennで読む](https://zenn.dev/git_dungeon/articles/ai-forensics-relation-level-methodology) |
| 最新原稿 | [articles/ai-forensics-relation-level-methodology.md](../articles/ai-forensics-relation-level-methodology.md) |
| 引用用の固定原稿 | [2822ca6de06e](https://github.com/Blackpug-LLM48P/fable-forensic-skill/blob/2822ca6de06e5baacc988831f2fe81e3be552541/articles/ai-forensics-relation-level-methodology.md) |
| 利用条件 | [記事専用の権利表示](../rights/ai-forensics-relation-level-methodology.txt) |

## 公開範囲

記事は、定義、関係単位の観察、確認待ちの監査、積極的な機能所見、所見内の主張の混在、検証と評価計画を扱います。作例は説明用の合成例です。

鑑識プロンプト本文、起動指示、モード別の実行手順、具体的な閾値や例外処理、非公開の評価資料は公開対象に含みません。

本文・図表・作例には専用の権利表示が適用されます。既存のMIT対象資料との範囲は、[LICENSE](../LICENSE)に記載しています。

## 引用例

> 黒パグ（Blackpug-LLM48P）「AI鑑識学の公開理論：関係・機能・保留を監査する」公開理論稿 v0.2、Zenn、2026年10月16日公開。

- 公開記事：[https://zenn.dev/git_dungeon/articles/ai-forensics-relation-level-methodology](https://zenn.dev/git_dungeon/articles/ai-forensics-relation-level-methodology)
- この版の固定原稿：[GitHub commit 2822ca6de06e](https://github.com/Blackpug-LLM48P/fable-forensic-skill/blob/2822ca6de06e5baacc988831f2fe81e3be552541/articles/ai-forensics-relation-level-methodology.md)

最新版へのリンクに加え、実際に参照したcommitの固定原稿を付けると、引用対象を後から照合できます。Gitへの保存時点とZennの公開日は別の記録です。

## 保存履歴

| 段階 | 固定commit | 内容 |
|---|---|---|
| 初稿 v0.1 | [b86c5659719d](https://github.com/Blackpug-LLM48P/fable-forensic-skill/commit/b86c5659719dd737db2515cb159c19d144e31710) | 新規記事を下書きとして追加し、専用の権利表示を設定 |
| 増補 v0.2 | [5ebe7ded4101](https://github.com/Blackpug-LLM48P/fable-forensic-skill/commit/5ebe7ded410103333cf2ba76a8ccec0e2aaa7a36) | 約15,000字へ増補 |
| 表示調整 | [0392d53f78aa](https://github.com/Blackpug-LLM48P/fable-forensic-skill/commit/0392d53f78aa312534d74050874a776d0329f409) | Zennでのコメント・権利表記・参考リンクの表示を調整 |
| 公開設定の同期 | [2822ca6de06e](https://github.com/Blackpug-LLM48P/fable-forensic-skill/commit/2822ca6de06e5baacc988831f2fe81e3be552541) | Zennの公開状態に合わせて `published: true` に変更。本文は表示調整版と同一 |

## 更新手順

1. `main` の `articles/ai-forensics-relation-level-methodology.md` を更新します。同じ記事を更新するときはファイル名を維持します。
2. 公開中の記事は `published: true` を維持します。公開を取り下げる場合だけ、意図を確認して変更します。
3. 理論や主張を改訂した場合は、本文の版・改訂情報、権利表示の対象版、CHANGELOG、ここにある引用対象を対応付けます。表記のみの調整もCHANGELOGに記録します。
4. Git更新後、[Zennのデプロイ履歴](https://zenn.dev/dashboard/deploys)で対象commitの成功を確認します。
5. 記事ページで公開状態と表示を確認します。Gitへの保存、Zennへの取り込み、実際の表示は、それぞれ確認する対象です。

この原稿版番号は記事の版を表します。Fable Forensic Skillのリリース番号とは別に管理します。
