---
title: プルリクエストへコメントする
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request
  - /articles/adding-commit-comments
  - /articles/commenting-on-the-diff-of-a-pull-request
  - /articles/commenting-on-differences-between-files
  - /articles/commenting-on-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request
  - /github/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/commenting-on-a-pull-request
intro: リポジトリのプルリクエストのオープン後、コラボレーターや Team メンバーは、特定の 2 つのブランチ間におけるファイルの比較について、またプロジェクト全体についてコメントできます。
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: Comment on a PR
---

## プルリクエストのコメントについて

プルリクエストの [**Conversation**] タブに、一般的なコメント、質問、提案などを書き込むことができます。 プルリクエストの作者がコメントから直接適用できる変更を提案することもできます。

![プルリクエストの会話](/assets/images/help/pull_requests/conversation.png)

プルリクエストの [**Files changed**] タブにあるファイルの、特定のセクションに、行コメントまたは [Pull Request レビュー](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)の一部としてコメントすることも可能です。 行コメントを追加することは、インプリメンテーションについての問題を話し合ったり、作者にフィードバックを行ったりする上でよい方法です。

For more information on adding line comments to a pull request review, see "[Reviewing proposed changes in a pull request](/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/reviewing-proposed-changes-in-a-pull-request)."

{% note %}

**注釈:** プルリクエストにメールで返信した場合、そのコメントは [**Conversation**] タブに追加され、Pull Request レビューには含まれません。

{% endnote %}

既存の行コメントに返信するには、[**Conversation**] タブまたは [**Files changed**] タブに移動して、既存のコメントの下に行コメントを追加します。

{% tip %}

**参考:**
- プルリクエストのコメントては、@メンション、絵文字、参照など、{% data variables.product.product_name %}の通常のコメントにおいてサポートされている[フォーマット](/categories/writing-on-github)がサポートされています。
- You can add reactions to comments in pull requests in the **Files changed** tab.

{% endtip %}

## プルリクエストに行コメントを追加する

{% data reusables.repositories.sidebar-pr %}
2. プルリクエストのリストで、行コメントをしたいプルリクエストをクリックします。
{% data reusables.repositories.changed-files %}
{% data reusables.repositories.start-line-comment %}
{% data reusables.repositories.type-line-comment %}
{% data reusables.repositories.suggest-changes %}
5. 完了したら、[**Add single comment**] をクリックします。 ![インラインコメントウインドウ](/assets/images/help/commits/inline-comment.png)

プルリクエストまたはリポジトリを Watch している全員が、コメントの通知を受信します。

{% data reusables.pull_requests.resolving-conversations %}

## 参考リンク

- [GitHubでの執筆](/github/writing-on-github)
{% ifversion fpt or ghec %}- 「[乱用やスパムをレポートする](/communities/maintaining-your-safety-on-github/reporting-abuse-or-spam)」
{% endif %}
