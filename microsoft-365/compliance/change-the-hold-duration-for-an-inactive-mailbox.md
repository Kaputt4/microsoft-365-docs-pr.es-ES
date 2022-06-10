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
description: Después de que un buzón de Office 365 esté inactivo, cambie la duración de la retención o Office 365 directiva de retención asignada al buzón inactivo.
ms.openlocfilehash: f9db81631c563bb985d087b4dfd12ae784c825ff
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66015844"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Un [buzón inactivo](inactive-mailboxes-in-office-365.md) es el estado del buzón que se usa para conservar el correo electrónico de un empleado anterior después de abandonar la organización. Un buzón de correo pasa a estar inactivo cuando se le aplica una suspensión aplicable antes de que se elimine el Microsoft 365 objeto de usuario.  Los siguientes tipos de retenciones iniciarán la creación de un buzón inactivo tras la eliminación de la cuenta de usuario:

- [Microsoft 365 directivas y etiquetas de retención](retention.md) con la configuración de retención o retención y eliminación

- Una suspensión asociada a un caso [de exhibición de documentos electrónicos](ediscovery.md)

- [Retención por litigio](create-a-litigation-hold.md)

- Una suspensión de In-Place existente.

> [!IMPORTANT]
> Aunque cualquiera de las retenciones anteriores obligará a que un buzón de correo se inactiva tras Microsoft 365 eliminación de la cuenta de usuario, se recomienda encarecidamente usar Microsoft 365 retención al planear proactivamente el uso de buzones inactivos.
>
> - Las retenciones de eDiscovery están destinadas a casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y las retenciones asociadas al caso se quitarán y el caso de exhibición de documentos electrónicos se cerrará (o eliminará). Si una suspensión que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y se libera la suspensión o se cierra o elimina el caso de exhibición de documentos electrónicos, el buzón inactivo se eliminará permanentemente.
>
> - In-Place se han retirado las retenciones en el centro de administración de Exchange. A partir del 1 de julio de 2020, no se pudieron crear nuevas suspensiones de In-Place en Exchange Online. A partir del 1 de octubre de 2020, la duración de la suspensión de las retenciones en contexto ya no se podía cambiar. Cualquier buzón inactivo que tenga aplicada una suspensión In-Place solo se puede eliminar quitando la In-Place Suspensión. Los buzones inactivos existentes que están en In-Place suspensión se seguirán conservando hasta que se quite la suspensión. Para obtener más información sobre la retirada de In-Place holds, consulte [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md).
>
> - [La suspensión por juicio](create-a-litigation-hold.md) sigue siendo compatible como método alternativo para conservar el contenido de un buzón y convertirlo en inactivo después de eliminar una cuenta de usuario. Sin embargo, como tecnología anterior, se recomienda usar Microsoft 365 retención en su lugar.

Una vez inactivo, el contenido del buzón, incluida la [carpeta Elementos recuperables](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) , se conserva hasta que ya no se aplica la suspensión que se colocó en el buzón antes de que se inactiva.  

Si la retención aplicable no está basada en el tiempo, como una suspensión asociada a una directiva o etiqueta de retención de solo retención indefinida Microsoft 365, un caso de exhibición de documentos electrónicos o una suspensión por juicio (sin configurar```LitigationHoldDuration```), el contenido del buzón se conservará indefinidamente hasta que se quite la suspensión.  

Sin embargo, si la suspensión está basada en el tiempo, el contenido del buzón se conservará hasta que expire la duración de la suspensión, momento en el que cualquier elemento de la carpeta Elementos recuperables se eliminará permanentemente (purgará) del buzón inactivo.

> [!NOTE]
> En el caso de los buzones inactivos, se recomienda usar una configuración de retención y eliminación para las etiquetas o directivas de retención de Microsoft 365.  Si elige una configuración de solo retención, la carpeta Elementos recuperables se purgará al final de la duración de la suspensión, pero cualquier otro elemento no eliminado permanecerá en el buzón inactivo indefinidamente.

A medida que evolucionan las regulaciones y las directivas, puede haber algunas situaciones en las que tenga que cambiar la duración de la suspensión asignada al buzón inactivo.  En los pasos siguientes se describe cómo hacerlo.

## <a name="connect-to-powershell"></a>Conectar a PowerShell

Como hemos mencionado antes, muchos tipos diferentes de retenciones pueden desencadenar la creación de un buzón inactivo.  Por este motivo, para cambiar la duración de retención aplicada al buzón inactivo, primero debe identificar qué tipo de retenciones le afectan.  Para ello, debe usar Exchange Online PowerShell para identificar los tipos de retenciones y, si el buzón inactivo se ve afectado por Microsoft 365 directivas o etiquetas de retención, también debe usar PowerShell de cumplimiento de seguridad & para identificar las directivas específicas.

- Para conectarse a Exchange Online PowerShell o PowerShell de cumplimiento de seguridad &, consulte uno de los temas siguientes:

  - [Conectarse a Exchange Online mediante PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)

  - [Conectarse a Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Dado que se pueden colocar diferentes tipos de retenciones o una o varias Microsoft 365 directivas de retención en un buzón inactivo, el primer paso es identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de un buzón inactivo específico de la organización.
  
```powershell
Get-Mailbox -Identity <identity of inactive mailbox> -InactiveMailboxOnly | FL DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied
```

Si necesita identificar el tipo de retención de varios buzones inactivos y su organización tiene un gran número de ellos, es posible que no se pueda ver mediante PowerShell. En este caso, puede exportar toda la información aplicable a un archivo CSV mediante el siguiente comando y modificar según ```Path``` sea necesario para su entorno:

```powershell
Get-Mailbox -InactiveMailboxOnly -ResultSize Unlimited | Select DisplayName,Name,DistinguishedName,ExchangeGuid,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,LitigationHoldDate,LitigationHoldOwner,InPlaceHolds,ComplianceTagHoldApplied | Export-Csv -NoTypeInformation -Path "C:\Temp\InactiveMailboxHoldTypes.csv"
```

A los efectos de este ejemplo, a continuación se muestran los resultados de seis buzones inactivos con diferentes tipos de suspensión posibles.

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

En la tabla siguiente se identifican los seis tipos de suspensión diferentes que se usaron para que cada buzón de correo esté inactivo en el ejemplo anterior.
  
|**Buzón inactivo**|**Tipo de suspensión**|**Cómo identificar la suspensión en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por litigio  <br/> | La  `LitigationHoldEnabled`  propiedad se establece en  `True` que indica que el buzón está en suspensión por juicio. <br/><br/> Además, se establece `365.00:00:00` en `LitigationHoldDuration` que indica que los elementos del buzón de correo ya no estarán sujetos a la suspensión por juicio 365 días después de su fecha de creación (enviada/recibida).  <br/><br/> `LitigationHoldDate` indica la fecha en que se ha habilitado LitigationHold e `LitigationHoldOwner` identifica a la persona que inició la suspensión del litigio. <br/> |
|Carol Olson  <br/> |Microsoft 365 directiva de retención desde el portal de cumplimiento de Microsoft Purview que se aplica a buzones específicos  <br/> |La `InPlaceHolds` propiedad contiene el GUID de la directiva de retención de Microsoft 365 que se aplica al buzón inactivo. Puede indicar que se trata de una directiva de retención que se aplica a buzones específicos porque el GUID comienza con el `mbx` prefijo y termina en o `:2` `:3`. <br/><br/> Para obtener más información, vea [Descripción del formato del valor de InPlaceHolds para las directivas de retención](identify-a-hold-on-an-exchange-online-mailbox.md#understanding-the-format-of-the-inplaceholds-value-for-retention-policies).  <br/> |
|Megan Bowen <br/> | Microsoft 365 etiqueta de retención con una acción de retención o retención y eliminación se aplica al menos a un elemento del buzón  <br/> |La `ComplianceTagHoldApplied` propiedad `True` indica que un elemento se ha etiquetado con una etiqueta de retención o retención y eliminación.  <br/><br/> Además, la `InPlaceHolds` propiedad contiene el GUID de la directiva de etiqueta de retención de Microsoft 365 que se aplica al buzón inactivo.  <br/><br/> Para obtener más información, consulte [Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento](identify-a-hold-on-an-exchange-online-mailbox.md#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item). <br/>  |
|Mario Necaise  <br/> |Directiva de retención de Microsoft 365 para toda la organización desde el portal de cumplimiento de Microsoft Purview <br/> |La  `InPlaceHolds`  propiedad está vacía, `LitigationHoldEnabled` es `False` y `ComplianceTagHoldApplied` es `False`. Esto indica que una o varias ubicaciones completas (Exchange) Microsoft 365 directivas de retención aplicadas a la organización que hereda el buzón inactivo. <br/><br/> Para obtener más información, vea [Cómo confirmar que se aplica una directiva de retención de toda la organización a un buzón de correo](identify-a-hold-on-an-exchange-online-mailbox.md#how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox). <br/> |
|Abraham McMahon  <br/> |Suspensión de casos de eDiscovery en el portal de cumplimiento de Microsoft Purview  <br/> |La  `InPlaceHolds`  propiedad contiene el GUID de la retención de mayúsculas y minúsculas de eDiscovery que se coloca en el buzón inactivo. Puede indicar que se trata de una suspensión de mayúsculas y minúsculas de eDiscovery porque el GUID comienza con el  `UniH` prefijo .  <br/><br/> Para obtener más información, vea [las retenciones de eDiscovery](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds). <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La  `InPlaceHolds`  propiedad contiene el GUID del In-Place Hold que se coloca en el buzón inactivo. Puede indicar que se trata de una suspensión de In-Place porque el GUID no comienza con un prefijo.  <br/><br/> **NOTA**: A partir del 1 de octubre de 2020, la duración de retención de las retenciones en contexto ya no se puede cambiar. Solo puede quitar una suspensión de In-Place que dará lugar a la eliminación del buzón inactivo. <br/><br/> Para obtener más información, vea [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md). <br/> |

## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención.  El proceso varía en función del tipo de suspensión aplicada.

- [Cambiar la duración de una directiva de retención de Microsoft 365](#change-the-duration-for-a-microsoft-365-retention-policy)

- [Cambiar la duración de una etiqueta de retención de Microsoft 365](#change-the-duration-for-a-microsoft-365-retention-label)

- [Cambiar la duración de una suspensión de exhibición de documentos electrónicos](#change-the-duration-for-an-ediscovery-hold)

- [Cambiar la duración de una suspensión por juicio](#change-the-duration-for-a-litigation-hold)

- [Cambiar la duración de una suspensión de In-Place](#change-the-duration-for-an-in-place-hold)

### <a name="change-the-duration-for-a-microsoft-365-retention-policy"></a>Cambiar la duración de una directiva de retención de Microsoft 365

Para modificar la duración de retención de una directiva de retención de Microsoft 365, primero debe identificar la directiva que afecta al buzón inactivo mediante la ejecución `Get-RetentionCompliancePolicy` con el GUID asociado de la `InPlaceHolds` propiedad del buzón en PowerShell de cumplimiento de seguridad &.

Asegúrese de quitar el prefijo y el sufijo del GUID al ejecutar este comando.  Por ejemplo, con la información de ejemplo anterior, tomaría el `InPlaceHolds` valor de `mbxcdbbb86ce60342489bff371876e7f224:3` y, a continuación, quitaría `mbx` y `:3` daría como resultado un GUID de directiva de `cdbbb86ce60342489bff371876e7f224`.  En este ejemplo, le gustaría ejecutar:

```powershell
Get-RetentionCompliancePolicy cdbbb86ce60342489bff371876e7f224 | FL Name
```

Una vez que conozca el nombre de la directiva, simplemente puede modificar la directiva de retención en el portal de cumplimiento de Microsoft Purview.  Tenga en cuenta que las directivas de retención se aplican normalmente a más de una ubicación, por lo que la modificación de la directiva afectará a todas las ubicaciones aplicadas, tanto inactivas como activas, que también pueden incluir ubicaciones distintas de Exchange.  Para obtener más información, consulte [Creación y configuración de directivas de retención](create-retention-policies.md).  

> [!IMPORTANT]
> Las directivas de retención con [el bloqueo de conservación](retention-preservation-lock.md) habilitado pueden ampliar el período de retención, pero no reducirse ni quitarse.

Si la intención es modificar el período de retención solo para buzones inactivos o solo buzones inactivos específicos, puede considerar la posibilidad de implementar [ámbitos de directiva adaptable](retention.md#adaptive-or-static-policy-scopes-for-retention), que se pueden usar para dirigirse individualmente a buzones específicos (o tipos de buzones, como buzones inactivos) mediante Azure AD y Exchange atributos y propiedades.

### <a name="change-the-duration-for-a-microsoft-365-retention-label"></a>Cambiar la duración de una etiqueta de retención de Microsoft 365

Al igual que con las directivas de retención, al modificar la duración de retención de una etiqueta de retención de Microsoft 365, primero debe identificar la directiva que publica la etiqueta que afecta al contenido del buzón inactivo mediante la ejecución `Get-RetentionCompliancePolicy` con el GUID asociado desde la `InPlaceHolds` propiedad en el buzón de Seguridad & Cumplimiento de PowerShell.

Asegúrese de quitar el prefijo y el sufijo del GUID al ejecutar este comando.  Por ejemplo, con la información de ejemplo anterior, tomaría el `InPlaceHolds` valor de `mbx6fe063689d404a5bb9940eed0f0bf5d2:1` y, a continuación, quitaría `mbx` y `:1` daría como resultado un GUID de directiva de `6fe063689d404a5bb9940eed0f0bf5d2`.  En este ejemplo, le gustaría ejecutar:

```powershell
Get-RetentionCompliancePolicy 6fe063689d404a5bb9940eed0f0bf5d2 | FL Name
```

Una vez que haya identificado la directiva, sabrá qué etiquetas se han publicado y su configuración.  Dado que las etiquetas se aplican a elementos individuales, en función del número de etiquetas publicadas con la directiva y su configuración, es posible que no pueda identificar directamente qué etiqueta está afectando al contenido.  

Un método que puede usar para identificar el contenido al que se aplica cada etiqueta es mediante [búsqueda de contenido](content-search.md).  Por ejemplo, con la información de ejemplo anterior, suponga que la directiva publica varias etiquetas, una de las cuales se denomina "HR-Content".  Con los [permisos correctos](microsoft-365-compliance-center-permissions.md), se puede ejecutar una búsqueda de contenido con el [comando De PowerShell New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch), especificando la dirección SMTP principal del buzón inactivo, con un punto (`.`) y el parámetro para omitir la `-AllowNotFoundExchangeLocationsEnabled $true` validación:

```powershell
New-ComplianceSearch -Name "MeganB Inactive Mailbox HR-Content Label Search" -ExchangeLocation .meganb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true -ContentMatchQuery "compliancetag=HR-Content"
```

Una vez creada la búsqueda, iniciará la búsqueda con el siguiente comando:

```powershell
Start-ComplianceSearch "MeganB Inactive Mailbox HR-Content Label Search"
```

Con este método, puede identificar qué etiquetas de la directiva de etiquetas identificadas se aplican al contenido del buzón inactivo para que pueda modificar sus períodos de retención. Tenga en cuenta que las etiquetas de retención se aplican normalmente a más de una ubicación, por lo que la modificación de una etiqueta afectará a todas las ubicaciones aplicadas y al contenido etiquetado, que también puede incluir ubicaciones y contenido distintos de Exchange. Para obtener más información, vea [Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md).

> [!NOTE]
> No se pueden modificar todos los tipos de etiquetas de retención.  En el caso de algunas etiquetas, es posible que solo pueda aumentar el tiempo de retención y, para otras, es posible que no pueda modificar el período de retención en absoluto.

### <a name="change-the-duration-for-an-ediscovery-hold"></a>Cambiar la duración de una suspensión de exhibición de documentos electrónicos

Las retenciones asociadas a los casos de eDiscovery son suspensiones indefinidas, lo que significa que no hay ninguna duración de suspensión que se pueda cambiar. Los elementos se mantienen para siempre o hasta que [se quita la suspensión](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold) o se cierra el caso.
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Debe usar Exchange Online PowerShell para cambiar la duración de retención de una suspensión por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, la duración de la suspensión se cambia a un período de tiempo ilimitado:
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la suspensión o se cambia la duración de la suspensión a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.

### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

In-Place las retenciones se han retirado y ya no se pueden modificar. Si un buzón inactivo tiene una In-Place suspensión aplicada, no puede cambiar la duración de la suspensión. Solo puede quitar el In-Place Suspensión, lo que dará lugar a la eliminación del buzón inactivo. Para obtener más información, vea [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md#remove-in-place-holds).
  
## <a name="more-information"></a>Más información

- **¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea.
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no se especifica ninguna duración para la suspensión colocada en el buzón inactivo, los elementos de la carpeta Elementos recuperables nunca se purgan (a menos que se cambie la duración de retención del buzón inactivo). 
    
- **¿Se sigue procesando una directiva de MRM Exchange en buzones inactivos?**  Si se aplicó una directiva de retención de MRM a un buzón antes de que se inactiva, las directivas de eliminación (etiquetas de retención de MRM configuradas con una acción **Eliminar** ) se seguirán procesando en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación de MRM se moverán a la carpeta Elementos recuperables cuando expire el período de retención. Esos elementos se purgan del buzón inactivo cuando expira la duración de retención. Si no se especifica una duración de retención para el buzón inactivo, los elementos de la carpeta Recuperar elementos se conservarán indefinidamente.

    Por el contrario, se omiten las directivas de archivo (etiquetas de retención de MRM configuradas con una acción **MoveToArchive** ) que se incluyen en la directiva de retención de MRM asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Se conservarán indefinidamente.
    > [!NOTE]
    > La aplicación de una directiva de retención de Exchange (la característica Administración de registros de mensajería o MRM en Exchange Online) no crea un buzón inactivo cuando se elimina la cuenta de usuario.

- **Al igual que con los buzones normales, Managed Folder Assistant (MFA) también procesa buzones inactivos.** En Exchange Online, MFA procesa buzones aproximadamente una vez cada siete días. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si muchos `InPlaceHolds` se colocan en un buzón inactivo, no se mostrarán todos los GUID de suspensión.** Puede ejecutar el siguiente comando para mostrar los GUID de todos los `InPlaceHolds` que se colocan en un buzón inactivo.
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
