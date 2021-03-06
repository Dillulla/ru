---
title: Enterprise アカウントのアイデンティおよびアクセス管理について
intro: アイデンティティプロバイダ (IdP) を使用して、Enterprise のリソース、Organization のメンバーシップ、および Team のメンバーシップへのアクセスを一元管理できます。
product: '{% data reusables.gated-features.enterprise-accounts %}'
versions:
  fpt: '*'
topics:
  - Enterprise
redirect_from:
  - /github/setting-up-and-managing-your-enterprise/about-identity-and-access-management-for-your-enterprise-account
shortTitle: IAM for your enterprise
---

## Enterprise アカウントのアイデンティおよびアクセス管理について

{% data reusables.saml.dotcom-saml-explanation %} {% data reusables.saml.about-saml-enterprise-accounts %} For more information, see "[Enforcing SAML single sign-on for organizations in your enterprise account](/github/setting-up-and-managing-your-enterprise/configuring-identity-and-access-management-for-your-enterprise-account/enforcing-saml-single-sign-on-for-organizations-in-your-enterprise-account)."

SAML SSO を有効にした後、使用する IdP によっては、追加のアイデンティおよびアクセス管理機能を有効にできる場合があります。 {% data reusables.scim.enterprise-account-scim %}

IdP として Azure AD を使用している場合は、Team 同期を使用して、各 Organization 内の Team メンバーシップを管理できます。 {% data reusables.identity-and-permissions.about-team-sync %} 詳しい情報については、「[Enterprise アカウントで Organization の Team 同期を管理する](/github/setting-up-and-managing-your-enterprise/managing-team-synchronization-for-organizations-in-your-enterprise-account)」を参照してください。

{% data reusables.saml.switching-from-org-to-enterprise %} For more information, see "[Switching your SAML configuration from an organization to an enterprise account](/github/setting-up-and-managing-your-enterprise/configuring-identity-and-access-management-for-your-enterprise-account/switching-your-saml-configuration-from-an-organization-to-an-enterprise-account)."

## サポートされている IdP

以下の IdP はテスト済みで公式にサポートされています。 SAML SSO の場合、SAML 2.0 標準を実装するすべてのアイデンティティプロバイダに対して限定的なサポートが提供されています。 詳しい情報については、OASIS Web サイトの [SAML Wiki](https://wiki.oasis-open.org/security) を参照してください。

| IdP                                   |                              SAML                              |                           Team の同期                            |
| ------------------------------------- |:--------------------------------------------------------------:|:-------------------------------------------------------------:|
| Active Directory フェデレーションサービス (AD FS) | {% octicon "check-circle-fill" aria-label= "The check icon" %} |                                                               |
| Azure Active Directory (Azure AD)     | {% octicon "check-circle-fill" aria-label="The check icon" %}  | {% octicon "check-circle-fill" aria-label="The check icon" %}
| OneLogin                              | {% octicon "check-circle-fill" aria-label="The check icon" %}  |                                                               |
| PingOne                               | {% octicon "check-circle-fill" aria-label="The check icon" %}  |                                                               |
| Shibboleth                            | {% octicon "check-circle-fill" aria-label="The check icon" %}  |                                                               |

