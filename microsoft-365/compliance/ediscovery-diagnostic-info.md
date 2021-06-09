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
description: Obtenga información sobre cómo recopilar información de diagnóstico de exhibición de documentos electrónicos para un caso de soporte técnico de Microsoft.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926560"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Recopilar información de diagnóstico de eDiscovery

En ocasiones, los ingenieros de soporte técnico de Microsoft requieren información específica sobre el problema al abrir un caso de soporte técnico relacionado con la exhibición de documentos electrónicos principal o Advanced eDiscovery. En este artículo se proporcionan instrucciones sobre cómo recopilar información de diagnóstico para ayudar a los ingenieros a investigar y resolver problemas. Normalmente, no es necesario recopilar esta información hasta que un ingeniero de soporte técnico de Microsoft lo pida.

> [!IMPORTANT]
> El resultado de los cmdlets y la información de diagnóstico que se describe en este artículo puede incluir información confidencial sobre litigios o investigaciones internas en su organización. Antes de enviar la información de diagnóstico sin procesar al Soporte técnico de Microsoft, debe revisar la información y redactar cualquier información confidencial (como nombres u otra información sobre partes en litigio o investigación) reemplazando por `XXXXXXX` . El uso de este método también indicará al ingeniero de soporte técnico de Microsoft que se redactó la información.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Recopilar información de diagnóstico para eDiscovery principal

La recopilación de información de diagnóstico para eDiscovery principal está basada en cmdlets, por lo que tendrá que usar PowerShell del Centro de seguridad & cumplimiento. Los siguientes ejemplos de PowerShell ejecutarán cmdlets y, a continuación, guardarán el resultado en un archivo de texto especificado. En la mayoría de los casos de compatibilidad, solo debe ejecutar uno de estos comandos.

Para ejecutar los cmdlets siguientes, [conéctese a </span> PowerShell & Centro de](/powershell/exchange/connect-to-scc-powershell)seguridad y cumplimiento . Después de conectarse, ejecute uno o varios de los siguientes comandos y asegúrese de reemplazar los marcadores de posición por los nombres de objeto reales.

Después de revisar el archivo de texto generado y de redactar información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.

> [!NOTE]
> También puede ejecutar los comandos de esta sección para recopilar información  de diagnóstico de las búsquedas y exportaciones que aparecen en la página Búsqueda de contenido en el centro de Microsoft 365 cumplimiento.

### <a name="collect-information-about-searches"></a>Recopilar información sobre búsquedas

El siguiente comando recopila información útil al investigar problemas con una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Recopilar información sobre acciones de búsqueda

El siguiente comando recopila información para investigar problemas con la vista previa, la exportación o la depuración de los resultados de una búsqueda de contenido o una búsqueda asociada con un caso de exhibición de documentos electrónicos principal. Puede identificar el nombre de la acción de búsqueda haciendo clic en una exportación que aparece en la **pestaña** Exportaciones. Para identificar los nombres de las acciones de vista previa y purga, puede ejecutar el cmdlet **Get-ComplianceSearchAction** para mostrar una lista de todas las acciones. El formato del nombre de la acción de búsqueda se construye anexando , o al `_Preview` nombre de la búsqueda `_Export` `_Purge` correspondiente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Recopilar información sobre las retenciones de exhibición de documentos electrónicos

Cuando una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal no funciona como se esperaba, ejecute el siguiente comando para recopilar información sobre la directiva de retención de casos y la regla de retención de casos asociada para la retención de exhibición de documentos electrónicos. El *nombre de la directiva de retención case* en el siguiente comando es el mismo que el nombre de la retención de exhibición de documentos electrónicos. Puede identificar este nombre en las **pestañas Retenciones** en el caso de exhibición de documentos electrónicos principales.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Recopilar toda la información de casos

A veces, no es aparente qué información requiere el soporte técnico de Microsoft para investigar el problema. En esta situación, puede recopilar toda la información de diagnóstico para un caso de exhibición de documentos electrónicos principal. El *nombre* del caso de exhibición de documentos electrónicos principal en el siguiente  comando es el mismo que el nombre de un caso que se muestra en la página Exhibición de documentos electrónicos principales en el centro de cumplimiento de Microsoft 365 de documentos electrónicos.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Recopilar información de diagnóstico para Advanced eDiscovery

La **Configuración** en un caso Advanced eDiscovery permite copiar rápidamente la información de diagnóstico del caso. La información de diagnóstico se guarda en el Portapapeles para que puedas pegarla en un archivo de texto y enviarla al Soporte técnico de Microsoft.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Mostrar > eDiscovery > Advanced**.

2. Seleccione un caso y, a **continuación, haga** clic en Configuración pestaña.

3. En **Información de casos**, haga clic **en Seleccionar**.

4. En la página desplegable, haz clic en **Copiar información de diagnóstico** para copiar la información en el Portapapeles.

5. Abra un archivo de texto (en Bloc de notas) y pegue la información en el archivo de texto.

6. Guarde el archivo de texto y así lo asigne un nombre `AeD Diagnostic Info YYYY.MM.DD` parecido (por ejemplo, `AeD Diagnostic Info 2020.11.03` ).

Después de revisar el archivo y redactar información confidencial, envíelo al ingeniero de soporte técnico de Microsoft que trabaja en su caso.