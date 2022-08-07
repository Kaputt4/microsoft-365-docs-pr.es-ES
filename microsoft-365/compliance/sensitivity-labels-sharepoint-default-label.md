---
title: Configurar una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Configure una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint para documentos nuevos y sin etiquetar.
ms.openlocfilehash: 4ffb0dacac36c79593a8cdfbeed0f4360e246f35
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276445"
---
# <a name="configure-a-default-sensitivity-label-for-a-sharepoint-document-library"></a>Configurar una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Esta característica se está implementando gradualmente en versión preliminar y está sujeta a cambios. También es una característica premium con detalles de licencia que se proporcionarán cuando la característica esté disponible con carácter general (GA).
> 
> Para leer el anuncio de vista previa, consulte la [entrada de blog](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/public-preview-default-label-for-a-document-library-in/ba-p/3585136).

Cuando SharePoint está [habilitado para etiquetas de confidencialidad](sensitivity-labels-sharepoint-onedrive-files.md), puede configurar una etiqueta predeterminada para las bibliotecas de documentos. A continuación, los archivos nuevos cargados en esa biblioteca o los archivos existentes editados en la biblioteca tendrán esa etiqueta aplicada si aún no tienen una etiqueta de confidencialidad o tienen una etiqueta de confidencialidad pero con [prioridad inferior](sensitivity-labels.md#label-priority-order-matters).

Por ejemplo, la etiqueta **Confidencial** se configura como la etiqueta de confidencialidad predeterminada para una biblioteca de documentos. Un usuario que tiene **General** como etiqueta predeterminada de directiva guarda un nuevo archivo en esa biblioteca. SharePoint etiquetará este archivo como **Confidencial** debido a la mayor prioridad de esa etiqueta. Para obtener un resumen rápido de los resultados posibles, vea [Will an existing label be over invalidado](#will-an-existing-label-be-overridden) en esta página.

Una etiqueta predeterminada ofrece un nivel de protección de línea base y una forma de etiquetado automático sin inspección de contenido. Para ayudarle a distinguir entre la etiqueta predeterminada de esta característica con la etiqueta predeterminada en las directivas de etiqueta:

- **Etiqueta de confidencialidad predeterminada para una biblioteca de documentos**: etiquetado basado en ubicación, aplicable solo para SharePoint. Invalida una etiqueta de prioridad inferior a menos que se aplique manualmente.
- **Etiqueta de confidencialidad predeterminada de una directiva**: siempre aplicable para todas las ubicaciones. Nunca invalida una etiqueta existente.

Cuando se usa Office en la Web para crear o editar un archivo, la etiqueta de confidencialidad predeterminada para una biblioteca de documentos se puede aplicar sin retrasos. Sin embargo, el etiquetado no es inmediato si carga un archivo o lo crea mediante Microsoft 365 应用版 en Windows, macOS, iOS o Android y, a continuación, guárdelo en SharePoint:

- Carga de archivos: la etiqueta puede tardar unos minutos en aplicarse.
- Microsoft 365 应用版: la etiqueta se aplica después de cerrar la aplicación.

## <a name="will-an-existing-label-be-overridden"></a>¿Se invalidará una etiqueta ya existente?

Resumen de los resultados:

|Etiqueta ya existente |Invalidación con la etiqueta predeterminada de la biblioteca |
|:-----|:-----|:-----|
|Aplicado manualmente, cualquier prioridad| No |
|Aplicado automáticamente, prioridad inferior | Sí |
|Aplicado automáticamente, mayor prioridad | No |
|Etiqueta predeterminada de la directiva, prioridad inferior | Sí |
|Etiqueta predeterminada de la directiva, prioridad superior | No |

## <a name="requirements"></a>Requisitos

- Tiene [etiquetas de confidencialidad habilitadas para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

- [SharePoint Information Rights Management (IRM) no está habilitado para la biblioteca](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists). Esta tecnología anterior no es compatible con el uso de una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint. Si una biblioteca está habilitada para IRM, no podrá seleccionar una etiqueta de confidencialidad predeterminada.

## <a name="limitations"></a>Limitaciones

- No se aplica a los archivos existentes en reposo en SharePoint.

- A menos que haya [habilitado la coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md), verá un retraso en la aplicación de la etiqueta de confidencialidad predeterminada para una biblioteca de documentos cuando los usuarios **seleccionen la** \> opción **Guardar como** archivo.

- Al igual que con las etiquetas de confidencialidad para Office på nettet, algunas [configuraciones de etiquetas que aplican cifrado](encryption-sensitivity-labels.md#configure-encryption-settings) no son adecuadas para SharePoint, por lo que no admiten una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint:
    - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y la casilla **En Word, PowerPoint y Excel, pedir a los usuarios que especifiquen permisos** seleccionada. A veces, esta configuración se conoce como "permisos definidos por el usuario".
    - **El acceso del usuario al contenido expira** establecido en un valor distinto de **Nunca**.
    - **Cifrado de clave doble** seleccionado.

## <a name="how-to-configure-a-default-sensitivity-label-for-a-sharepoint-document-library"></a>Configuración de una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint

Para una biblioteca de documentos existente:

1. En SharePoint, vaya a la configuración de la biblioteca **de documentos Configuración** \> **de la biblioteca**\>.

2. En el panel flotante **Configuración** de biblioteca, seleccione **Etiquetas de confidencialidad predeterminadas** y, a continuación, seleccione una etiqueta en el cuadro desplegable. Por ejemplo:
    
    ![Captura de pantalla que muestra cómo configurar una etiqueta de confidencialidad predeterminada para una biblioteca de SharePoint.](../media/default-sensitivity-label-spo2.png)
    
    Aunque vea que la configuración menciona la compatibilidad con archivos PDF, este tipo de archivo no se admite actualmente en este escenario.

Si va a crear una nueva biblioteca de documentos, puede configurar la misma configuración de **etiquetas de confidencialidad predeterminadas** en el panel flotante **Crear biblioteca de documentos** .

> [!NOTE]
> Esta nueva configuración se está implementando gradualmente en los inquilinos. Si no los ve, inténtelo de nuevo en unos días.

## <a name="monitoring-application-of-library-default-sensitivity-labels"></a>Supervisión de la aplicación de etiquetas de confidencialidad predeterminadas de la biblioteca

Use la columna **Confidencialidad de** SharePoint para ver los nombres de las etiquetas de confidencialidad aplicadas a los archivos. Cuando esta característica ha aplicado la etiqueta, la información sobre herramientas del nombre de la etiqueta muestra **Este archivo se ha etiquetado automáticamente**. Sin embargo, esta información sobre herramientas no es exclusiva de la etiqueta de confidencialidad predeterminada para una biblioteca de documentos. También se muestra cuándo se aplican las etiquetas de confidencialidad mediante directivas de etiquetado automático o como resultado de la etiqueta predeterminada de un usuario de las directivas de etiqueta de confidencialidad.

Para identificar específicamente cuándo se aplicó la etiqueta debido a la etiqueta de confidencialidad predeterminada de la biblioteca, use el [registro de auditoría en el portal de cumplimiento](search-the-audit-log-in-security-and-compliance.md) y el evento de auditoría de **archivos de etiqueta de confidencialidad aplicada** del grupo **actividades Etiqueta de confidencialidad** . Luego:
1. Seleccione una entrada para ver los detalles en un panel flotante.

2. En el panel de detalles, desplácese hasta la **sección SensitivityLabelEventData** e identifique el valor de **ActionScourceDetails**.

3. Se usa un valor de **6** para cuando se aplicó la etiqueta debido a la etiqueta de confidencialidad predeterminada para la biblioteca de documentos.

Para auditar la configuración de esta característica, use el evento de auditoría de **lista Actualizado** del grupo de **actividades de lista de SharePoint** . En el panel flotante de detalles de la biblioteca de documentos, desplácese hasta la sección **SensitivityLabelEventData** , donde **OldSensitivityLabeld** y **SensitivityLabelId** pueden reflejar tres cambios de estados:

- Etiqueta de confidencialidad aplicada
- Etiqueta de confidencialidad cambiada de una etiqueta a otra
- Etiqueta de confidencialidad eliminada

Para asignar GUID de etiqueta de confidencialidad a nombres de etiqueta, use el cmdlet [Get-Label](/powershell/module/exchange/get-label) :

1. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. A continuación, ejecute el siguiente comando, donde especifique el GUID:

    ```powershell
    Get-Label -Identity "<GUID>" | Name

## Next steps

Default labeling ensures a minimum level of protection but doesn't take into account the file contents that might require a higher level of protection. Consider supplementing this labeling method with [automatic labeling](apply-sensitivity-label-automatically.md) that uses content inspection, and encourage [manual labeling](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) for users to replace the default label when needed.