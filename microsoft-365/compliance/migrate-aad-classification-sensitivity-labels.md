---
title: Etiquetas de clasificación y confidencialidad de Azure Active Directory para grupos de Microsoft 365
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: En este artículo se analizan las etiquetas clásicas de clasificación y confidencialidad de Azure Active Directory.
ms.openlocfilehash: 1be7e31ee4091e561f7eedb34b41958efc69a339
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926338"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Etiquetas de clasificación y confidencialidad de Azure Active Directory para grupos de Microsoft 365

En este artículo se analizan las etiquetas clásicas de clasificación y confidencialidad de Azure Active Directory.

Estos servicios admiten etiquetas [de confidencialidad.](./sensitivity-labels-teams-groups-sites.md#support-for-the-sensitivity-labels)

Para obtener información completa acerca de las etiquetas de confidencialidad, [consulta Información sobre etiquetas de confidencialidad.](sensitivity-labels.md)

Para obtener más información sobre las etiquetas de confidencialidad y su comportamiento para sitios y grupos de Microsoft 365, vea Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de [Microsoft 365](sensitivity-labels-teams-groups-sites.md)y sitios de SharePoint.

Vea los siguientes escenarios para obtener procedimientos recomendados al migrar de la clasificación clásica de AAD a las etiquetas de confidencialidad.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Escenario 1: el inquilino nunca usó clasificaciones clásicas de AAD o etiquetas de confidencialidad para documentos y correos electrónicos

- El administrador de inquilinos habilita las etiquetas de confidencialidad para los grupos estableciendo la marca de inquilino "EnableMIPLabels" en true a través del cmdlet de powershell de AAD.
- El administrador de inquilinos crea las etiquetas de confidencialidad en el Centro de [cumplimiento de Microsoft 365](https://compliance.microsoft.com).
    - El administrador de inquilinos puede elegir acciones relacionadas con el archivo y el correo electrónico, como el cifrado y la marca de agua.
    - El administrador de inquilinos puede elegir grupos de Microsoft 365 y acciones relacionadas con el sitio de SharePoint Online para las etiquetas de confidencialidad.
- El administrador de inquilinos publica la directiva.
- **Las cargas de trabajo compatibles** muestran etiquetas de confidencialidad. Use las etiquetas de confidencialidad para crear grupos. Las cargas de trabajo compatibles son los servicios que admiten etiquetas de confidencialidad.
- **Las cargas de trabajo no** compatibles son los servicios que aún no admiten etiquetas de confidencialidad. Los grupos se pueden crear, sin embargo, no pueden asociarse con la etiqueta de confidencialidad a través de cargas de trabajo no compatibles. Para asociar estos grupos con etiquetas de confidencialidad, los administradores de inquilinos pueden ejecutar cmdlets de PowerShell.

Tabla 1. Comportamiento de cargas de trabajo compatibles y no compatibles: crear, editar o eliminar grupos

|Carga de trabajo|¿Qué lista de etiquetas ve el usuario en la ventana de grupo?|Crear nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatible   |etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |No hay etiquetas de confidencialidad visibles. |El usuario puede crear un grupo sin seleccionar la etiqueta de confidencialidad. <br><br> Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1:** No hay etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2:** etiqueta de confidencialidad aplicada anteriormente en segundo plano mediante cmdlet. El usuario puede editar un grupo correctamente, excluyendo el caso en el que el usuario selecciona una combinación no válida de configuración de privacidad con respecto a la etiqueta. |Ningún cambio de comportamiento.|

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilita etiquetas de confidencialidad en su inquilino y su usuario está en una versión anterior del cliente de escritorio de Outlook (Win 32):
>
> - El usuario ve que las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se invalida mediante la configuración de privacidad de la etiqueta de confidencialidad aplicada.
>
> Se recomienda que los usuarios de una versión antigua del cliente de Outlook actualicen a la versión más reciente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Escenario 2: El inquilino ya usa clasificaciones [clásicas de](../enterprise/manage-microsoft-365-groups-with-powershell.md) AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: el inquilino nunca usó etiquetas de confidencialidad para documentos y correos electrónicos

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)se recomienda crear etiquetas de confidencialidad con el mismo nombre que las etiquetas clásicas de Azure AD existentes.
2. Use el cmdlet de PowerShell para aplicar estas etiquetas de confidencialidad a los grupos de Microsoft 365 existentes y los sitios de SharePoint mediante la asignación de nombres.
3. El administrador puede elegir eliminar las etiquetas clásicas de Azure AD:
    - Las cargas de trabajo compatibles muestran que estas etiquetas de confidencialidad y los grupos se crean con ellas.
    - Las cargas de trabajo no compatibles funcionan al crear grupos, pero no se les adjunta ninguna etiqueta de confidencialidad.
4. Los administradores pueden ejecutar cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos sin etiquetas.
    - Como alternativa, un administrador puede elegir conservar las etiquetas clásicas de Azure AD:
        - Las cargas de trabajo compatibles muestran estas etiquetas de confidencialidad y los grupos se crean con ellas. Las cargas de trabajo compatibles son los servicios que admiten etiquetas de confidencialidad.
        - Las cargas de trabajo no compatibles funcionan al crear grupos y muestran etiquetas clásicas de Azure AD. Estas etiquetas clásicas de Azure AD se adjuntan a estos grupos creados con cargas de trabajo no compatibles.
5. Se recomienda encarecidamente que los administradores ejecuten cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos con etiquetas clásicas de Azure AD.

Tabla 2. Comportamiento de cargas de trabajo compatibles y no compatibles: crear, editar o eliminar grupos

|Carga de trabajo|¿Qué lista de etiquetas ve el usuario en la ventana de grupo?|Crear nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Compatible   |etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |Etiquetas de AAD clásicas antiguas. |El usuario puede crear un grupo con la etiqueta clásica de Azure AD seleccionada. <br><br>Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1:** No hay etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2:** etiquetas clásicas de AAD previamente seleccionadas. El usuario puede editar un grupo.<br><br> **Caso 3:** etiqueta de confidencialidad aplicada anteriormente en segundo plano mediante cmdlet. El usuario debe poder editar un grupo, excepto un caso en el que el usuario selecciona una combinación no válida de configuración de privacidad con respecto a la etiqueta. |El usuario puede eliminar un grupo. |

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilita etiquetas de confidencialidad en su inquilino y su usuario está en una versión anterior del cliente de escritorio de Outlook (Win 32):
>
> - El usuario ve que las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se invalida mediante la configuración de privacidad de la etiqueta de confidencialidad aplicada.
>
> Se recomienda que los usuarios de una versión antigua del cliente de Outlook actualicen a la versión más reciente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: El inquilino usa etiquetas de confidencialidad para documentos y correos electrónicos

1. Tan pronto como el administrador habilita la característica de etiqueta de confidencialidad en el inquilino estableciendo la marca de inquilino "EnableMIPLabels" en true, aparecerán las etiquetas de confidencialidad de documento y correo electrónico en cuadros de diálogo de creación y edición de grupo,sitio o equipo.
2. Un administrador puede usar las mismas etiquetas de confidencialidad de documentos y correo electrónico para exigir la privacidad y el acceso de usuarios externos en el grupo, sitio o equipo especificando la configuración de grupo relacionada:
    1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)seleccione la pestaña Sitios **y** grupos.
    2. Edite una etiqueta de confidencialidad de documento o correo electrónico.

## <a name="sample-script"></a>Script de ejemplo

Para obtener un script de ejemplo para migrar grupos con etiquetas clásicas de AAD a etiquetas de confidencialidad, vea [Classic Azure AD group classification](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification).