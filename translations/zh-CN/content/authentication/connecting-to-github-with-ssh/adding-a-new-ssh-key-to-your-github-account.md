---
title: 新增 SSH 密钥到 GitHub 帐户
intro: '要在 {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %} 上配置帐户以使用新的（或现有的）SSH 密钥，还需要将密钥添加到帐户。'
redirect_from:
  - /articles/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account
  - /github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - SSH
shortTitle: Add a new SSH key
ms.openlocfilehash: c53fe44c92a5ef22a4c031c840fd57ccef508f1d
ms.sourcegitcommit: d186fc3b5766172b09b4e7370ae888c2523ac24a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2022
ms.locfileid: '147507981'
---
## <a name="about-addition-of-ssh-keys-to-your-account"></a>关于向帐户添加 SSH 密钥

{% data reusables.ssh.about-ssh %} 有关详细信息，请参阅“[关于 SSH](/authentication/connecting-to-github-with-ssh/about-ssh)”。

生成 SSH 密钥对后，必须将公钥添加到 {% ifversion fpt or ghec or ghes %}{% data variables.product.product_location %}{% elsif ghae %}{% data variables.product.product_name %}{% endif %} 以启用帐户的 SSH 访问。

## <a name="prerequisites"></a>先决条件

在将新的 SSH 密钥添加到 {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %} 上的帐户之前，请完成以下步骤。

1. 检查现有 SSH 密钥。 有关详细信息，请参阅“[检查现有 SSH 密钥](/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)”。
1. 生成新的 SSH 密钥，并将其添加到计算机的 SSH 代理。 有关详细信息，请参阅“[生成新的 SSH 密钥并将其添加到 ssh-agent](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)”。

## <a name="adding-a-new-ssh-key-to-your-account"></a>向你的帐户添加新的 SSH 密钥

在向您在 {% ifversion ghae %}{% data variables.product.product_name %}{% else %}{% data variables.product.product_location %}{% endif %} 上的帐户添加新 SSH 密钥后，您可以重新配置任何本地存储库以使用 SSH。 有关详细信息，请参阅“[将远程 URL 从 HTTPS 切换到 SSH](/github/getting-started-with-github/managing-remote-repositories/#switching-remote-urls-from-https-to-ssh)”。

{% data reusables.ssh.key-type-support %}

{% mac %}

{% webui %}

1. 将 SSH 公钥复制到剪贴板。

  如果您的 SSH 公钥文件与示例代码不同，请修改文件名以匹配您当前的设置。 在复制密钥时，请勿添加任何新行或空格。

  ```shell
  $ pbcopy &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard
  ```

  {% tip %}

  提示：如果 `pbcopy` 不起作用，你可以找到隐藏的 `.ssh` 文件夹，在你最喜欢的文本编辑器中打开该文件，并将其复制到剪贴板。

  {% endtip %}

{% data reusables.user-settings.access_settings %} {% data reusables.user-settings.ssh %}
4. 单击“新建 SSH 密钥”或“添加 SSH 密钥” 。
  ![SSH 密钥按钮](/assets/images/help/settings/ssh-add-ssh-key.png)
5. 在 "Title"（标题）字段中，为新密钥添加描述性标签。 例如，如果您使用的是个人 Mac，此密钥名称可能是 "Personal MacBook Air"。
6. 将密钥粘贴到 "Key"（密钥）字段。
  ![密钥字段](/assets/images/help/settings/ssh-key-paste.png)
7. 单击“添加 SSH 密钥”。
  ![“添加密钥”按钮](/assets/images/help/settings/ssh-add-key.png) {% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endmac %}

{% windows %}

{% webui %}

1. 将 SSH 公钥复制到剪贴板。

  如果您的 SSH 公钥文件与示例代码不同，请修改文件名以匹配您当前的设置。 在复制密钥时，请勿添加任何新行或空格。

  ```shell
  $ clip &lt; ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Copies the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file to your clipboard
  ```

  {% tip %}

  提示：如果 `clip` 不起作用，你可以找到隐藏的 `.ssh` 文件夹，在你最喜欢的文本编辑器中打开该文件，并将其复制到剪贴板。

  {% endtip %}

{% data reusables.user-settings.access_settings %} {% data reusables.user-settings.ssh %}
4. 单击“新建 SSH 密钥”或“添加 SSH 密钥” 。
  ![SSH 密钥按钮](/assets/images/help/settings/ssh-add-ssh-key.png)
5. 在 "Title"（标题）字段中，为新密钥添加描述性标签。 例如，如果您使用的是个人 Mac，此密钥名称可能是 "Personal MacBook Air"。
6. 将密钥粘贴到 "Key"（密钥）字段。
  ![密钥字段](/assets/images/help/settings/ssh-key-paste.png)
7. 单击“添加 SSH 密钥”。
  ![“添加密钥”按钮](/assets/images/help/settings/ssh-add-key.png) {% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endwindows %}

{% linux %}

{% webui %}

1. 将 SSH 公钥复制到剪贴板。

  如果您的 SSH 公钥文件与示例代码不同，请修改文件名以匹配您当前的设置。 在复制密钥时，请勿添加任何新行或空格。

  ```shell
  $ cat ~/.ssh/id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub
  # Then select and copy the contents of the id_{% ifversion ghae %}rsa{% else %}ed25519{% endif %}.pub file
  # displayed in the terminal to your clipboard
  ```

  {% tip %}

  提示：或者，你也可以找到隐藏的 `.ssh` 文件夹，在你最喜欢的文本编辑器中打开该文件，并将其复制到剪贴板。

  {% endtip %}

{% data reusables.user-settings.access_settings %} {% data reusables.user-settings.ssh %}
4. 单击“新建 SSH 密钥”或“添加 SSH 密钥” 。
  ![SSH 密钥按钮](/assets/images/help/settings/ssh-add-ssh-key.png)
5. 在 "Title"（标题）字段中，为新密钥添加描述性标签。 例如，如果您使用的是个人 Mac，此密钥名称可能是 "Personal MacBook Air"。
6. 将密钥粘贴到 "Key"（密钥）字段。
  ![密钥字段](/assets/images/help/settings/ssh-key-paste.png)
7. 单击“添加 SSH 密钥”。
  ![“添加密钥”按钮](/assets/images/help/settings/ssh-add-key.png) {% data reusables.user-settings.sudo-mode-popup %}

{% endwebui %}

{% endlinux %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

在使用 {% data variables.product.prodname_cli %} 将 SSH 密钥添加到帐户之前，必须向 {% data variables.product.prodname_cli %} 进行身份验证。 有关详细信息，请参阅 {% data variables.product.prodname_cli %} 文档中的“[`gh auth login`](https://cli.github.com/manual/gh_auth_login)”。

要将 SSH 密钥添加到你的 GitHub 帐户，请使用 `ssh-key add` 子命令指定你的公钥。

```shell
gh ssh-key add <em>key-file</em>
```

若要包含新密钥的标题，请使用 `-t` 或 `--title` 标记。

```shell
gh ssh-key add <em>key-file</em> --title "personal laptop"
```

如果按照“[生成新的 SSH 密钥](/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)”中的说明生成 SSH 密钥，则可以使用此命令将密钥添加到帐户。

```shell
gh ssh-key add ~/.ssh/id_ed25519.pub
```

{% endcli %}

{% ifversion fpt or ghec %}
## <a name="further-reading"></a>延伸阅读

- “[授权一个用于 SAML 单一登录的 SSH 密钥](/articles/authorizing-an-ssh-key-for-use-with-saml-single-sign-on)”{% endif %}
