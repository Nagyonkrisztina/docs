---
title: 关于组织的消息馈送
intro: 您可以使用组织的消息馈送跟进该组织拥有的仓库上的近期活动。
redirect_from:
  - /articles/news-feed
  - /articles/about-your-organization-s-news-feed
  - /articles/about-your-organizations-news-feed
  - /github/setting-up-and-managing-organizations-and-teams/about-your-organizations-news-feed
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Organizations
  - Teams
shortTitle: Organization news feed
ms.openlocfilehash: 2ef8e11cd2ede1fedd284aed3d554bcd658d413e
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145128604'
---
组织的消息馈送显示其他人在该组织拥有的仓库上的活动。 您可以使用组织的消息馈送来查看何时有人打开、关闭或合并议题或拉取请求，创建或删除分支，创建标记或发行版，评论议题，拉取请求，或者提交或推送提交到 {% data variables.product.product_name %}。

## 访问组织的消息馈送

1. {% data variables.product.signin_link %} 到 {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %} 上的帐户。
2. 打开 {% data reusables.user-settings.personal_dashboard %}。
3. 单击页面左上角的帐户上下文切换器。
  ![Enterprise 中的上下文切换器按钮](/assets/images/help/organizations/account_context_switcher.png)
4. 从下拉菜单中选择组织。{% ifversion fpt or ghec %} ![dotcom 中的上下文切换器菜单](/assets/images/help/organizations/account-context-switcher-selected-dotcom.png){% else %} ![Enterprise 中的上下文切换器菜单](/assets/images/help/organizations/account_context_switcher.png){% endif %}
