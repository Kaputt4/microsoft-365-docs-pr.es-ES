---
title: Etiquetas de confidencialidad y clasificación de Azure Active Directory para grupos de 365 de Microsoft
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: En este artículo se describen las etiquetas de confidencialidad y clasificación de Azure Active Directory clásicas.
ms.openlocfilehash: f11473653884392048d5f9a84f8e284dba5f6f27
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755394"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Etiquetas de confidencialidad y clasificación de Azure Active Directory para grupos de 365 de Microsoft

En este artículo se describen las etiquetas de confidencialidad y clasificación de Azure Active Directory clásicas.

[Estos servicios](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)admiten las etiquetas de confidencialidad.

Para obtener información completa acerca de las etiquetas de confidencialidad, consulte [información sobre las etiquetas de confidencialidad](sensitivity-labels.md).

Para obtener más información sobre las etiquetas de confidencialidad y su comportamiento para los sitios y los grupos de Microsoft 365, consulte [usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de microsoft 365 y sitios de SharePoint](sensitivity-labels-teams-groups-sites.md).

Consulte los siguientes escenarios para conocer los procedimientos recomendados a la hora de migrar de una clasificación clásica de AAD a las etiquetas de confidencialidad.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Escenario 1: el inquilino nunca usaba las clasificaciones de AAD clásicas o las etiquetas de confidencialidad para documentos y correos electrónicos

- El administrador de espacios empresariales habilita las etiquetas de confidencialidad para los grupos estableciendo el indicador de inquilino "EnableMIPLabels" en true mediante el cmdlet de PowerShell de AAD.
- El administrador de inquilinos crea las etiquetas de confidencialidad en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
    - El administrador de inquilinos puede elegir acciones relacionadas con el correo electrónico y archivos como el cifrado y la marca de agua.
    - El administrador de inquilinos puede elegir los grupos de Microsoft 365 y las acciones relacionadas con el sitio de SharePoint Online para las etiquetas de confidencialidad.
- El administrador del espacio empresarial publica la Directiva.
- Las **cargas de trabajo compatibles** muestran las etiquetas de confidencialidad. Use las etiquetas de confidencialidad para crear grupos. Las cargas de trabajo compatibles son los servicios que admiten las etiquetas de confidencialidad.
- Las **cargas de trabajo no compatibles** son los servicios que aún no admiten las etiquetas de confidencialidad. No obstante, se pueden crear grupos, pero no pueden asociarse con la etiqueta de confidencialidad a través de cargas de trabajo no compatibles. Para asociar estos grupos a las etiquetas de confidencialidad, los administradores de espacios empresariales pueden ejecutar cmdlets de PowerShell.

Tabla 1. Comportamiento de las cargas de trabajo compatibles y no compatibles: creación, edición o eliminación de grupos

|Carga de trabajo|¿Qué etiqueta muestra el usuario en la ventana de grupo?|Crear nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Con   |las etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |No se ve ninguna etiqueta de confidencialidad. |El usuario puede crear un grupo sin seleccionar la etiqueta de confidencialidad. <br><br> Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1**: no hay etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2**: etiqueta de confidencialidad aplicada anteriormente en segundo plano con el cmdlet. El usuario puede editar un grupo correctamente, excluido el caso en el que el usuario selecciona una combinación no válida de la configuración de privacidad con respecto a la etiqueta. |Ningún cambio de comportamiento.|

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilite las etiquetas de confidencialidad en su espacio empresarial y que su usuario esté en una versión anterior del cliente de escritorio de Outlook (Win 32):
> - El usuario ve las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se reemplaza por la configuración de privacidad de la etiqueta de confidencialidad aplicada.
> Se recomienda que los usuarios de una versión antigua del cliente de Outlook se actualicen a la versión más reciente.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Escenario 2: el inquilino ya usa las [clasificaciones](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization) clásicas de AAD

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Caso A: espacio empresarial no usado nunca etiquetas de sensibilidad para documentos y correos electrónicos

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), se recomienda crear etiquetas de confidencialidad con el mismo nombre que las etiquetas de Azure ad clásicas existentes.
2. Use el cmdlet de PowerShell para aplicar estas etiquetas de confidencialidad a los grupos de Microsoft 365 y a los sitios de SharePoint existentes que usan la asignación de nombres.
3. El administrador puede elegir eliminar las etiquetas de Azure AD clásicas:
    - Las cargas de trabajo compatibles muestran los grupos y las etiquetas de confidencialidad que se crean con ellos.
    - Las cargas de trabajo no compatibles funcionan cuando se crean grupos pero no se les adjunta ninguna etiqueta de confidencialidad.
4. Los administradores pueden ejecutar cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos sin etiquetas.
    - Como alternativa, un administrador puede elegir mantener las etiquetas de Azure AD clásicas:
        - Las cargas de trabajo compatibles muestran estas etiquetas de confidencialidad y los grupos se crean con ellas. Las cargas de trabajo compatibles son los servicios que admiten las etiquetas de confidencialidad.
        - Las cargas de trabajo no compatibles funcionan cuando se crean grupos y se muestran las etiquetas de Azure AD clásicas. Estas etiquetas clásicas de Azure AD se adjuntan a estos grupos creados con cargas de trabajo no compatibles.
5. Es muy recomendable que los administradores ejecuten cmdlets de PowerShell para aplicar etiquetas de confidencialidad a estos grupos con etiquetas de Azure AD clásicas.

Tabla 2. Comportamiento de las cargas de trabajo compatibles y no compatibles: creación, edición o eliminación de grupos

|Carga de trabajo|¿Qué etiqueta muestra el usuario en la ventana de grupo?|Crear nuevo grupo |Editar grupo |Eliminar grupo |
|:-------|:-------|:--------|:--------|:--------|   
|Con   |las etiquetas de confidencialidad. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |Ningún cambio de comportamiento. |
|No compatible |Antiguas etiquetas de AAD clásicas. |El usuario puede crear un grupo con la etiqueta clásica de Azure AD seleccionada. <br><br>Tenga en cuenta que el administrador puede ejecutar cmdlets para aplicar etiquetas de confidencialidad en segundo plano. |**Caso 1**: no hay etiqueta de confidencialidad seleccionada anteriormente. El usuario puede editar un grupo.<br><br> **Caso 2**: etiquetas de AAD clásicas previamente seleccionadas. El usuario puede editar un grupo.<br><br> **Caso 3**: etiqueta de confidencialidad aplicada anteriormente en segundo plano con el cmdlet. El usuario debe ser capaz de editar un grupo, excluido un caso en el que el usuario selecciona una combinación no válida de configuración de privacidad con respecto a la etiqueta. |El usuario puede eliminar un grupo. |

> [!NOTE]
> En el caso del cliente de escritorio de Outlook (Win 32), después de que el administrador habilite las etiquetas de confidencialidad en su espacio empresarial y que su usuario esté en una versión anterior del cliente de escritorio de Outlook (Win 32):
> - El usuario ve las etiquetas de confidencialidad aparecen en la versión anterior del cliente de escritorio de Outlook.
> - Sin embargo, cuando el usuario edita un grupo y guarda el grupo con una etiqueta de confidencialidad, la configuración de privacidad seleccionada se reemplaza por la configuración de privacidad de la etiqueta de confidencialidad aplicada.
> Se recomienda que los usuarios de una versión antigua del cliente de Outlook se actualicen a la versión más reciente.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Caso B: etiquetas de confidencialidad usadas por inquilino para documentos y correos electrónicos

1. En cuanto el administrador habilita la característica de etiqueta de confidencialidad estableciendo la marca de inquilino "EnableMIPLabels" en true, aparecen las etiquetas de confidencialidad del documento y del correo electrónico en los cuadros de diálogo crear y editar del grupo/sitio/equipo.
2. Un administrador puede usar el mismo documento y las etiquetas de confidencialidad del correo electrónico para aplicar privacidad y el acceso de usuarios externos en el grupo/sitio/equipo especificando la configuración de grupo relacionada:
    1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), seleccione la pestaña **sitios y grupos** .
    2. Editar una etiqueta de confidencialidad de documento o correo electrónico.

## <a name="sample-script"></a>Script de ejemplo

Para obtener un script de ejemplo para migrar grupos con etiquetas clásicas de AAD a etiquetas de confidencialidad, consulte [Classic Azure ad Group Classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

