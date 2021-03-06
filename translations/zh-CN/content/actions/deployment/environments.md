---
title: 环境
intro: 您可以使用保护规则和机密配置环境。 工作流程作业可以引用环境来使用环境的保护规则和机密。
product: '{% data reusables.gated-features.environments %}'
redirect_from:
  - /actions/reference/environments
versions:
  fpt: '*'
  ghes: '>=3.1'
  ghae: '*'
---

{% data reusables.actions.ae-beta %}

## 关于环境

您可以使用保护规则和机密配置环境。 当工作流程引用环境时，作业在环境的所有保护规则通过之前不会开始。 在所有环境保护规则通过之前，作业也不能访问在环境中定义的机密。

{% ifversion fpt %}
Environment protection rules and environment secrets are only available on private repositories with {% data variables.product.prodname_ghe_cloud %}. {% data reusables.enterprise.link-to-ghec-trial %}

If you don't use {% data variables.product.prodname_ghe_cloud %} and convert a repository from public to private, any configured protection rules or environment secrets will be ignored, and you will not be able to configure any environments. 如果将仓库转换回公共，您将有权访问以前配置的任何保护规则和环境机密。
{% endif %}

### 环境保护规则

环境保护规则要求通过特定的条件，然后引用环境的作业才能继续。 {% ifversion fpt or ghae-next or ghes > 3.1 %}您可以使用环境保护规则来要求手动批准、延迟作业或者将环境限于某些分支。{% else %}您可以使用环境保护规则要求手动批准或延迟作业。{% endif %}

#### 需要的审查者

使用所需的审查者要求特定人员或团队批准引用环境的工作流程作业。 您最多可以列出六个用户或团队作为审查者。 审查者必须至少具有对仓库的读取访问权限。 只有一个必需的审查者需要批准该作业才能继续。

有关与必需审查者一起审查引用环境的作业的详细信息，请参阅“[审查部署](/actions/managing-workflow-runs/reviewing-deployments)”。

#### 等待计时器

在最初触发作业后，使用等待计时器将作业延迟特定时间。 时间（分钟）必须是 0 至 43,200（30天）之间的整数。

{% ifversion fpt or ghae-next or ghes > 3.1 %}
#### 部署分支

使用部署分支来限制哪些分支可以部署到环境中。 以下是环境部署分支的选项：

* **All branches（所有分支）**：仓库中的所有分支都可以部署到环境。
* **Protected branches（受保护的分支）**：只有启用分支保护规则的分支才能部署到环境。 如果没有为仓库中的任何分支定义分支保护规则，那么所有分支都可以部署。 有关分支保护规则的更多信息，请参阅“[关于受保护分支](/github/administering-a-repository/about-protected-branches)”。
* **Selected branches（所选分支）**：只有与指定的名称模式匹配的分支才能部署到环境。

  例如，如果您指定 `releases/*` 为部署分支规则，则只有其名称开头为 `releases/` 的分支才能部署到环境。 （通配符字符将不匹配 `/`。 要匹配以 `release/` 开头并且包含额外单一斜杠的分支，请使用 `release/*/*`）。 如果您添加 `main` 作为部署分支规则，则名为 `main` 的分支也可以部署到环境。 有关部署分支的语法选项的更多信息，请参阅 [Ruby File.fnmatch 文档](https://ruby-doc.org/core-2.5.1/File.html#method-c-fnmatch)。
{% endif %}
### 环境机密

存储在环境中的机密仅可用于引用环境的工作流程作业。 如果环境需要批准，作业在所需的审查者批准之前不能访问环境机密。 有关机密的更多信息，请参阅“[加密密码](/actions/reference/encrypted-secrets)”。

{% note %}

**注意：** 在自托管运行器上运行的工作流程不会在一个孤立的容器中运行，即使它们使用环境。 环境机密应与存储库和组织机密的安全级别相同。 更多信息请参阅“[GitHub Actions 的安全性增强](/actions/learn-github-actions/security-hardening-for-github-actions#hardening-for-self-hosted-runners)”。

{% endnote %}

## 创建环境

{% data reusables.github-actions.permissions-statement-environment %}

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.github-actions.sidebar-environment %}
1. 单击 **New environment（新环境）**。
1. 为环境输入一个名称, 然后单击 **Configure environment（配置环境）**。 环境名称不区分大小写。 环境名称不能超过 255 个字符，且必须在仓库中唯一。
1. 配置任何环境保护规则或环境机密。

{% ifversion fpt or ghae-next or ghes > 3.1 %}您也可以通过 REST API 创建和配置环境。 更多信息请参阅“[环境](/rest/reference/repos#environments)”和“[密码](/rest/reference/actions#secrets)”。{% endif %}

运行引用不存在的环境的工作流程将使用引用的名称创建环境。 新创建的环境将不配置任何保护规则或机密。 可在仓库中编辑工作流程的任何人都可以通过工作流程文件创建环境，但只有仓库管理员才能配置环境。

## 引用环境

工作流程中的每个作业都可以引用单个环境。 在将引用环境的作业发送到运行器之前，必须通过为环境配置的任何保护规则。 将作业发送到运行器时，作业可以访问环境的机密。

有关工作流程中引用环境的语法的更多信息，请参阅“[GitHub Actions 的工作流程语法](/actions/reference/workflow-syntax-for-github-actions#jobsjob_idenvironment)”。 有关与必需审查者一起审查引用环境的作业的详细信息，请参阅“[审查部署](/actions/managing-workflow-runs/reviewing-deployments)”。

当工作流程引用环境时，环境将显示在仓库的部署中。 有关查看当前和以前的部署的详细信息，请参阅“[查看部署历史记录](/developers/overview/viewing-deployment-history)”。

{% ifversion fpt or ghae-next or ghes > 3.1 %}
## 使用并发在环境中序列化部署
您可以使用并发，以便环境中每次最多有一个正在进行的部署和一个待处理的部署。 更多信息请参阅“[GitHub Actions 的工作流程语法](/actions/reference/workflow-syntax-for-github-actions#concurrency)”。{% endif %}

## 删除环境

{% data reusables.github-actions.permissions-statement-environment %}

删除环境将删除与环境关联的所有机密和保护规则。 由于已删除环境的保护规则而正在等待的任何作业将自动失败。

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.sidebar-settings %}
{% data reusables.github-actions.sidebar-environment %}
1. 在要删除的环境旁边，单击 {% octicon "trash" aria-label="The trash icon" %}。
2. 单击 **I understand, delete this environment（我了解，删除此环境）**。

{% ifversion fpt or ghae-next or ghes > 3.1 %}您也可以通过 REST API 删除环境。 更多信息请参阅“[环境](/rest/reference/repos#environments)”。{% endif %}
