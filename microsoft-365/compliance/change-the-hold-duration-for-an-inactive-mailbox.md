---
title: Cambiar la duración de retención para un buzón inactivo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/29/2017
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
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Después de que Office 365 buzón de correo esté inactivo, cambie la duración de la retención o Office 365 de retención asignada al buzón inactivo.
ms.openlocfilehash: bf1131aa0d14222bec7ab1c94983925cfe39e673
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62241616"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Un [buzón inactivo es el](inactive-mailboxes-in-office-365.md) estado del buzón que se usa para conservar el correo electrónico de un antiguo empleado después de salir de la organización. Un buzón se vuelve inactivo cuando se le aplica una retención aplicable antes de eliminar Microsoft 365 objeto de usuario.  Los siguientes tipos de retenciones iniciarán la creación de un buzón inactivo tras la eliminación de la cuenta de usuario:

- [Microsoft 365 directivas de retención y etiquetas con](retention.md) la configuración de retención o retención y eliminación

- Una retención asociada a un [caso de exhibición de documentos](ediscovery.md) electrónicos

- [Retención por litigio](create-a-litigation-hold.md)

- Una retención In-Place existente.

> [!IMPORTANT]
> Aunque cualquiera de las retenciones anteriores forzará Microsoft 365 que un buzón se vuelva inactivo al eliminar una cuenta de usuario, se recomienda encarecidamente que use la retención de Microsoft 365 cuando planee proactivamente usar buzones inactivos.
>
> - Las retenciones de exhibición de documentos electrónicos están destinadas a casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y las retenciones asociadas con el caso se quitarán y el caso de exhibición de documentos electrónicos se cerrará (o se eliminará). Si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y la retención se libera o el caso de exhibición de documentos electrónicos se cierra o elimina, el buzón inactivo se eliminará permanentemente.
>
> - In-Place las retenciones en el Exchange de administración ya están retiradas. A partir del 1 de julio de 2020, las nuevas In-Place no se podían crear en Exchange Online. A partir del 1 de octubre de 2020, ya no se podía cambiar la duración de retención de las retenciones locales. Cualquier buzón inactivo que tenga una retención In-Place aplicación solo se puede eliminar quitando la In-Place espera. Los buzones inactivos existentes que están In-Place conservarán hasta que se quite la retención. Para obtener más información sobre In-Place de retención de documentos electrónicos, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
>
> - [La retención por](create-a-litigation-hold.md) juicio sigue siendo compatible como un método alternativo para retener contenido en un buzón y hacerlo inactivo después de eliminar una cuenta de usuario. Sin embargo, como una tecnología más antigua, se recomienda usar la retención Microsoft 365 en su lugar.

Una vez inactivo, el contenido del [](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) buzón, incluida la carpeta Elementos recuperables, se conserva hasta que ya no se aplica la retención que se colocó en el buzón antes de que se pusiera inactivo.  

Si la retención aplicable no está basada en el tiempo, como una retención asociada a una directiva de retención o etiqueta de Microsoft 365 retención de solo retención indefinida, un caso de exhibición de documentos electrónicos o una retención por juicio (sin una configuración), el contenido del buzón se conservará indefinidamente hasta que se quite la ```LitigationHoldDuration``` retención.  

Sin embargo, si la retención se basa en el tiempo, el contenido del buzón se conservará hasta que expire la duración de la retención, momento en el que los elementos de la carpeta Elementos recuperables se eliminarán permanentemente (purgarán) del buzón inactivo.

> [!NOTE]
> En el caso de los buzones inactivos, se recomienda usar una configuración de retención y eliminación para las Microsoft 365 o etiquetas de retención.  Si elige una configuración de solo retención, la carpeta Elementos recuperables se purgará al final de la duración de la retención, pero cualquier otro elemento no eliminado permanecerá en el buzón inactivo indefinidamente.

A medida que evolucionan las normativas y las directivas, puede haber algunas situaciones en las que necesite cambiar la duración de la retención asignada al buzón inactivo.  Los siguientes pasos describen cómo hacerlo.

## <a name="connect-to-powershell"></a>Conectar a PowerShell

Como hemos mencionado anteriormente, muchos tipos diferentes de retenciones pueden desencadenar la creación de un buzón inactivo.  Por este motivo, para cambiar la duración de retención aplicada al buzón inactivo, primero debe identificar qué tipo de retenciones le están afectando.  Para ello, debe usar Exchange Online PowerShell para identificar los tipos de retenciones y, si el buzón inactivo se ve afectado por las etiquetas o directivas de retención de Microsoft 365, también debe usar PowerShell del Centro de seguridad y cumplimiento para identificar las directivas específicas.

- Para conectarse Exchange Online PowerShell o PowerShell del Centro de & seguridad, consulte uno de los siguientes temas:

  - [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

  - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Dado que pueden colocarse diferentes tipos de retenciones o una o más directivas de retención Microsoft 365 en un buzón inactivo, el primer paso consiste en identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de un buzón inactivo específico de la organización.
  
```powershell
Get-Mailbox -Identity <identity of inactive mailbox> -InactiveMailboxOnly | FL DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied
```

Si necesita identificar el tipo de retención de varios buzones inactivos y su organización tiene un gran número de ellos, puede que no sea manejable ver con PowerShell. En este caso, puede exportar toda la información aplicable a un archivo CSV con el siguiente comando y modificar la según ```Path``` sea necesario para su entorno:

```powershell
Get-Mailbox -InactiveMailboxOnly -ResultSize Unlimited | Select DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied | Export-Csv -NoTypeInformation -Path "C:\Temp\InactiveMailboxHoldTypes.csv"
```

En este ejemplo, se muestran los resultados de seis buzones inactivos con diferentes tipos de retención posibles.

> [!NOTE]
> Se pueden aplicar varias retenciones, incluidos varios tipos de retenciones, a un único buzón inactivo.
  
```text
DisplayName              : Ann Beebe
Name                     : annb
DistinguishedName        : CN=annb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 664ef44e-c1a0-47b0-9553-2ecdfc6ef840
IsInactiveMailbox        : True
LitigationHoldEnabled    : True
LitigationHoldDuration   : 365.00:00:00
LitigationHoldDate       : 10/25/2021 6:54:57 PM
LitigationHoldOwner      : admin@contoso.com
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Carol Olson
Name                     : carolo
DistinguishedName        : CN=carolo,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : e646a369-00bf-43d3-837a-8eae8b301d44
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbxcdbbb86ce60342489bff371876e7f224:3}
ComplianceTagHoldApplied : False
...
DisplayName              : Megan Bowen
Name                     : meganb
DistinguishedName        : CN=meganb,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 36ec77cb-c524-468a-a8e8-bfb75e01a176
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {mbx6fe063689d404a5bb9940eed0f0bf5d2:1}
ComplianceTagHoldApplied : True
...
DisplayName              : Mario Necaise
Name                     : marion
DistinguishedName        : CN=marion,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 0579e039-a695-40d5-8f0a-0dc04f4b4c8f
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {}
ComplianceTagHoldApplied : False
...
DisplayName              : Abraham McMahon
Name                     : abrahamm
DistinguishedName        : CN=abrahamm,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 55ad8905-4e68-4c8d-940d-e068ec6b51fc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
ComplianceTagHoldApplied : False
...
DisplayName              : Pilar Pinilla
Name                     : pilarp
DistinguishedName        : CN=pilarp,OU=Soft Deleted
                           Objects,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange
                           Hosted Organizations,DC=NAMPR06A007,DC=PROD,DC=OUTLOOK,DC=COM
ExchangeGuid             : 8d7867d6-bb6d-4cd8-a51f-09d208f97fcc
IsInactiveMailbox        : True
LitigationHoldEnabled    : False
LitigationHoldDuration   : Unlimited
LitigationHoldDate       :
LitigationHoldOwner      :
InPlaceHolds             : {c0ba3ce811b6432a8751430937152491}
ComplianceTagHoldApplied : False
```

En la tabla siguiente se identifican los seis tipos de retención diferentes que se usaron para que cada buzón quedara inactivo en el ejemplo anterior.
  
|**Buzón inactivo**|**Tipo de retención**|**Cómo identificar la retención en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por litigio  <br/> | La  `LitigationHoldEnabled`  propiedad se establece en indicar que el buzón está en retención por  `True` juicio. <br/><br/> Además, se establece en indicar que los elementos del buzón ya no estarán sujetos a retención por juicio 365 días después de su fecha de creación `LitigationHoldDuration` `365.00:00:00` (enviado/recibido).  <br/><br/> Indica la fecha en que se ha habilitado LitigationHold e identifica a `LitigationHoldDate` la persona que `LitigationHoldOwner` inició la retención por juicio. <br/> |
|Carol Olson  <br/> |Microsoft 365 de retención de la Centro de cumplimiento de Microsoft 365 que se aplica a buzones específicos  <br/> |La propiedad contiene el GUID de la directiva Microsoft 365 de retención que se aplica al `InPlaceHolds` buzón inactivo. Puede saber que se trata de una directiva de retención que se aplica a buzones específicos porque el GUID comienza con el prefijo y `mbx` termina en un o `:2` `:3` . <br/><br/> Para obtener más información, vea [Understanding the format of the InPlaceHolds value for retention policies](identify-a-hold-on-an-exchange-online-mailbox.md#understanding-the-format-of-the-inplaceholds-value-for-retention-policies).  <br/> |
|Megan Bowen <br/> | Microsoft 365 etiqueta de retención con una acción de retención o retención y eliminación se aplica al menos a un elemento del buzón  <br/> |La propiedad indica que un elemento se ha etiquetado con una etiqueta de retención `ComplianceTagHoldApplied` `True` o retención y eliminación.  <br/><br/> Además, la propiedad contiene el GUID de la directiva Microsoft 365 etiqueta de retención que se aplica al `InPlaceHolds` buzón inactivo.  <br/><br/> Para obtener más información, vea [Identifying mailboxes on hold because a retention label has been applied to a folder or item](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) <br/>  |
|Mario Necaise  <br/> |Directiva de retención Microsoft 365 toda la organización desde el Centro de cumplimiento de Microsoft 365  <br/> |La  `InPlaceHolds`  propiedad está vacía, es y `LitigationHoldEnabled` es `False` `ComplianceTagHoldApplied` `False` . Esto indica que una o varias directivas de retención de Exchange (Exchange Microsoft 365) se aplican a la organización que hereda el buzón inactivo. <br/><br/> Para obtener más información, vea [How to confirm that an organization-wide retention policy is applied to a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox) <br/> |
|Abraham McMahon  <br/> |Retención de casos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365  <br/> |La propiedad contiene el GUID de la retención de casos de exhibición de documentos electrónicos que se  `InPlaceHolds`  coloca en el buzón inactivo. Puede saber que se trata de una retención de casos de exhibición de documentos electrónicos porque el GUID comienza por el  `UniH` prefijo.  <br/><br/> Para obtener más información, [vea eDiscovery holds](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds). <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La  `InPlaceHolds`  propiedad contiene el GUID de la In-Place que se coloca en el buzón inactivo. Puede saber que se trata de una retención In-Place porque el GUID no comienza con un prefijo.  <br/><br/> **NOTA**: A partir del 1 de octubre de 2020, la duración de retención de las retenciones locales ya no se puede cambiar. Solo puede quitar una retención In-Place que dará como resultado la eliminación del buzón inactivo. <br/><br/> Para obtener más información, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md). <br/> |

## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención.  El proceso varía según el tipo de retención aplicada.

- [Cambiar la duración de una directiva Microsoft 365 de retención](#change-the-duration-for-a-microsoft-365-retention-policy)

- [Cambiar la duración de una etiqueta Microsoft 365 de retención](#change-the-duration-for-a-microsoft-365-retention-label)

- [Cambiar la duración de una retención de exhibición de documentos electrónicos](#change-the-duration-for-an-ediscovery-hold)

- [Cambiar la duración de una retención por juicio](#change-the-duration-for-a-litigation-hold)

- [Cambiar la duración de una In-Place retención](#change-the-duration-for-an-in-place-hold)

### <a name="change-the-duration-for-a-microsoft-365-retention-policy"></a>Cambiar la duración de una directiva Microsoft 365 de retención

Para modificar la duración de retención de una directiva de retención de Microsoft 365, primero debe identificar la directiva que afecta al buzón inactivo ejecutando con el GUID asociado desde la propiedad en el buzón en PowerShell del Centro de seguridad y `Get-RetentionCompliancePolicy` `InPlaceHolds` cumplimiento.

Asegúrese de quitar el prefijo y el sufijo del GUID al ejecutar este comando.  Por ejemplo, con la información de ejemplo de arriba, tomaría el valor de quitar y dar como resultado `InPlaceHolds` un GUID de directiva de `mbxcdbbb86ce60342489bff371876e7f224:3` `mbx` `:3` `cdbbb86ce60342489bff371876e7f224` .  En este ejemplo, desea ejecutar:

```powershell
Get-RetentionCompliancePolicy cdbbb86ce60342489bff371876e7f224 | FL Name
```

Una vez que sepa el nombre de la directiva, simplemente puede modificar la directiva de retención en el centro de Microsoft 365 cumplimiento.  Tenga en cuenta que las directivas de retención se aplican normalmente a más de una ubicación, por lo que la modificación de la directiva afectará a todas las ubicaciones aplicadas, tanto inactivas como activas, que también pueden incluir ubicaciones distintas de Exchange.  Para obtener más información, vea [Create and configure retention policies](create-retention-policies.md).  

> [!IMPORTANT]
> Las directivas de retención con bloqueo [de](retention-preservation-lock.md) conservación habilitado pueden extender el período de retención, pero no disminuir ni quitarse.

Si la intención es modificar el período de retención solo para buzones inactivos o solo [buzones inactivos específicos,](retention.md#adaptive-or-static-policy-scopes-for-retention)puede considerar la posibilidad de implementar ámbitos de directiva adaptables , que se pueden usar para dirigirse individualmente a buzones específicos o tipos de buzones, como buzones inactivos, mediante atributos y propiedades de Azure AD y Exchange.

### <a name="change-the-duration-for-a-microsoft-365-retention-label"></a>Cambiar la duración de una etiqueta Microsoft 365 de retención

Al igual que con las directivas de retención, al modificar la duración de retención de una etiqueta de retención de Microsoft 365, primero debe identificar la directiva que publica la etiqueta que afecta al contenido dentro del buzón inactivo ejecutando con el GUID asociado desde la propiedad en el buzón en PowerShell del Centro de seguridad y `Get-RetentionCompliancePolicy` `InPlaceHolds` cumplimiento.

Asegúrese de quitar el prefijo y el sufijo del GUID al ejecutar este comando.  Por ejemplo, con la información de ejemplo de arriba, tomaría el valor de quitar y dar como resultado `InPlaceHolds` un GUID de directiva de `mbx6fe063689d404a5bb9940eed0f0bf5d2:1` `mbx` `:1` `6fe063689d404a5bb9940eed0f0bf5d2` .  En este ejemplo, desea ejecutar:

```powershell
Get-RetentionCompliancePolicy 6fe063689d404a5bb9940eed0f0bf5d2 | FL Name
```

Una vez que haya identificado la directiva, sabrá qué etiquetas se han publicado y su configuración.  Dado que las etiquetas se aplican a elementos individuales, según el número de etiquetas publicadas con la directiva y su configuración, es posible que no pueda identificar directamente qué etiqueta está afectando al contenido.  

Un método que puede usar para identificar el contenido al que se aplica cada etiqueta es el uso de [búsqueda de contenido](content-search.md).  Por ejemplo, mediante la información de ejemplo de arriba, supongamos que la directiva publica varias etiquetas, una de las cuales se denomina "CONTENIDO-HR".  Con los permisos [correctos,](microsoft-365-compliance-center-permissions.md)se puede ejecutar una búsqueda de contenido con el comando [PowerShell New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch), especificando la dirección SMTP principal del buzón inactivo, con un punto ( ), y el parámetro para omitir la `.` `-AllowNotFoundExchangeLocationsEnabled $true` validación:

```powershell
New-ComplianceSearch -Name "MeganB Inactive Mailbox HR-Content Label Search" -ExchangeLocation .meganb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true -ContentMatchQuery "compliancetag=HR-Content"
```

Una vez creada la búsqueda, iniciará la búsqueda con el siguiente comando:

```powershell
Start-ComplianceSearch "MeganB Inactive Mailbox HR-Content Label Search"
```

Con este método, puede identificar qué etiquetas de la directiva de etiquetas identificadas se aplican al contenido del buzón inactivo para poder modificar sus períodos de retención. Tenga en cuenta que las etiquetas de retención normalmente se aplican a más de una ubicación, por lo que modificar una etiqueta afectará a todas las ubicaciones aplicadas y al contenido etiquetado, que también puede incluir ubicaciones y contenido que no sean Exchange. Para obtener más información, consulta [Crear etiquetas de retención y aplicarlas en aplicaciones.](create-apply-retention-labels.md)

> [!NOTE]
> No se pueden modificar todos los tipos de etiquetas de retención.  Para algunas etiquetas, es posible que solo pueda aumentar el tiempo de retención y, para otras, es posible que no pueda modificar el período de retención en absoluto.

### <a name="change-the-duration-for-an-ediscovery-hold"></a>Cambiar la duración de una retención de exhibición de documentos electrónicos

Las retenciones asociadas con casos de exhibición de documentos electrónicos son retenciones indefinidas, lo que significa que no hay ninguna duración de retención que se pueda cambiar. Los elementos se mantienen para siempre o hasta que [se quita la retención](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold) o se cierra el caso.
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Debe usar Exchange Online PowerShell para cambiar la duración de retención de una retención por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, la duración de retención se cambia a un período de tiempo ilimitado:
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la retención o se cambia la duración de la retención a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.

### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

In-Place las retenciones se han retirado y ya no se pueden modificar. Si un buzón inactivo tiene una retención In-Place aplicación, no puede cambiar la duración de retención. Solo puede quitar la retención In-Place, lo que dará como resultado la eliminación del buzón inactivo. Para obtener más información, vea [Eliminar un buzón inactivo.](delete-an-inactive-mailbox.md#remove-in-place-holds)
  
## <a name="more-information"></a>Más información

- **¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea.
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no hay ninguna duración especificada para la retención colocada en el buzón inactivo, los elementos de la carpeta Elementos recuperables nunca se purgan (a menos que se cambie la duración de retención del buzón inactivo). 
    
- **¿Se sigue Exchange directiva de MRM en buzones inactivos?**  Si se aplicó una directiva de retención de MRM **a** un buzón antes de que pasara a estar inactiva, las directivas de eliminación (etiquetas de retención de MRM configuradas con una acción Eliminar) se seguirán procesando en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación de MRM se mueven a la carpeta Elementos recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

    Por el contrario, se omiten las directivas de archivo (etiquetas de retención de MRM configuradas con una acción **MoveToArchive)** que se incluyen en la directiva de retención de MRM asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.
    > [!NOTE]
    > La aplicación de una directiva Exchange de retención (la característica De administración de registros de mensajería o MRM en Exchange Online) no crea un buzón inactivo cuando se elimina la cuenta de usuario.

- **Al igual que con los buzones normales, el Asistente para carpetas administradas (MFA) también procesa buzones inactivos.** En Exchange Online, la MFA procesa buzones aproximadamente una vez cada siete días. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si muchos se colocan en un buzón inactivo, no se mostrarán todos los `InPlaceHolds` GUID de retención.** Puede ejecutar el siguiente comando para mostrar los GUID de todos los que se `InPlaceHolds` colocan en un buzón inactivo.
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
