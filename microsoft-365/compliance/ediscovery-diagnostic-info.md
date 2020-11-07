---
title: Recopilar información de diagnóstico de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo recopilar información de diagnóstico de eDiscovery para un caso de soporte técnico de Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944401"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Recopilar información de diagnóstico de eDiscovery

Ocasionalmente, los ingenieros de soporte técnico de Microsoft necesitan información específica sobre su problema al abrir un caso de soporte técnico relacionado con la exhibición de documentos electrónicos avanzada o la exhibición avanzada de documentos electrónicos. En este artículo se proporcionan instrucciones sobre cómo recopilar información de diagnóstico para ayudar a los ingenieros de soporte a investigar y resolver problemas. Normalmente, no es necesario recopilar esta información hasta que lo solicite un ingeniero de soporte técnico de Microsoft.

> [!IMPORTANT]
> El resultado de los cmdlets y la información de diagnóstico que se describe en este artículo puede incluir información confidencial sobre litigios o investigaciones internas de su organización. Antes de enviar la información de diagnóstico sin formato a soporte técnico de Microsoft, debe revisar la información y censurar la información confidencial (por ejemplo, los nombres u otra información de las partes en los litigios o la investigación) reemplazándolo por `XXXXXXX` . El uso de este método también indica al ingeniero de soporte técnico de Microsoft que la información se ha censurado.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Recopilar información de diagnóstico para la exhibición de documentos electrónicos principal

La recopilación de información de diagnóstico para la exhibición de documentos electrónicos principal está basada en cmdlet, por lo que tendrá que usar el PowerShell del centro de cumplimiento de & de seguridad. Los siguientes ejemplos de PowerShell ejecutarán cmdlets y, a continuación, guardarán el resultado en un archivo de texto especificado. En la mayoría de los casos de soporte técnico, solo debe ejecutar uno de estos comandos.

Para ejecutar los cmdlets siguientes, [Conéctese a PowerShell </span> del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Una vez conectado, ejecute uno o varios de los siguientes comandos y asegúrese de reemplazar los marcadores de posición por los nombres reales del objeto.

Después de revisar el archivo de texto generado y censurar la información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.

> [!NOTE]
> También puede ejecutar los comandos de esta sección para recopilar información de diagnóstico para las búsquedas y exportaciones que aparecen en la página **búsqueda de contenido** en el centro de cumplimiento de Microsoft 365.

### <a name="collect-information-about-searches"></a>Recopilar información sobre las búsquedas

El siguiente comando recopila información útil para investigar problemas con una búsqueda de contenido o una búsqueda asociada a un caso de eDiscovery principal.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Recopilar información sobre las acciones de búsqueda

El siguiente comando recopila información para investigar los problemas con la vista previa, la exportación o la depuración de los resultados de una búsqueda de contenido o una búsqueda asociada a un caso de exhibición de documentos electrónicos principal. Puede identificar el nombre de la acción de búsqueda haciendo clic en una exportación que aparece en la ficha **exportaciones** . Para identificar los nombres de las acciones de vista previa y de depuración, puede ejecutar el cmdlet **Get-ComplianceSearchAction** para mostrar una lista de todas las acciones. El formato del nombre de la acción de búsqueda se crea anexando `_Preview` , `_Export` o `_Purge` al nombre de la búsqueda correspondiente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Recopilar información sobre las suspensiones de eDiscovery

Cuando una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal no funciona como se esperaba, ejecute el siguiente comando para recopilar información sobre la Directiva de suspensión de casos y la regla de suspensión de casos asociada para la retención de exhibición de documentos electrónicos. El *nombre* de la Directiva de suspensión de casos en el comando siguiente es el mismo que el nombre de la retención de exhibición de documentos electrónicos. Puede identificar este nombre en las pestañas **suspensiones** del caso principal de eDiscovery.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Recopilar toda la información del caso

A veces, no es evidente qué información necesita el soporte técnico de Microsoft para investigar su problema. En esta situación, puede recopilar toda la información de diagnóstico para un caso principal de eDiscovery. El *nombre del caso de eDiscovery principal* del siguiente comando es el mismo que el nombre de un caso que se muestra en la página **principal de eDiscovery** en el centro de cumplimiento de Microsoft 365.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Recopilar información de diagnóstico para eDiscovery avanzado

La pestaña **configuración** en un caso de exhibición avanzada de documentos electrónicos le permite copiar rápidamente la información de diagnóstico del caso. La información de diagnóstico se guarda en el portapapeles para que se pueda pegar en un archivo de texto y enviar a soporte técnico de Microsoft.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Mostrar todos los > EDiscovery > avanzadas**.

2. Seleccione un caso y, a continuación, haga clic en la pestaña **configuración** .

3. En **información de caso** , haga clic en **seleccionar**.

4. En la página de flotante, haga clic en **copiar información de diagnóstico** para copiar la información en el portapapeles.

5. Abra un archivo de texto (en el Bloc de notas) y, a continuación, pegue la información en el archivo de texto.

6. Guarde el archivo de texto y asígnele un nombre similar a `AeD Diagnostic Info YYYY.MM.DD` (por ejemplo, `AeD Diagnostic Info 2020.11.03` ).

Después de revisar el archivo y censurar la información confidencial, envíela al ingeniero de soporte técnico de Microsoft que esté trabajando en su caso.
