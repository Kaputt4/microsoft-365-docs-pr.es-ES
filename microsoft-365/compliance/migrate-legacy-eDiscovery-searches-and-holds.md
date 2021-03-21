---
title: Migrar búsquedas y retenciones de exhibición de documentos electrónicos heredados al Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: ef5562aa6f5c7519d19452100b55dd4bc30d4126
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926328"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a>Migrar búsquedas y retenciones de exhibición de documentos electrónicos heredados al Centro de cumplimiento de Microsoft 365

El Centro de cumplimiento de Microsoft 365 proporciona una experiencia mejorada para el uso de exhibición de documentos electrónicos, que incluye: mayor confiabilidad, mejor rendimiento y muchas características adaptadas a flujos de trabajo de exhibición de documentos electrónicos, incluidos casos para organizar el contenido por asunto, conjuntos de revisión para revisar contenido y análisis para ayudar a eliminar datos para su revisión, como agrupaciones casi duplicadas, subprocesos de correo electrónico, análisis de temas y codificación predictiva.

Para ayudar a los clientes a aprovechar la funcionalidad nueva y mejorada, en este artículo se proporcionan instrucciones básicas sobre cómo migrar las búsquedas y retenciones de exhibición de documentos electrónicos In-Place desde el Centro de administración de Exchange al centro de cumplimiento de Microsoft 365.

> [!NOTE]
> Dado que hay muchos escenarios diferentes, este artículo proporciona instrucciones generales para realizar la transición de búsquedas y retenciones a un caso principal de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. El uso de casos de exhibición de documentos electrónicos no siempre es necesario, pero agregan una capa adicional de seguridad al permitirle asignar permisos para controlar quién tiene acceso a los casos de exhibición de documentos electrónicos en su organización.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento para ejecutar los comandos de PowerShell descritos en este artículo. También debe ser miembro del grupo de roles Administración de detección en el Centro de administración de Exchange.

- En este artículo se proporcionan instrucciones sobre cómo crear una retención de exhibición de documentos electrónicos. La directiva de retención se aplicará a los buzones a través de un proceso asincrónico. Al crear una retención de exhibición de documentos electrónicos, debe crear una CaseHoldPolicy y CaseHoldRule, de lo contrario, no se creará la retención y las ubicaciones de contenido no se colocarán en espera.

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a>Paso 1: Conectarse a PowerShell de Exchange Online y PowerShell & Centro de cumplimiento

El primer paso es conectarse a PowerShell de Exchange Online y PowerShell & Centro de cumplimiento. Puede copiar el siguiente script, pegarlo en una ventana de PowerShell y, a continuación, ejecutarlo. Se le pedirán las credenciales de la organización a la que desea conectarse. 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

Debe ejecutar los comandos en los siguientes pasos de esta sesión de PowerShell.

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a>Paso 2: Obtener una lista de In-Place búsquedas de exhibición de documentos electrónicos mediante Get-MailboxSearch

Después de autenticarse, puede obtener una lista de In-Place búsquedas de exhibición de documentos electrónicos mediante la ejecución del cmdlet **Get-MailboxSearch.** Copie y pegue el siguiente comando en PowerShell y, a continuación, ejecutarlo. Se mostrará una lista de búsquedas con sus nombres y el estado de cualquier In-Place espera.

```powershell
Get-MailboxSearch
```

El resultado del cmdlet será similar al siguiente:

![Ejemplo de PowerShell Get-MailboxSearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a>Paso 3: Obtener información sobre las In-Place de exhibición de documentos electrónicos y las In-Place que desea migrar

De nuevo, usará el cmdlet **Get-MailboxSearch,** pero esta vez para obtener las propiedades de la búsqueda. Puede almacenar estas propiedades en una variable para usarlas más adelante. En el ejemplo siguiente se almacenan los resultados del cmdlet **Get-MailboxSearch** en una variable y, a continuación, se muestran las propiedades de la búsqueda.

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

El resultado de estos dos comandos será similar al siguiente:

![Ejemplo de resultados de PowerShell de usar Get-MailboxSearch para una búsqueda individual](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> La duración de la In-Place hold en este ejemplo es indefinida (*ItemHoldPeriod: Unlimited*). Esto es típico para escenarios de exhibición de documentos electrónicos e investigación legal. Si la duración de retención tiene un valor diferente al indefinido, es probable que el motivo se deba a que la retención se usa para retener contenido en un escenario de retención. En lugar de usar los cmdlets de exhibición de documentos electrónicos en PowerShell del Centro de seguridad & Cumplimiento para escenarios de retención, se recomienda usar [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy) y [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule) para conservar el contenido. El resultado del uso de estos cmdlets será similar al uso de **New-CaseHoldPolicy** y **New-CaseHoldRule,** pero podrá especificar un período de retención y una acción de retención, como eliminar contenido después de que expire el período de retención. Además, el uso de los cmdlets de retención no requiere que asocie las retenciones con un caso de exhibición de documentos electrónicos.

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a>Paso 4: Crear un caso en el Centro de cumplimiento de Microsoft 365

Para crear una retención de exhibición de documentos electrónicos, debe crear un caso de exhibición de documentos electrónicos con el que asociar la retención. En el siguiente ejemplo se crea un caso de exhibición de documentos electrónicos con el nombre que prefiera. Almacenaremos las propiedades del nuevo caso en una variable para su uso más adelante. Puede ver estas propiedades ejecutando el `$case | FL` comando después de crear el caso.

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Ejemplo de ejecución del New-ComplianceCase comando](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a>Paso 5: Crear la retención de exhibición de documentos electrónicos

Después de crear el caso, puede crear la retención y asociarla con el caso que creó en el paso anterior. Es importante recordar que debe crear una directiva de retención de casos y una regla de retención de casos. Si la regla de retención de mayúsculas y minúsculas no se crea después de crear la directiva de retención de casos, la retención de exhibición de documentos electrónicos no se creará y el contenido no se pondrá en espera.

Ejecute los siguientes comandos para volver a crear la retención de exhibición de documentos electrónicos que desea migrar. Estos ejemplos usan las propiedades de In-Place hold del paso 3 que desea migrar. El primer comando crea una nueva directiva de retención de mayúsculas y minúsculas y guarda las propiedades en una variable. El segundo comando crea la regla de retención de mayúsculas y minúsculas correspondiente.

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![Ejemplo de uso de cmdlets NewCaseHoldPolicy y NewCaseHoldRule](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a>Paso 6: Comprobar la retención de exhibición de documentos electrónicos

Para asegurarse de que no haya problemas en la creación de la retención, es bueno comprobar que el estado de distribución de retención es correcto. La distribución significa que la retención se ha aplicado a todas las ubicaciones de contenido especificadas en el *parámetro ExchangeLocation* en el paso anterior. Para ello, puede ejecutar el cmdlet **Get-CaseHoldPolicy.** Dado que las propiedades guardadas en la variable $policy que creó en el paso anterior no se actualizan automáticamente en la variable, debe volver *a* ejecutar el cmdlet para comprobar que la distribución se realiza correctamente. Las directivas de retención de casos pueden tardar entre 5 minutos y 24 horas en distribuirse correctamente.

Ejecute el siguiente comando para comprobar que la retención de exhibición de documentos electrónicos se ha distribuido correctamente.

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

El valor de **Success para** la *propiedad DistributionStatus* indica que la retención se colocó correctamente en las ubicaciones de contenido. Si la distribución aún no está completa, se muestra un valor **de Pending.**

![Ejemplo de Get-CaseHoldPolicy PowerShell](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a>Paso 7: Crear la búsqueda

El último paso es volver a crear la búsqueda que identificó en el paso 3 y asociarla con el caso. Después de crear la búsqueda, puede ejecutarla con el cmdlet **Start-ComplianceSearch** o ejecutarla más adelante.

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![Ejemplo de New-ComplianceSearch PowerShell](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a>Paso 8: Comprobar el caso, la retención y la búsqueda en el Centro de cumplimiento de Microsoft 365

Para asegurarse de que todo está configurado correctamente, vaya al Centro de cumplimiento de Microsoft 365 en y haga clic en [https://compliance.microsoft.com](https://compliance.microsoft.com) **eDiscovery > Core**.

![Exhibición de documentos electrónicos del Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery7.png)

El caso que creó en el paso 3 aparece en la **página eDiscovery** principal. Abra el caso y, a continuación, observe la retención que creó en el paso 4 en la lista en la **pestaña Retenciones.** Puede hacer clic en la retención para ver detalles, incluido el número de buzones a los que se aplica la retención y el estado de distribución.

![Exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery8.png)

La búsqueda que creó en el paso 7 aparece en la lista en la pestaña **Búsquedas** del caso de exhibición de documentos electrónicos.

![Búsqueda de casos de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365](../media/MigrateLegacyeDiscovery9.png)

Si migra una búsqueda In-Place exhibición de documentos electrónicos pero no la asocia con un caso de exhibición de documentos electrónicos, aparecerá en la página Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365.

## <a name="more-information"></a>Más información

- Para obtener más información sobre In-Place de exhibición de documentos electrónicos & en el Centro de administración de Exchange, vea:
  
  - [Exhibición de documentos electrónicos en contexto](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [Conservación local y retención por juicio](/exchange/security-and-compliance/in-place-and-litigation-holds)

- Para obtener más información acerca de los cmdlets de PowerShell usados en el artículo, vea:

  - [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)
  
  - [New-ComplianceCase](/powershell/module/exchange/new-compliancecase)

  - [New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy)
  
  - [New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule)

  - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
  
  - [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

  - [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

- Para obtener más información acerca del Centro de cumplimiento de Microsoft 365, vea [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).