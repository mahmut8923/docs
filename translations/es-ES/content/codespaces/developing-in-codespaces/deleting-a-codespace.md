---
title: Borrar un codespace
intro: Puedes borrar un codespace que ya no necesites.
product: '{% data reusables.gated-features.codespaces %}'
redirect_from:
  - /github/developing-online-with-github-codespaces/deleting-a-codespace
  - /github/developing-online-with-codespaces/deleting-a-codespace
versions:
  fpt: '*'
  ghec: '*'
type: how_to
topics:
  - Codespaces
  - Fundamentals
  - Developer
shortTitle: Delete a codespace
ms.openlocfilehash: c3f9577642c0b3016f8145da9f65cf9ccb457d5e
ms.sourcegitcommit: f638d569cd4f0dd6d0fb967818267992c0499110
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2022
ms.locfileid: '148109877'
---
Hay costos asociados al almacenamiento de codespaces. Por lo tanto, debes eliminar los codespaces que ya no necesites. Para más información, consulta "[Acerca de la facturación de GitHub Codespaces](/billing/managing-billing-for-github-codespaces/about-billing-for-github-codespaces)".

{% data reusables.codespaces.max-number-codespaces %}

## Borrar un codespace

{% webui %}

{% data reusables.codespaces.your-codespaces-procedure-step %}
1. A la derecha del codespace que quiera eliminar, haga clic en {% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %} y después en **{% octicon "trash" aria-label="The trash icon" %} Eliminar**

   ![Botón Eliminar](/assets/images/help/codespaces/delete-codespace.png)

{% endwebui %}

{% vscode %}

{% data reusables.codespaces.deleting-a-codespace-in-vscode %}

{% endvscode %}


{% cli %}

{% data reusables.cli.cli-learn-more %}

Para eliminar un codespace, use el subcomando `gh codespace delete` y, después, elija un codespace en la lista que se muestra.

```shell
gh codespace delete
```

Si tienes cambios sin guardar, se te pedirá confirmar el borrado. Puede usar la marca `--force` para forzar la eliminación y evitar este aviso.

Para más información sobre este comando, vea [el manual de {% data variables.product.prodname_cli %}](https://cli.github.com/manual/gh_codespace_delete).

{% endcli %}

## Eliminación masiva de codespaces

{% webui %}

Puedes usar {% data variables.product.prodname_cli %} para eliminar varios o todos los codespaces con un solo comando. Para obtener más información, haz clic en la pestaña **{% data variables.product.prodname_cli %}** que se encuentra cerca de la parte superior de esta página.

{% endwebui %}

{% vscode %}

Puedes usar {% data variables.product.prodname_cli %} para eliminar varios codespaces con un solo comando, o todos ellos. Para obtener más información, haz clic en la pestaña **{% data variables.product.prodname_cli %}** que se encuentra cerca de la parte superior de esta página.

{% endvscode %}


{% cli %}

Puedes eliminar varios codespaces, o todos ellos, con un solo comando mediante `gh codespace delete` seguido de una de estas marcas:

`--all`: elimina todos los codespaces.

`--repo REPOSITORY`: elimina todos los codespaces de este repositorio. O bien, úsalo junto con la marca `--days` para filtrar por antigüedad del codespace.

`--days NUMBER`: elimina todos los codespaces anteriores al número de días especificado. Se puede usar junto con la marca `--repo`.

De manera predeterminada, se te pedirá que confirmes la eliminación de los codespaces que contengan cambios no guardados. Puedes usar la marca `--force` para omitir esta confirmación. 

### Ejemplo

Elimina todos los codespaces del repositorio `octo-org/octo-repo` que has creado hace más de 7 días.

```
gh cs delete --repo octo-org/octo-repo --days 7
```

{% endcli %}

## Eliminación de codespaces en la organización

Como propietario de la organización, puedes usar {% data variables.product.prodname_cli %} para eliminar cualquier codespace de la organización.

{% webui %}

Para obtener más información, haz clic en la pestaña "{% data variables.product.prodname_cli %}" que se encuentra cerca de la parte superior de esta página.

{% endwebui %}

{% vscode %}

Para obtener más información, haz clic en la pestaña "{% data variables.product.prodname_cli %}" que se encuentra cerca de la parte superior de esta página.

{% endvscode %}

{% cli %}

1. Escribe uno de estos comandos para mostrar una lista de codespaces.
   * `gh codespace delete --org ORGANIZATION` : enumera los codespaces actuales de la organización especificada. 
   * `gh codespace delete --org ORGANIZATION --user USER` : enumera solo los codespaces creados por el usuario especificado.
   Debes ser un propietario de la organización especificada.
1. En la lista de codespaces, ve al codespace que desees eliminar.
1. Para eliminar el codespace seleccionado, presiona <kbd>Entrar</kbd>.

   Si el codespace contiene cambios no guardados, se te pedirá que confirmes la eliminación.

{% endcli %}

También puedes usar la API de REST para eliminar codespaces para tu organización. Para más información, consulta "[Organizaciones de Codespaces](/rest/codespaces/organizations#delete-a-codespace-from-the-organization)".

## Información adicional
- "[Ciclo de vida de Codespaces](/codespaces/developing-in-codespaces/codespaces-lifecycle)"
- "[Configuración de la eliminación automática de los codespaces](/codespaces/customizing-your-codespace/configuring-automatic-deletion-of-your-codespaces)"
