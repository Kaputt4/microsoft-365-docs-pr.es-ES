---
title: Eliminar un buzón inactivo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Cuando ya no necesite conservar el contenido de un buzón Microsoft 365 inactivo, puede eliminar permanentemente el buzón inactivo.
ms.openlocfilehash: 1f45e5ce3aca79e4f5abbc13442876ecbb22e90c
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66017950"
---
# <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Un buzón inactivo se usa para conservar el correo electrónico de un empleado anterior después de abandonar la organización. Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente. Además, es posible que varias retenciones se coloquen en un buzón inactivo. Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales. Además, Microsoft 365 retención podría aplicarse al buzón inactivo. Tiene que quitar todas las retenciones y directivas de retención de un buzón inactivo para eliminarlo. Después de quitar las directivas de retención y retención, el buzón inactivo se marca para su eliminación y se elimina de forma permanente después de procesarlo.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo de diferentes maneras para conservar el contenido del buzón de correo, anunciamos la retirada de las suspensiones de In-Place en el centro de administración de Exchange. Esto significa que debe usar las directivas de retención y retención por juicio para crear un buzón inactivo. A partir del 1 de julio de 2020 no podrá crear nuevas suspensiones de In-Place en Exchange Online. Pero seguirá siendo capaz de cambiar la duración de retención de un In-Place Suspensión colocado en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de la suspensión. Solo podrá eliminar un buzón inactivo quitando el In-Place Suspensión. Los buzones inactivos existentes que están en In-Place suspensión se conservarán hasta que se quite la suspensión. Para obtener más información sobre la retirada de In-Place retenciones, consulte [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md).
  
Consulte la sección [Más información](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Antes de eliminar un buzón inactivo

- Debe usar Exchange Online PowerShell para quitar las retenciones de un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC) ni el portal de cumplimiento de Microsoft Purview para estos procedimientos. Para obtener instrucciones paso a paso para usar Exchange Online PowerShell, consulte [Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo. Para obtener más información, consulte [Restauración de un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).

- Si quita la directiva de retención o retención de un buzón inactivo y el período de retención de buzón eliminado temporalmente para el buzón ha expirado, el buzón se eliminará permanentemente después de que expire el período de retención de buzón eliminado temporalmente durante 183 días. Para obtener más información sobre el período de retención de buzones eliminado temporalmente, consulte la sección [Más información](#more-information) de este artículo. Una vez que el buzón inactivo se elimina permanentemente, no se puede recuperar. Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón. Si desea reactivar un buzón inactivo, puede recuperarlo. Para obtener más información, consulte [Recuperación de un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).

- Para obtener más información acerca de los buzones inactivos, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md).

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Como se indicó anteriormente, se podría colocar una directiva de retención, suspensión In-Place o litigio en un buzón inactivo. El primer paso es identificar las retenciones de un buzón inactivo.
  
[Conectar para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)y, a continuación, ejecute el siguiente comando para mostrar la información de retención de todos los buzones inactivos de la organización.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una conservación local se coloca en un buzón inactivo, el GUID de la retención se muestra como el valor de la propiedad **InPlaceHolds**. Por ejemplo, los siguientes resultados para dos buzones inactivos muestran que se coloca una suspensión por juicio en Ann Beebe y que una directiva de retención y suspensión de In-Place se coloca en Pilar Pinilla.
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Si se colocan muchas directivas de retención o retención de In-Place en un buzón inactivo, no se mostrarán todos los GUID de suspensión de In-Place. Puede ejecutar el siguiente comando para mostrar todos los GUID de la propiedad InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Para obtener más información sobre la identificación de retenciones, vea [Cómo identificar el tipo de suspensión colocada en un buzón de correo](identify-a-hold-on-an-exchange-online-mailbox.md).

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Paso 2: Quitar una retención de un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es quitar las retenciones del buzón. Como se mencionó anteriormente, tiene que quitar todas las retenciones para eliminar de forma permanente un buzón inactivo.
  
### <a name="remove-a-litigation-hold"></a>Quitar una retención de litigios

Ejecute el siguiente comando de PowerShell para quitar una suspensión por juicio.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor Nombre distintivo o GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Quitar un buzón inactivo de una directiva de retención

El procedimiento para quitar un buzón inactivo de una directiva de retención de Microsoft 365 depende de si la directiva de retención asignada al buzón inactivo es explícita o de toda la organización:

- Directivas de retención de toda la organización asignadas a todos los buzones de la organización. Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización.

- Directivas de retención de ubicación específicas asignadas a buzones específicos. Se trata de directivas que se asignan a las ubicaciones de contenido de usuarios específicos. Use el cmdlet **Get-Mailbox -IncludeInactiveMailbox** en Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones inactivos específicos.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Eliminación de un buzón inactivo de una directiva de retención de toda la organización

Ejecute el siguiente comando de PowerShell para excluir un buzón inactivo de una directiva de retención de toda la organización.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Para obtener más información sobre cómo identificar las directivas de retención de toda la organización aplicadas a un buzón inactivo y obtener el GUID de una directiva de retención, consulte la sección "Get-OrganizationConfig" en [Cómo identificar el tipo de retención colocado en un buzón](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).

Como alternativa, puede ejecutar el siguiente comando de PowerShell para quitar el buzón inactivo de todas las directivas de toda la organización:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Quitar un buzón inactivo de una directiva de retención de ubicación específica

Use [Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell) para quitar un buzón inactivo de una directiva de retención explícita:

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -RemoveExchangeLocation <identity of inactive mailbox>
```

Para obtener más información sobre cómo identificar directivas de retención de ubicación específicas que se aplican a un buzón inactivo y obtener el GUID de una directiva de retención, vea la sección "Get-Mailbox" en [Cómo identificar el tipo de retención colocada en un buzón](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).

### <a name="remove-in-place-holds"></a>Quitar retenciones locales

 Hay dos maneras de quitar una retención local de un buzón inactivo:
  
- **Elimine el objeto In-Place Hold**. Si el buzón inactivo que desea eliminar permanentemente es el único buzón de origen para un In-Place Hold, puede eliminar el objeto In-Place Hold. 

    > [!NOTE]
    > Tiene que deshabilitar la retención antes de poder eliminar un objeto de retención local. Si intenta eliminar un objeto de retención local que tiene habilitada la retención, recibirá un mensaje de error. 
  
- **Quite el buzón inactivo como buzón de origen de un In-Place Suspensión**. Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local.

#### <a name="delete-an-in-place-hold"></a>Eliminación de una suspensión de In-Place

1. Cree una variable que contenga las propiedades de la retención local que quiera eliminar. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Deshabilite la retención en la retención local.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Elimine la retención local.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Quitar un buzón inactivo de un In-Place suspensión

Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC. Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local. Si un buzón inactivo no aparece en la página **Orígenes**, puede usar Exchange Online PowerShell para quitarlo de la suspensión de In-Place. 
  
1. Cree una variable que contenga las propiedades de la retención local colocada en el buzón inactivo. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > La propiedad *Sources* de la retención local identifica los buzones de origen por sus propiedades *LegacyExchangeDN*. Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado. También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP. 

3. Quite el buzón inactivo de la lista de buzones de origen en la variable. Asegúrese de usar la propiedad **LegacyExchangeDN** del buzón inactivo devuelto por el comando en el paso anterior. 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Por ejemplo, el siguiente comando quita el buzón inactivo para Pilar Pinilla.

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.

   ```powershell
   $InPlaceHold.Sources
   ```

5. Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Más información

- **Un buzón inactivo es un tipo de buzón eliminado temporalmente.** En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se pueden recuperar en un período de retención específico. En el caso de los buzones eliminados temporalmente que no están en espera, el buzón se puede recuperar en un plazo de 30 días. Un buzón inactivo (un buzón en espera antes de eliminarse) permanecerá en un estado de suspensión eliminado temporalmente hasta que se quite la suspensión. Después de quitar la suspensión de un buzón inactivo, el buzón ya no estará en estado inactivo. En su lugar, se eliminará temporalmente y permanecerá en Exchange Online durante 183 días a partir del día en que se quitó la suspensión y se podrá recuperar durante ese tiempo. Después de 183 días, un buzón eliminado temporalmente se marca para su eliminación permanente y no se puede recuperar.

- **¿Qué ocurre después de quitar la retención en un buzón inactivo?** El buzón se trata como otros buzones eliminados temporalmente y se marca para su eliminación permanente después de que expire el período de retención de buzón eliminado temporalmente durante 183 días. Este período de retención comienza en la fecha en que se quita la suspensión del buzón inactivo. La propiedad *InactiveMailboxRetireTime* se establece cuando el buzón pasa de estar inactivo (eliminado temporalmente en suspensión) a dejar de estar inactivo (eliminado temporalmente sin retenciones). En ese momento, la propiedad *InactiveMailboxRetireTime* se establece en la fecha actual en la que se produjo la transición. Hay un asistente que se ejecuta (denominado *asistente MailboxLifeCycle* ) que busca buzones que tengan establecida la propiedad *InactiveMailboxRetireTime* . Si "InactiveMailboxRetireTime + 183 días" es menor que la fecha actual, purgará el buzón.

- **¿Un buzón inactivo se elimina de forma permanente inmediatamente después de quitar la retención?** Un buzón anteriormente inactivo estará disponible en estado eliminado temporalmente durante 183 días. Después de 183 días, el buzón se marcará para su eliminación permanente.

- **¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?** Una vez que se quita una suspensión y el buzón inactivo se revierte a un buzón eliminado temporalmente, no se devolverá mediante el parámetro  *InactiveMailboxOnly*  con el cmdlet **Get-Mailbox** . Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**. Por ejemplo:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 16 de junio de 2020. La propiedad *WasInactiveMailbox* aparece como `True` porque anteriormente era un buzón inactivo. El buzón se eliminará permanentemente 183 días después del 30 de septiembre de 2020.
