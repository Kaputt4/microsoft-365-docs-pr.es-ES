---
title: Eliminar elementos de la carpeta Elementos recuperables
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Obtenga información sobre cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón está en suspensión legal.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
ms.openlocfilehash: 2c512cda6df8d83301702062ad5a38d2a86b6c14
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67817364"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube

La carpeta Elementos recuperables de un buzón de Exchange Online existe para protegerse de eliminaciones accidentales o malintencionadas. También se usa para almacenar elementos a los que se conserva y al que acceden las características de cumplimiento, como las retenciones y las búsquedas de eDiscovery. Sin embargo, en algunas situaciones, las organizaciones pueden tener datos que se han conservado involuntariamente en la carpeta Elementos recuperables que deben eliminar. Por ejemplo, un usuario podría enviar o reenviar sin saberlo un mensaje de correo electrónico que contenga información confidencial o información que pueda tener consecuencias empresariales graves. Incluso si el mensaje se elimina permanentemente, puede conservarse indefinidamente porque se ha colocado una suspensión legal en el buzón. Este escenario se conoce como *derrame de datos* porque los datos se han *derramado* involuntariamente en Office 365. En estas situaciones, puede eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón está en suspensión con una de las distintas características de suspensión de Office 365. Estos tipos de retenciones incluyen retenciones por juicio, retenciones de In-Place, retenciones de exhibición de documentos electrónicos y directivas de retención creadas en el centro de seguridad y cumplimiento de Office 365 o Microsoft 365.

En este artículo se explica cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables para los buzones basados en la nube que están en espera. Este procedimiento implica deshabilitar el acceso al buzón de correo y deshabilitar la recuperación de elementos únicos, deshabilitar el Asistente para carpetas administradas para que no procese el buzón, quitar temporalmente la suspensión, eliminar elementos de la carpeta Elementos recuperables y, a continuación, revertir el buzón a su configuración anterior. Este es el proceso:
  
[Paso 1: Recopilar información sobre el buzón](#step-1-collect-information-about-the-mailbox)

[Paso 2: Preparar el buzón](#step-2-prepare-the-mailbox)

[Paso 3: Quitar todas las retenciones del buzón](#step-3-remove-all-holds-from-the-mailbox)

[Paso 4: Quitar la retención de retraso del buzón](#step-4-remove-the-delay-hold-from-the-mailbox)

[Paso 5: Eliminar elementos en la carpeta Elementos recuperables](#step-5-delete-items-in-the-recoverable-items-folder)

[Paso 6: Revertir el buzón a su estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Los procedimientos descritos en este artículo harán que los datos se eliminen (purguen) permanentemente de un buzón de Exchange Online. Esto significa que los mensajes que elimina de la carpeta Elementos recuperables no se pueden recuperar y no estarán disponibles para la detección legal u otros fines de cumplimiento. Si desea eliminar mensajes de un buzón que se encuentra en suspensión como parte de una suspensión por juicio, In-Place suspensión, suspensión de exhibición de documentos electrónicos o directiva de retención creada en el portal de cumplimiento Microsoft Purview, consulte con los departamentos legales o de administración de registros antes de quitar la suspensión. Su organización puede tener una directiva que defina si un buzón en espera o un incidente de derrame de datos tiene prioridad.
  
## <a name="before-you-delete-items"></a>Antes de eliminar elementos

- Para crear y ejecutar una búsqueda de contenido, tiene que ser miembro del grupo de roles Administrador de eDiscovery o tener asignado el rol de administración Búsqueda de cumplimiento. Para eliminar mensajes, tiene que ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración Búsqueda y eliminación. Para obtener información sobre cómo agregar usuarios a un grupo de roles, vea [Asignar permisos de exhibición de documentos electrónicos](./assign-ediscovery-permissions.md).

- Si se asigna un buzón a una directiva de retención de toda la organización, debe excluir el buzón de la directiva antes de poder eliminar elementos de la carpeta Elementos recuperables. Puede tardar hasta 24 horas en sincronizar el cambio de directiva y quitar el buzón de la directiva. Para obtener más información, vea "Directivas de retención para toda la organización" en la sección [Quitar todas las retenciones del buzón](#organization-wide-retention-policies) de este artículo.

- No puede realizar este procedimiento para un buzón al que se le haya asignado la configuración de retención con una directiva de retención bloqueada mediante el bloqueo de conservación. Esto se debe a que este bloqueo impide quitar o excluir el buzón de la directiva y deshabilitar el Asistente para carpetas administradas en el buzón. Para obtener más información sobre las directivas de bloqueo para la retención, consulte [Uso del bloqueo de conservación para restringir los cambios en las directivas de retención y las directivas de etiquetas de retención](retention-preservation-lock.md).

- El procedimiento descrito en este artículo no es compatible con los buzones inactivos. Esto se debe a que no puede volver a aplicar una suspensión (o directiva de retención) a un buzón inactivo después de quitarlo. Al quitar una retención de un buzón inactivo, se cambia a un buzón de correo normal eliminado temporalmente y se eliminará permanentemente de la organización después de que el Asistente para carpetas administradas lo procese.

- Si un buzón no está en espera (o no tiene habilitada la recuperación de un solo elemento), puede eliminar los elementos de la carpeta Elementos recuperables. Para obtener más información sobre cómo hacerlo, consulte [Búsqueda y eliminación de mensajes de correo electrónico en su organización](./search-for-and-delete-messages-in-your-organization.md).

## <a name="step-1-collect-information-about-the-mailbox"></a>Paso 1: Recopilar información sobre el buzón

Este primer paso consiste en recopilar las propiedades seleccionadas del buzón de destino que afectarán a este procedimiento. Asegúrese de anotar esta configuración o guardarla en un archivo de texto porque cambiará algunas de estas propiedades y, a continuación, revertirá a los valores originales del paso 6, después de eliminar elementos de la carpeta Elementos recuperables. Esta es una lista de las propiedades de buzón que necesita recopilar.
  
- *SingleItemRecoveryEnabled*  y  *RetainDeletedItemsFor*. Si es necesario, deshabilitará la recuperación única y aumentará el período de retención de elementos eliminados en el paso 3.

- *LitigationHoldEnabled*  e  *InPlaceHolds*. Debe identificar todas las retenciones colocadas en el buzón de correo para poder quitarlas temporalmente en el paso 3. Consulte la sección [Más información](#more-information) para obtener sugerencias sobre cómo identificar el tipo de suspensión que se puede colocar en un buzón.

Además, debe obtener la configuración de acceso de cliente del buzón para que pueda deshabilitarlas temporalmente para que el propietario (u otros usuarios) no pueda acceder al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta Elementos recuperables. Después de eliminar elementos de la carpeta Elementos recuperables del paso 5, usará esta información para comprobar que los elementos se quitaron.
  
1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador a la que se hayan asignado los roles de administración adecuados en Exchange Online.

2. Ejecute el siguiente comando para obtener información sobre la recuperación de elementos únicos y el período de retención de elementos eliminados.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Si la recuperación de un solo elemento está habilitada, tendrá que deshabilitarla en el paso 2. Si el período de retención de elementos eliminados no se establece durante 30 días (el valor máximo en Exchange Online), puede aumentarlo en el paso 2.

3. Ejecute el siguiente comando para obtener la configuración de acceso del buzón de correo.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Deshabilitará todos estos métodos de acceso en el paso 2.

4. Ejecute el siguiente comando para obtener información sobre las retenciones y las directivas de retención aplicadas al buzón.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos ellos, puede ejecutar el  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente.
  
5. Ejecute el siguiente comando para obtener información sobre las directivas de retención de toda la organización. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Si su organización tiene directivas de retención para toda la organización, tendrá que excluir el buzón de correo de estas directivas en el paso 3. El cambio puede tardar hasta 24 horas en replicarse.

    > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos ellos, puede ejecutar el  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada valor en una línea independiente. 
  
6. Ejecute el siguiente comando para determinar si se aplica una retención retrasada al buzón de correo.

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   Si el valor de la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* está establecido en **True**, se aplica una suspensión de retraso al buzón y se debe quitar. Para obtener más información sobre las retenciones de retraso, vea [Paso 4: Quitar la retención de retraso del buzón](#step-4-remove-the-delay-hold-from-the-mailbox).

   Si el valor de cualquiera de las propiedades se establece en **False**, no se aplica una retención retrasada al buzón de correo y puede omitir el paso 4.

7. Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Si el buzón de archivo del usuario está habilitado, ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas de la carpeta Elementos recuperables de su buzón de archivo. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Al eliminar elementos en el paso 5, puede optar por eliminar o no los elementos de la carpeta Elementos recuperables del buzón de archivo principal del usuario. Si el archivado de expansión automática está habilitado para el buzón, no se eliminarán los elementos de un buzón de archivo auxiliar.
  
## <a name="step-2-prepare-the-mailbox"></a>Paso 2: Preparar el buzón

Después de recopilar y guardar información sobre el buzón de correo, el siguiente paso es preparar el buzón realizando las siguientes tareas:
  
- **Deshabilite el acceso de cliente al buzón de correo para** que el propietario del buzón no pueda acceder a su buzón y realice cambios en los datos del buzón durante este procedimiento.

- **Aumente el período de retención de elementos eliminados** a 30 días (el valor máximo de Exchange Online) para que los elementos no se purguen de la carpeta Elementos recuperables antes de poder eliminarlos en el paso 5.

- **Deshabilite la recuperación de elementos únicos** para que los elementos no se conserven (durante el período de retención de elementos eliminados) después de eliminarlos de la carpeta Elementos recuperables del paso 5.

- **Deshabilite el Asistente para carpetas administradas** para que no procese el buzón y conserve los elementos que elimine en el paso 5.

Realice los pasos siguientes en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para deshabilitar todo el acceso de cliente al buzón. La sintaxis del comando supone que todos los métodos de acceso de cliente se habilitaron en el buzón.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > Puede tardar hasta 60 minutos en deshabilitar todos los métodos de acceso de cliente al buzón. Tenga en cuenta que deshabilitar estos métodos de acceso no desconectará el propietario del buzón si han iniciado sesión actualmente. Si el propietario no ha iniciado sesión, no podrá acceder a su buzón después de deshabilitar estos métodos de acceso.
  
2. Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados en un máximo de 30 días. Se supone que la configuración actual es inferior a 30 días.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Ejecute el siguiente comando para deshabilitar la recuperación de un solo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > La recuperación de un solo elemento puede tardar hasta 240 minutos. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período.
  
4. Ejecute el siguiente comando para evitar que el Asistente para carpetas administradas procese el buzón. Como se explicó anteriormente, puede deshabilitar el Asistente para carpetas administradas solo si no se aplica una directiva de retención con un bloqueo de conservación al buzón.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Paso 3: Quitar todas las retenciones del buzón

El último paso antes de poder eliminar elementos de la carpeta Elementos recuperables es quitar todas las retenciones (que identificó en el paso 1) colocadas en el buzón. Todas las retenciones deben quitarse para que los elementos no se conserven después de eliminarlos de la carpeta Elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar diferentes tipos de retenciones en un buzón de correo. Consulte la sección [Más información](#more-information) para obtener sugerencias sobre cómo identificar el tipo de suspensión que se puede colocar en un buzón. Para obtener más información, vea [Cómo identificar el tipo de retención colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Como se indicó anteriormente, consulte con los departamentos legales o de administración de registros antes de quitar una retención de un buzón de correo.
  
### <a name="litigation-hold"></a>Retención por litigio
  
Ejecute el siguiente comando en Exchange Online PowerShell para quitar una suspensión por juicio del buzón.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> De forma similar a deshabilitar la recuperación de un solo elemento, puede tardar hasta 240 minutos en quitar la suspensión por juicio. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período.
  
### <a name="in-place-hold"></a>Retención en contexto
  
Ejecute el siguiente comando en Exchange Online PowerShell para identificar la suspensión de In-Place que se coloca en el buzón. Use el GUID para el In-Place Hold que identificó en el paso 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Después de identificar el In-Place Detención, puede usar el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> o Exchange Online PowerShell para quitar el buzón de correo de la suspensión. Para obtener más información, consulte [Creación o eliminación de una suspensión de In-Place](/exchange/security-and-compliance/create-or-remove-in-place-holds).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Directivas de retención aplicadas a buzones específicos
  
Ejecute el siguiente comando en [PowerShell de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell) para identificar la directiva de retención que se aplica al buzón. Este comando también devolverá las directivas de retención de conversaciones de Teams aplicadas a un buzón. Use el GUID (sin incluir el `mbx` prefijo o `skp` ) para la directiva de retención que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar la directiva de retención, vaya a la página **Administración** >  del ciclo de vida de datos **de Microsoft 365** > **Retención** en el portal de cumplimiento, edite la directiva de retención que identificó en el paso anterior y quite el buzón de la lista de destinatarios que se incluyen en la directiva de retención.
  
### <a name="organization-wide-retention-policies"></a>Directivas de retención para toda la organización
  
Las directivas de retención de toda la organización, de Toda Exchange y de Teams se aplican a todos los buzones de correo de la organización. Se aplican en el nivel de organización (no en el nivel de buzón) y se devuelven al ejecutar el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando en [PowerShell de cumplimiento de seguridad &](/powershell/exchange/exchange-online-powershell) para identificar las directivas de retención de toda la organización. Use el GUID (sin incluir el  `mbx` prefijo) para las directivas de retención de toda la organización que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar las directivas de retención de toda la organización, vaya a la página **Data lifecycle management** >  Microsoft 365 Retention (Administración del ciclo de vida de datos **de Microsoft 365** > **Retención**) en el portal de cumplimiento, edite cada directiva de retención de toda la organización que haya identificado en el paso anterior y agregue el buzón a la lista de destinatarios excluidos. Al hacerlo, se quitará el buzón de correo del usuario de la directiva de retención.

> [!IMPORTANT]
> Después de excluir un buzón de una directiva de retención de toda la organización, puede tardar hasta 24 horas en sincronizar este cambio y quitar el buzón de la directiva.

### <a name="retention-labels"></a>Etiquetas de retención

Cada vez que un usuario aplica una etiqueta configurada para conservar contenido o conservar y, a continuación, eliminar contenido en cualquier carpeta o elemento de su buzón, la propiedad *ComplianceTagHoldApplied* mailbox se establece en **True**. Cuando esto sucede, se considera que el buzón está en espera, como si se colocara en suspensión por juicio o se asignara a una directiva de retención.

Para ver el valor de la propiedad *ComplianceTagHoldApplied*, ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Una vez que haya identificado que un buzón está en espera porque se aplica una etiqueta de retención a una carpeta o elemento, puede usar la herramienta búsqueda de contenido en el portal de cumplimiento para buscar elementos etiquetados mediante la condición **Etiqueta de retención** . Para obtener más información, consulte:

- La sección "Uso de búsqueda de contenido para buscar todo el contenido con una etiqueta de retención específica" en [Información sobre las directivas de retención y las etiquetas de retención](retention.md#using-content-search-to-find-all-content-with-a-specific-retention-label)

- La sección "Condiciones de búsqueda" en [Consultas de palabras clave y condiciones de búsqueda para Búsqueda de contenido](keyword-queries-and-search-conditions.md#conditions-for-common-properties).

Para obtener más información sobre las etiquetas, consulte [Más información sobre las directivas de retención y las etiquetas de retención](retention.md).

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery
  
Ejecute los siguientes comandos en [PowerShell de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell) para identificar la retención asociada a un caso de exhibición de documentos electrónicos ( *denominados retenciones de eDiscovery*) que se aplica al buzón de correo. Use el GUID (sin incluir el  `UniH` prefijo) para la suspensión de eDiscovery que identificó en el paso 1. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos al que está asociada la suspensión; el tercer comando muestra el nombre de la suspensión.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Después de identificar el nombre del caso de eDiscovery y la suspensión, vaya a la página **eDiscovery** \> **eDiscovery** del centro de cumplimiento, abra el caso y quite el buzón de la suspensión. Para obtener más información sobre cómo identificar las retenciones de eDiscovery, vea la sección "eDiscovery holds" (Retenciones de exhibición de documentos electrónicos) en [How to identify the type of hold placed on an Exchange Online mailbox (Cómo identificar el tipo de suspensión colocada en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Paso 4: Quitar la retención de retraso del buzón

Después de quitar cualquier tipo de suspensión de un buzón, el valor de la propiedad de buzón *DelayHoldApplied* o *DelayReleaseHoldApplied* se establece en **True**. Esto ocurre la próxima vez que el Asistente para carpetas administradas procese el buzón y detecte que se ha quitado una suspensión. Esto se denomina *retención diferida* y significa que la eliminación real de la suspensión se retrasa durante 30 días para evitar que los datos se eliminen permanentemente del buzón. (El propósito de una suspensión retrasada es dar a los administradores la oportunidad de buscar o recuperar elementos de buzón que se purgarán después de quitar una suspensión).  Cuando se coloca una suspensión de retraso en el buzón de correo, el buzón se sigue considerando que está en espera durante un tiempo ilimitado, como si el buzón estuviera en suspensión por juicio. Después de 30 días, la suspensión de retraso expira y Microsoft 365 intentará quitar automáticamente la suspensión de retraso (estableciendo la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* en **False**) para que se quite la suspensión. Para obtener más información sobre una suspensión retrasada, vea la sección "Administración de buzones en espera de retraso" en [Cómo identificar el tipo de retención colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Si el valor de la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* está establecido en **True**, ejecute uno de los siguientes comandos para quitar la suspensión de retraso:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol Detención legal en Exchange Online para usar el parámetro *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied*.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Paso 5: Eliminar elementos en la carpeta Elementos recuperables

Ahora ya está listo para eliminar realmente los elementos de la carpeta Elementos recuperables mediante los cmdlets [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) y [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) en PowerShell de seguridad & cumplimiento.

Para buscar elementos que se encuentran en la carpeta Elementos recuperables, se recomienda realizar una *colección de destino*. Esto significa que limita el ámbito de la búsqueda solo a los elementos ubicados en la carpeta Elementos recuperables. Para ello, ejecute el script en el artículo [Usar búsqueda de contenido para colecciones de destino](use-content-search-for-targeted-collections.md) . Este script devuelve el valor de la propiedad id. de carpeta para todas las subcarpetas de la carpeta Elementos recuperables de destino. A continuación, use el identificador de carpeta en una consulta de búsqueda para devolver los elementos ubicados en esa carpeta.

Esta es una introducción al proceso para buscar y eliminar elementos en la carpeta Elementos recuperables de un usuario:

1. Ejecute el script de recopilación de destino que devuelve los identificadores de carpeta de todas las carpetas del buzón del usuario de destino. El script se conecta a Exchange Online PowerShell y PowerShell de cumplimiento de seguridad & en la misma sesión de PowerShell. Para obtener más información, vea [Ejecutar el script para obtener una lista de carpetas para un buzón](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).

2. Copie los identificadores de carpeta de todas las subcarpetas de la carpeta Elementos recuperables. Como alternativa, puede redirigir la salida del script a un archivo de texto.

   Esta es una lista y una descripción de las subcarpetas de la carpeta Elementos recuperables de las que puede buscar y eliminar elementos:

   - **Eliminaciones**: contiene elementos eliminados temporalmente cuyo período de retención de elementos eliminados no ha expirado. Los usuarios pueden recuperar elementos eliminados temporalmente de esta subcarpeta mediante la herramienta Recuperar elementos eliminados en Outlook.

   - **DiscoveryHolds**: contiene elementos eliminados de forma rígida que se han conservado mediante una suspensión de eDiscovery o una directiva de retención. Esta subcarpeta no es visible para los usuarios finales.

   - **SubstrateHolds**: contiene elementos eliminados de forma rígida de Teams y otras aplicaciones basadas en la nube que se han conservado mediante una directiva de retención u otro tipo de suspensión. Esta subcarpeta no es visible para los usuarios finales.

3. Use el cmdlet **New-ComplianceSearch** (en Security & Compliance PowerShell) o use la herramienta búsqueda de contenido en el centro de cumplimiento para crear una búsqueda de contenido que devuelva elementos de la carpeta Elementos recuperables del usuario de destino. Para ello, incluya FolderId en la consulta de búsqueda de todas las subcarpetas que desea buscar. Por ejemplo, la siguiente consulta devuelve todos los mensajes de las subcarpetas Eliminaciones y eDiscoveryHolds:

   ```text
   folderid:<folder ID of Deletions subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Para obtener más información y ejemplos sobre cómo ejecutar búsquedas de contenido que usan la propiedad id. de carpeta, consulte [Uso de un identificador de carpeta o para realizar una colección de destino](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).

   > [!NOTE]
   > Si usa el cmdlet **New-ComplianceSearch** para buscar en la carpeta Elementos recuperables, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda.

4. Después de crear una búsqueda de contenido y validar que devuelve los elementos que desea eliminar, use el `New-ComplianceSearchAction -Purge -PurgeType HardDelete` comando (en PowerShell de seguridad & cumplimiento) para eliminar permanentemente los elementos devueltos por la búsqueda de contenido que creó en el paso anterior. Por ejemplo, puede ejecutar un comando similar al siguiente:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Al ejecutar el comando anterior, se eliminan un máximo de 10 elementos por buzón. Esto significa que es posible que tenga que ejecutar el `New-ComplianceSearchAction -Purge` comando varias veces para eliminar todos los elementos que desea eliminar en la carpeta Elementos recuperables. Para eliminar elementos adicionales, primero debe quitar la acción de purga de búsqueda de cumplimiento anterior. Para ello, ejecute el `Remove-ComplianceSearchAction` cmdlet . Por ejemplo, para eliminar la acción de purga que se ejecutó en el paso anterior, ejecute el siguiente comando:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Después de hacerlo, puede crear una nueva acción de purga de búsqueda de cumplimiento para eliminar más elementos. Tendrá que eliminar cada acción de purga antes de crear una nueva.

   Para obtener una lista de las acciones de búsqueda de cumplimiento, puede ejecutar el `Get-ComplianceSearchAction` cmdlet . Las acciones de purga se identifican anexando `_Purge` al nombre de búsqueda.

### <a name="verify-that-items-were-deleted"></a>Comprobación de que se eliminaron elementos

Para comprobar que ha eliminado correctamente elementos de la carpeta Elementos recuperables de un buzón de correo, use el cmdlet **Get-MailboxFolderStatistics** en Exchange Online PowerShell para comprobar el tamaño y el número de elementos de la carpeta Elementos recuperables. Puede comparar estas estadísticas con las que recopiló en el paso 1.
  
Ejecute el siguiente comando en para obtener el tamaño actual y el número total de elementos en carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas de la carpeta Elementos recuperables del buzón de archivo del usuario.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Paso 6: Revertir el buzón a su estado anterior

El último paso es revertir el buzón a su configuración anterior. Esto significa restablecer las propiedades que cambió en el paso 2 y volver a aplicar las retenciones que quitó en el paso 3. Esto incluye lo siguiente:
  
- Volver a cambiar el período de retención de elementos eliminados a su valor anterior. Como alternativa, puede dejar este conjunto en 30 días, el valor máximo en Exchange Online.

- Volver a habilitar la recuperación de elementos únicos.

- Vuelva a habilitar los métodos de acceso de cliente para que el propietario pueda acceder a su buzón.

- Volver a aplicar las directivas de retención y retención que ha quitado.

- Vuelva a habilitar el Asistente para carpetas administradas para procesar el buzón.

> [!IMPORTANT]
> Se recomienda esperar 24 horas después de volver a aplicar una directiva de retención o suspensión (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpetas administradas para procesar el buzón.
  
Realice los pasos siguientes (en la secuencia especificada) en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para cambiar el período de retención de elementos eliminados a su valor original. Esto supone que la configuración anterior es inferior a 30 días; por ejemplo, 14 días.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Ejecute el siguiente comando para volver a habilitar la recuperación de un solo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente en el buzón.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Vuelva a aplicar las retenciones que quitó en el paso 3. En función del tipo de suspensión, use uno de los procedimientos siguientes.

    **Suspensión por juicio**

    Ejecute el siguiente comando para volver a habilitar una suspensión por juicio para el buzón.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    Use el EAC (o Exchange Online PowerShell) para volver a agregar el buzón al In-Place Suspensión.

    **Directivas de retención aplicadas a buzones específicos**

    Use el portal de cumplimiento para volver a agregar el buzón a la directiva de retención. Vaya a la página **Data lifecycle management** >  Microsoft 365 Retention (Administración del ciclo de vida de datos de **Microsoft 365** > **Retención**) en el centro de cumplimiento, edite la directiva de retención y vuelva a agregar el buzón a la lista de destinatarios a los que se aplica la directiva de retención.

    **Directivas de retención para toda la organización**

    Si quitó una directiva de retención de toda la organización o de Exchange al excluirla de la directiva, use el portal de cumplimiento para quitar el buzón de la lista de usuarios excluidos. Vaya a la página **Data lifecycle management** >  Microsoft 365 Retention (Administración del ciclo de vida de datos **de Microsoft 365** > **Retención**) en el centro de cumplimiento, edite la directiva de retención de toda la organización y quite el buzón de la lista de destinatarios excluidos. Al hacerlo, se volverá a aplicar la directiva de retención al buzón del usuario.

    **EDiscovery case holds**

    Use el portal de cumplimiento para agregar el buzón de vuelta a la suspensión asociada a un caso de exhibición de documentos electrónicos. Vaya a la página **eDiscovery** > **Core** , abra el caso y vuelva a agregar el buzón a la suspensión. 

5. Ejecute el siguiente comando para permitir que el Asistente para carpetas administradas vuelva a procesar el buzón. Como se indicó anteriormente, se recomienda esperar 24 horas después de volver a aplicar una directiva de retención o suspensión (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpetas administradas.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Para comprobar que el buzón se ha revertido a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, comparar la configuración con las que recopiló en el paso 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Más información

Esta es una tabla que describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad  *InPlaceHolds*  al ejecutar los cmdlets **Get-Mailbox** o **Get-OrganizationConfig** . Para obtener información más detallada, vea [Cómo identificar el tipo de retención colocado en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Como se explicó anteriormente, debe quitar todas las directivas de retención y retención de un buzón para poder eliminar correctamente los elementos de la carpeta Elementos recuperables.
  
| Tipo de suspensión | Valor de ejemplo | Identificación de la suspensión |
|:-----|:-----|:-----|
|Retención por litigio  <br/> | `True` <br/> |La propiedad  *LitigationHoldEnabled*  está establecida en  `True`.  <br/> |
|Retención en contexto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La propiedad  *InPlaceHolds*  contiene el GUID de la In-Place Hold que se coloca en el buzón. Puede indicar que se trata de una suspensión de In-Place porque el GUID no comienza con un prefijo.  <br/> Puede usar el `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando en Exchange Online PowerShell para obtener información sobre el In-Place Mantener en el buzón.  <br/> |
| Directivas de retención en el portal de cumplimiento aplicado a buzones específicos  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> o  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Al ejecutar el cmdlet **Get-Mailbox** , la propiedad  *InPlaceHolds*  también contiene GUID de directivas de retención aplicadas al buzón. Puede identificar las directivas de retención porque el GUID comienza con el  `mbx` prefijo . Si el GUID de la directiva de retención comienza con el `skp` prefijo , esto indica que la directiva de retención se aplica a Skype Empresarial conversaciones.  <br/> Para identificar la directiva de retención que se aplica al buzón de correo, ejecute el siguiente comando en PowerShell de cumplimiento de seguridad &: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Asegúrese de quitar el  `mbx` prefijo o  `skp` al ejecutar este comando.  <br/> |
|Directivas de retención para toda la organización en el portal de cumplimiento  <br/> |Sin valor  <br/> o  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indica que el buzón de correo está excluido de una directiva de toda la organización)  <br/> |Incluso si la propiedad  *InPlaceHolds*  está vacía al ejecutar el cmdlet **Get-Mailbox** , puede haber una o varias directivas de retención de toda la organización aplicadas al buzón.  <br/> Para comprobarlo, puede ejecutar el `Get-OrganizationConfig | FL InPlaceHolds` comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de toda la organización. El GUID de las directivas de retención de toda la organización aplicadas a los buzones de Exchange comienza con el  `mbx` prefijo ; por ejemplo,  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> Para identificar la directiva de retención de toda la organización que se aplica al buzón de correo, ejecute el siguiente comando en PowerShell de seguridad & cumplimiento: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Si se excluye un buzón de correo de una directiva de retención de toda la organización, el GUID de la directiva de retención se muestra en la propiedad  *InPlaceHolds*  del buzón del usuario al ejecutar el cmdlet **Get-Mailbox** ; se identifica mediante el prefijo  `-mbx`; por ejemplo,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|Suspensión de casos de eDiscovery en el portal de cumplimiento  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La propiedad  *InPlaceHolds*  también contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el portal de cumplimiento que se pueda colocar en el buzón. Puede indicar que se trata de una suspensión de mayúsculas y minúsculas de eDiscovery porque el GUID comienza con el  `UniH` prefijo .  <br/> Puede usar el  `Get-CaseHoldPolicy` cmdlet en PowerShell de cumplimiento de seguridad & para obtener información sobre el caso de exhibición de documentos electrónicos al que está asociada la suspensión en el buzón. Por ejemplo, puede ejecutar el comando  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para mostrar el nombre de la suspensión de mayúsculas y minúsculas que se encuentra en el buzón. Asegúrese de quitar el  `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de eDiscovery al que está asociada la suspensión en el buzón, ejecute los siguientes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
