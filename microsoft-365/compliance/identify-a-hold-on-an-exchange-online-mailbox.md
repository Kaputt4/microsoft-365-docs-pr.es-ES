---
title: Cómo identificar el tipo de retención en un buzón de Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Obtenga información sobre cómo identificar los diferentes tipos de retenciones que se pueden colocar en un buzón de correo de Microsoft 365. Estos tipos de retenciones incluyen la retención por juicio, las suspensiones de eDiscovery y las directivas de retención de Microsoft 365. También puede determinar si un usuario se ha excluido de una directiva de retención para toda la organización.
ms.openlocfilehash: 331fd37f48e42666ceb33a2a751b7d7a7a945e4b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352319"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Cómo identificar el tipo de retención en un buzón de Exchange Online

En este artículo se explica cómo identificar las suspensiones colocadas en buzones de Exchange online en Microsoft 365.

Microsoft 365 ofrece varias formas en que la organización puede evitar que el contenido de los buzones se elimine permanentemente. Esto permite a su organización conservar el contenido para cumplir con las normas de cumplimiento o durante las investigaciones legales y de otro tipo. Esta es una lista de las características de retención (también llamadas *suspensiones*) en Office 365:

- ** [Retención por juicio](create-a-litigation-hold.md):** Suspensiones que se aplican a los buzones de usuario en Exchange Online.

- ** [retención de exhibición](create-ediscovery-holds.md)** de documentos electrónicos: Suspensiones asociadas a un caso de exhibición de documentos electrónicos principal en el centro de seguridad y cumplimiento. las suspensiones de eDiscovery se pueden aplicar a los buzones de correo de los usuarios y al buzón correspondiente para los grupos de Microsoft 365 y Microsoft Teams.

- ** [Conservación local](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Suspensiones que se aplican a los buzones de usuario mediante el uso de la herramienta eDiscovery local & conservación en el centro de administración de Exchange en Exchange Online.

- ** [Directivas de retención de Microsoft 365](retention-policies.md):** Se puede configurar para conservar (o conservar y luego eliminar) el contenido de los buzones de usuario en Exchange Online y en el buzón de correo correspondiente para los grupos de Microsoft 365 y Microsoft Teams. También puede crear una directiva de retención para conservar las conversaciones de Skype empresarial, que se almacenan en los buzones de los usuarios.

  Hay dos tipos de directivas de retención de Microsoft 365 que se pueden asignar a los buzones de correo.

    - **Directivas de retención de ubicación específicas:** Estas son las directivas que se asignan a las ubicaciones de contenido de usuarios específicos. Use el cmdlet **Get-Mailbox** en Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones de correo específicos.

    - **Directivas de retención de toda la organización:** Estas son las directivas que se asignan a todas las ubicaciones de contenido de la organización. Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización.
    
  Para obtener más información, vea [aplicar una directiva de retención a toda la organización o a ubicaciones específicas](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations) .

- **[Etiquetas de retención de 365 de Microsoft](labels.md):** si un usuario aplica una etiqueta de retención de Microsoft 365 (una que esté configurada para conservar contenido o conservar y, a continuación, eliminar contenido) en *cualquier* carpeta o elemento del buzón, se aplica una retención al buzón como si el buzón estuviera en retención por juicio o asignado a una directiva de retención de Microsoft 365. Para obtener más información, consulte la sección [identificar buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) de este artículo.

Para administrar buzones en retención, es posible que tenga que identificar el tipo de retención que se coloca en un buzón de correo para que pueda realizar tareas como cambiar la duración de la retención, quitar la retención temporal o permanentemente o excluir un buzón de una directiva de retención de Microsoft 365. En estos casos, el primer paso es identificar el tipo de retención colocada en el buzón. Y debido a que se pueden colocar varias suspensiones (y distintos tipos de retenciones) en un único buzón, tiene que identificar todas las suspensiones colocadas en un buzón de correo si desea quitar o cambiar una suspensión.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Paso 1: obtener el GUID de las suspensiones colocadas en un buzón

Puede ejecutar los dos cmdlets siguientes en Exchange Online PowerShell para obtener el GUID de las suspensiones que se colocan en un buzón. Después de obtener un GUID, úselo para identificar la suspensión específica en el paso 2. Una retención por juicio no se identifica mediante un GUID. Las suspensiones por juicio están habilitadas o deshabilitadas para un buzón de correo.

- **Get-Mailbox:** Use este cmdlet para determinar si la retención por juicio está habilitada para un buzón y para obtener los GUID para las suspensiones de eDiscovery, las conservaciones locales y las directivas de retención de Microsoft 365 que se asignan específicamente a un buzón. El resultado de este cmdlet también indicará si un buzón se ha excluido explícitamente de una directiva de retención para toda la organización.

- **Get-OrganizationConfig:** Use este cmdlet para obtener los GUID de las directivas de retención de toda la organización.

Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

### <a name="get-mailbox"></a>Get-Mailbox

Ejecute el siguiente comando para obtener información sobre las suspensiones y las directivas de retención de Microsoft 365 aplicadas a un buzón de correo.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no todos ellos se muestran, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la tabla siguiente se describe cómo identificar distintos tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* cuando se ejecuta el cmdlet **Get-Mailbox** .


|Tipo de retención  |Valor de ejemplo  |Cómo identificar la retención  |
|---------|---------|---------|
|Retención por juicio     |    `True`     |     La retención por juicio está habilitada para un buzón de correo cuando la propiedad *LitigationHoldEnabled* se establece en `True` .    |
|conservación de exhibición de documentos electrónicos     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *propiedad InPlaceHolds* contiene el GUID de cualquier suspensión asociado con un caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. Puede decir que se trata de una retención de eDiscovery porque el GUID comienza por el `UniH` prefijo (lo que denota una retención unificada).      |
|Retención en contexto     |     `c0ba3ce811b6432a8751430937152491` <br/> o <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La propiedad *InPlaceHolds* contiene el GUID de la retención local que está colocada en el buzón. Puede decir que se trata de una conservación local porque el GUID no se inicia con un prefijo o se inicia con el `cld` prefijo.     |
|Directiva de retención de Microsoft 365 aplicada específicamente al buzón de correo     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> o <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La propiedad InPlaceHolds contiene los GUID de cualquier directiva de retención de ubicación específica que se aplique al buzón. Puede identificar las directivas de retención porque el GUID se inicia con el `mbx` o el `skp` prefijo. El `skp` prefijo indica que la Directiva de retención se aplica a las conversaciones de Skype empresarial en el buzón de correo del usuario.    |
|Excluido de una directiva de retención de Microsoft 365 para toda la organización     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Si un buzón se excluye de una directiva de retención de Microsoft 365 de toda la organización, el GUID de la Directiva de retención en la que se excluye el buzón se muestra en la propiedad InPlaceHolds y se identifica por el `-mbx` prefijo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Si la propiedad *InPlaceHolds* está vacía cuando ejecuta el cmdlet **Get-Mailbox** , es posible que haya una o varias directivas de retención de Microsoft 365 de toda la organización aplicadas al buzón. Ejecute el siguiente comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de Microsoft 365 para toda la organización.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no todos ellos se muestran, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la tabla siguiente se describen los distintos tipos de retenciones de toda la organización y cómo identificar cada tipo en función de los GUID contenidos en la propiedad *InPlaceHolds* cuando se ejecuta el cmdlet **Get-OrganizationConfig** .


|Tipo de retención  |Valor de ejemplo  |Descripción  |
|---------|---------|---------|
|Directivas de retención de 365 de Microsoft aplicadas a buzones de Exchange, carpetas públicas de Exchange y chats de Microsoft Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Las directivas de retención de toda la organización que se aplican a los buzones de Exchange, las carpetas públicas de Exchange y los chats de 1xN en Microsoft Teams se identifican mediante GUID que comienzan con el `mbx` prefijo. Nota 1xN chats se almacenan en el buzón de los participantes individuales del chat.      |
|Directiva de retención de Microsoft 365 aplicada a los mensajes de canal de Microsoft Teams y grupos de 365     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Las directivas de retención de toda la organización que se aplican a los grupos de Microsoft 365 y a los mensajes de canal en Microsoft Teams se identifican mediante GUID que comienzan con el `grp` prefijo. Nota los mensajes de canal se almacenan en el buzón de grupo asociado a un equipo de Microsoft.     |

Para obtener más información sobre las directivas de retención que se aplican a Microsoft Teams, consulte la sección "ubicación de Teams" [información general de las directivas de retención](create-retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Información sobre el formato del valor InPlaceHolds de las directivas de retención

Además del prefijo (MBX, SKP o GRP) que identifica un elemento de la propiedad InPlaceHolds como una directiva de retención de Microsoft 365, el valor también contiene un sufijo que identifica el tipo de acción de retención que está configurada para la Directiva. Por ejemplo, el sufijo de acción se resalta en negrita en los siguientes ejemplos:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

En la tabla siguiente se definen las tres posibles acciones de retención:

|Valor  |Descripción  |
|---------|---------|
|**1**     | Indica que la Directiva de retención está configurada para eliminar elementos. La Directiva no conserva los elementos.        |
|**segundo**    |    Indica que la Directiva de retención está configurada para contener elementos. La Directiva no elimina los elementos una vez que expira el período de retención.     |
|**3**     |   Indica que la Directiva de retención está configurada para mantener elementos y, a continuación, eliminarlos una vez que expire el período de retención.      |

Para obtener más información acerca de las acciones de retención, consulte la sección "conservar contenido durante un período de tiempo específico" en [información general sobre las directivas de retención](create-retention-policies.md#retaining-content-for-a-specific-period-of-time).
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Paso 2: usar el GUID para identificar la retención

Después de obtener el GUID de una retención que se aplica a un buzón, el siguiente paso consiste en usar ese GUID para identificar la retención. Las secciones siguientes muestran cómo identificar el nombre de la retención (y otra información) mediante el GUID de retención.

### <a name="ediscovery-holds"></a>suspensiones de eDiscovery

Ejecute los siguientes comandos en el PowerShell del centro de cumplimiento de & de seguridad para identificar una retención de exhibición de documentos electrónicos que se ha aplicado al buzón. Use el GUID (sin incluir el prefijo UniH) para la suspensión de exhibición de documentos electrónicos que identificó en el paso 1. El primer comando crea una variable que contiene información sobre la conservación. Esta variable se usa en los otros comandos. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos con el que está asociada la retención. El tercer comando muestra el nombre de la suspensión y una lista de los buzones a los que se aplica la retención.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Para conectarse a PowerShell del centro de cumplimiento de & de seguridad, vea [Connect to security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="in-place-holds"></a>Retenciones locales

Ejecute el siguiente comando en Exchange Online PowerShell para identificar la conservación local que se aplica al buzón. Use el GUID de la retención local que identificó en el paso 1. El comando muestra el nombre de la suspensión y una lista de los buzones a los que se aplica la retención.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Si el GUID de la retención local comienza con el `cld` prefijo, asegúrese de incluir el prefijo al ejecutar el comando anterior.

> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido de los buzones, estamos anunciando la retirada de conservaciones locales en el centro de administración de Exchange (EAC). A partir del 1 de julio de 2020, no podrá crear nuevas retenciones locales en Exchange Online. Pero todavía podrá administrar suspensiones locales en el EAC o mediante el cmdlet **set-MailboxSearch** en Exchange Online PowerShell. Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar suspensiones locales. Solo se quitarán en el EAC o mediante el cmdlet **Remove-MailboxSearch** . Para obtener más información acerca de la retirada de suspensiones locales, consulte [jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md).

### <a name="microsoft-365-retention-policies"></a>Directivas de retención de Microsoft 365

Ejecute el siguiente comando en el PowerShell del centro de cumplimiento de & de seguridad para identificar la Directiva de retención 365 de Microsoft (en toda la organización o específica) que se aplica al buzón. Use el GUID (sin incluir el prefijo MBX, SKP o GRP o el sufijo Action) que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificación de buzones en retención porque se ha aplicado una etiqueta de retención a una carpeta o elemento

Cuando un usuario aplica una etiqueta de retención configurada para conservar contenido o conservar y, a continuación, eliminar contenido en cualquier carpeta o elemento de su buzón de correo, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **true**. Cuando esto ocurre, se considera que el buzón está en espera, como si se hubiera puesto en retención por juicio o asignado a una directiva de retención de Microsoft 365. Cuando la propiedad *ComplianceTagHoldApplied* se establece en **true**, se pueden producir las siguientes acciones:

- Si se elimina el buzón o la cuenta de usuario del usuario, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md).
- No puede deshabilitar el buzón (el buzón principal o el buzón de archivo, si está habilitado).
- Es posible que los elementos del buzón de correo se conserven durante más tiempo de lo esperado. Esto se debe a que el buzón está en retención y, por lo tanto, no se eliminan elementos de forma permanente (purga).

Para ver el valor de la propiedad *ComplianceTagHoldApplied* , ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obtener más información acerca de las etiquetas de retención, vea [Overview of Microsoft 365 Retention Labels](labels.md).

## <a name="managing-mailboxes-on-delay-hold"></a>Administración de buzones de correo en suspensión de retardo

Una vez que se quita cualquier tipo de retención de un buzón, se aplica una *suspensión de retraso* . Esto significa que la eliminación real de la retención se retrasa durante 30 días para impedir que los datos se eliminen de forma permanente (purga) del buzón de correo. Esto proporciona a los administradores una oportunidad para buscar o recuperar los elementos del buzón que se purgarán después de que se quite la retención. Se coloca una retención retrasada en un buzón la próxima vez que el Asistente para carpeta administrada procesa el buzón y detecta que se ha quitado una retención. En concreto, se aplica una retención retrasada a un buzón de correo cuando el Asistente para carpeta administrada define una de las siguientes propiedades de buzón en **true**:

- **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la web) que se almacena en el buzón de correo de un usuario.

- **DelayReleaseHoldApplied:** Esta propiedad se aplica a contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos de nube generados por una aplicación de Microsoft se almacenan normalmente en una carpeta oculta en el buzón de un usuario.
 
 Cuando se coloca una retención en el buzón de correo (cuando cualquiera de las propiedades anteriores se establece en **true**), el buzón sigue considerándose en espera durante una duración de retención ilimitada, como si el buzón estuviera en retención por juicio. Transcurrido el plazo de 30 días, la retención en espera expira y Microsoft 365 automáticamente intentará quitar la retención retrasada (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **false**) para que se elimine la retención. Una vez que cualquiera de estas propiedades se establece en **false**, los elementos correspondientes marcados para la eliminación se purgan la próxima vez que el Asistente para carpetas administradas procesa el buzón de correo.

Para ver los valores de las propiedades DelayHoldApplied y DelayReleaseHoldApplied de un buzón de correo, ejecute el siguiente comando en Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para quitar la retención por retraso antes de que expire, puede ejecutar uno (o ambos) los siguientes comandos en Exchange Online PowerShell, en función de la propiedad que desee cambiar: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol retención legal en Exchange Online para usar los parámetros *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied* . 

Para quitar la retención retrasada en un buzón inactivo, ejecute uno de los siguientes comandos en Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> La mejor forma de especificar un buzón inactivo en el comando anterior es usar su nombre distintivo o el valor de GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 

Para obtener más información acerca del uso de estos parámetros para administrar suspensiones de retardo, consulte [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Tenga en cuenta lo siguiente cuando administre un buzón de correo en espera de retraso:

- Si la propiedad DelayHoldApplied o DelayReleaseHoldApplied se establece en **true** y se elimina un buzón (o la cuenta de usuario correspondiente), el buzón se convierte en un buzón inactivo. Esto se debe a que un buzón de correo se considera en espera si alguna de las propiedades se establece en **true**y la eliminación de un buzón de correo en retención da como resultado un buzón inactivo. Para eliminar un buzón y no convertirlo en un buzón inactivo, tiene que establecer ambas propiedades en **false**.

- Como se indicó anteriormente, un buzón se considera en espera durante una duración de retención ilimitada si la propiedad DelayHoldApplied o DelayReleaseHoldApplied está establecida en **true**. Sin embargo, esto no significa que se conserve *todo* el contenido del buzón. Depende del valor que se establezca en cada propiedad. Por ejemplo, supongamos que ambas propiedades se establecen en **true** porque se quitan las suspensiones del buzón de correo. A continuación, quita solo la retención retrasada que se aplica a los datos que no son de la nube de Outlook (mediante el parámetro *RemoveDelayReleaseHoldApplied* ). La próxima vez que el Asistente para carpetas administradas procese el buzón, se purgarán los elementos que no sean de Outlook marcados para su eliminación. No se purgarán todos los elementos de Outlook marcados para su eliminación porque la propiedad DelayHoldApplied sigue establecida en **true**. Lo contrario también será true: si DelayHoldApplied se establece en **false** y DelayReleaseHoldApplied se establece en **true**, se purgarán sólo los elementos de Outlook marcados para su eliminación.

## <a name="next-steps"></a>Pasos siguientes

Después de identificar las suspensiones que se aplican a un buzón de correo, puede realizar tareas como cambiar la duración de la retención, quitar temporalmente o permanentemente la retención o excluir un buzón inactivo de una directiva de retención de Microsoft 365. Para obtener más información acerca de cómo realizar tareas relacionadas con las suspensiones, consulte uno de los siguientes temas:

- Ejecute el comando de [ \<>buzón de usuario Set-RetentionCompliancePolicy-AddExchangeLocationException](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps) en el centro de seguridad & cumplimiento de PowerShell para excluir un buzón de una directiva de retención de Microsoft 365 de toda la organización. Este comando solo puede usarse para directivas de retención en las que el valor de la propiedad *ExchangeLocation* es igual a `All` .

- Ejecute el comando [set-Mailbox-ExcludeFromOrgHolds \< retenido sin prefijo o sufijo>](https://docs.microsoft.com/powershell/module/exchange/set-mailbox?view=exchange-ps) en Exchange Online PowerShell para excluir un buzón inactivo de una directiva de retención de Microsoft 365 de toda la organización.

- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md)

- [Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
