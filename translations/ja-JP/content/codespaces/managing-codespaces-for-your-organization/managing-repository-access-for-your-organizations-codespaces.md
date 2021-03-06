---
title: Managing repository access for your organization's codespaces
shortTitle: Repository access
intro: '{% data variables.product.prodname_codespaces %} がアクセスできる Organization 内のリポジトリを管理できます。'
product: '{% data reusables.gated-features.codespaces %}'
permissions: 'To manage access and security for Codespaces for an organization, you must be an organization owner.'
versions:
  fpt: '*'
type: how_to
topics:
  - Codespaces
  - Security
  - Administrator
redirect_from:
  - /codespaces/managing-codespaces-for-your-organization/managing-access-and-security-for-your-organizations-codespaces
  - /github/developing-online-with-codespaces/managing-access-and-security-for-codespaces
  - /codespaces/working-with-your-codespace/managing-access-and-security-for-codespaces
---

デフォルト設定では、Codespace は作成されたリポジトリにのみアクセスできます。 Organization が所有するリポジトリのアクセスとセキュリティを有効にすると、そのリポジトリ用に作成された Codespaces には、Organization が所有する他のすべてのリポジトリへの読み取りおよび書き込みアクセスがあり、codespace の作者にはアクセス権があります。 codespace がアクセスできるリポジトリを制限する場合、codespace が作成されたリポジトリまたは特定のリポジトリのいずれかに制限できます。 信頼するリポジトリに対してのみ、アクセスとセキュリティを有効にしてください。

Organization 内のどのユーザが {% data variables.product.prodname_codespaces %} を使用できるかを管理するには、「[Organization のユーザ権限を管理する](/codespaces/managing-codespaces-for-your-organization/managing-user-permissions-for-your-organization)」を参照してください。

{% data reusables.profile.access_org %}
{% data reusables.profile.org_settings %}
{% data reusables.organizations.click-codespaces %}
1. [Access and security] で、あなたの Organization の設定を選択します。 ![信頼するリポジトリを管理するラジオボタン](/assets/images/help/settings/codespaces-org-access-and-security-radio-buttons.png)
1. [Selected repositories] を選択した場合、ドロップダウンメニューを選択してから、あなたの Organization が所有するその他のリポジトリにアクセスを許可する、リポジトリのコードスペースをクリックします。 その他のリポジトリにコードスペースによるアクセスを許可したい、すべてのリポジトリについて同じ手順を繰り返します。 ![[Selected repositories]ドロップダウンメニュー](/assets/images/help/settings/codespaces-access-and-security-repository-drop-down.png)
