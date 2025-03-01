---
title: 创建和删除仓库中的分支
intro: '您可以直接在 {% data variables.product.product_name %} 上创建或删除分支。'
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository
  - /articles/deleting-branches-in-a-pull-request
  - /articles/creating-and-deleting-branches-within-your-repository
  - /github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: 创建和删除分支
---

## 创建分支
您可以在 {% data variables.product.product_name %} 上以不同的方式创建分支。

{% note %}

**注意：** 您只能在您具有推送访问权限的存储库中创建分支。

{% endnote %}

{% ifversion create-branch-from-overview %}
### 通过分支概述创建分支
{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.navigate-to-branches %}
1. 单击 **New Branch（新分支）**。 ![突出显示了新分支按钮的分支概述页面的屏幕截图](/assets/images/help/branches/new-branch-button.png)
2. 在对话框中，输入分支名称，并根据需要更改分支源。  
   如果存储库是复刻，您还可以选择上游存储库作为分支源。 ![强调分支源的复刻的分支创建模式屏幕截图](/assets/images/help/branches/branch-creation-popup-branch-source.png)
3. 单击 **Create Branch（创建分支）**。 ![突出显示了创建分支按钮的分支创建模式的屏幕截图](/assets/images/help/branches/branch-creation-popup-button.png)
{% endif %}

### 使用分支下拉列表创建分支
{% data reusables.repositories.navigate-to-repo %}
1. （可选）如果要从仓库的默认分支以外的分支创建新分支，请单击 {% octicon "git-branch" aria-label="The branch icon" %}**Branches（分支）**，然后选择另一个分支。 ![概述页面上的分支链接](/assets/images/help/branches/branches-overview-link.png)
1. 单击分支选择器菜单。 ![分支选择器菜单](/assets/images/help/branch/branch-selection-dropdown.png)
1. 为新分支键入唯一名称，然后选择 **Create branch（创建分支）**。 ![分支创建文本框](/assets/images/help/branch/branch-creation-text-box.png)

{% ifversion fpt or ghec or ghes > 3.4 %}
### 为议题创建分支
您可以创建一个分支，直接从议题页面处理议题，然后立即开始。 更多信息请参阅“[创建分支以处理议题](/issues/tracking-your-work-with-issues/creating-a-branch-for-an-issue)”。
{% endif %}

## 删除分支

{% data reusables.pull_requests.automatically-delete-branches %}

{% note %}

**注意：**如果要删除的分支是仓库的默认分支，则在删除该分支之前必须选择新的默认分支。 更多信息请参阅“[更改默认分支](/github/administering-a-repository/changing-the-default-branch)”。

{% endnote %}

如果要删除的分支与打开的拉取请求关联，则在删除该分支之前必须合并或关闭拉取请求。 更多信息请参阅“[合并拉取请求](/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)”和“[关闭拉取请求](/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/closing-a-pull-request)”。

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.navigate-to-branches %}
1. 滚动到要删除的分支，然后单击 {% octicon "trash" aria-label="The trash icon to delete the branch" %}。 ![delete the branch](/assets/images/help/branches/branches-delete.png) {% ifversion fpt or ghes > 3.5 or ghae-issue-6763 or ghec %}
1. 如果尝试删除与至少一个打开的拉取请求关联的分支，则必须确认是否要关闭拉取请求。

   ![确认删除分支](/assets/images/help/branches/confirm-deleting-branch.png){% endif %}

{% data reusables.pull_requests.retargeted-on-branch-deletion %}
更多信息请参阅“[关于分支](/github/collaborating-with-issues-and-pull-requests/about-branches#working-with-branches)。”

## 延伸阅读

- "[关于分支](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)"
- “[查看仓库中的分支](/github/administering-a-repository/viewing-branches-in-your-repository)”
- "[删除和恢复拉取请求中的分支](/github/administering-a-repository/deleting-and-restoring-branches-in-a-pull-request)"
