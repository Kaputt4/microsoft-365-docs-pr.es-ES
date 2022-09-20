---
title: Cómo identificar la suspensión en un buzón de Exchange Online
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Obtenga información sobre cómo identificar los diferentes tipos de retención que se pueden colocar en un buzón de Exchange Online en Microsoft 365.
ms.openlocfilehash: 9c18d2bc99fae93ae3b288475661872e5e6d49d9
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67822713"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Cómo identificar el tipo de retención en un buzón de Exchange Online

En este artículo se explica cómo identificar las retenciones colocadas en Exchange Online buzones de Correo de Microsoft 365.

Microsoft 365 ofrece varias maneras de que su organización pueda evitar que el contenido del buzón de correo se elimine permanentemente. Esto permite a su organización conservar el contenido para cumplir con las regulaciones de cumplimiento o durante los tipos legales y otros tipos de investigaciones. Esta es una lista de las características de retención (también *denominadas retenciones*) en Office 365:

- **[Suspensión por juicio](create-a-litigation-hold.md):** Retenciones que se aplican a los buzones de usuario en Exchange Online.

- **[Suspensión de eDiscovery](create-ediscovery-holds.md):** Retenciones asociadas a un caso de Microsoft Purview eDiscovery (estándar) en el centro de seguridad y cumplimiento. Las retenciones de eDiscovery se pueden aplicar a los buzones de usuario y al buzón correspondiente para Grupos de Microsoft 365 y Microsoft Teams.

- **[Suspensión local](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** retenciones que se aplican a los buzones de usuario mediante la herramienta In-Place eDiscovery & Hold en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> en Exchange Online. 

   > [!NOTE]
   > In-Place se han retirado las retenciones y ya no se pueden crear In-Place retenciones ni aplicarlas a buzones de correo. Sin embargo, es posible que las retenciones de In-Place se sigan aplicando a los buzones de su organización, por lo que se incluyen en este artículo. Para obtener más información, vea [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center).

- **[Directivas de retención de Microsoft 365](retention.md):** Se puede configurar para conservar (o conservar y eliminar) contenido en buzones de usuario en Exchange Online y en el buzón correspondiente para Grupos de Microsoft 365 y Microsoft Teams. También puede crear una directiva de retención para conservar Skype Empresarial Conversaciones, que se almacenan en buzones de usuario.

  Hay dos tipos de directivas de retención de Microsoft 365 que se pueden asignar a buzones de correo.

    - **Directivas de retención de ubicación específicas:** Se trata de directivas que se asignan a las ubicaciones de contenido de usuarios específicos. Use el cmdlet **Get-Mailbox** en Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones específicos. Para obtener más información sobre este tipo de directiva de retención, consulte la sección [Directiva A con inclusiones o exclusiones específicas](retention-settings.md#a-policy-with-specific-inclusions-or-exclusions) de la documentación de la directiva de retención.

    - **Directivas de retención para toda la organización:** Se trata de directivas que se asignan a todas las ubicaciones de contenido de la organización. Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización. Para obtener más información sobre este tipo de directiva de retención, consulte la sección [Directiva A que se aplica a ubicaciones completas](retention-settings.md#a-policy-that-applies-to-entire-locations) en la documentación de la directiva de retención.

- **[Etiquetas de retención de Microsoft 365](retention.md):** si un usuario aplica una etiqueta de retención de Microsoft 365 (una configurada para conservar contenido o conservar y eliminar contenido) a *cualquier* carpeta o elemento de su buzón, se coloca una suspensión en el buzón como si el buzón se colocara en suspensión por juicio o se asignara a una directiva de retención de Microsoft 365. Para obtener más información, vea la sección [Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) de este artículo.

Para administrar buzones en espera, es posible que tenga que identificar el tipo de retención que se coloca en un buzón de correo para que pueda realizar tareas como cambiar la duración de la suspensión, quitar temporal o permanentemente la suspensión, o excluir un buzón de correo de una directiva de retención de Microsoft 365. En estos casos, el primer paso es identificar el tipo de retención colocado en el buzón. Y dado que se pueden colocar varias retenciones (y diferentes tipos de retenciones) en un único buzón, debe identificar todas las retenciones colocadas en un buzón si desea quitar o cambiar una suspensión.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Paso 1: Obtener el GUID de las retenciones colocadas en un buzón

Puede ejecutar los dos cmdlets siguientes en Exchange Online PowerShell para obtener el GUID de las retenciones que se colocan en un buzón. Después de obtener un GUID, úselo para identificar la suspensión específica en el paso 2. Una suspensión por juicio no se identifica mediante un GUID. Las retenciones por juicio están habilitadas o deshabilitadas para un buzón.

- **Get-Mailbox:** Use este cmdlet para determinar si la suspensión por juicio está habilitada para un buzón y para obtener los GUID de las retenciones de exhibición de documentos electrónicos, las In-Place y las directivas de retención de Microsoft 365 que se asignan específicamente a un buzón. La salida de este cmdlet también indicará si un buzón de correo se ha excluido explícitamente de una directiva de retención de toda la organización.

- **Get-OrganizationConfig:** Use este cmdlet para obtener los GUID de las directivas de retención de toda la organización.

Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="get-mailbox"></a>Get-Mailbox

Ejecute el siguiente comando para obtener información sobre las retenciones y las directivas de retención de Microsoft 365 aplicadas a un buzón.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos ellos, puede ejecutar el `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la tabla siguiente se describe cómo identificar diferentes tipos de retenciones en función de los valores de la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-Mailbox** .

| Tipo de suspensión                                                          | Valor de ejemplo                                                                                  | Identificación de la suspensión                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Retención por litigio                                                    | `True`                                                                                         | La suspensión por juicio está habilitada para un buzón cuando la propiedad *LitigationHoldEnabled* está establecida en `True`.                                                                                                                                                                                                                                         |
| Suspensión de eDiscovery                                                    | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`                                                     | La *propiedad InPlaceHolds* contiene el GUID de cualquier retención asociada a un caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento. Puede indicar que se trata de una suspensión de eDiscovery porque el GUID comienza con el `UniH` prefijo (que denota una suspensión unificada).                                                                                   |
| Retención en contexto                                                      | `c0ba3ce811b6432a8751430937152491` <br/> o <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`        | La propiedad *InPlaceHolds* contiene el GUID de la In-Place Hold que se coloca en el buzón. Puede indicar que se trata de una suspensión de In-Place porque el GUID no comienza con un prefijo o comienza por el `cld` prefijo.                                                                                                               |
| Directiva de retención de Microsoft 365 aplicada específicamente al buzón | `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> o <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3` | La propiedad InPlaceHolds contiene GUID de cualquier directiva de retención de ubicación específica que se aplique al buzón. Puede identificar las directivas de retención porque el GUID comienza con el `mbx` prefijo o `skp` . El `skp` prefijo indica que la directiva de retención se aplica a Skype Empresarial conversaciones en el buzón del usuario. |
| Excluido de una directiva de retención de Microsoft 365 para toda la organización  | `-mbxe9b52bf7ab3b46a286308ecb29624696`                                                         | Si se excluye un buzón de correo de una directiva de retención de Microsoft 365 para toda la organización, el GUID de la directiva de retención del que se excluye el buzón se muestra en la propiedad InPlaceHolds y se identifica mediante el `-mbx` prefijo .                                                                                                     |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Si la propiedad *InPlaceHolds* está vacía al ejecutar el cmdlet **Get-Mailbox** , puede haber una o varias directivas de retención de Microsoft 365 para toda la organización aplicadas al buzón. Ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para obtener una lista de GUID para las directivas de retención de Microsoft 365 para toda la organización.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Si hay demasiados valores en la propiedad InPlaceHolds y no se muestran todos ellos, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando para mostrar cada GUID en una línea independiente.

En la tabla siguiente se describen los diferentes tipos de retenciones de toda la organización y cómo identificar cada tipo en función de los GUID contenidos en la propiedad *InPlaceHolds* al ejecutar el cmdlet **Get-OrganizationConfig** .

| Tipo de suspensión                                                                                                | Valor de ejemplo                           | Descripción                                                                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Directivas de retención de Microsoft 365 aplicadas a buzones de Exchange, carpetas públicas de Exchange y chats de Teams | `mbx7cfb30345d454ac0a989ab3041051209:2` | Las directivas de retención de toda la organización aplicadas a buzones de Exchange, carpetas públicas de Exchange y chats 1xN en Microsoft Teams se identifican mediante GUID que comienzan con el `mbx` prefijo . Nota Los chats 1xN se almacenan en el buzón de los participantes de chat individuales.  |
| Directiva de retención de Microsoft 365 aplicada a Grupos de Microsoft 365 y mensajes de canal de Teams                | `grp1a0a132ee8944501a4bb6a452ec31171:3` | Las directivas de retención de toda la organización aplicadas a los grupos de Microsoft 365 y los mensajes de canal en Microsoft Teams se identifican mediante GUID que comienzan con el `grp` prefijo . Tenga en cuenta que los mensajes de canal se almacenan en el buzón de grupo asociado a un equipo de Microsoft. |

Para obtener más información sobre las directivas de retención aplicadas a Microsoft Teams, consulte [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md).

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Descripción del formato del valor de InPlaceHolds para las directivas de retención

Además del prefijo (mbx, skp o grp) que identifica un elemento de la propiedad InPlaceHolds como una directiva de retención de Microsoft 365, el valor también contiene un sufijo que identifica el tipo de acción de retención configurada para la directiva. Por ejemplo, el sufijo de acción se resalta en negrita en los ejemplos siguientes:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

En la tabla siguiente se definen las tres posibles acciones de retención:

| Valor | Descripción                                                                                                                          |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **1** | Indica que la directiva de retención está configurada para eliminar elementos. La directiva no conserva elementos.                                  |
| **2** | Indica que la directiva de retención está configurada para contener elementos. La directiva no elimina elementos después de que expire el período de retención. |
| **3** | Indica que la directiva de retención está configurada para contener elementos y, a continuación, eliminarlos después de que expire el período de retención.             |

Para obtener más información sobre las acciones de retención, consulte la sección [Retención de contenido durante un período de tiempo específico](retention-settings.md#retaining-content-for-a-specific-period-of-time) .
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Paso 2: Uso del GUID para identificar la suspensión

Después de obtener el GUID de una suspensión que se aplica a un buzón de correo, el siguiente paso es usar ese GUID para identificar la suspensión. En las secciones siguientes se muestra cómo identificar el nombre de la suspensión (y otra información) mediante el GUID de suspensión.

### <a name="ediscovery-holds"></a>Suspensiones de eDiscovery

Ejecute los siguientes comandos en PowerShell de cumplimiento de seguridad & para identificar una suspensión de eDiscovery que se aplica al buzón. Use el GUID (sin incluir el prefijo UniH) para la suspensión de eDiscovery que identificó en el paso 1. 

Para conectarse a PowerShell de cumplimiento de & de seguridad, consulte [Conexión a PowerShell de cumplimiento de & de seguridad](/powershell/exchange/connect-to-scc-powershell).

El primer comando crea una variable que contiene información sobre la suspensión. Esta variable se usa en los otros comandos. El segundo comando muestra el nombre del caso de exhibición de documentos electrónicos al que está asociada la suspensión. El tercer comando muestra el nombre de la suspensión y una lista de los buzones a los que se aplica la suspensión.

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

Ejecute el siguiente comando en Exchange Online PowerShell para identificar la suspensión de In-Place que se aplica al buzón. Use el GUID para el In-Place Hold que identificó en el paso 1. El comando muestra el nombre de la suspensión y una lista de los buzones a los que se aplica la suspensión.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Si el GUID de la In-Place Hold comienza con el `cld` prefijo, asegúrese de incluir el prefijo al ejecutar el comando anterior.

> [!IMPORTANT]
> A medida que seguimos invirtiendo de diferentes maneras para conservar el contenido del buzón de correo, anunciamos la retirada de las suspensiones de In-Place en el Centro de administración de Exchange (EAC). A partir del 1 de julio de 2020 no podrá crear nuevas suspensiones de In-Place en Exchange Online. Pero seguirá siendo capaz de administrar In-Place retenciones en el EAC o mediante el cmdlet **Set-MailboxSearch** en Exchange Online PowerShell. Sin embargo, a partir del 1 de octubre de 2020, no podrá administrar In-Place suspensiones. Solo se quitarán en el EAC o mediante el cmdlet **Remove-MailboxSearch** . Para obtener más información sobre la retirada de In-Place retenciones, consulte [Retirada de herramientas de exhibición de documentos electrónicos heredadas](legacy-ediscovery-retirement.md).

### <a name="microsoft-365-retention-policies"></a>Directivas de retención de Microsoft 365

[Conéctese a Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell) y ejecute el siguiente comando para identificar la directiva de retención de Microsoft 365 (ubicación específica o de toda la organización) que se aplica al buzón. Use el GUID (sin incluir el prefijo mbx, skp o grp o el sufijo de acción) que identificó en el paso 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Identificación de buzones en espera porque se ha aplicado una etiqueta de retención a una carpeta o elemento

Cada vez que un usuario aplica una etiqueta de retención configurada para *conservar* o *conservar y, a continuación, eliminar* contenido en cualquier carpeta o elemento de su buzón, la propiedad *complianceTagHoldApplied* del buzón se establece en **True**. Cuando esto sucede, el buzón se trata de forma similar a si se ha colocado en suspensión, como cuando se asigna a una directiva de retención de Microsoft 365 o se coloca en suspensión por juicio, sin embargo, con algunas advertencias. Cuando la propiedad *ComplianceTagHoldApplied* se establece en **True**, se producen las siguientes cosas:

- Si se elimina el buzón o la cuenta de Microsoft 365 del usuario, el buzón se convierte en un [buzón inactivo](inactive-mailboxes-in-office-365.md).
- No puede deshabilitar el buzón (ya sea el buzón principal o el buzón de archivo, si está habilitado).
- Los elementos que se han eliminado del buzón seguirán una de las dos rutas de acceso en función de si están etiquetados o no:
    - **Los elementos sin etiquetar** seguirán la misma ruta de acceso que los elementos eliminados cuando no se apliquen retenciones al buzón.  El tiempo que tardan estos elementos en eliminarse permanentemente viene determinado por la configuración de [retención de elementos eliminados](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#deleted-item-retention) y si la [recuperación de elementos únicos](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#single-item-recovery) está habilitada para el buzón o no.
    - **Los elementos etiquetados** se conservarán dentro de la [carpeta de elementos recuperables](/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder#recoverable-items-folder) de la misma manera que lo serían si se aplicara una directiva de retención de Microsoft 365, pero en el nivel de elemento individual.  Si varios elementos tienen etiquetas diferentes que están configuradas para *conservar* o *conservar y, a continuación, eliminar* contenido a intervalos diferentes, cada elemento se conservará en función de la configuración de la etiqueta aplicada.
- Otras retenciones, como las directivas de retención de Microsoft 365, las retenciones de exhibición de documentos electrónicos o la suspensión por juicio pueden ampliar cuánto tiempo se conservan los elementos [etiquetados en función de los principios de retención](retention.md#the-principles-of-retention-or-what-takes-precedence).

Para ver el valor de la propiedad *ComplianceTagHoldApplied* para un único buzón de correo, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Get-Mailbox <username> | FL ComplianceTagHoldApplied
```

Para obtener más información sobre las etiquetas de retención, consulte [Etiquetas de retención](retention.md#retention-labels).

## <a name="managing-mailboxes-on-delay-hold"></a>Administración de buzones en espera de retraso

Una vez que se quita cualquier tipo de suspensión de un buzón, se aplica una *suspensión de retraso* . Esto significa que la eliminación real de la suspensión se retrasa durante 30 días para evitar que los datos se eliminen (purguen) permanentemente del buzón. Esto ofrece a los administradores la oportunidad de buscar o recuperar elementos de buzón que se purgarán después de quitar una suspensión. La próxima vez que el Asistente para carpetas administradas procese el buzón, se coloca una suspensión retrasada en un buzón y detecta que se quitó una suspensión. En concreto, se aplica una retención retrasada a un buzón cuando el Asistente para carpetas administradas establece una de las siguientes propiedades de buzón en **True**:

- **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la Web) que se almacena en el buzón de un usuario.

- **DelayReleaseHoldApplied:** Esta propiedad se aplica al contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos en la nube generados por una aplicación de Microsoft se almacenan normalmente en una carpeta oculta en el buzón de un usuario.

Cuando se coloca una suspensión de retraso en el buzón (cuando cualquiera de las propiedades anteriores se establece en **True**), el buzón sigue considerándose que está en espera durante una duración de suspensión ilimitada, como si el buzón estuviera en suspensión por juicio. Después de 30 días, la suspensión de retraso expira y Microsoft 365 intentará quitar automáticamente la suspensión de retraso (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **False**) para que se quite la suspensión. Después de establecer cualquiera de estas propiedades en **False**, los elementos correspondientes marcados para la eliminación se purgan la próxima vez que el Asistente para carpetas administradas procese el buzón.

Para ver los valores de las propiedades DelayHoldApplied y DelayReleaseHoldApplied de un buzón, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Para quitar la suspensión de retraso antes de que expire, puede ejecutar uno (o ambos) los siguientes comandos en Exchange Online PowerShell, dependiendo de la propiedad que quiera cambiar:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

Debe tener asignado el rol Detención legal en Exchange Online para usar los parámetros *RemoveDelayHoldApplied* o *RemoveDelayReleaseHoldApplied*. 

Para quitar la suspensión de retraso en un buzón inactivo, ejecute uno de los siguientes comandos en Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

O bien

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> La mejor manera de especificar un buzón inactivo en el comando anterior es usar su nombre distintivo o el valor GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 

Para obtener más información sobre el uso de estos parámetros para administrar las retenciones de retraso, vea [Set-Mailbox](/powershell/module/exchange/set-mailbox).

Tenga en cuenta lo siguiente al administrar un buzón en espera de retraso:

- Si la propiedad DelayHoldApplied o DelayReleaseHoldApplied se establece en **True** y se elimina un buzón (o la cuenta de usuario correspondiente), el buzón se convierte en un buzón inactivo. Esto se debe a que se considera que un buzón de correo está en espera si cualquiera de las propiedades está establecida en **True** y la eliminación de un buzón en espera da como resultado un buzón inactivo. Para eliminar un buzón y no convertirlo en un buzón inactivo, debe establecer ambas propiedades en **False**.

- Como se indicó anteriormente, se considera que un buzón está en espera durante una duración de retención ilimitada si la propiedad DelayHoldApplied o DelayReleaseHoldApplied está establecida en **True**. Sin embargo, eso no significa que *se conserve todo* el contenido del buzón. Depende del valor establecido en cada propiedad. Por ejemplo, supongamos que ambas propiedades están establecidas en **True** porque las retenciones se quitan del buzón. A continuación, solo se quita la suspensión de retraso que se aplica a datos en la nube que no son de Outlook (mediante el parámetro *RemoveDelayReleaseHoldApplied* ). La próxima vez que el Asistente para carpetas administradas procese el buzón, se purgan los elementos que no son de Outlook marcados para su eliminación. Los elementos de Outlook marcados para la eliminación no se purgarán porque la propiedad DelayHoldApplied todavía está establecida en **True**. Lo contrario también sería true: si DelayHoldApplied se establece en **False** y DelayReleaseHoldApplied se establece en **True**, solo se purgarán los elementos de Outlook marcados para su eliminación.

## <a name="how-to-confirm-that-an-organization-wide-retention-policy-is-applied-to-a-mailbox"></a>Cómo confirmar que se aplica una directiva de retención de toda la organización a un buzón

Cuando se aplica o quita una directiva de retención de toda la organización a un buzón de correo, la exportación de los registros de diagnóstico del buzón puede ayudarle a estar seguro de que Exchange Online realmente ha aplicado o quitado la directiva de retención al buzón. Para ver esta información, primero debe validar algunas cosas mediante [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

### <a name="obtain-the-guids-for-any-retention-policies-explicitly-applied-to-a-mailbox"></a>Obtener los GUID de las directivas de retención aplicadas explícitamente a un buzón

```powershell
Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="obtain-the-guids-for-any-organization-wide-retention-policies-applied-to-mailboxes"></a>Obtener los GUID de las directivas de retención de toda la organización aplicadas a los buzones

```powershell
Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds
```

### <a name="get-the-mailbox-diagnostics-for-holdtracking"></a>Obtención de los diagnósticos de buzones para HoldTracking

Los registros de diagnóstico de buzón de seguimiento de retención mantienen un historial de las retenciones aplicadas a un buzón de usuario.

```powershell
$ht = Export-MailboxDiagnosticLogs <username> -ComponentName HoldTracking
$ht.MailboxLog | Convertfrom-Json
```

### <a name="review-the-results-of-the-mailbox-diagnostics-logs"></a>Revisión de los resultados de los registros de diagnóstico de buzones

Si recopila datos del paso anterior, los datos resultantes pueden tener un aspecto similar al siguiente:

> **Ed**`  : 0001-01-01T00:00:00.0000000`
>  **Escondió**` : mbx7cfb30345d454ac0a989ab3041051209:1`
>  **Ht**`  : 4`
>  **Lsd**` : 2020-03-23T18:24:37.1884606Z`
>  **Osd**` : 2020-03-23T18:24:37.1884606Z`

Use la tabla siguiente para ayudarle a comprender cada uno de los valores anteriores enumerados en el registro de diagnóstico.

| Valor   | Descripción |
|:------- |:----------- |
| **ed**  | Indica la fecha de finalización, que es la fecha en que se deshabilitó la directiva de retención. MinValue significa que la directiva sigue asignada al buzón de correo. |
| **Escondió** | Indica el GUID de la directiva de retención. Este valor se correlacionará con los GUID que recopiló para las directivas de retención explícitas o de toda la organización asignadas al buzón.|
| **Lsd** | Indica la última fecha de inicio, que es la fecha en que se asignó la directiva de retención al buzón.|
| **Osd** | Indica la fecha de inicio original, que es la fecha en que Exchange registró por primera vez información sobre la directiva de retención. |
|||

Cuando una directiva de retención ya no se aplique a un buzón de correo, colocaremos una suspensión temporal en el usuario para evitar purgar contenido. Se puede deshabilitar una suspensión de retraso mediante la ejecución del `Set-Mailbox -RemoveDelayHoldApplied` comando .

## <a name="next-steps"></a>Pasos siguientes

Después de identificar las retenciones que se aplican a un buzón de correo, puede realizar tareas como cambiar la duración de la suspensión, quitar temporal o permanentemente la suspensión o excluir un buzón inactivo de una directiva de retención de Microsoft 365. Para obtener más información sobre cómo realizar tareas relacionadas con las retenciones, consulte uno de los temas siguientes:

- Ejecute el comando [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox>](/powershell/module/exchange/set-retentioncompliancepolicy) en [Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell) para excluir un buzón de una directiva de retención de Microsoft 365 para toda la organización. Este comando solo se puede usar para directivas de retención donde el valor de la propiedad *ExchangeLocation* es igual a `All`.

- [Cambiar la duración de retención para un buzón inactivo](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Eliminar un buzón inactivo](delete-an-inactive-mailbox.md)

- [Eliminar elementos de la carpeta de elementos recuperables de buzones en retención en la nube](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
