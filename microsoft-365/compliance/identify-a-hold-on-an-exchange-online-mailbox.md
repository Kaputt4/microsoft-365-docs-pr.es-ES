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
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo identificar los diferentes tipos de retención que se pueden colocar en un buzón de Exchange Online en Microsoft 365.
ms.openlocfilehash: c0f5d11066169181b524632c7a1340c54f0061f0
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370340"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Cómo identificar el tipo de retención en un buzón de Exchange Online

En este artículo se explica cómo identificar las retenciones realizadas en buzones de Exchange Online en Microsoft 365.

Microsoft 365 ofrece varias formas de que su organización pueda impedir que el contenido del buzón se elimine permanentemente. Esto permite a su organización conservar el contenido para cumplir con las normativas de cumplimiento normativo o durante las investigaciones legales y otros tipos de investigaciones. Esta es una lista de las características de retención (también *denominadas retenciones)* en Office 365:

- **[Retención por juicio:](create-a-litigation-hold.md)** Retenciones que se aplican a los buzones de usuario en Exchange Online.

- **[Retención de exhibición de documentos electrónicos:](create-ediscovery-holds.md)** Retenciones asociadas a un caso de exhibición de documentos electrónicos principal en el centro de seguridad y cumplimiento. Las retenciones de exhibición de documentos electrónicos se pueden aplicar a los buzones de usuario y al buzón correspondiente para Grupos de Microsoft 365 y Microsoft Teams.

- **[Retención local:](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds)** Retenciones que se aplican a los buzones de usuario mediante la herramienta de retención In-Place eDiscovery & en el Centro de administración de Exchange en Exchange Online.

- Directivas de retención de **[Microsoft 365:](retention.md)** Se puede configurar para conservar (o retener y eliminar) contenido en buzones de usuario en Exchange Online y en el buzón correspondiente para Grupos de Microsoft 365 y Microsoft Teams. También puede crear una directiva de retención para conservar las conversaciones de Skype Empresarial, que se almacenan en buzones de usuario.

  Hay dos tipos de directivas de retención de Microsoft 365 que se pueden asignar a los buzones.

    - **Directivas de retención de ubicación específicas:** Se trata de directivas asignadas a las ubicaciones de contenido de usuarios específicos. Use el cmdlet **Get-Mailbox en** Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones específicos. Para obtener más información acerca de este tipo de directiva de retención, vea la sección Directiva A con inclusiones o [exclusiones](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) específicas de la documentación de la directiva de retención.

    - **Directivas de retención en toda la organización:** Se trata de directivas asignadas a todas las ubicaciones de contenido de la organización. Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización. Para obtener más información acerca de este tipo de directiva de retención, vea la sección Directiva A que se aplica a ubicaciones [enteras](create-retention-policies.md#a-policy-that-applies-to-entire-locations) de la documentación de la directiva de retención.

- **Etiquetas de retención de [Microsoft 365:](retention.md)** si un usuario aplica una etiqueta de retención de Microsoft 365 (una que está configurada para retener contenido o retener y, a continuación, eliminar contenido) a cualquier carpeta o elemento de su buzón, se coloca una retención en el buzón como si el buzón se hubiera colocado en retención por juicio o se asignara a una directiva de retención de Microsoft 365.  Para obtener más información, consulte la sección Identificación de buzones en suspensión porque se ha aplicado una etiqueta de retención [a](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) una carpeta o sección de elementos de este artículo.

Para administrar buzones en retención, es posible que tenga que identificar el tipo de retención que se coloca en un buzón para poder realizar tareas como cambiar la duración de retención, quitar temporal o permanentemente la suspensión o excluir un buzón de una directiva de retención de Microsoft 365. En estos casos, el primer paso es identificar el tipo de retención colocada en el buzón. Y como se pueden colocar varias retenciones (y diferentes tipos de retenciones) en un único buzón, debe identificar todas las retenciones realizadas en un buzón si desea quitar o cambiar una retención.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Paso 1: Obtener el GUID de las retenciones colocadas en un buzón

Puede ejecutar los dos cmdlets siguientes en Exchange Online PowerShell para obtener el GUID de las retenciones que se colocan en un buzón. Después de obtener un GUID, se usa para identificar la retención específica en el paso 2. Una retención por juicio no se identifica mediante un GUID. Las retenciones por juicio están habilitadas o deshabilitadas para un buzón.

- **Get-Mailbox:** Use este cmdlet para determinar si la retención por juicio está habilitada para un buzón de correo y para obtener los GUID para las retenciones de exhibición de documentos electrónicos, las retenciones de In-Place y las directivas de retención de Microsoft 365 asignadas específicamente a un buzón. El resultado de este cmdlet también indicará si un buzón se ha excluido explícitamente de una directiva de retención en toda la organización.

- **Get-OrganizationConfig:** Use este cmdlet para obtener los GUID de las directivas de retención de toda la organización.

Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Ejecute el siguiente comando para obtener información sobre las retenciones y las directivas de retención de Microsoft 365 aplicadas a un buzón.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos, puede ejecutar el comando para mostrar cada GUID en `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.

En la tabla siguiente se describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-Mailbox.**


|Tipo de retención  |Valor de ejemplo  |Cómo identificar la retención  |
|---------|---------|---------|
|Retención por juicio     |    `True`     |     La retención por juicio está habilitada para un buzón cuando la *propiedad LitigationHoldEnabled* está establecida en `True` .    |
|Retención de exhibición de documentos electrónicos     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *propiedad InPlaceHolds* contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. Puede saber que se trata de una retención de exhibición de documentos electrónicos porque el GUID comienza con el `UniH` prefijo (que indica una retención unificada).      |
|Retención en contexto     |     `c0ba3ce811b6432a8751430937152491` <br/> o <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La *propiedad InPlaceHolds* contiene el GUID de la In-Place que se coloca en el buzón. Puede saber que se trata de una retención In-Place porque el GUID no empieza con un prefijo o comienza con el `cld` prefijo.     |
|Directiva de retención de Microsoft 365 aplicada específicamente al buzón     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> o <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La propiedad InPlaceHolds contiene GUID de cualquier directiva de retención de ubicación específica que se aplica al buzón. Puede identificar directivas de retención porque el GUID comienza por `mbx` el prefijo o por el `skp` prefijo. El prefijo indica que la directiva de retención se aplica a las conversaciones de `skp` Skype Empresarial en el buzón del usuario.    |
|Excluido de una directiva de retención de Microsoft 365 en toda la organización     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Si se excluye un buzón de una directiva de retención de Microsoft 365 en toda la organización, el GUID de la directiva de retención de la que se excluye el buzón se muestra en la propiedad InPlaceHolds y se identifica mediante el `-mbx` prefijo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Si la *propiedad InPlaceHolds* está vacía al ejecutar el cmdlet **Get-Mailbox,** es posible que se apliquen al buzón una o varias directivas de retención de Microsoft 365 en toda la organización. Ejecute el siguiente comando en Exchange Online PowerShell para obtener una lista de GUID para las directivas de retención de Microsoft 365 en toda la organización.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos, puede ejecutar el comando para mostrar cada GUID en `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.

En la tabla siguiente se describen los distintos tipos de retenciones de toda la organización y cómo identificar cada tipo en función de los GUID contenidos en la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-OrganizationConfig.**


|Tipo de retención  |Valor de ejemplo  |Descripción  |
|---------|---------|---------|
|Directivas de retención de Microsoft 365 aplicadas a buzones de Exchange, carpetas públicas de Exchange y chats de Teams    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Las directivas de retención de toda la organización aplicadas a buzones de Exchange, carpetas públicas de Exchange y chats 1xN en Microsoft Teams se identifican mediante GUID que comienzan con el `mbx` prefijo. Nota: los chats 1xN se almacenan en el buzón de los participantes individuales del chat.      |
|Directiva de retención de Microsoft 365 aplicada a los mensajes de canal de Grupos de Microsoft 365 y Teams     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Las directivas de retención de toda la organización aplicadas a grupos de Microsoft 365 y mensajes de canal en Microsoft Teams se identifican mediante GUID que comienzan con el `grp` prefijo. Tenga en cuenta que los mensajes de canal se almacenan en el buzón de grupo que está asociado con Un equipo de Microsoft.     |

Para obtener más información acerca de las directivas de retención aplicadas a Microsoft Teams, vea [Más información sobre las directivas de retención para Microsoft Teams.](retention-policies-teams.md)

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Descripción del formato del valor InPlaceHolds para las directivas de retención

Además del prefijo (mbx, skp o grp) que identifica un elemento de la propiedad InPlaceHolds como una directiva de retención de Microsoft 365, el valor también contiene un sufijo que identifica el tipo de acción de retención que está configurada para la directiva. Por ejemplo, el sufijo de acción se resalta en negrita en los siguientes ejemplos:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

En la tabla siguiente se definen las tres acciones de retención posibles:

|Valor  |Descripción  |
|---------|---------|
|**1**     | Indica que la directiva de retención está configurada para eliminar elementos. La directiva no conserva elementos.        |
|**2**    |    Indica que la directiva de retención está configurada para contener elementos. La directiva no elimina elementos después de que expire el período de retención.     |
|**3**     |   Indica que la directiva de retención está configurada para retener elementos y, a continuación, eliminarlos después de que expire el período de retención.      |

Para obtener más información acerca de las acciones de retención, vea la sección Retener [contenido durante un período de tiempo](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) específico.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Paso 2: Usar el GUID para identificar la retención

Después de obtener el GUID de una retención que se aplica a un buzón de correo, el siguiente paso es usar ese GUID para identificar la retención. En las secciones siguientes se muestra cómo identificar el nombre de la retención (y otra información) mediante el GUID de retención.

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery

Ejecute los siguientes comandos en PowerShell del Centro de seguridad & cumplimiento para identificar una retención de exhibición de documentos electrónicos que se aplica al buzón. Use el GUID (sin incluir el prefijo UniH) para la retención de exhibición de documentos electrónicos que identificó en el paso 1. El primer comando crea una variable que contiene información sobre la retención. Esta variable se usa en los demás comandos. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos al que está asociada la retención. El tercer comando muestra el nombre de la retención y una lista de los buzones a los que se aplica la retención.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

Para conectarse a PowerShell & Centro de seguridad y cumplimiento, consulte Conectarse a  [PowerShell del Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)de & seguridad y cumplimiento.

### <a name="in-place-holds"></a>Retenciones locales

Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención In-Place que se aplica al buzón. Use el GUID para la retención In-Place que identificó en el paso 1. El comando muestra el nombre de la retención y una lista de los buzones a los que se aplica la retención.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Si el GUID de la retención In-Place comienza por el prefijo, asegúrese de incluir el prefijo al `cld` ejecutar el comando anterior.

> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de In-Place Holds en el Centro de administración de Exchange (EAC). A partir del 1 de julio de 2020 no podrá crear nuevas retenciones de In-Place en Exchange Online. Pero aún podrá administrar las retenciones de In-Place en el EAC o mediante el cmdlet **Set-MailboxSearch** en Exchange Online PowerShell. Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar las In-Place locales. Solo los quitará en el EAC o con el cmdlet **Remove-MailboxSearch.** Para obtener más información acerca de la retirada de In-Place de documentos electrónicos, vea Retirada de herramientas de exhibición de [documentos electrónicos heredadas.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Directivas de retención de Microsoft 365

Ejecute el siguiente comando en PowerShell del Centro de seguridad & Cumplimiento para identificar la directiva de retención de Microsoft 365 (ubicación específica o en toda la organización) que se aplica al buzón. Use el GUID (sin incluir el prefijo mbx, skp o grp o el sufijo de acción) que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificación de buzones de correo en suspensión porque se ha aplicado una etiqueta de retención a una carpeta o elemento

Siempre que un usuario aplica una etiqueta de retención que está configurada para retener contenido o retener y, a continuación, eliminar contenido en cualquier carpeta o elemento de su buzón, la propiedad de *buzón ComplianceTagHoldApplied* se establece en **True**. Cuando esto sucede, se considera que el buzón está en suspensión, como si se hubiera colocado en retención por juicio o se hubiera asignado a una directiva de retención de Microsoft 365. Cuando la *propiedad ComplianceTagHoldApplied* se establece en **True**, pueden ocurrir lo siguiente:

- Si se elimina el buzón o la cuenta de usuario del usuario, el buzón se convierte en [un buzón inactivo.](inactive-mailboxes-in-office-365.md)
- No puede deshabilitar el buzón de correo (ya sea el buzón principal o el buzón de archivo, si está habilitado).
- Los elementos del buzón pueden conservarse durante más tiempo del esperado. Esto se debe a que el buzón está en retención y, por lo tanto, no se eliminan permanentemente elementos (purgados).

Para ver el valor de la *propiedad ComplianceTagHoldApplied,* ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obtener más información acerca de las etiquetas de retención, vea [etiquetas de retención.](retention.md#retention-labels)

## <a name="managing-mailboxes-on-delay-hold"></a>Administración de buzones en retención retrasada

Después de quitar cualquier tipo de retención de un buzón, se aplica *una retención* retrasada. Esto significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente (se purguen) del buzón. Esto ofrece a los administradores la oportunidad de buscar o recuperar elementos del buzón que se purgarán después de quitar una retención. La próxima vez que el Asistente para carpetas administradas procese el buzón y detecte que se quitó una retención, se coloca una retención retrasada en un buzón. En concreto, se aplica una retención retrasada a un buzón cuando el Asistente para carpeta administrada establece una de las siguientes propiedades de buzón en **True:**

- **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la Web) que se almacena en el buzón de un usuario.

- **DelayReleaseHoldApplied:** Esta propiedad se aplica al contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos en la nube generados por una aplicación de Microsoft normalmente se almacenan en una carpeta oculta en el buzón de un usuario.
 
 Cuando se coloca una retención retrasada en el buzón (cuando cualquiera de las propiedades anteriores se establece en **True**), el buzón aún se considera que está en suspensión durante una duración de retención ilimitada, como si el buzón se encontrara en retención por juicio. Después de 30 días, la retención por retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **False)** para que se quite la retención. Después de establecer cualquiera de estas propiedades en **False**, los elementos correspondientes marcados para su eliminación se purgan la próxima vez que el Asistente para carpeta administrada procese el buzón.

Para ver los valores de las propiedades DelayHoldApplied y DelayReleaseHoldApplied para un buzón, ejecute el siguiente comando en Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para quitar la retención de retraso antes de que expire, puede ejecutar uno (o ambos) los siguientes comandos en Exchange Online PowerShell, en función de la propiedad que desee cambiar: 
 
```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien
 
```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol de retención legal en Exchange Online para usar los parámetros *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied.* 

Para quitar la retención retrasada en un buzón inactivo, ejecute uno de los siguientes comandos en Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> La mejor manera de especificar un buzón inactivo en el comando anterior es usar su nombre distintivo o el valor GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 

Para obtener más información acerca del uso de estos parámetros para administrar retenciones retrasadas, vea [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

Tenga en cuenta lo siguiente al administrar un buzón en retención con retraso:

- Si la propiedad DelayHoldApplied o DelayReleaseHoldApplied se establece en **True** y se elimina un buzón (o la cuenta de usuario correspondiente), el buzón se convierte en un buzón inactivo. Esto se debe a que se considera que un buzón está en retención si cualquiera de las propiedades está establecida en **True** y, al eliminar un buzón en retención, se produce un buzón inactivo. Para eliminar un buzón y no convertirlo en un buzón inactivo, debe establecer ambas propiedades en **False**.

- Como se indicó anteriormente, se considera que un buzón está en retención durante una duración de retención ilimitada si la propiedad DelayHoldApplied o DelayReleaseHoldApplied se establece en **True**. Sin embargo, eso no significa que *todo* el contenido del buzón se conserve. Depende del valor que se establezca en cada propiedad. Por ejemplo, supongamos que ambas propiedades se establecen en **True** porque las retenciones se quitan del buzón. A continuación, solo se quita la retención retrasada que se aplica a datos que no son de la nube de Outlook (mediante el parámetro *RemoveDelayReleaseHoldApplied).* La próxima vez que el Asistente para carpeta administrada procese el buzón, se purgarán los elementos que no sean de Outlook marcados para su eliminación. Los elementos de Outlook marcados para su eliminación no se purgarán porque la propiedad DelayHoldApplied aún está establecida en **True**. Lo contrario también sería verdadero: si DelayHoldApplied se establece en **False** y DelayReleaseHoldApplied se establece en **True**, solo se purgarán los elementos de Outlook marcados para su eliminación.

## <a name="next-steps"></a>Pasos siguientes

Después de identificar las retenciones que se aplican a un buzón de correo, puede realizar tareas como cambiar la duración de la retención, quitar temporal o permanentemente la suspensión o excluir un buzón inactivo de una directiva de retención de Microsoft 365. Para obtener más información acerca de cómo realizar tareas relacionadas con las retenciones, consulte uno de los siguientes temas:

- Ejecute el comando [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) en PowerShell del Centro de seguridad & cumplimiento para excluir un buzón de una directiva de retención de Microsoft 365 en toda la organización. Este comando solo se puede usar para directivas de retención donde el valor de la propiedad *ExchangeLocation* es igual a `All` .

- Ejecute el [comando Set-Mailbox \<hold GUID without prefix or suffix> -ExcludeFromOrgHolds](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) en Exchange Online PowerShell para excluir un buzón inactivo de una directiva de retención de Microsoft 365 en toda la organización.

- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md)

- [Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
