---
title: 管理シェル (SSH) にアクセスする
redirect_from:
  - /enterprise/admin/articles/ssh-access
  - /enterprise/admin/articles/adding-an-ssh-key-for-shell-access
  - /enterprise/admin/guides/installation/administrative-shell-ssh-access
  - /enterprise/admin/articles/troubleshooting-ssh-permission-denied-publickey
  - /enterprise/admin/2.13/articles/troubleshooting-ssh-permission-denied-publickey
  - /enterprise/admin/2.14/articles/troubleshooting-ssh-permission-denied-publickey
  - /enterprise/admin/2.15/articles/troubleshooting-ssh-permission-denied-publickey
  - /enterprise/admin/installation/accessing-the-administrative-shell-ssh
  - /enterprise/admin/configuration/accessing-the-administrative-shell-ssh
  - /admin/configuration/accessing-the-administrative-shell-ssh
intro: '{% data reusables.enterprise_site_admin_settings.about-ssh-access %}'
versions:
  ghes: '*'
type: how_to
topics:
  - Enterprise
  - Fundamentals
  - SSH
shortTitle: Access the admin shell (SSH)
ms.openlocfilehash: 8d8b9cd71a436c0874355b1bdd53ba2e400660a0
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2022
ms.locfileid: '145120741'
---
## 管理シェルでのアクセスについて

管理シェルへの SSH アクセスがある場合は、{% data variables.product.prodname_ghe_server %} のコマンドラインユーティリティを実行できます。 SSHでのアクセスは、トラブルシューティングやバックアップの実行、レプリケーションの設定にも役立ちます。 管理のためのSSHアクセスはGitのSSHアクセスとは別に管理され、ポート122を通じてのみアクセスできます。

## SSH経由での管理シェルへのアクセスの有効化

管理のためのSSHアクセスを有効化するには、SSHの公開鍵をインスタンスの認証済みキーのリストに追加しなければなりません。

{% tip %}

**ヒント:** 認証済み SSH キーへの変更は、すぐに有効になります。

{% endtip %}

{% data reusables.enterprise_site_admin_settings.access-settings %} {% data reusables.enterprise_site_admin_settings.management-console %}
3. "SSH でのアクセス" の下のテキスト ボックスにキーを貼り付け、 **[キーの追加]** をクリックしてください。
  ![SSH キーを追加するためのテキスト ボックスおよびボタン](/assets/images/enterprise/settings/add-authorized-ssh-key-admin-shell.png) {% data reusables.enterprise_management_console.save-settings %}

## SSH経由での管理シェルへの接続

SSH キーをリストに追加したら、ポート 122 の `admin` ユーザーとしてインスタンスに SSH 経由で接続します。

```shell
$ ssh -p 122 admin@github.example.com
Last login: Sun Nov 9 07:53:29 2014 from 169.254.1.1
admin@github-example-com:~$ █
```

### SSH 接続問題のトラブルシューティング

SSH 経由で {% data variables.product.product_location %} に接続しようとしたときに、`Permission denied (publickey)` エラーが発生した場合は、ポート 122 経由で接続していることを確認してください。 使用するプライベートな SSH キーを明確に指定することが必要になる場合があります。

コマンド ラインを使用して秘密 SSH キーを指定するには、`-i` 引数を指定して `ssh` を実行ます。

```shell
ssh -i /path/to/ghe_private_key -p 122 admin@<em>hostname</em>
```

SSH 構成ファイル (`~/.ssh/config`) を使用して SSH 秘密キーを指定することもできます。

```shell
Host <em>hostname</em>
  IdentityFile /path/to/ghe_private_key
  User admin
  Port 122
```

## ローカルコンソールを使った管理シェルへのアクセス

たとえばSSHが利用でいないような緊急時には、管理シェルにローカルでアクセスできます。 `admin` ユーザーとしてサインインし、{% data variables.product.prodname_ghe_server %} の初期セットアップ中に設定されたパスワードを使用します。

## 管理シェルへのアクセス制限

管理シェルへのアクセスは、トラブルシューティングとドキュメント化された運用手順の実行時のみ許されます。 システムやアプリケーションのファイル変更、プログラムの実行、サポートされていないソフトウェアパッケージのインストールは、サポート契約を無効にすることがあります。 サポート契約の下で許されているアクティビティについて質問があれば、{% data variables.contact.contact_ent_support %} に連絡してください。
