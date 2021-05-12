---
title: Eliminar elementos de la carpeta Elementos recuperables de los buzones de correo en la nube en espera
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: Obtenga información sobre cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón Exchange Online, incluso si ese buzón está en retención legal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326647"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube

La carpeta Elementos recuperables de un buzón Exchange Online existe para protegerse de eliminaciones accidentales o malintencionadas. También se usa para almacenar elementos a los que las características de cumplimiento retienen y acceden a ellos, como las retenciones y las búsquedas de exhibición de documentos electrónicos. Sin embargo, en algunas situaciones, las organizaciones pueden tener datos que se han retenido involuntarlamente en la carpeta Elementos recuperables que deben eliminar. Por ejemplo, un usuario puede enviar o reenviar un mensaje de correo electrónico que contenga información confidencial o información que pueda tener graves consecuencias empresariales. Incluso si el mensaje se elimina permanentemente, podría conservarse indefinidamente porque se ha colocado una retención legal en el buzón. Este escenario se conoce como *derrame de* datos porque los datos se han derramado involuntarlamente *en* Office 365. En estas situaciones, puede eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón está en espera con una de las diferentes características de retención de Office 365. Estos tipos de retenciones incluyen retenciones por juicio, retenciones de In-Place, retenciones de exhibición de documentos electrónicos y directivas de retención creadas en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365.

En este artículo se explica cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables para los buzones basados en la nube que están en espera. Este procedimiento implica deshabilitar el acceso al buzón de correo y deshabilitar la recuperación de elementos individuales, deshabilitar el Asistente para carpetas administradas para que no procese el buzón, quitar temporalmente la retención, eliminar elementos de la carpeta Elementos recuperables y, a continuación, revertir el buzón a su configuración anterior. Este es el proceso:
  
[Paso 1: Recopilar información sobre el buzón](#step-1-collect-information-about-the-mailbox)

[Paso 2: Preparar el buzón](#step-2-prepare-the-mailbox)

[Paso 3: Quitar todas las retenciones del buzón](#step-3-remove-all-holds-from-the-mailbox)

[Paso 4: Quitar la retención de retraso del buzón](#step-4-remove-the-delay-hold-from-the-mailbox)

[Paso 5: Eliminar elementos de la carpeta Elementos recuperables](#step-5-delete-items-in-the-recoverable-items-folder)

[Paso 6: Revertir el buzón a su estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Los procedimientos descritos en este artículo darán como resultado la eliminación permanente (purgación) de datos de un buzón Exchange Online correo. Esto significa que los mensajes que elimina de la carpeta Elementos recuperables no se pueden recuperar y no estarán disponibles para la detección legal u otros fines de cumplimiento. Si desea eliminar mensajes de un buzón de correo que está en espera como parte de una retención por juicio, una retención In-Place, una retención de exhibición de documentos electrónicos o una directiva de retención creada en el centro de seguridad y cumplimiento, consulte con los departamentos legales o de administración de registros antes de quitar la retención. Es posible que la organización tenga una directiva que defina si un buzón de correo en espera o un incidente de derrame de datos tiene prioridad.
  
## <a name="before-you-delete-items"></a>Antes de eliminar elementos

- Para crear y ejecutar una búsqueda de contenido, tiene que ser miembro del grupo de roles Administrador de eDiscovery o tener asignado el rol de administración Búsqueda de cumplimiento. Para eliminar mensajes, tiene que ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración Búsqueda y eliminación. Para más información sobre cómo agregar usuarios a un grupo de roles, consulte [ Asignar permisos de eDiscovery en el Centro de seguridad y cumplimiento](./assign-ediscovery-permissions.md).

- El procedimiento descrito en este artículo no es compatible con buzones inactivos. Esto se debe a que no puede volver a aplicar una retención (o directiva de retención) a un buzón inactivo después de quitarla. Al quitar una retención de un buzón inactivo, se cambia a un buzón de correo normal eliminado temporalmente y se eliminará permanentemente de la organización después de que el Asistente para carpetas administradas lo procese.

- No puede realizar este procedimiento para un buzón al que se haya asignado la configuración de retención con una directiva bloqueada mediante el bloqueo de conservación. Esto se debe a que este bloqueo le impide quitar o excluir el buzón de correo de la directiva y deshabilitar el Asistente para carpetas administradas en el buzón. Para obtener más información acerca del bloqueo de directivas de retención, vea [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

- Si un buzón no está en espera (o no tiene habilitada la recuperación de un solo elemento), puede eliminar los elementos de la carpeta Elementos recuperables. Para obtener más información acerca de cómo hacerlo, vea Buscar y eliminar mensajes de correo electrónico [en la organización.](./search-for-and-delete-messages-in-your-organization.md)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Paso 1: Recopilar información sobre el buzón

Este primer paso consiste en recopilar las propiedades seleccionadas del buzón de destino que afectarán a este procedimiento. Asegúrese de escribir esta configuración o guardarla en un archivo de texto porque cambiará algunas de estas propiedades y, a continuación, volverá a los valores originales del paso 6, después de eliminar elementos de la carpeta Elementos recuperables. Esta es una lista de las propiedades de buzón que necesita recopilar.
  
- *SingleItemRecoveryEnabled*  y  *RetainDeletedItemsFor*. Si es necesario, deshabilitará la recuperación única y aumentará el período de retención de elementos eliminados en el paso 3.

- *LitigationHoldEnabled*  e  *InPlaceHolds*. Debe identificar todas las retenciones colocadas en el buzón para poder quitarlas temporalmente en el paso 3. Vea la [sección Más información](#more-information) para obtener sugerencias sobre cómo identificar la retención de tipos que se puede colocar en un buzón.

Además, debe obtener la configuración de acceso de cliente de buzón para poder deshabilitarlas temporalmente para que el propietario (u otros usuarios) no pueda acceder al buzón durante este procedimiento. Por último, puede obtener el tamaño actual y el número de elementos en la carpeta Elementos recuperables. Después de eliminar elementos de la carpeta Elementos recuperables del paso 5, usará esta información para comprobar que se quitaron los elementos.
  
1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador a la que se han asignado los roles de administración adecuados en Exchange Online.

2. Ejecute el siguiente comando para obtener información sobre la recuperación de un solo elemento y el período de retención de elementos eliminados.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Si la recuperación de un solo elemento está habilitada, tendrá que deshabilitarla en el paso 2. Si el período de retención de elementos eliminados no se establece durante 30 días (el valor máximo de Exchange Online), puede aumentarlo en el paso 2.

3. Ejecute el siguiente comando para obtener la configuración de acceso al buzón para el buzón.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Deshabilitará todos estos métodos de acceso en el paso 2.

4. Ejecute el siguiente comando para obtener información sobre las directivas de retención y retención aplicadas al buzón.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos ellos, puede ejecutar el comando para mostrar cada valor en  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.
  
5. Ejecute el siguiente comando para obtener información sobre las directivas de retención de toda la organización. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Si su organización tiene directivas de retención para toda la organización, tendrá que excluir el buzón de estas directivas en el paso 3. El cambio puede tardar hasta 24 horas.

    > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos ellos, puede ejecutar el comando para mostrar cada valor en  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una línea independiente. 
  
6. Ejecute el siguiente comando para determinar si se aplica una retención de retraso al buzón.

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   Si el valor de la *propiedad DelayHoldApplied* o *DelayReleaseHoldApplied* se establece en **True**, se aplica una retención de retraso al buzón y se debe quitar. Para obtener más información acerca de las retenciones de retraso, vea [Step 4: Remove the delay hold from the mailbox](#step-4-remove-the-delay-hold-from-the-mailbox).

   Si el valor de cualquiera de las propiedades se establece en **False**, no se aplica una retención de retraso al buzón y puede omitir el paso 4.

7. Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Si el buzón de archivo del usuario está habilitado, ejecute el siguiente comando para obtener el tamaño y el número total de elementos en carpetas y subcarpetas de la carpeta Elementos recuperables en su buzón de archivo. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Al eliminar elementos del paso 5, puede eliminar o no eliminar elementos de la carpeta Elementos recuperables del buzón de archivo principal del usuario. Si el archivado de expansión automática está habilitado para el buzón, los elementos de un buzón de archivo auxiliar no se eliminarán.
  
## <a name="step-2-prepare-the-mailbox"></a>Paso 2: Preparar el buzón

Después de recopilar y guardar información sobre el buzón, el siguiente paso es preparar el buzón realizando las siguientes tareas:
  
- **Deshabilite el acceso** de cliente al buzón para que el propietario del buzón no pueda tener acceso a su buzón y realice cambios en los datos del buzón durante este procedimiento.

- **Aumente** el período de retención de elementos eliminados a 30 días (el valor máximo en Exchange Online) para que los elementos no se purguen de la carpeta Elementos recuperables antes de poder eliminarlos en el paso 5.

- **Deshabilite** la recuperación de elementos individuales para que los elementos no se conserven (durante el período de retención de elementos eliminados) después de eliminarlos de la carpeta Elementos recuperables del paso 5.

- **Deshabilite el Asistente para** carpetas administradas para que no procese el buzón y conserve los elementos que elimine en el paso 5.

Realice los pasos siguientes en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para deshabilitar todo el acceso de cliente al buzón. La sintaxis del comando supone que todos los métodos de acceso de cliente estaban habilitados en el buzón.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > Puede tardar hasta 60 minutos en deshabilitar todos los métodos de acceso de cliente al buzón. Tenga en cuenta que deshabilitar estos métodos de acceso no desconectará al propietario del buzón si ha iniciado sesión actualmente. Si el propietario no ha iniciado sesión, no podrá tener acceso a su buzón después de deshabilitar estos métodos de acceso.
  
2. Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados el máximo de 30 días. Esto supone que la configuración actual es inferior a 30 días.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Ejecute el siguiente comando para deshabilitar la recuperación de un solo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > Puede tardar hasta 60 minutos en deshabilitar la recuperación de un solo elemento. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período. 
  
4. Ejecute el siguiente comando para evitar que el Asistente para carpetas administradas procese el buzón. Como se explicó anteriormente, solo puede deshabilitar el Asistente para carpetas administradas si no se aplica una directiva de retención con un bloqueo de conservación al buzón. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Paso 3: Quitar todas las retenciones del buzón

El último paso antes de poder eliminar elementos de la carpeta Elementos recuperables es quitar todas las retenciones (que identificó en el paso 1) colocadas en el buzón. Todas las retenciones deben quitarse para que los elementos no se conserven después de eliminarlos de la carpeta Elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar diferentes tipos de retenciones en un buzón. Vea la [sección Más información](#more-information) para obtener sugerencias sobre cómo identificar la retención de tipos que se puede colocar en un buzón. Para obtener más información, [vea How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Como se ha indicado anteriormente, consulte con los departamentos legales o de administración de registros antes de quitar una retención de un buzón. 
  
### <a name="litigation-hold"></a>Retención por juicio
  
Ejecute el siguiente comando en Exchange Online PowerShell para quitar una retención por juicio del buzón.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> De forma similar a deshabilitar los métodos de acceso de cliente y la recuperación de un solo elemento, puede tardar hasta 60 minutos en quitar la retención por juicio. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período. 
  
### <a name="in-place-hold"></a>Retención en contexto
  
Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención In-Place que se coloca en el buzón. Use el GUID para la retención In-Place que identificó en el paso 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Después de identificar la retención In-Place, puede usar el Centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de la retención. Para obtener más información, [vea Create or remove an In-Place Hold](/exchange/security-and-compliance/create-or-remove-in-place-holds).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Directivas de retención aplicadas a buzones específicos
  
Ejecute el siguiente comando en [PowerShell del Centro de & seguridad](/powershell/exchange/exchange-online-powershell) para identificar la directiva de retención que se aplica al buzón. Este comando también devolverá las directivas de retención Teams de conversación aplicadas a un buzón. Use el GUID (sin incluir el prefijo o) para la directiva `mbx` de retención que `skp` identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar la directiva de retención, vaya a la página Retención de gobierno de información en el Centro de seguridad & Cumplimiento, edite la directiva de retención que identificó en el paso anterior y quite el buzón de la lista de destinatarios que se incluyen en la directiva de  >   retención.
  
### <a name="organization-wide-retention-policies"></a>Directivas de retención en toda la organización
  
Las directivas de retención Exchange toda la organización, Teams de toda la organización se aplican a todos los buzones de la organización. Se aplican en el nivel de organización (no en el nivel de buzón) y se devuelven cuando se ejecuta el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando en [PowerShell del Centro de & seguridad](/powershell/exchange/exchange-online-powershell) para identificar las directivas de retención de toda la organización. Use el GUID (sin incluir el prefijo) para las directivas de retención de toda la organización que  `mbx` identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar las directivas de retención de toda la organización, vaya a la página Retención de gobierno de información del Centro de cumplimiento de seguridad &, edite cada directiva de retención de toda la organización que identificó en el paso anterior y agregue el buzón a la lista de destinatarios  >   excluidos. Al hacerlo, se quitará el buzón del usuario de la directiva de retención. El cambio puede tardar hasta 24 horas.

### <a name="retention-labels"></a>Etiquetas de retención

Cada vez que un usuario aplica una etiqueta configurada para retener contenido o conservar y, a continuación, eliminar contenido en cualquier carpeta o elemento de su buzón, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **True**. Cuando esto sucede, se considera que el buzón está en espera, como si se hubiera colocado en retención por juicio o se asignara a una directiva de retención.

Para ver el valor de la *propiedad ComplianceTagHoldApplied,* ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Después de identificar que un buzón está en espera porque se aplica una etiqueta de retención a una carpeta o elemento, puede usar la herramienta búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar elementos etiquetados mediante la condición de búsqueda ComplianceTag. Para obtener más información, vea la sección "Condiciones de búsqueda" en Consultas de palabras clave y [condiciones de búsqueda para búsqueda de contenido.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

Para obtener más información acerca de las etiquetas, vea [Learn about retention policies and retention labels](retention.md).

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery
  
Ejecute los siguientes comandos en [PowerShell](/powershell/exchange/connect-to-scc-powershell) del Centro de seguridad & cumplimiento para identificar la retención asociada a un caso de exhibición de documentos electrónicos (denominado retención de exhibición de documentos *electrónicos)* que se aplica al buzón. Use el GUID (sin incluir el prefijo) para la retención de exhibición de documentos electrónicos  `UniH` que identificó en el paso 1. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos al que está asociada la retención; el tercer comando muestra el nombre de la retención.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Después de identificar el nombre del caso de exhibición de  documentos electrónicos y la retención, vaya a la página \> **eDiscovery de** exhibición de documentos electrónicos en el centro de cumplimiento, abra el caso y quite el buzón de correo de la retención. Para obtener más información acerca de cómo identificar las retenciones de exhibición de documentos electrónicos, vea la sección "retenciones de exhibición de documentos electrónicos" en How [to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Paso 4: Quitar la retención de retraso del buzón

Después de quitar cualquier tipo de retención de un buzón, el valor de la propiedad de buzón *DelayHoldApplied* o *DelayReleaseHoldApplied* se establece en **True**. Esto ocurre la próxima vez que el Asistente para carpetas administradas procesa el buzón y detecta que se ha quitado una retención. Esto se denomina *retención* retrasada y significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente del buzón. (El propósito de una retención retrasada es dar a los administradores la oportunidad de buscar o recuperar elementos de buzón que se purgarán después de quitar una retención).  Cuando se coloca una retención de retraso en el buzón, se considera que el buzón está en espera durante una duración ilimitada, como si el buzón se encontrara en retención por juicio. Después de 30 días, la retención de retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* en **False)** para que se quite la retención. Para obtener más información acerca de una retención de retraso, vea la sección "Administración de buzones en retención retrasada" en How [to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Si el valor de *la propiedad DelayHoldApplied* o *DelayReleaseHoldApplied* está establecido en **True**, ejecute uno de los siguientes comandos para quitar la retención de retraso:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol Retención legal en Exchange Online usar el parámetro *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied.*

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Paso 5: Eliminar elementos de la carpeta Elementos recuperables

Ahora ya está listo para eliminar los elementos de la carpeta Elementos recuperables mediante los cmdlets [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) y [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) en PowerShell del Centro de seguridad & cumplimiento.

Para buscar elementos que se encuentran en la carpeta Elementos recuperables, se recomienda realizar una *colección de destino.* Esto significa que limita el ámbito de la búsqueda solo a los elementos ubicados en la carpeta Elementos recuperables. Para ello, ejecute el script en el artículo Usar búsqueda de contenido [para colecciones de](use-content-search-for-targeted-collections.md) destino. Este script devuelve el valor de la propiedad id. de carpeta para todas las subcarpetas de la carpeta elementos recuperables de destino. A continuación, use el identificador de carpeta en una consulta de búsqueda para devolver los elementos ubicados en esa carpeta.

Este es un resumen del proceso para buscar y eliminar elementos en la carpeta Elementos recuperables de un usuario:

1. Ejecute el script de colección de destino que devuelve los id. de carpeta para todas las carpetas del buzón del usuario de destino. El script se conecta Exchange Online PowerShell y Security & Compliance PowerShell en la misma sesión de PowerShell. Para obtener más información, [vea Ejecutar el script para obtener una lista de carpetas para un buzón](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).

2. Copie los IDs de carpeta para todas las subcarpetas de la carpeta Elementos recuperables. Como alternativa, puede redirigir el resultado del script a un archivo de texto.

   Esta es una lista y una descripción de las subcarpetas de la carpeta Elementos recuperables de las que puede buscar y eliminar elementos:

   - **Eliminaciones:** contiene elementos eliminados temporalmente cuyo período de retención de elementos eliminados no ha expirado. Los usuarios pueden recuperar elementos eliminados temporalmente de esta subcarpeta mediante la herramienta Recuperar elementos eliminados en Outlook.

   - **Purgas:** contiene elementos eliminados de forma permanente cuyo período de retención de elementos eliminados ha expirado. Los usuarios también pueden eliminar de forma permanente los elementos de su carpeta Elementos recuperables. Si el buzón está en espera, se conservan los elementos eliminados de forma permanente. Esta subcarpeta no es visible para los usuarios finales.

   - **DiscoveryHolds:** contiene elementos eliminados de forma permanente que se han conservado mediante una retención de exhibición de documentos electrónicos o una directiva de retención. Esta subcarpeta no es visible para los usuarios finales.

   - **SubstrateHolds:** contiene elementos eliminados de forma permanente de Teams y otras aplicaciones basadas en la nube que se han conservado mediante una directiva de retención u otro tipo de retención. Esta subcarpeta no es visible para los usuarios finales.

3. Use el cmdlet **New-ComplianceSearch** (en PowerShell del Centro de seguridad & cumplimiento) o use la herramienta de búsqueda de contenido en el centro de cumplimiento para crear una búsqueda de contenido que devuelva elementos de la carpeta Elementos recuperables del usuario de destino. Para ello, incluya FolderId en la consulta de búsqueda de todas las subcarpetas que desee buscar. Por ejemplo, la siguiente consulta devuelve todos los mensajes de las subcarpetas Purgas y eDiscoveryHolds:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Para obtener más información y ejemplos sobre cómo ejecutar búsquedas de contenido que usan la propiedad id. de carpeta, vea [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).

   > [!NOTE]
   > Si usa el cmdlet **New-ComplianceSearch** para buscar en la carpeta Elementos recuperables, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda.

4. Después de crear una búsqueda de contenido y validar que devuelve los elementos que desea eliminar, use el comando (en PowerShell del Centro de seguridad & cumplimiento) para eliminar permanentemente los elementos devueltos por la búsqueda de contenido que creó en el paso `New-ComplianceSearchAction -Purge -PurgeType HardDelete` anterior. Por ejemplo, puede ejecutar un comando similar al siguiente:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Al ejecutar el comando anterior, se elimina un máximo de 10 elementos por buzón. Esto significa que es posible que tenga que ejecutar el comando varias veces para eliminar todos los elementos que desea eliminar en la carpeta `New-ComplianceSearchAction -Purge` Elementos recuperables. Para eliminar elementos adicionales, primero debe quitar la acción de purga de búsqueda de cumplimiento anterior. Para ello, ejecute el `Remove-ComplianceSearchAction` cmdlet. Por ejemplo, para eliminar la acción de purga que se ha ejecutado en el paso anterior, ejecute el siguiente comando:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Después de hacerlo, puede crear una nueva acción de purga de búsqueda de cumplimiento para eliminar más elementos. Tendrás que eliminar cada acción de purga antes de crear una nueva.

   Para obtener una lista de las acciones de búsqueda de cumplimiento, puede ejecutar el `Get-ComplianceSearchAction` cmdlet. Las acciones de purga se identifican `_Purge` anexando al nombre de búsqueda.

### <a name="verify-that-items-were-deleted"></a>Comprobar que los elementos se eliminaron

Para comprobar que ha eliminado correctamente elementos de la carpeta Elementos recuperables de un buzón, use el cmdlet **Get-MailboxFolderStatistics** en Exchange Online PowerShell para comprobar el tamaño y el número de elementos de la carpeta Elementos recuperables. Puede comparar estas estadísticas con las que recopiló en el paso 1.
  
Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Ejecute el siguiente comando para obtener el tamaño y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables en el buzón de archivo del usuario.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Paso 6: Revertir el buzón a su estado anterior

El último paso es revertir el buzón a su configuración anterior. Esto significa restablecer las propiedades que cambió en el paso 2 y volver a aplicar las retenciones que quitó en el paso 3. Esto incluye:
  
- Cambiar el período de retención de elementos eliminados a su valor anterior. Como alternativa, puede dejar este conjunto en 30 días, el valor máximo en Exchange Online.

- Volver a habilitar la recuperación de elementos únicos.

- Volver a habilitar los métodos de acceso de cliente para que el propietario pueda tener acceso a su buzón.

- Volver a aplicar las directivas de retención y retención que quitó.

- Volver a habilitar el Asistente para carpeta administrada para procesar el buzón.

> [!IMPORTANT]
> Se recomienda esperar 24 horas después de volver a aplicar una directiva de retención o retención (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpeta administrada para procesar el buzón.
  
Realice los siguientes pasos (en la secuencia especificada) en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para volver a cambiar el período de retención de elementos eliminados a su valor original. Esto supone que la configuración anterior es inferior a 30 días; por ejemplo, 14 días.

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

4. Vuelva a aplicar las retenciones que eliminó en el paso 3. Según el tipo de retención, use uno de los siguientes procedimientos.

    **Retención por juicio**

    Ejecute el siguiente comando para volver a habilitar una retención por juicio para el buzón.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    Use el EAC (o Exchange Online PowerShell) para volver a agregar el buzón a la In-Place espera.

    **Directivas de retención aplicadas a buzones específicos**

    Use el Centro de seguridad & cumplimiento para volver a agregar el buzón a la directiva de retención. Vaya a la página Retención de gobierno de información en el Centro de seguridad y cumplimiento de &, edite la directiva de retención y vuelva a agregar el buzón a la lista de destinatarios a los que se aplica la directiva de  >   retención.

    **Directivas de retención en toda la organización**

    Si quitó una directiva de retención de toda la organización o de Exchange al excluirla de la directiva, use el Centro de seguridad & cumplimiento para quitar el buzón de la lista de usuarios excluidos. Vaya a la página **Retención** de gobierno de información en el Centro de seguridad & cumplimiento, edite la directiva de retención de toda la organización y quite el buzón de la lista de  >   destinatarios excluidos. Al hacerlo, se volverá a aplicar la directiva de retención al buzón del usuario.

    **Retenciones de casos de exhibición de documentos electrónicos**

    Use el Centro de seguridad & cumplimiento para agregar el buzón de correo de nuevo la retención asociada a un caso de exhibición de documentos electrónicos. Vaya a la **página eDiscovery**  >  **eDiscovery,** abra el caso y vuelva a agregar el buzón a la retención. 

5. Ejecute el siguiente comando para permitir que el Asistente para carpetas administradas vuelva a procesar el buzón. Como se ha indicado anteriormente, se recomienda esperar 24 horas después de volver a aplicar una directiva de retención o retención (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpetas administradas.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Para comprobar que el buzón ha vuelto a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, comparar la configuración con las que recopiló en el paso 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Más información

Esta es una tabla que describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* al ejecutar los cmdlets **Get-Mailbox** o **Get-OrganizationConfig.** Para obtener información más detallada, vea [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).

Como se explicó anteriormente, debe quitar todas las retenciones y directivas de retención de un buzón para poder eliminar correctamente los elementos de la carpeta Elementos recuperables.
  
| Tipo de retención | Valor de ejemplo | Cómo identificar la retención |
|:-----|:-----|:-----|
|Retención por juicio  <br/> | `True` <br/> |La  *propiedad LitigationHoldEnabled*  se establece en  `True` .  <br/> |
|Retención en contexto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la In-Place que se coloca en el buzón. Puede saber que se trata de una retención In-Place porque el GUID no comienza con un prefijo.  <br/> Puede usar el comando de Exchange Online PowerShell para obtener información sobre la retención In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` en el buzón.  <br/> |
| Directivas de retención en el Centro de seguridad & cumplimiento aplicado a buzones específicos  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> o  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Al ejecutar el cmdlet **Get-Mailbox,** la propiedad  *InPlaceHolds*  también contiene GUID de directivas de retención aplicadas al buzón. Puede identificar directivas de retención porque el GUID comienza por el  `mbx` prefijo. Si el GUID de la directiva de retención comienza por el prefijo, eso indica que la directiva de retención se aplica a las conversaciones de  `skp` Skype Empresarial.  <br/> Para identificar la directiva de retención que se aplica al buzón de correo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Asegúrese de quitar el  `mbx` prefijo o al ejecutar este  `skp` comando.  <br/> |
|Directivas de retención de toda la organización en el Centro de & seguridad  <br/> |Sin valor  <br/> o  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indica que el buzón está excluido de una directiva de toda la organización)  <br/> |Incluso si la  *propiedad InPlaceHolds*  está vacía al ejecutar el cmdlet **Get-Mailbox,** es posible que aún haya una o más directivas de retención en toda la organización aplicadas al buzón.  <br/> Para comprobar esto, puede ejecutar el comando en PowerShell de Exchange Online para obtener una lista de los GUID para directivas de retención de  `Get-OrganizationConfig | FL InPlaceHolds` toda la organización. El GUID de las directivas de retención de toda la organización aplicadas a buzones de Exchange comienza con el  `mbx` prefijo; por ejemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Para identificar la directiva de retención de toda la organización que se aplica al buzón de correo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Si se excluye un buzón de correo de una directiva de retención de toda la organización, el GUID de la directiva de retención se muestra en la propiedad  *InPlaceHolds*  del buzón del usuario al ejecutar el cmdlet **Get-Mailbox;** se identifica por el  `-mbx` prefijo; por ejemplo,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|Retención de casos de exhibición de documentos electrónicos en el Centro de & seguridad  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La  *propiedad InPlaceHolds*  también contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento que se puede colocar en el buzón. Puede saber que se trata de una retención de casos de exhibición de documentos electrónicos porque el GUID comienza por el  `UniH` prefijo.  <br/> Puede usar el cmdlet de PowerShell del Centro de seguridad & cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos al que está asociada la  `Get-CaseHoldPolicy` retención en el buzón. Por ejemplo, puede ejecutar el comando para mostrar el nombre de la retención  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` de casos que está en el buzón. Asegúrese de quitar el  `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de exhibición de documentos electrónicos al que está asociada la retención en el buzón de correo, ejecute los siguientes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
