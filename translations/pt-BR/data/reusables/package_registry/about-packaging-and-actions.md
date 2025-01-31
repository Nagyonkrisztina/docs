---
ms.openlocfilehash: 9e47cc05dec3bbdef729dfc6a06eff8056dd9502
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2022
ms.locfileid: "145096318"
---
### Empacotamento em fluxos de trabalho de integração contínua

Uma etapa de empacotamento é uma parte comum de um fluxo de trabalho de integração contínua ou de continuous delivery. Criar um pacote ao fim de um fluxo de trabalho de integração contínua pode ajudar durante as análises de código ou durante o pull request.

Após criar e testar o seu código, uma etapa de empacotamento pode produzir um artefato executável ou aplicável. Dependendo do tipo de aplicativo que você estiver criando, este pacote pode ser baixado localmente para teste manual, disponibilizado para download dos usuários ou implementado em um ambiente de teste ou produção.

Por exemplo, um fluxo de trabalho de integração contínua para um projeto Java poderá executar `mvn package` para produzir um arquivo JAR. Ou um fluxo de trabalho CI para um aplicativo Node.js pode criar um contêiner Docker.

Agora, ao revisar um pull request, você poderá ver a execução do fluxo de trabalho e fazer o download do artefato produzido.

![Menu suspenso do para fazer download do artefato](/assets/images/help/repository/artifact-drop-down-updated.png)

Isso permitirá que você execute o código no pull request em sua máquina, o que pode ajudar a depurar ou testar o pull request.

### Fluxos de trabalho para publicação de pacotes

Além de fazer o upload dos artefatos de empacotamento para teste em um fluxo de trabalho de integração contínua, você poderá criar fluxos de trabalho que criam o seu projeto e publicam pacotes no pacote de registro.

* **Publicar pacotes no {% data variables.product.prodname_registry %}**  
  {% data variables.product.prodname_registry %} pode atuar como um serviço de hospedagem de pacotes para vários tipos de pacotes. Você pode escolher compartilhar os seus pacotes com todos {% data variables.product.prodname_dotcom %} ou compartilhar pacotes privados com colaboradores ou uma organização. Para obter mais informações, confira "[Introdução aos Pacotes do GitHub](/packages/learn-github-packages/introduction-to-github-packages)".

  Você pode querer publicar pacotes em {% data variables.product.prodname_registry %} em cada push no branch padrão. Isso permitirá que desenvolvedores no seu projeto possam sempre executar e testar a última criação a partir do branch padrão facilmente, instalando-o a partir de {% data variables.product.prodname_registry %}.

* **Publicar pacotes em um registro de pacotes**  
  Para muitos projetos, a publicação em um registro de pacotes é executada sempre que uma nova versão de um projeto é lançada. Por exemplo, um projeto que produz um arquivo JAR pode fazer o upload de novas versões no repositório central do Maven. Ou um projeto .NET pode produzir um pacote nuget e fazer o upload na Galeria NuGet.

  Você pode automatizar isso criando um fluxo de trabalho que publica pacotes em um registro de pacote em cada versão. Para obter mais informações, confira "[Como criar versões](/github/administering-a-repository/creating-releases)".
