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
description: Obtenga información sobre cómo identificar los diferentes tipos de retención que se pueden colocar en un buzón Exchange Online en Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917540"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Cómo identificar el tipo de retención en un buzón de Exchange Online

En este artículo se explica cómo identificar las retenciones realizadas en Exchange Online buzones de correo en Microsoft 365.

Microsoft 365 ofrece varias formas de que su organización pueda impedir que el contenido del buzón se elimine permanentemente. Esto permite a la organización conservar contenido para cumplir con las normativas de cumplimiento o durante las investigaciones legales y de otro tipo. Esta es una lista de las características de retención (también *denominadas retenciones)* en Office 365:

- **[Retención por juicio](create-a-litigation-hold.md):** Retenciones que se aplican a los buzones de usuario en Exchange Online.

- **[Retención de exhibición de documentos electrónicos](create-ediscovery-holds.md):** Retenciones asociadas a un caso de exhibición de documentos electrónicos principales en el centro de seguridad y cumplimiento. Las retenciones de exhibición de documentos electrónicos se pueden aplicar a los buzones de usuario y al buzón correspondiente para Microsoft 365 grupos y Microsoft Teams.

- **[Retención local:](/Exchange/security-and-compliance/create-or-remove-in-place-holds)** Retenciones que se aplican a los buzones de usuario mediante la herramienta de retención In-Place eDiscovery & en el Centro de administración de Exchange en Exchange Online. 

   > [!NOTE]
   > In-Place las retenciones se han retirado y ya no puede crear In-Place o aplicarlas a buzones. Sin embargo, In-Place las retenciones de correo aún se pueden aplicar a los buzones de su organización, por lo que se incluyen en este artículo. Para obtener más información, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center).

- **[Microsoft 365 de retención:](retention.md)** Se puede configurar para conservar (o conservar y eliminar) contenido en buzones de usuario en Exchange Online y en el buzón correspondiente para grupos de Microsoft 365 y Microsoft Teams. También puede crear una directiva de retención para conservar Skype Empresarial conversaciones, que se almacenan en buzones de usuario.

  Hay dos tipos de directivas Microsoft 365 de retención que se pueden asignar a los buzones.

    - **Directivas de retención de ubicaciones específicas:** Se trata de directivas que se asignan a las ubicaciones de contenido de usuarios específicos. Use el cmdlet **Get-Mailbox** en Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones específicos. Para obtener más información acerca de este tipo de directiva de retención, vea la sección Directiva A con inclusiones o [exclusiones](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) específicas de la documentación de la directiva de retención.

    - **Directivas de retención en toda la organización:** Se trata de directivas asignadas a todas las ubicaciones de contenido de la organización. Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización. Para obtener más información acerca de este tipo de directiva de retención, vea la sección Directiva A que se aplica a ubicaciones [enteras](create-retention-policies.md#a-policy-that-applies-to-entire-locations) de la documentación de la directiva de retención.

- **[Microsoft 365](retention.md)** etiquetas de retención: si un usuario aplica una etiqueta de retención de Microsoft 365 (una que está  configurada para retener contenido o retener y, a continuación, eliminar contenido) a cualquier carpeta o elemento de su buzón, se coloca una retención en el buzón como si el buzón se colocara en retención por juicio o se asignara a una directiva de retención de Microsoft 365. Para obtener más información, vea la sección Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una [carpeta](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) o elemento en este artículo.

Para administrar buzones en espera, es posible que tenga que identificar el tipo de retención que se coloca en un buzón para poder realizar tareas como cambiar la duración de retención, quitar temporal o permanentemente la retención o excluir un buzón de una directiva de retención de Microsoft 365. En estos casos, el primer paso consiste en identificar el tipo de retención que se coloca en el buzón. Y como se pueden colocar varias retenciones (y diferentes tipos de retenciones) en un único buzón, debe identificar todas las retenciones realizadas en un buzón si desea quitar o cambiar una retención.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Paso 1: Obtener el GUID de las retenciones colocadas en un buzón

Puede ejecutar los dos cmdlets siguientes en Exchange Online PowerShell para obtener el GUID de las retenciones que se colocan en un buzón. Después de obtener un GUID, se usa para identificar la retención específica en el paso 2. Un GUID no identifica una retención por juicio. Las retenciones por juicio están habilitadas o deshabilitadas para un buzón.

- **Get-Mailbox:** Use este cmdlet para determinar si la retención por juicio está habilitada para un buzón de correo y para obtener los GUID para las retenciones de exhibición de documentos electrónicos, las retenciones de In-Place y las directivas de retención de Microsoft 365 asignadas específicamente a un buzón. El resultado de este cmdlet también indicará si un buzón se ha excluido explícitamente de una directiva de retención en toda la organización.

- **Get-OrganizationConfig:** Use este cmdlet para obtener los GUID de directivas de retención de toda la organización.

Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Ejecute el siguiente comando para obtener información sobre las retenciones y Microsoft 365 directivas de retención aplicadas a un buzón.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos ellos, puede ejecutar el comando para mostrar cada GUID en `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.

En la tabla siguiente se describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-Mailbox.**

|Tipo de retención  |Valor de ejemplo  |Cómo identificar la retención  |
|---------|---------|---------|
|Retención por juicio     |    `True`     |     La retención por juicio está habilitada para un buzón cuando la *propiedad LitigationHoldEnabled* está establecida en `True` .    |
|Retención de exhibición de documentos electrónicos     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   La *propiedad InPlaceHolds* contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. Puede indicar que se trata de una retención de exhibición de documentos electrónicos porque el GUID comienza por el `UniH` prefijo (que indica una retención unificada).      |
|Retención en contexto     |     `c0ba3ce811b6432a8751430937152491` <br/> o <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     La *propiedad InPlaceHolds* contiene el GUID de la In-Place que se coloca en el buzón. Puede saber que se trata de una retención In-Place porque el GUID no empieza con un prefijo o empieza por el `cld` prefijo.     |
|Microsoft 365 directiva de retención específicamente aplicada al buzón     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> o <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     La propiedad InPlaceHolds contiene GUID de cualquier directiva de retención de ubicación específica que se aplique al buzón. Puede identificar directivas de retención porque el GUID comienza por el `mbx` prefijo `skp` o. El prefijo indica que la directiva de retención se aplica a `skp` Skype Empresarial conversaciones en el buzón del usuario.    |
|Excluido de una directiva de retención de Microsoft 365 toda la organización     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Si se excluye un buzón de una directiva de retención de Microsoft 365 en toda la organización, el GUID de la directiva de retención de la que se excluye el buzón se muestra en la propiedad InPlaceHolds y se identifica mediante el `-mbx` prefijo.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Si la *propiedad InPlaceHolds* está vacía al ejecutar el cmdlet **Get-Mailbox,** puede haber una o más directivas de retención de Microsoft 365 toda la organización aplicadas al buzón. Ejecute el siguiente comando en Exchange Online PowerShell para obtener una lista de GUID para las directivas de retención Microsoft 365 organización.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos ellos, puede ejecutar el comando para mostrar cada GUID en `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` una línea independiente.

En la tabla siguiente se describen los diferentes tipos de retenciones de toda la organización y cómo identificar cada tipo en función de los GUID contenidos en la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-OrganizationConfig.**

|Tipo de retención  |Valor de ejemplo  |Descripción  |
|---------|---------|---------|
|Microsoft 365 directivas de retención aplicadas Exchange buzones de correo, Exchange carpetas públicas y Teams chats    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Las directivas de retención de toda la organización aplicadas Exchange buzones de correo, Exchange carpetas públicas y chats de 1xN en Microsoft Teams se identifican mediante GUID que comienzan con el `mbx` prefijo. Nota Los chats 1xN se almacenan en el buzón de los participantes de chat individuales.      |
|Microsoft 365 directiva de retención aplicada a Microsoft 365 grupos y Teams mensajes de canal     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Las directivas de retención de toda la organización aplicadas Microsoft 365 grupos y mensajes de canal en Microsoft Teams se identifican mediante GUID que comienzan con el `grp` prefijo. Nota Los mensajes de canal se almacenan en el buzón de grupo asociado a un equipo de Microsoft.     |

Para obtener más información acerca de las directivas de retención aplicadas Microsoft Teams, vea [Learn about retention policies for Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Descripción del formato del valor InPlaceHolds para las directivas de retención

Además del prefijo (mbx, skp o grp) que identifica un elemento de la propiedad InPlaceHolds como una directiva de retención de Microsoft 365, el valor también contiene un sufijo que identifica el tipo de acción de retención configurada para la directiva. Por ejemplo, el sufijo de acción se resalta en negrita en los ejemplos siguientes:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

En la tabla siguiente se definen las tres posibles acciones de retención:

|Valor  |Descripción  |
|---------|---------|
|**1**     | Indica que la directiva de retención está configurada para eliminar elementos. La directiva no retiene elementos.        |
|**2**    |    Indica que la directiva de retención está configurada para contener elementos. La directiva no elimina elementos después de que expire el período de retención.     |
|**3**     |   Indica que la directiva de retención está configurada para contener elementos y, a continuación, eliminarlos después de que expire el período de retención.      |

Para obtener más información acerca de las acciones de retención, consulte la sección [Retener contenido durante un período de tiempo](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) específico.
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Paso 2: Usar el GUID para identificar la retención

Después de obtener el GUID de una retención que se aplica a un buzón, el siguiente paso es usar ese GUID para identificar la retención. En las secciones siguientes se muestra cómo identificar el nombre de la retención (y otra información) mediante el GUID de retención.

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery

Ejecute los siguientes comandos en PowerShell del Centro de seguridad & cumplimiento para identificar una retención de exhibición de documentos electrónicos que se aplica al buzón. Use el GUID (sin incluir el prefijo UniH) para la retención de exhibición de documentos electrónicos que identificó en el paso 1. 

Para conectarse a PowerShell & Centro de seguridad y cumplimiento, vea [Conectar a Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

El primer comando crea una variable que contiene información sobre la retención. Esta variable se usa en los demás comandos. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos al que está asociada la retención. El tercer comando muestra el nombre de la retención y una lista de los buzones a los que se aplica la retención.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>Retenciones locales

Ejecute el siguiente comando en Exchange Online PowerShell para identificar la retención In-Place que se aplica al buzón. Use el GUID para la retención In-Place que identificó en el paso 1. El comando muestra el nombre de la retención y una lista de los buzones a los que se aplica la retención.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Si el GUID de la In-Place hold comienza por el prefijo, asegúrese de incluir `cld` el prefijo al ejecutar el comando anterior.

> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de las retenciones de In-Place en el Centro de administración de Exchange (EAC). A partir del 1 de julio de 2020 no podrá crear nuevas retenciones In-Place en Exchange Online. Pero aún podrá administrar las In-Place en el EAC o mediante el cmdlet **Set-MailboxSearch** en Exchange Online PowerShell. Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar las In-Place retenciones. Solo se quitarán en el EAC o mediante el cmdlet **Remove-MailboxSearch.** Para obtener más información acerca de la retirada de In-Place, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 de retención

Ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento para identificar la directiva de retención de Microsoft 365 (ubicación específica o de toda la organización) que se aplica al buzón. Use el GUID (sin incluir el prefijo mbx, skp o grp o el sufijo de acción) que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento

Cada vez que un usuario aplica una etiqueta de retención configurada para retener contenido o retener y, a continuación, eliminar contenido a cualquier carpeta o elemento de su buzón, la propiedad de buzón *ComplianceTagHoldApplied* se establece en **True**. Cuando esto sucede, se considera que el buzón está en espera, como si se hubiera colocado en retención por juicio o se hubiera asignado a una directiva Microsoft 365 retención. Cuando la *propiedad ComplianceTagHoldApplied* se establece en **True**, pueden ocurrir lo siguiente:

- Si se elimina el buzón o la cuenta de usuario del usuario, el buzón se convierte en [un buzón inactivo.](inactive-mailboxes-in-office-365.md)
- No puede deshabilitar el buzón (ya sea el buzón principal o el buzón de archivo, si está habilitado).
- Los elementos del buzón pueden conservarse más tiempo del esperado. Esto se debe a que el buzón está en espera y, por lo tanto, no se elimina ningún elemento de forma permanente (purgado).

Para ver el valor de la *propiedad ComplianceTagHoldApplied,* ejecute el siguiente comando en Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Para obtener más información acerca de las etiquetas de retención, vea [retention labels](retention.md#retention-labels).

## <a name="managing-mailboxes-on-delay-hold"></a>Administración de buzones en retención retrasada

Después de quitar cualquier tipo de retención de un buzón, se aplica *una retención retrasada.* Esto significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente (se purguen) del buzón. Esto ofrece a los administradores la oportunidad de buscar o recuperar elementos de buzón que se purgarán después de quitar una retención. La próxima vez que el Asistente para carpetas administradas procese el buzón y detecte que se ha quitado una retención, se coloca una retención en un buzón. En concreto, se aplica una retención de retraso a un buzón cuando el Asistente para carpetas administradas establece una de las siguientes propiedades de buzón en **True**:

- **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la web) que se almacena en el buzón de un usuario.

- **DelayReleaseHoldApplied:** Esta propiedad se aplica al contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos en la nube generados por una aplicación microsoft normalmente se almacenan en una carpeta oculta en el buzón de un usuario.

Cuando se coloca una retención de retraso en el buzón (cuando cualquiera de las propiedades anteriores se establece en **True),** el buzón se considera aún en espera durante una duración de retención ilimitada, como si el buzón se encontraba en retención por juicio. Después de 30 días, la retención de retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **False)** para que se quite la retención. Después de establecer cualquiera de estas propiedades en **False**, los elementos correspondientes marcados para la eliminación se purgan la próxima vez que el Asistente para carpetas administradas procese el buzón.

Para ver los valores de las propiedades DelayHoldApplied y DelayReleaseHoldApplied para un buzón, ejecute el siguiente comando en Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para quitar la retención de retraso antes de que expire, puede ejecutar uno (o ambos) los siguientes comandos en Exchange Online PowerShell, en función de la propiedad que desee cambiar:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien:

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol Retención legal en Exchange Online para usar los parámetros *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied.* 

Para quitar la retención de retraso en un buzón inactivo, ejecute uno de los siguientes comandos en Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

O bien:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> La mejor manera de especificar un buzón inactivo en el comando anterior es usar su nombre distintivo o su Exchange GUID. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 

Para obtener más información acerca del uso de estos parámetros para administrar retenciones de retraso, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Tenga en cuenta lo siguiente al administrar un buzón en espera de retraso:

- Si la propiedad DelayHoldApplied o DelayReleaseHoldApplied se establece en **True** y se elimina un buzón (o la cuenta de usuario correspondiente), el buzón se convierte en un buzón inactivo. Esto se debe a que se considera que un buzón está en espera si cualquiera de las propiedades está establecida en **True** y la eliminación de un buzón en espera da como resultado un buzón inactivo. Para eliminar un buzón y no convertirlo en un buzón inactivo, debe establecer ambas propiedades en **False**.

- Como se indicó anteriormente, se considera que un buzón está en espera durante una duración de retención ilimitada si la propiedad DelayHoldApplied o DelayReleaseHoldApplied está establecida en **True**. Sin embargo, eso no significa que *se* conserve todo el contenido del buzón. Depende del valor que se establezca en cada propiedad. Por ejemplo, supongamos que ambas propiedades se establecen en **True** porque las retenciones se quitan del buzón. A continuación, solo se quita la retención de retraso que se aplica a datos de nube que no Outlook (mediante el parámetro *RemoveDelayReleaseHoldApplied).* La próxima vez que el Asistente para carpetas administradas procese el buzón, se purgarán los elementos no Outlook marcados para la eliminación. Los Outlook marcados para la eliminación no se purgarán porque la propiedad DelayHoldApplied todavía está establecida en **True**. Lo contrario también sería cierto: si DelayHoldApplied se establece en **False** y DelayReleaseHoldApplied se establece en **True**, solo se purgarán Outlook elementos marcados para la eliminación.

## <a name="next-steps"></a>Pasos siguientes

Después de identificar las retenciones que se aplican a un buzón de correo, puede realizar tareas como cambiar la duración de la retención, quitar temporal o permanentemente la retención o excluir un buzón inactivo de una directiva de retención de Microsoft 365. Para obtener más información acerca de cómo realizar tareas relacionadas con las retenciones, vea uno de los temas siguientes:

- Ejecute el comando [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) en PowerShell del Centro de seguridad & cumplimiento para excluir un buzón de una directiva de retención Microsoft 365 toda la organización. Este comando solo se puede usar para directivas de retención donde el valor de la *propiedad ExchangeLocation* es igual `All` a .

- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md)

- [Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)