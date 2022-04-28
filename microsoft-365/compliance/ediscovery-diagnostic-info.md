---
title: Recopilar información de diagnóstico de eDiscovery
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Obtenga información sobre cómo recopilar información de diagnóstico de eDiscovery para un caso de Soporte técnico de Microsoft.
ms.openlocfilehash: 2759156a3948339629ea7d988eaaa5464da197fa
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095892"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Recopilar información de diagnóstico de eDiscovery

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En ocasiones, los ingenieros de Soporte técnico de Microsoft requieren información específica sobre el problema al abrir un caso de soporte técnico relacionado con eDiscovery de Microsoft Purview (estándar) o eDiscovery de Microsoft Purview (Premium). En este artículo se proporcionan instrucciones sobre cómo recopilar información de diagnóstico para ayudar a los ingenieros de soporte técnico a investigar y resolver problemas. Normalmente, no es necesario recopilar esta información hasta que un ingeniero de Soporte técnico de Microsoft lo solicite.

> [!IMPORTANT]
> La salida de los cmdlets y la información de diagnóstico descrita en este artículo puede incluir información confidencial sobre litigios o investigaciones internas en su organización. Antes de enviar la información de diagnóstico sin procesar a Soporte técnico de Microsoft, debe revisar la información y redactar cualquier información confidencial (como nombres u otra información sobre las partes en litigio o investigación) reemplazando por `XXXXXXX`. El uso de este método también indicará al ingeniero de Soporte técnico de Microsoft que se redactó la información.

## <a name="collect-diagnostic-information-for-ediscovery-standard"></a>Recopilación de información de diagnóstico para eDiscovery (estándar)

La recopilación de información de diagnóstico para eDiscovery (Estándar) se basa en cmdlets, por lo que tendrá que usar PowerShell del Centro de cumplimiento de seguridad &. En los siguientes ejemplos de PowerShell se ejecutarán cmdlets y, a continuación, se guardará la salida en un archivo de texto especificado. En la mayoría de los casos de soporte técnico, solo debe ejecutar uno de estos comandos.

Para ejecutar los siguientes cmdlets, [conéctese a PowerShell</span> security & Compliance Center](/powershell/exchange/connect-to-scc-powershell). Una vez conectado, ejecute uno o varios de los siguientes comandos y asegúrese de reemplazar los marcadores de posición por los nombres de objeto reales.

Después de revisar el archivo de texto generado y redactar información confidencial, envíela al ingeniero de Soporte técnico de Microsoft que trabaja en su caso.

> [!NOTE]
> También puede ejecutar los comandos de esta sección para recopilar información de diagnóstico de las búsquedas y exportaciones que aparecen en la página **Búsqueda de contenido** del portal de cumplimiento de Microsoft Purview.

### <a name="collect-information-about-searches"></a>Recopilación de información sobre búsquedas

El siguiente comando recopila información útil al investigar problemas con una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar).

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Recopilación de información sobre acciones de búsqueda

El siguiente comando recopila información para investigar problemas con la vista previa, la exportación o la purga de los resultados de una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar). Puede identificar el nombre de la acción de búsqueda haciendo clic en una exportación que aparece en la pestaña **Exportaciones** . Para identificar los nombres de las acciones de vista previa y purga, puede ejecutar el cmdlet **Get-ComplianceSearchAction** para mostrar una lista de todas las acciones. El formato del nombre de la acción de búsqueda se construye anexando `_Preview`, `_Export`o `_Purge` al nombre de la búsqueda correspondiente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Recopilación de información sobre las retenciones de eDiscovery

Cuando una suspensión de eDiscovery asociada a un caso de exhibición de documentos electrónicos (estándar) no funciona según lo esperado, ejecute el siguiente comando para recopilar información sobre la directiva de suspensión de casos y la regla de suspensión de casos asociada para la suspensión de eDiscovery. El nombre de la *directiva de retención* de mayúsculas y minúsculas en el comando siguiente es el mismo que el nombre de la suspensión de eDiscovery. Puede identificar este nombre en las pestañas **Detenciones** en el caso de eDiscovery (Estándar).

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Recopilar toda la información del caso

A veces, no es evidente qué información necesita Soporte técnico de Microsoft para investigar el problema. En esta situación, puede recopilar toda la información de diagnóstico de un caso de exhibición de documentos electrónicos (estándar). El *nombre del caso de eDiscovery (Estándar)* en el siguiente comando es el mismo que el nombre de un caso que se muestra en la página **eDiscovery (Estándar)** del portal de cumplimiento.

```powershell
Get-ComplianceCase "<eDiscovery (Standard) case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-ediscovery-premium"></a>Recopilar información de diagnóstico para eDiscovery (Premium)

La **pestaña Configuración** en un caso de exhibición de documentos electrónicos (Premium) permite copiar rápidamente la información de diagnóstico del caso. La información de diagnóstico se guarda en el Portapapeles para que pueda pegarla en un archivo de texto y enviarla a Soporte técnico de Microsoft.

1. Vaya al portal de cumplimiento y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank">**eDiscoveryAdvanced**</a> > .

2. Seleccione un caso y, a continuación, haga clic en la pestaña **Configuración**.

3. En **Información del caso**, haga clic en **Seleccionar**.

4. En la página de control flotante, haga clic en **ActionsCopy support information (Información de soporte técnico** de **ActionsCopy** > ) para copiar la información en el Portapapeles.

5. Abra un archivo de texto (en Bloc de notas) y pegue la información en el archivo de texto.

6. Guarde el archivo de texto y asígnele un nombre similar `AeD Diagnostic Info YYYY.MM.DD` (por ejemplo, `AeD Diagnostic Info 2020.11.03`).

Después de revisar el archivo y redactar información confidencial, envíela al ingeniero de Soporte técnico de Microsoft que trabaja en su caso.
