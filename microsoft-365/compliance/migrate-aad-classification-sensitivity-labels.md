---
title: Etiquetas de clasificación y confidencialidad de AAD para grupos de Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
description: En este artículo se describen las etiquetas clásicas de clasificación y confidencialidad de Azure Active Directory.
ms.openlocfilehash: 260b71d703f2534e5e2ddcf4ef45fe28a914eeab
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623791"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Etiquetas de clasificación y confidencialidad de Azure Active Directory para grupos de Microsoft 365

En este artículo se describen las etiquetas clásicas de clasificación y confidencialidad de Azure Active Directory.

[Estos servicios](./sensitivity-labels-teams-groups-sites.md) admiten etiquetas de confidencialidad.

Para obtener información completa sobre las etiquetas de confidencialidad, consulte [Información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Para obtener más información sobre las etiquetas de confidencialidad y su comportamiento para sitios y grupos de Microsoft 365, consulte [Uso de etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md).

Consulte los siguientes escenarios para ver los procedimientos recomendados al migrar de la clasificación clásica de AAD a las etiquetas de confidencialidad.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Escenario 1: El inquilino nunca usó las clasificaciones clásicas de AAD ni las etiquetas de confidencialidad para documentos y correos electrónicos

- El Administración de inquilino habilita las etiquetas de confidencialidad para los grupos estableciendo la marca de inquilino "EnableMIPLabels" en true a través del cmdlet de PowerShell de AAD.
- El Administración de inquilino crea las etiquetas de confidencialidad en el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com).
    - El administrador de inquilinos puede elegir acciones relacionadas con el archivo y el correo electrónico, como el cifrado y la marca de agua.
    - El administrador de inquilinos puede elegir Grupos de Microsoft 365 y acciones relacionadas con el sitio de SharePoint Online para las etiquetas de confidencialidad.
- El inquilino Administración publica la directiva.
- **Las cargas de trabajo compatibles** muestran etiquetas de confidencialidad. Use las etiquetas de confidencialidad para crear grupos. Las cargas de trabajo compatibles son los servicios que admiten etiquetas de confidencialidad.
- **Las cargas de trabajo no compatibles** son los servicios que aún no admiten etiquetas de confidencialidad. Los grupos se pueden crear, pero no se pueden asociar a la etiqueta de confidencialidad a través de cargas de trabajo no compatibles. Para asociar estos grupos a etiquetas de confidencialidad, los administradores de inquilinos pueden ejecutar cmdlets de PowerShell.

Tabla 1. Comportamiento de cargas de trabajo compatibles y no compatibles: creación, edición o eliminación de grupos

|Carga de trabajo|¿Qué lista de etiquetas ve el usuario en la ventana de grupo?|Creación de un nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibles   |etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |No hay etiquetas de confidencialidad visibles. |El usuario puede crear un grupo sin seleccionar la etiqueta de confidencialidad. <br><br> Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1**: Ninguna etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2**: etiqueta de confidencialidad aplicada anteriormente en segundo plano mediante el cmdlet . El usuario puede editar un grupo correctamente, excluyendo el caso en el que el usuario selecciona una combinación no válida de configuración de privacidad con respecto a la etiqueta. |Ningún cambio de comportamiento.|

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilita las etiquetas de confidencialidad en su inquilino y su usuario se encuentra en una versión anterior del cliente de escritorio de Outlook (Win 32):
>
> - El usuario ve que las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se invalida mediante la configuración de privacidad de la etiqueta de confidencialidad aplicada.
>
> Se recomienda que los usuarios en una versión anterior del cliente de Outlook actualicen a la versión más reciente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Escenario 2: El inquilino ya usa [clasificaciones clásicas](../enterprise/manage-microsoft-365-groups-with-powershell.md) de AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: El inquilino nunca usó etiquetas de confidencialidad para documentos y correos electrónicos

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), se recomienda crear etiquetas de confidencialidad con el mismo nombre que las etiquetas clásicas de Azure AD existentes.
2. Use el cmdlet de PowerShell para aplicar estas etiquetas de confidencialidad a grupos de Microsoft 365 y sitios de SharePoint existentes mediante la asignación de nombres.
3. Administración puede optar por eliminar las etiquetas clásicas de Azure AD:
    - Las cargas de trabajo compatibles muestran que estas etiquetas y grupos de confidencialidad se crean con ellas.
    - Las cargas de trabajo no compatibles funcionan al crear grupos, pero no se les adjunta ninguna etiqueta de confidencialidad.
4. Los administradores pueden ejecutar cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos sin etiquetas.
    - Como alternativa, un administrador puede elegir mantener las etiquetas clásicas de Azure AD:
        - Las cargas de trabajo compatibles muestran estas etiquetas de confidencialidad y los grupos se crean con ellas. Las cargas de trabajo compatibles son los servicios que admiten etiquetas de confidencialidad.
        - Las cargas de trabajo no compatibles funcionan al crear grupos y muestran etiquetas clásicas de Azure AD. Estas etiquetas clásicas de Azure AD se adjuntan a estos grupos creados con cargas de trabajo no compatibles.
5. Se recomienda encarecidamente que los administradores ejecuten cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos con etiquetas clásicas de Azure AD.

Tabla 2. Comportamiento de cargas de trabajo compatibles y no compatibles: creación, edición o eliminación de grupos

|Carga de trabajo|¿Qué lista de etiquetas ve el usuario en la ventana de grupo?|Creación de un nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatibles   |etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |Etiquetas de AAD clásicas antiguas. |El usuario puede crear un grupo con la etiqueta clásica de Azure AD seleccionada. <br><br>Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1**: Ninguna etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2**: Etiquetas de AAD clásicas seleccionadas anteriormente. El usuario puede editar un grupo.<br><br> **Caso 3**: etiqueta de confidencialidad aplicada anteriormente en segundo plano mediante el cmdlet . El usuario debe poder editar un grupo, excepto un caso en el que el usuario selecciona una combinación no válida de configuración de privacidad con respecto a la etiqueta. |El usuario puede eliminar un grupo. |

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilita las etiquetas de confidencialidad en su inquilino y su usuario se encuentra en una versión anterior del cliente de escritorio de Outlook (Win 32):
>
> - El usuario ve que las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se invalida mediante la configuración de privacidad de la etiqueta de confidencialidad aplicada.
>
> Se recomienda que los usuarios en una versión anterior del cliente de Outlook actualicen a la versión más reciente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: El inquilino usó etiquetas de confidencialidad para documentos y correos electrónicos

1. En cuanto el administrador habilita la característica de etiqueta de confidencialidad en el inquilino estableciendo la marca de inquilino "EnableMIPLabels" en true, aparecen las etiquetas de confidencialidad de documentos y correos electrónicos en los cuadros de diálogo de creación y edición de grupos, sitios o equipos.
2. Un administrador puede usar las mismas etiquetas de confidencialidad de documentos y correo electrónico para aplicar la privacidad y el acceso de usuarios externos en el grupo, sitio o equipo especificando la configuración del grupo relacionada:
    1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), seleccione la pestaña **Sitios y grupos**.
    2. Edite un documento o una etiqueta de confidencialidad de correo electrónico.

## <a name="sample-script"></a>Script de ejemplo

Para obtener un script de ejemplo para migrar grupos con etiquetas de AAD clásicas a etiquetas de confidencialidad, consulte [Clasificación de grupos de Azure AD clásica](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification).
