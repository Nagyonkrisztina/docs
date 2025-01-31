---
title: Buscar wikis
intro: 'Puedes buscar wikis en {% data variables.product.product_name %} y acotar los resultados utilizando estos calificadores de búsqueda de wiki en cualquier combinación.'
redirect_from:
  - /articles/searching-wikis
  - /github/searching-for-information-on-github/searching-wikis
  - /github/searching-for-information-on-github/searching-on-github/searching-wikis
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - GitHub search
ms.openlocfilehash: da73bcaa13c718be9840483e2a34c4b90ba96e63
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2022
ms.locfileid: '145118857'
---
Puedes buscar wikis globalmente a través de todos los {% data variables.product.product_name %}, o buscar wikis dentro de un repositorio u organización particular. Para obtener más información, consulte "[Acerca de la búsqueda en {% data variables.product.company_short %}](/search-github/getting-started-with-searching-on-github/about-searching-on-github)".

{% data reusables.search.syntax_tips %}

## Buscar dentro de los repositorios de un usuario u organización

Para buscar páginas wiki de todos los repositorios que son propiedad de una determinada organización o un determinado usuario, puede utilizar el calificador `user` o `org`. Para buscar páginas wiki desde un repositorio específico, use el calificador `repo`.

| Calificador:        | Ejemplo
| ------------- | -------------
| <code>user:<em>USERNAME</em></code> | [**user:defunkt**](https://github.com/search?q=user%3Adefunkt&type=Wikis) busca páginas wiki de repositorios propiedad de @defunkt.
| <code>org:<em>ORGNAME</em></code> | [**org:github**](https://github.com/search?q=org%3Agithub&type=Wikis&utf8=%E2%9C%93) busca wikis en repositorios propiedad de la organización de GitHub.
| <code>repo:<em>USERNAME/REPOSITORY</em></code> | [**repo:defunkt/gibberish**](https://github.com/search?q=user%3Adefunkt&type=Wikis) busca páginas wiki del repositorio "gibberish" de @defunkt.

## Buscar dentro del título o el texto del cuerpo de una página wiki

El calificador `in` acota la búsqueda al título o al texto del cuerpo de la página wiki. Sin el calificador, se busca tanto en el título como en el texto del cuerpo.

| Calificador:        | Ejemplo
| ------------- | -------------
| `in:title` | [**usage in:title**](https://github.com/search?q=usage+in%3Atitle&type=Wikis) busca títulos de páginas wiki con la palabra "usage".
| `in:body` | [**installation in:body**](https://github.com/search?q=installation+in%3Abody&type=Wikis) busca páginas wiki con la palabra "installation" en el texto del cuerpo principal.

## Buscar por la última fecha de actualización

El calificador `updated` busca páginas wiki que fueron actualizadas por última vez dentro de un rango específico de fechas.

{% data reusables.search.date_gt_lt %}

| Calificador:        | Ejemplo
| ------------- | -------------
| <code>updated:<em>YYYY-MM-DD</em></code> | [**usage updated:>2016-01-01**](https://github.com/search?q=usage+updated%3A>2016-01-01&type=Wikis) busca páginas wiki con la palabra "usage" que se actualizaron por última vez después del 01-01-2016.

## Información adicional

- "[Ordenar los resultados de la búsqueda](/search-github/getting-started-with-searching-on-github/sorting-search-results/)"
