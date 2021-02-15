---
title: Eliminar elementos de la carpeta Elementos recuperables del buzón de correo en la nube en espera
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
description: Obtenga información sobre cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón está en retención legal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919960"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube

La carpeta Elementos recuperables de un buzón de Exchange Online existe para protegerse de eliminaciones accidentales o malintencionadas. También se usa para almacenar elementos que se conservan y a los que acceden las características de cumplimiento, como las retenciones y las búsquedas de exhibición de documentos electrónicos. Sin embargo, en algunas situaciones, es posible que las organizaciones tengan datos que se han conservado involuntarlamente en la carpeta Elementos recuperables que deben eliminar. Por ejemplo, es posible que un usuario envíe o reenvía sin darse cuenta un mensaje de correo electrónico que contenga información confidencial o información que pueda tener consecuencias empresariales graves. Incluso si el mensaje se elimina permanentemente, es posible que se conserve indefinidamente porque se ha colocado una retención legal en el buzón. Este escenario se conoce como *pérdida de* datos porque los datos se han desbordado *involuntarlamente* en Office 365. En estas situaciones, puede eliminar elementos de la carpeta Elementos recuperables de un usuario para un buzón de Exchange Online, incluso si ese buzón se coloca en espera con una de las distintas características de retención de Office 365. Estos tipos de retenciones incluyen retenciones por juicio, retenciones de In-Place, retenciones de exhibición de documentos electrónicos y directivas de retención creadas en el Centro de seguridad y cumplimiento de Office 365 o Microsoft 365.
  
 En este artículo se explica cómo los administradores pueden eliminar elementos de la carpeta Elementos recuperables para los buzones basados en la nube que están en retención. Este procedimiento implica deshabilitar el acceso al buzón y deshabilitar la recuperación de elementos individuales, deshabilitar el Asistente para carpeta administrada para que no procese el buzón, quitar temporalmente la suspensión, eliminar elementos de la carpeta Elementos recuperables y, a continuación, revertir el buzón a su configuración anterior. Este es el proceso:
  
[Paso 1: Recopilar información sobre el buzón](#step-1-collect-information-about-the-mailbox)

[Paso 2: Preparar el buzón](#step-2-prepare-the-mailbox)

[Paso 3: Quitar todas las retenciones del buzón](#step-3-remove-all-holds-from-the-mailbox)

[Paso 4: Quitar la retención con retraso del buzón](#step-4-remove-the-delay-hold-from-the-mailbox)

[Paso 5: Eliminar elementos de la carpeta Elementos recuperables](#step-5-delete-items-in-the-recoverable-items-folder)

[Paso 6: Revertir el buzón a su estado anterior](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> Los procedimientos descritos en este artículo darán como resultado que los datos se eliminen permanentemente (se purguen) de un buzón de Exchange Online. Esto significa que los mensajes que elimina de la carpeta Elementos recuperables no se pueden recuperar y no estarán disponibles para fines de detección legal u otros fines de cumplimiento. Si desea eliminar mensajes de un buzón que se coloca en suspensión como parte de una retención por juicio, una suspensión de In-Place, una suspensión de exhibición de documentos electrónicos o una directiva de retención creada en el centro de seguridad y cumplimiento, consulte con los departamentos legales o de administración de registros antes de quitar la suspensión. Es posible que su organización tenga una directiva que defina si un buzón de correo en espera o un incidente de pérdida de datos tiene prioridad.
  
## <a name="before-you-delete-items"></a>Antes de eliminar elementos

- Para crear y ejecutar una búsqueda de contenido, tiene que ser miembro del grupo de roles Administrador de eDiscovery o tener asignado el rol de administración Búsqueda de cumplimiento. Para eliminar mensajes, tiene que ser miembro del grupo de roles Administración de la organización o tener asignado el rol de administración Búsqueda y eliminación. Para más información sobre cómo agregar usuarios a un grupo de roles, consulte [ Asignar permisos de eDiscovery en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).

- El procedimiento descrito en este artículo no es compatible con los buzones inactivos. Esto se debe a que no puede volver a aplicar una retención (o directiva de retención) a un buzón inactivo después de quitarla. Cuando quita una retención de un buzón inactivo, se cambia a un buzón de correo normal eliminado temporalmente y se eliminará permanentemente de su organización después de que el Asistente para carpeta administrada lo procese.

- No puede realizar este procedimiento para un buzón al que se ha asignado una configuración de retención con una directiva bloqueada mediante el bloqueo de conservación. Esto se debe a que este bloqueo le impide quitar o excluir el buzón de la directiva y deshabilitar el Asistente para carpeta administrada en el buzón. Para obtener más información acerca de las directivas de bloqueo para la retención, vea Usar el bloqueo de conservación para restringir los cambios a las directivas de retención y las directivas de [etiquetas de retención.](retention-preservation-lock.md)

- Si un buzón no está en retención (o no tiene habilitada la recuperación de un solo elemento), puede eliminar los elementos de la carpeta Elementos recuperables. Para obtener más información acerca de cómo hacerlo, vea Buscar y eliminar mensajes de [correo electrónico en su organización.](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>Paso 1: Recopilar información sobre el buzón

Este primer paso es recopilar las propiedades seleccionadas del buzón de destino que afectarán a este procedimiento. Asegúrese de anotar estas opciones de configuración o guárdelas en un archivo de texto porque cambiará algunas de estas propiedades y, a continuación, volverá a los valores originales del paso 6, después de eliminar los elementos de la carpeta Elementos recuperables. Esta es una lista de las propiedades de buzón que necesita recopilar.
  
- *SingleItemRecoveryEnabled*  y  *RetainDeletedItemsFor*. Si es necesario, deshabilitará la recuperación única y aumentará el período de retención de elementos eliminados en el paso 3.

- *LitigationHoldEnabled*  e  *InPlaceHolds*. Debe identificar todas las retenciones colocadas en el buzón para poder quitarlas temporalmente en el paso 3. Consulte la [sección Más información](#more-information) para obtener sugerencias sobre cómo identificar el tipo de retención que se puede colocar en un buzón.

Además, debe obtener la configuración de acceso de cliente de buzón de correo para poder deshabilitarlas temporalmente para que el propietario (u otros usuarios) no pueda acceder al buzón durante este procedimiento. Por último, puede obtener el tamaño y el número actuales de elementos en la carpeta Elementos recuperables. Después de eliminar los elementos de la carpeta Elementos recuperables en el paso 5, usará esta información para comprobar que se quitaron los elementos.
  
1. [Conéctese al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=396554). Asegúrese de usar un nombre de usuario y una contraseña para una cuenta de administrador a la que se hayan asignado los roles de administración adecuados en Exchange Online.

2. Ejecute el siguiente comando para obtener información sobre la recuperación de elementos individuales y el período de retención de elementos eliminados.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   Si la recuperación de un solo elemento está habilitada, tendrá que deshabilitarla en el paso 2. Si el período de retención de elementos eliminados no se establece durante 30 días (el valor máximo en Exchange Online), puede aumentarlo en el paso 2.

3. Ejecute el siguiente comando para obtener la configuración de acceso al buzón para el buzón.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   Deshabilitará todos estos métodos de acceso en el paso 2.

4. Ejecute el siguiente comando para obtener información sobre las retenciones y directivas de retención aplicadas al buzón.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos, puede ejecutar el comando para mostrar cada valor en  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.
  
5. Ejecute el siguiente comando para obtener información sobre las directivas de retención de toda la organización. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   Si su organización tiene alguna directiva de retención en toda la organización, tendrá que excluir el buzón de estas directivas en el paso 3.

   > [!TIP]
    > Si hay demasiados valores en la propiedad  *InPlaceHolds*  y no se muestran todos, puede ejecutar el comando para mostrar cada valor en  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una línea independiente. 
  
6. Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Si el buzón de archivo del usuario está habilitado, ejecute el siguiente comando para obtener el tamaño y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables de su buzón de archivo. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   Al eliminar elementos en el paso 5, puede eliminar o no los elementos de la carpeta Elementos recuperables del buzón de archivo principal del usuario. Si el archivado de expansión automática está habilitado para el buzón, los elementos de un buzón de archivo auxiliar no se eliminarán.
  
## <a name="step-2-prepare-the-mailbox"></a>Paso 2: Preparar el buzón

Después de recopilar y guardar información sobre el buzón, el siguiente paso es preparar el buzón realizando las siguientes tareas:
  
- **Deshabilite el acceso** de cliente al buzón para que el propietario del buzón no pueda tener acceso a su buzón y realizar cambios en los datos del buzón durante este procedimiento.

- **Aumente** el período de retención de elementos eliminados a 30 días (el valor máximo en Exchange Online) para que los elementos no se purguen de la carpeta Elementos recuperables antes de poder eliminarlos en el paso 5.

- **Deshabilite** la recuperación de un solo elemento para que los elementos no se conserven (durante el período de retención de elementos eliminados) después de eliminarlos de la carpeta Elementos recuperables en el paso 5.

- **Deshabilite el Asistente** para carpeta administrada para que no procese el buzón y conserve los elementos que elimine en el paso 5.

Realice los pasos siguientes en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para deshabilitar todo el acceso de cliente al buzón. La sintaxis de comando supone que todos los métodos de acceso de cliente se habilitaron en el buzón.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > Puede tardar hasta 60 minutos en deshabilitar todos los métodos de acceso de cliente al buzón. Tenga en cuenta que deshabilitar estos métodos de acceso no desconectará al propietario del buzón en el que ha iniciado sesión actualmente. Si el propietario no ha iniciado sesión, no podrá acceder a su buzón después de deshabilitar estos métodos de acceso.
  
2. Ejecute el siguiente comando para aumentar el período de retención de elementos eliminados el máximo de 30 días. Esto supone que la configuración actual es inferior a 30 días.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. Ejecute el siguiente comando para deshabilitar la recuperación de un solo elemento.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > La recuperación de un único elemento puede tardar hasta 60 minutos. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período. 
  
4. Ejecute el siguiente comando para evitar que el Asistente para carpeta administrada procese el buzón. Como se ha explicado anteriormente, puede deshabilitar el Asistente para carpeta administrada solo si no se aplica al buzón una directiva de retención con un bloqueo de conservación. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>Paso 3: Quitar todas las retenciones del buzón

El último paso antes de poder eliminar elementos de la carpeta Elementos recuperables es quitar todas las retenciones (identificadas en el paso 1) colocadas en el buzón. Todas las retenciones deben quitarse para que los elementos no se conserven después de eliminarlos de la carpeta Elementos recuperables. Las secciones siguientes contienen información sobre cómo quitar diferentes tipos de retenciones en un buzón. Consulte la [sección Más información](#more-information) para obtener sugerencias sobre cómo identificar el tipo de retención que se puede colocar en un buzón. Para obtener más información, [consulte Cómo identificar el tipo de retención colocada en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).
  
> [!CAUTION]
> Como se indicó anteriormente, consulte con los departamentos legales o de administración de registros antes de quitar una retención de un buzón. 
  
### <a name="litigation-hold"></a>Retención por juicio
  
Ejecute el siguiente comando en Exchange Online PowerShell para quitar una retención por juicio del buzón.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> De forma similar a deshabilitar los métodos de acceso de cliente y la recuperación de elementos individuales, la retención por juicio puede tardar hasta 60 minutos. No elimine elementos de la carpeta Elementos recuperables hasta que haya transcurrido este período. 
  
### <a name="in-place-hold"></a>Retención en contexto
  
Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención In-Place que se coloca en el buzón. Use el GUID para la retención In-Place que identificó en el paso 1.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

Después de identificar la retención In-Place, puede usar el Centro de administración de Exchange (EAC) o Exchange Online PowerShell para quitar el buzón de la retención. Para obtener más información, [vea Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>Directivas de retención aplicadas a buzones específicos
  
Ejecute el siguiente comando en [PowerShell del Centro de & seguridad para](https://go.microsoft.com/fwlink/?linkid=627084) identificar la directiva de retención que se aplica al buzón. Este comando también devolverá las directivas de retención de conversaciones de Teams aplicadas a un buzón. Use el GUID (sin incluir el prefijo o) para la directiva `mbx` de retención que `skp` identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar la directiva de retención, vaya a la página Retención de gobierno de la información en el Centro de seguridad y cumplimiento de &, edite la directiva de retención que identificó en el paso anterior y quite el buzón de la lista de destinatarios que se incluyen en la directiva de  >   retención.
  
### <a name="organization-wide-retention-policies"></a>Directivas de retención en toda la organización
  
Las directivas de retención de toda la organización, de Exchange y de Teams se aplican a todos los buzones de la organización. Se aplican en el nivel de organización (no en el nivel de buzón) y se devuelven cuando se ejecuta el cmdlet **Get-OrganizationConfig** en el paso 1. Ejecute el siguiente comando en [PowerShell del Centro de & seguridad para](https://go.microsoft.com/fwlink/?linkid=627084) identificar las directivas de retención en toda la organización. Use el GUID (sin incluir el prefijo) para las directivas de retención de toda la organización  `mbx` que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

Después de identificar las directivas de retención en toda la organización, vaya a la página Retención de gobierno de información en el Centro de seguridad & y cumplimiento, edite cada directiva de retención de toda la organización que identificó en el paso anterior y agregue el buzón a la lista de destinatarios  >   excluidos. Al hacerlo, se quitará el buzón del usuario de la directiva de retención.

### <a name="retention-labels"></a>Etiquetas de retención

Siempre que un usuario aplica una etiqueta configurada para retener contenido o retener y, a continuación, eliminar contenido en cualquier carpeta o elemento de su buzón, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **True**. Cuando esto sucede, se considera que el buzón está en suspensión, como si se hubiera colocado en retención por juicio o se hubiera asignado a una directiva de retención.

Para ver el valor de la *propiedad ComplianceTagHoldApplied,* ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Después de identificar que un buzón está en suspensión porque se aplica una etiqueta de retención a una carpeta o elemento, puede usar la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar elementos etiquetados mediante la condición de búsqueda ComplianceTag. Para obtener más información, vea la sección "Condiciones de búsqueda" en Consultas de palabras clave y condiciones de búsqueda [para búsqueda de contenido.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

Para obtener más información acerca de las etiquetas, vea [Más información sobre las directivas de retención y las etiquetas de retención.](retention.md)

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery
  
Ejecute los siguientes comandos en [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) del Centro de seguridad & Cumplimiento para identificar la retención asociada a un caso de exhibición de documentos electrónicos (denominadas retenciones de exhibición de documentos *electrónicos)* que se aplica al buzón. Use el GUID (sin incluir el prefijo) para la retención de exhibición de documentos electrónicos  `UniH` que identificó en el paso 1. El segundo comando muestra el nombre del caso de eDiscovery al que está asociada la retención; el tercer comando muestra el nombre de la retención.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

Después de identificar el nombre del caso de eDiscovery y la retención, vaya a la página **eDiscovery** de exhibición de documentos electrónicos en el centro de cumplimiento, abra el caso y quite el buzón de la \>  retención. Para obtener más información acerca de cómo identificar retenciones de exhibición de documentos electrónicos, vea la sección "Retenciones de exhibición de documentos electrónicos" en Cómo identificar el tipo de retención colocada en un buzón [de Exchange Online.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>Paso 4: Quitar la retención con retraso del buzón

Después de quitar cualquier tipo de retención de un buzón, el valor de la propiedad de buzón *DelayHoldApplied* o *DelayReleaseHoldApplied* se establece en **True**. Esto ocurre la próxima vez que el Asistente para carpeta administrada procesa el buzón y detecta que se ha quitado una retención. Esto se denomina *retención* retrasada y significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente del buzón. (El propósito de una retención retrasada es dar a los administradores la oportunidad de buscar o recuperar elementos del buzón que se purgarán después de quitar una retención).  Cuando se coloca una retención retrasada en el buzón, el buzón aún se considera que está en suspensión durante un período ilimitado, como si el buzón se encontrara en retención por juicio. Después de 30 días, la retención por retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* en **False)** para que se quite la retención. Para obtener más información acerca de una retención retrasada, vea la sección "Administración de buzones en retención retrasada" en Cómo identificar el tipo de retención colocada en un buzón [de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

Para poder eliminar elementos en el paso 5, debe quitar una retención retrasada del buzón. En primer lugar, determine si la retención retrasada se aplica al buzón ejecutando el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

Si el valor de la propiedad *DelayHoldApplied* o *DelayReleaseHoldApplied* se establece en **False**, no se ha colocado una retención de retraso en el buzón. Puede ir al paso 5 y eliminar elementos de la carpeta Elementos recuperables.

Si el valor de *la propiedad DelayHoldApplied* o *DelayReleaseHoldApplied* está establecido en **True**, ejecute uno de los siguientes comandos para quitar la retención de retraso:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol de retención legal en Exchange Online para usar el parámetro *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied.*

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>Paso 5: Eliminar elementos de la carpeta Elementos recuperables

Ahora está listo para eliminar realmente los elementos de la carpeta Elementos recuperables mediante los cmdlets [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) y [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) en PowerShell del Centro de seguridad & cumplimiento.

Para buscar elementos que se encuentran en la carpeta Elementos recuperables, se recomienda realizar una colección *de destino.* Esto significa que limita el ámbito de la búsqueda solo a los elementos ubicados en la carpeta Elementos recuperables. Para ello, ejecute el script del artículo Usar búsqueda de contenido [para colecciones de](use-content-search-for-targeted-collections.md) destino. Este script devuelve el valor de la propiedad id. de carpeta para todas las subcarpetas de la carpeta Elementos recuperables de destino. A continuación, use el identificador de carpeta en una consulta de búsqueda para devolver los elementos ubicados en esa carpeta.

A continuación se ofrece información general sobre el proceso para buscar y eliminar elementos en la carpeta Elementos recuperables de un usuario:

1. Ejecute el script de colección de destino que devuelve los id. de carpeta de todas las carpetas del buzón del usuario de destino. El script se conecta a PowerShell de Exchange Online y a PowerShell de & cumplimiento en la misma sesión de PowerShell. Para obtener más información, [vea Ejecutar el script para obtener una lista de carpetas para un buzón.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. Copie los nombres de carpeta de todas las subcarpetas de la carpeta Elementos recuperables. Como alternativa, puede redirigir el resultado del script a un archivo de texto.

   Esta es una lista y una descripción de las subcarpetas de la carpeta Elementos recuperables de las que puede buscar y eliminar elementos:

   - **Eliminaciones:** contiene elementos eliminados temporalmente cuyo período de retención de elementos eliminados no ha expirado. Los usuarios pueden recuperar elementos eliminados temporalmente de esta subcarpeta mediante la herramienta Recuperar elementos eliminados en Outlook.

   - **Purgas:** contiene elementos eliminados permanentemente cuyo período de retención de elementos eliminados ha expirado. Los usuarios también pueden eliminar elementos de forma permanente purgando elementos de su carpeta Elementos recuperables. Si el buzón está en retención, se conservan los elementos eliminados permanentemente. Esta subcarpeta no es visible para los usuarios finales.

   - **Retenciones de** detección: contiene elementos eliminados permanentemente que se han conservado mediante una retención de exhibición de documentos electrónicos o una directiva de retención. Esta subcarpeta no es visible para los usuarios finales.

   - **SubstrateHolds:** contiene elementos eliminados permanentemente de Teams y otras aplicaciones basadas en la nube que se han conservado mediante una directiva de retención u otro tipo de retención. Esta subcarpeta no es visible para los usuarios finales.

3. Use el cmdlet **New-ComplianceSearch** (en PowerShell del Centro de seguridad & Cumplimiento) o use la herramienta de búsqueda de contenido en el Centro de cumplimiento para crear una búsqueda de contenido que devuelva elementos de la carpeta Elementos recuperables del usuario de destino. Para ello, incluya FolderId en la consulta de búsqueda de todas las subcarpetas que desee buscar. Por ejemplo, la siguiente consulta devuelve todos los mensajes de las subcarpetas Purgas y Retenciones de exhibición de documentos electrónicos:

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   Para obtener más información y ejemplos sobre cómo ejecutar búsquedas de contenido que usan la propiedad id. de carpeta, vea Usar un identificador de carpeta o para [realizar una colección de destino.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > Si usa el cmdlet **New-ComplianceSearch** para buscar en la carpeta Elementos recuperables, asegúrese de usar el cmdlet **Start-ComplianceSearch** para ejecutar la búsqueda.

4. Después de crear una búsqueda de contenido y validar que devuelve los elementos que desea eliminar, use el comando (en PowerShell del Centro de seguridad & cumplimiento) para eliminar permanentemente los elementos devueltos por la búsqueda de contenido que creó en el paso `New-ComplianceSearchAction -Purge -PurgeType HardDelete` anterior. Por ejemplo, puede ejecutar un comando similar al siguiente:

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. Al ejecutar el comando anterior, se elimina un máximo de 10 elementos por buzón. Esto significa que es posible que tenga que ejecutar el comando varias veces para eliminar todos los elementos que desea eliminar en la carpeta `New-ComplianceSearchAction -Purge` Elementos recuperables. Para eliminar elementos adicionales, primero debe quitar la acción anterior de depuración de búsqueda de cumplimiento. Para ello, ejecute el `Remove-ComplianceSearchAction` cmdlet. Por ejemplo, para eliminar la acción de purga que se ha ejecutado en el paso anterior, ejecute el siguiente comando:

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   Después de hacerlo, puede crear una nueva acción de depuración de búsqueda de cumplimiento para eliminar más elementos. Tendrá que eliminar cada acción de depuración antes de crear una nueva.

   Para obtener una lista de las acciones de búsqueda de cumplimiento, puede ejecutar el `Get-ComplianceSearchAction` cmdlet. Las acciones de depuración se identifican `_Purge` anexando al nombre de búsqueda.

### <a name="verify-that-items-were-deleted"></a>Comprobar que se eliminaron los elementos

Para comprobar que ha eliminado correctamente elementos de la carpeta Elementos recuperables de un buzón, use el cmdlet **Get-MailboxFolderStatistics** en Exchange Online PowerShell para comprobar el tamaño y el número de elementos de la carpeta Elementos recuperables. Puede comparar estas estadísticas con las que recopiló en el paso 1.
  
Ejecute el siguiente comando para obtener el tamaño actual y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables del buzón principal del usuario.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

Ejecute el siguiente comando para obtener el tamaño y el número total de elementos de carpetas y subcarpetas de la carpeta Elementos recuperables del buzón de archivo del usuario.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>Paso 6: Revertir el buzón a su estado anterior

El último paso es revertir el buzón a su configuración anterior. Esto significa restablecer las propiedades que cambió en el paso 2 y volver a aplicar las retenciones que quitó en el paso 3. Incluye lo siguiente:
  
- Cambiar el período de retención de elementos eliminados a su valor anterior. Como alternativa, puede dejar este conjunto en 30 días, el valor máximo en Exchange Online.

- Volver a habilitar la recuperación de elementos individuales.

- Vuelva a habilitar los métodos de acceso de cliente para que el propietario pueda tener acceso a su buzón.

- Volver a aplicar las retenciones y directivas de retención que quitó.

- Volver a habilitar el Asistente para carpeta administrada para procesar el buzón.

> [!IMPORTANT]
> Se recomienda esperar 24 horas después de volver a aplicar una retención o directiva de retención (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpeta administrada para procesar el buzón.
  
Realice los siguientes pasos (en la secuencia especificada) en Exchange Online PowerShell.
  
1. Ejecute el siguiente comando para volver a cambiar el período de retención de elementos eliminados a su valor original. Esto supone que la configuración anterior es inferior a 30 días; por ejemplo, 14 días.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. Ejecute el siguiente comando para volver a habilitar la recuperación de elementos individuales.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. Ejecute el siguiente comando para volver a habilitar todos los métodos de acceso de cliente en el buzón.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. Vuelva a aplicar las retenciones que quitó en el paso 3. Según el tipo de retención, use uno de los procedimientos siguientes.

    **Retención por juicio**

    Ejecute el siguiente comando para volver a habilitar una retención por juicio para el buzón.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**

    Use el EAC (o Exchange Online PowerShell) para volver a agregar el buzón a la In-Place retención.

    **Directivas de retención aplicadas a buzones específicos**

    Use el Centro de & cumplimiento para agregar el buzón de nuevo a la directiva de retención. Vaya a la página Retención de gobierno de la información en el Centro de seguridad y cumplimiento de &, edite la directiva de retención y vuelva a agregar el buzón a la lista de destinatarios a los que se aplica la directiva de  >   retención.

    **Directivas de retención en toda la organización**

    Si quitó una directiva de retención en toda la organización o en Toda Exchange al excluirla de la directiva, use el Centro de seguridad y cumplimiento de & para quitar el buzón de la lista de usuarios excluidos. Vaya a la **página** Retención de gobierno de la información en el Centro de seguridad & Cumplimiento, edite la directiva de retención en toda la organización y quite el buzón de la lista de destinatarios  >   excluidos. Al hacerlo, se volverá a aplicar la directiva de retención al buzón del usuario.

    **Retenciones de casos de eDiscovery**

    Use el Centro de & cumplimiento para agregar el buzón de correo de vuelta a la retención asociada a un caso de exhibición de documentos electrónicos. Vaya a la **página eDiscovery** de exhibición de documentos electrónicos, abra el caso y vuelva a agregar el  >   buzón a la retención. 

5. Ejecute el siguiente comando para permitir que el Asistente para carpeta administrada procese el buzón de nuevo. Como se indicó anteriormente, se recomienda esperar 24 horas después de volver a aplicar una retención o directiva de retención (y comprobar que está en su lugar) antes de volver a habilitar el Asistente para carpeta administrada.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. Para comprobar que el buzón se revierte a su configuración anterior, puede ejecutar los siguientes comandos y, a continuación, comparar la configuración con la que recopiló en el paso 1.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>Más información

Esta es una tabla que describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* al ejecutar los cmdlets **Get-Mailbox** o **Get-OrganizationConfig.** Para obtener información más detallada, consulte Cómo identificar el tipo de retención [colocada en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md).

Como se ha explicado anteriormente, debe quitar todas las retenciones y directivas de retención de un buzón para poder eliminar correctamente los elementos de la carpeta Elementos recuperables.
  
| Tipo de retención | Valor de ejemplo | Cómo identificar la retención |
|:-----|:-----|:-----|
|Retención por juicio  <br/> | `True` <br/> |La  *propiedad LitigationHoldEnabled*  se establece en  `True` .  <br/> |
|Retención en contexto  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la In-Place que se coloca en el buzón. Puede saber que se trata de una retención In-Place porque el GUID no comienza con un prefijo.  <br/> Puede usar el comando de Exchange Online PowerShell para obtener información sobre la retención In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` en el buzón.  <br/> |
| Directivas de retención en el Centro de seguridad & cumplimiento aplicados a buzones específicos  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> o  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |Al ejecutar el cmdlet **Get-Mailbox,** la propiedad  *InPlaceHolds*  también contiene GUID de directivas de retención aplicadas al buzón. Puede identificar directivas de retención porque el GUID comienza con el  `mbx` prefijo. Si el GUID de la directiva de retención comienza con el prefijo, eso indica que la directiva de retención se aplica a las conversaciones de  `skp` Skype Empresarial.  <br/> Para identificar la directiva de retención que se aplica al buzón, ejecute el siguiente comando en PowerShell del Centro de & seguridad: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Asegúrese de quitar el  `mbx` prefijo o cuando ejecute este  `skp` comando.  <br/> |
|Directivas de retención para toda la organización en el Centro de & cumplimiento  <br/> |Sin valor  <br/> o  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (indica que el buzón está excluido de una directiva para toda la organización)  <br/> |Incluso si la  *propiedad InPlaceHolds*  está vacía al ejecutar el cmdlet **Get-Mailbox,** es posible que se apliquen al buzón una o varias directivas de retención en toda la organización.  <br/> Para comprobarlo, puede ejecutar el comando en Exchange Online PowerShell para obtener una lista de los GUID para las directivas de retención  `Get-OrganizationConfig | FL InPlaceHolds` en toda la organización. El GUID de las directivas de retención de toda la organización aplicadas a los buzones de Exchange comienza por el  `mbx` prefijo; por ejemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> Para identificar la directiva de retención de toda la organización que se aplica al buzón, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>Si se excluye un buzón de una directiva de retención en toda la organización, el GUID de la directiva de retención se muestra en la propiedad  *InPlaceHolds*  del buzón del usuario cuando se ejecuta el cmdlet **Get-Mailbox;** se identifica por el  `-mbx` prefijo; por ejemplo,  `-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|Retención de casos de exhibición de documentos electrónicos en el Centro de & cumplimiento  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |La  *propiedad InPlaceHolds*  también contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento que se puede colocar en el buzón. Puede saber que se trata de una retención de casos de exhibición de documentos electrónicos porque el GUID comienza con el  `UniH` prefijo.  <br/> Puede usar el cmdlet de PowerShell del Centro de seguridad & Cumplimiento para obtener información sobre el caso de eDiscovery al que está asociada la retención en el  `Get-CaseHoldPolicy` buzón. Por ejemplo, puede ejecutar el comando para mostrar el nombre de la retención de  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` casos que se encuentra en el buzón. Asegúrese de quitar el  `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de exhibición de documentos electrónicos al que está asociada la retención en el buzón, ejecute los siguientes comandos:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
