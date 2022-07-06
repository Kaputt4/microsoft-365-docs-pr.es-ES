---
title: Migración de búsquedas y retenciones de eDiscovery heredadas a la portal de cumplimiento Microsoft Purview
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkEXCHANGE
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 607b66d863c0584ce1bb06c069de7870245cb167
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622599"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-compliance-portal"></a>Migración de búsquedas y retenciones de eDiscovery heredadas al portal de cumplimiento

El portal de cumplimiento Microsoft Purview proporciona una experiencia mejorada para el uso de eDiscovery, como: mayor confiabilidad, mejor rendimiento y muchas características adaptadas a flujos de trabajo de eDiscovery, incluidos casos para organizar el contenido por cuestión, conjuntos de revisión para revisar el contenido y análisis para ayudar a eliminar datos para su revisión, como agrupación casi duplicada, subprocesos de correo electrónico, análisis de temas y predictiva  Codificación.

Para ayudar a los clientes a aprovechar las ventajas de la funcionalidad nueva y mejorada, en este artículo se proporcionan instrucciones básicas sobre cómo migrar In-Place búsquedas y retenciones de exhibición de documentos electrónicos desde el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> al portal de cumplimiento.

> [!NOTE]
> Dado que hay muchos escenarios diferentes, en este artículo se proporcionan instrucciones generales para realizar búsquedas de transición y mantener un caso de exhibición de documentos electrónicos (estándar) en el portal de cumplimiento. El uso de casos de eDiscovery no siempre es necesario, pero agregan una capa adicional de seguridad, ya que permiten asignar permisos para controlar quién tiene acceso a los casos de eDiscovery en su organización.

## <a name="before-you-begin"></a>Antes de empezar

- Debe instalar el módulo Exchange Online V2. Para obtener instrucciones, consulte [Instalar y mantener el módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

- Debe ser miembro del grupo de roles administrador de eDiscovery en el portal de cumplimiento para ejecutar los comandos de PowerShell descritos en este artículo. También debe ser miembro del grupo de roles Administración de detección en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.

- En este artículo se proporcionan instrucciones sobre cómo crear una suspensión de eDiscovery. La directiva de retención se aplicará a los buzones a través de un proceso asincrónico. Al crear una suspensión de eDiscovery, debe crear un CaseHoldPolicy y un CaseHoldRule; de lo contrario, no se creará la suspensión y las ubicaciones de contenido no se colocarán en suspensión.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-powershell"></a>Paso 1: Conexión a Exchange Online PowerShell y PowerShell de cumplimiento de & de seguridad

El primer paso es conectarse a Exchange Online PowerShell y PowerShell de cumplimiento de seguridad & en la misma ventana de PowerShell. Puede copiar los siguientes comandos, pegarlos en una ventana de PowerShell y, a continuación, ejecutarlos. Se le pedirán las credenciales.

```powershell
Connect-IPPSSession
Connect-ExchangeOnline -UseRPSSession
```

Para obtener instrucciones detalladas, consulte [Connect to Security & Compliance PowerShell](/powershell/exchange/connect-to-scc-powershell) y [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Paso 2: Obtener una lista de In-Place búsquedas de exhibición de documentos electrónicos mediante Get-MailboxSearch

Después de conectarse, puede obtener una lista de In-Place búsquedas de eDiscovery mediante la ejecución del cmdlet **Get-MailboxSearch** . Copie y pegue el siguiente comando en la ventana de PowerShell y ejecútelo.

```powershell
Get-MailboxSearch
```

Se mostrará una lista de búsquedas con sus nombres y el estado de las retenciones de In-Place.

La salida del cmdlet será similar a la siguiente:

![Ejemplo de PowerShell Get-MailboxSearch.](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Paso 3: Obtener información sobre las búsquedas In-Place eDiscovery y las retenciones de In-Place que desea migrar

De nuevo, usará el cmdlet **Get-MailboxSearch** , pero esta vez para obtener las propiedades de la búsqueda. Puede almacenar estas propiedades en una variable para usarlas más adelante. En el ejemplo siguiente se almacenan los resultados del cmdlet **Get-MailboxSearch** en una variable y, a continuación, se muestran las propiedades de la búsqueda.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | Format-List
```

La salida de estos dos comandos será similar a la siguiente:

![Ejemplo de salida de PowerShell desde el uso de Get-MailboxSearch para una búsqueda individual.](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> La duración de la In-Place Hold en este ejemplo es indefinida (*ItemHoldPeriod: Unlimited*). Esto es típico de los escenarios de eDiscovery y de investigación legal. Si la duración de la retención tiene un valor diferente al indefinido, es probable que el motivo se deba a que la suspensión se usa para conservar el contenido en un escenario de retención. En lugar de usar los cmdlets de eDiscovery en PowerShell de cumplimiento de seguridad & para escenarios de retención, se recomienda usar [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) y [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) para conservar el contenido. El resultado del uso de estos cmdlets será similar al uso de **New-CaseHoldPolicy** y **New-CaseHoldRule**, pero podrá especificar un período de retención y una acción de retención, como la eliminación de contenido después de que expire el período de retención. Además, el uso de los cmdlets de retención no requiere que asocie las retenciones con un caso de exhibición de documentos electrónicos.

## <a name="step-4-create-a-case-in-the-microsoft-purview-compliance-portal"></a>Paso 4: Crear un caso en el portal de cumplimiento Microsoft Purview

Para crear una suspensión de eDiscovery, debe crear un caso de exhibición de documentos electrónicos con el que asociar la suspensión. En el ejemplo siguiente se crea un caso de exhibición de documentos electrónicos con el nombre que prefiera. Almacenaremos las propiedades del nuevo caso en una variable para usarlas más adelante. Para ver esas propiedades, ejecute el `$case | FL` comando después de crear el caso.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```

![Ejemplo de ejecución del comando New-ComplianceCase.](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Paso 5: Crear la suspensión de eDiscovery

Una vez creado el caso, puede crear la suspensión y asociarla al caso que creó en el paso anterior. Es importante recordar que debe crear una directiva de suspensión de casos y una regla de suspensión de casos. Si la regla de retención de casos no se crea después de crear la directiva de suspensión de casos, no se creará la suspensión de eDiscovery y no se colocará ningún contenido en espera.

Ejecute los siguientes comandos para volver a crear la suspensión de eDiscovery que desea migrar. En estos ejemplos se usan las propiedades de In-Place suspensión del paso 3 que desea migrar. El primer comando crea una nueva directiva de suspensión de mayúsculas y minúsculas y guarda las propiedades en una variable. El segundo comando crea la regla de suspensión de mayúsculas y minúsculas correspondiente.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Ejemplo de uso de cmdlets NewCaseHoldPolicy y NewCaseHoldRule.](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Paso 6: Comprobar la suspensión de eDiscovery

Para asegurarse de que no haya ningún problema en la creación de la suspensión, es recomendable comprobar que el estado de distribución de suspensión se ha realizado correctamente. La distribución significa que la suspensión se ha aplicado a todas las ubicaciones de contenido especificadas en el parámetro *ExchangeLocation* del paso anterior. Para ello, puede ejecutar el cmdlet **Get-CaseHoldPolicy** . Dado que las propiedades guardadas en la *variable $policy* que creó en el paso anterior no se actualizan automáticamente en la variable, debe volver a ejecutar el cmdlet para comprobar que la distribución se realiza correctamente. Las directivas de suspensión de casos pueden tardar entre 5 minutos y 24 horas en distribuirse correctamente.

Ejecute el siguiente comando para comprobar que la suspensión de eDiscovery se ha distribuido correctamente.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

El valor de **Success** para la propiedad *DistributionStatus* indica que la suspensión se ha colocado correctamente en las ubicaciones de contenido. Si la distribución aún no está completa **, se muestra** un valor pendiente.

![Ejemplo de Get-CaseHoldPolicy de PowerShell.](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Paso 7: Crear la búsqueda

El último paso consiste en volver a crear la búsqueda que identificó en el paso 3 y asociarla al caso. Después de crear la búsqueda, puede ejecutarla mediante el cmdlet **Start-ComplianceSearch** o ejecutarla más adelante.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Ejemplo de New-ComplianceSearch de PowerShell.](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-compliance-portal"></a>Paso 8: Comprobar el caso, mantener y buscar en el portal de cumplimiento

Para asegurarse de que todo está configurado correctamente, vaya al portal de cumplimiento en [https://compliance.microsoft.com](https://compliance.microsoft.com)y haga clic en **eDiscovery > Core**.

![portal de cumplimiento Microsoft Purview eDiscovery.](../media/MigrateLegacyeDiscovery7.png)

El caso que creó en el paso 3 aparece en la página **eDiscovery (Estándar).** Abra el caso y, a continuación, observe la suspensión que creó en el paso 4 de la lista en la pestaña **Suspensión** . Puede seleccionar la suspensión para ver los detalles de la página de control flotante, incluido el número de buzones a los que se aplica la suspensión y el estado de distribución.

![eDiscovery se mantiene en el portal de cumplimiento.](../media/MigrateLegacyeDiscovery8.png)

La búsqueda que creó en el paso 7 aparece en la pestaña **Búsquedas** del caso.

![Búsqueda de casos de eDiscovery en el portal de cumplimiento.](../media/MigrateLegacyeDiscovery9.png)

Si migra una búsqueda In-Place eDiscovery pero no la asocia a un caso de exhibición de documentos electrónicos, se mostrará en la página Búsqueda de contenido del portal de cumplimiento.

## <a name="more-information"></a>Más información

- Para obtener más información sobre In-Place & de exhibición de documentos electrónicos en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>, vea:

  - [Exhibición de documentos electrónicos en contexto](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Conservación local y retención por juicio](/exchange/security-and-compliance/in-place-and-litigation-holds)

- Para obtener más información sobre los cmdlets de PowerShell usados en el artículo, consulte:

  - [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)

  - [New-ComplianceCase](/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy)

  - [New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)

  - [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

- Para obtener más información sobre el portal de cumplimiento, consulte [Información general de la portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md).