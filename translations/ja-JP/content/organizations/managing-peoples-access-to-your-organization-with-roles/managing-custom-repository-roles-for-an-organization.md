---
title: Organizationのカスタムリポジトリロールの管理
intro: カスタムのリポジトリロールを作成することで、Organizationのリポジトリへのアクセスをより詳細に制御できます。
permissions: Organization owners can manage custom repository roles.
versions:
  feature: custom-repository-roles
topics:
  - Organizations
  - Teams
shortTitle: カスタムリポジトリロール
redirect_from:
  - /early-access/github/articles/managing-custom-repository-roles-for-an-organization
---

## カスタムリポジトリロールについて

リポジトリでのPull Requestの作成やOrganizationの支払い設定の変更など、{% data variables.product.product_name %}でなんらかのアクションを行うためには、ユーザは関連するアカウントやリソースに対する十分なアクセス権を持っていなければなりません。 このアクセスは、権限によって制御されます。 権限は、特定のアクションを行える能力です。 たとえばIssueを削除する能力は権限です。 ロールは、個人やTeamに割り当てることができる権限のセットです。

Organization内では、ロールをOrganization、Team、リポジトリのレベルで割り当てることができます。 ロールの様々なレベルに関する詳しい情報については「[Organizationのロール](/organizations/managing-peoples-access-to-your-organization-with-roles/roles-in-an-organization)」を参照してください。

最大で3つのカスタムリポジトリロールを作成することによって、リポジトリレベルで付与する権限をもっと詳細に制御できます。 カスタムリポジトリロールは、選択したカスタム名を持つ設定可能な権限のセットです。 カスタムロールを作成すると、リポジトリへの管理アクセスを持つユーザはそのロールを個人やTeamに割り当てることができます。 詳しい情報については「[Organizationのリポジトリへの個人のアクセスの管理](/organizations/managing-access-to-your-organizations-repositories/managing-an-individuals-access-to-an-organization-repository)」及び「[OrganizationのリポジトリへのTeamのアクセスの管理](/organizations/managing-access-to-your-organizations-repositories/managing-team-access-to-an-organization-repository)」を参照してください。

## 継承されたロールについて

カスタムリポジトリロールを作成する際は、事前設定された選択肢のセットから継承されたロールを選択することから始めます。 継承されたロールは、カスタムロールに含まれる権限の初期セットを決定します。 そして、そのロールは付与する追加権限を選択することによって、さらにカスタマイズできます。 利用可能な権限の完全なリストについては「[カスタムロールのための追加権限](#additional-permissions-for-custom-roles)」を参照してください。

継承されたロールの選択肢については、リポジトリの様々な種類のコントリビューターに対して標準化されています。

| 継承されたロール     | 設計対象                                                    |
| ------------ | ------------------------------------------------------- |
| **Read**     | プロジェクトを見たり議論したりしたい非コードコントリビューター。                        |
| **Triage**   | 書き込みアクセスなしに、積極的にIssueやPull Requestを管理する必要があるコントリビューター。  |
| **Write**    | アクティブにプロジェクトに対してプッシュを行うOrganizationのメンバーとコントリビューター。     |
| **Maintain** | 機微あるいは破壊的なアクションを行うためアクセスなしにリポジトリを管理する必要があるプロジェクトマネージャー。 |

## カスタムロールの例

以下は、設定できるカスタムリポジトリロールの例です。

| カスタムリポジトリロール      | 概要                                     | 継承されたロール     | 追加の権限                                                                                                                                                 |
| ----------------- | -------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Security engineer | コードをコントリビュートし、セキュリティパイプラインをメンテナンスできる   | **Maintain** | Code scanningの結果の削除                                                                                                                                   |
| Contractor        | webhookのインテグレーションを開発できる                | **Write**    | webhookの管理                                                                                                                                            |
| Community manager | コードをコントリビュートすることなく、コミュニティのすべてのやりとりを扱える | **Read**     | - Issueを重複としてマーク<br> - GitHub Pageの設定を管理<br> - Wikiの設定を管理<br> - ソーシャルプレビューの設定<br> - リポジトリのメタデータを編集<br> - ディスカッションのトリアージ |

## カスタムロールの追加権限

継承されたロールを選択した後、カスタムロールの追加権限を選択できます。

継承されたロールにまだ含まれていない場合にのみ、追加の権限を選択できます。 たとえば、継承されたロールがリポジトリへの**Write**アクセスを提供しているなら、"Close a pull request"権限は継承されたロールに既に含まれています。

{% ifversion discussions %}
### Discussions

- **Create a discussion category（ディスカッションカテゴリの作成）**: 新しいディスカッションカテゴリを作成できる。 詳しい情報については「[新しいディスカッションカテゴリの作成](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#creating-a-category)」を参照してください。
- **Edit a discussion category（ディスカッションカテゴリの編集）**: ディスカッションカテゴリを編集できる。 詳しい情報については「[ディスカッションカテゴリの編集](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#editing-a-category)」を参照してください。
- **Delete a discussion category（ディスカッションカテゴリの削除）**: ディスカッションカテゴリを削除できる。 詳しい情報については「[ディスカッションカテゴリの削除](/discussions/managing-discussions-for-your-community/managing-categories-for-discussions#deleting-a-category)」を参照してください。
- **Mark or unmark discussion answers（ディスカッションの回答のマークもしくはマーク解除）**: ディスカッションのカテゴリが回答を受け付ける藻のだった場合、ディスカッションの回答をマークできる。 詳しい情報については「[ディスカッション中のコメントを回答としてマークもしくはマーク解除する](/discussions/managing-discussions-for-your-community/moderating-discussions#marking-a-comment-as-an-answer)」を参照してください。
- **Hide or unhide discussion comments（ディスカッションコメントの非表示もしくは非表示解除）**: ディスカッションのコメントを非表示あるいは非表示解除できる。  詳しい情報については、「[ ディスカッションをモデレートする](/communities/moderating-comments-and-conversations/managing-disruptive-comments#hiding-a-comment)」を参照してください。
- **Convert issues to discussions（Issueをディスカッションに変換）**: Issueをディスカッションに変換できる。  詳しい情報については「[Issueのディスカッションへの変換](/discussions/managing-discussions-for-your-community/moderating-discussions#converting-an-issue-to-a-discussion)」を参照してください。
{% endif %}

### IssueとPull Request

- **Assign or remove a user（ユーザをアサインあるいは外す）**: ユーザをIssueあるいはPull Requestにアサインするか、ユーザをIssueあるいはPull Requestから外す。
- **Add or remove a label（ラベルの追加あるいは削除）**: ラベルをIssueあるいはPull Requestに追加するか、ラベルをIssueあるいはPull Requestから削除する。

### Issue

- **Close an issue（Issueのクローズ）**
- **Reopen a closed issue（クローズされたIssueの再オープン）**
- **Delete an issue（Issueの削除）**
- **Mark an issue as a duplicate（Issueを複製としてマーク）**

### プルリクエスト

- **Close a pull request（Pull Requestをクローズ）**
- **Reopen a closed pull request（クローズされたPull Requestを再オープン）**
- **Request a pull request review（Pull Requestのレビューをリクエスト）**: ユーザあるいはTeamからのレビューをリクエスト。

### リポジトリ

- **Set milestones（マイルストーンの設定）**: IssueあるいはPull Requestにマイルストーンを追加。
- **Manage wiki settings（Wiki設定の管理）**: リポジトリでWikiを有効化。
- **Manage project settings（プロジェクト設定の管理）**: リポジトリでプロジェクトを有効化。
- **Manage pull request merging settings（Pull Requestのマージ設定の管理）**: マージ、squash、リベースなど、リポジトリで許可されるマージコミットの種類を選択。
- **Manage {% data variables.product.prodname_pages %} settings（設定の管理）**: リポジトリで{% data variables.product.prodname_pages %}を有効化し、公開したいブランチを選択。 詳しい情報については「[{% data variables.product.prodname_pages %} サイトの公開元を設定する](/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)」を参照してください。
- **Manage webhooks（webhookの管理）**: リポジトリにwebhookを追加。
- **Manage deploy keys（デプロイキーを管理）**: リポジトリにデプロイキーを追加。
- **Edit repository metadata（リポジトリのメタデータを編集）**: リポジトリの説明とともにリポジトリのトピックを更新。
{%- ifversion ghec %}
- **Set interaction limits（インタラクションの制限を設定）**: 自分のパブリックリポジトリで特定のユーザによるコメント、Issueのオープン、Pull Requestの作成を一時的に制限し、アクティビティの制限期間を施行。 詳しい情報については「[リポジトリでの操作の制限](/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository)」を参照してください。
{%- endif %}
- **Set the social preview（ソーシャルプレビューの設定）**: リポジトリがリンクされたときにソーシャルメディア上に表示される識別画像をリポジトリに追加。 詳細は「[リポジトリのソーシャルメディア向けプレビューをカスタマイズする](/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview)」を参照してください。
- **Push commits to protected branches（保護されたブランチにコミットをプッシュ）**: 保護されたブランチとしてマークされているブランチにプッシュ。 ブランチ保護ルールは引き続き適用され、プッシュが拒否されることがあります。
- **Create protected tags（保護されたタグの作成）**: タグの保護ルールにマッチしたタグの作成。 詳しい情報については「[タグ保護ルールの設定](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-tag-protection-rules)」を参照してください。
- **Delete protected tags（タグ保護ルールの削除）**: タグ保護ルールにマッチしたタグの削除。 詳しい情報については「[タグ保護ルールの設定](/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/configuring-tag-protection-rules)」を参照してください。{% ifversion bypass-branch-protections %}
- **ブランチ保護のバイパス**: 保護されたブランチにブランチ保護ルールに準拠せずにプッシュ。{% endif %}

### セキュリティ

- **View {% data variables.product.prodname_code_scanning %} results（Code scanningの結果を表示）**: {% data variables.product.prodname_code_scanning %}アラートを表示できる。
- **Dismiss or reopen {% data variables.product.prodname_code_scanning %} results（Code scanningの結果を却下もしくは再オープン）**: {% data variables.product.prodname_code_scanning %}アラートを却下もしくは再オープンできる。
- **Delete {% data variables.product.prodname_code_scanning %} results（Code scanningの結果の削除）**: {% data variables.product.prodname_code_scanning %}アラートを削除できる。
- **View {% data variables.product.prodname_dependabot_alerts %}（Dependabotアラートの表示）**: {% data variables.product.prodname_dependabot_alerts %}を見ることができる。
- **Dismiss or reopen {% data variables.product.prodname_dependabot_alerts %}（Dependabotアラートを却下もしくは再オープン）**: {% data variables.product.prodname_dependabot_alerts %}を却下もしくは再オープンできる。
- **View {% data variables.product.prodname_secret_scanning %} results（Secret scanningの結果の表示）**: {% data variables.product.prodname_secret_scanning %}アラートを表示できる。
- **Dismiss or reopen {% data variables.product.prodname_secret_scanning %} results（Secret scanningの結果の却下もしくは再オープン）**: {% data variables.product.prodname_secret_scanning %}アラートを却下もしくは再オープンできる。

## 様々なアクセスレベルの優先順位

TeamのメンバーシップやOrganizationの基本権限など、様々な方法を通じて様々なレベルのアクセスを与えられている場合、最上位のアクセスが他よりも優先されます。 たとえば、OrganizationのオーナーがOrganizationのメンバーに継承ロールの"Read"を使うカスタムロールを与え、そしてOrganizationのオーナーがOrganizationの基本権限を"Write"にした場合、このカスタムロールはカスタムロールに含まれている追加の権限とともに、書き込みアクセスを持つことになります。

{% data reusables.organizations.mixed-roles-warning %}

競合するアクセスを解決するには、Organizationの基本アクセスあるいはTeamのアクセスを調整するか、カスタムロールを編集してください。 詳しい情報については、以下を参照してください。
  - 「[Organization の基本レベルの権限の設定](/github/setting-up-and-managing-organizations-and-teams/setting-base-permissions-for-an-organization)」
  - [OrganizationのリポジトリへのTeamのアクセスの管理](/organizations/managing-access-to-your-organizations-repositories/managing-team-access-to-an-organization-repository)
  - 「[リポジトリロールの編集](#editing-a-repository-role)」

## リポジトリロールの作成

新しいリポジトリロールを作成するには、継承されたロールに権限を追加し、カスタムロールに名前を付けます

{% ifversion ghec %}
{% note %}

**ノート:** {% data variables.product.prodname_ghe_cloud %}を使うOrganizationだけがカスタムリポジトリロールを作成できます。 {% data reusables.enterprise.link-to-ghec-trial %}

{% endnote %}
{% endif %}

{% data reusables.profile.access_profile %}
{% data reusables.profile.access_org %}
{% data reusables.organizations.org_settings %}
{% data reusables.organizations.org-list %}
{% data reusables.organizations.org-settings-repository-roles %}
5. **Create a Role（ロールの作成）**をクリックしてください。 !["ロールの作成"ボタンのスクリーンショット](/assets/images/help/organizations/repository-role-create-role.png)
4. "Name（名前）"の下で、リポジトリロールの名前を入力してください。 ![リポジトリロールの名前の入力フィールド](/assets/images/help/organizations/repository-role-name.png)
5. "Description（説明）"の下で、リポジトリロールの説明を入力してください。 ![リポジトリロールの説明の入力フィールド](/assets/images/help/organizations/repository-role-description.png)
6. "Choose a role to inherit（継承するロールの選択）"の下で、継承したいロールを選択してください。 ![リポジトリロールの基本ロールの選択](/assets/images/help/organizations/repository-role-base-role-option.png)
7. "Add Permissions（権限の追加）"の下で、ドロップダウンメニューを使ってカスタムロールに含めたい権限を選択してください。 ![リポジトリロールのドロップダウンで権限レベルを選択](/assets/images/help/organizations/repository-role-drop-down.png)
7. **Create role（ロールの作成）**をクリックしてください。 ![リポジトリロールの作成の確認](/assets/images/help/organizations/repository-role-creation-confirm.png)

## リポジトリロールの編集

{% data reusables.profile.access_profile %}
{% data reusables.profile.access_org %}
{% data reusables.organizations.org_settings %}
{% data reusables.organizations.org-list %}
{% data reusables.organizations.org-settings-repository-roles %}
3. 編集したいロールの右で{% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}をクリックし、続いて**Edit（編集）**をクリックしてください。 ![リポジトリロールのドロップダウンメニュー内の選択肢を編集](/assets/images/help/organizations/repository-role-edit-setting.png)
4. 編集し、続いて**Update role（ロールの更新）**をクリックしてください。 ![リポジトリロールのフィールドを編集して更新](/assets/images/help/organizations/repository-role-update.png)

## リポジトリロールの削除

既存のリポジトリロールを削除すると、そのカスタムロールを持つ保留中の招待、Team、ユーザはすべてOrganizationの基本権限に割り当てなおされます。

{% data reusables.profile.access_profile %}
{% data reusables.profile.access_org %}
{% data reusables.organizations.org_settings %}
{% data reusables.organizations.org-list %}
{% data reusables.organizations.org-settings-repository-roles %}
3. 削除したいロールの右で{% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}をクリックし、続いて**Delete（削除）**をクリックしてください。 ![リポジトリロールのドロップダウンメニュー内の選択肢を編集](/assets/images/help/organizations/repository-role-delete-setting.png)
4. 削除したいロールに対する変更をレビューし、続いて**Delete role（ロールの削除）**をクリックしてください。 ![リポジトリロールの削除を確認](/assets/images/help/organizations/repository-role-delete-confirm.png)
