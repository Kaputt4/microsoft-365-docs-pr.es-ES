---
title: Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)
description: Proporciona instrucciones para operacionalizar la implementación de reglas de reducción de superficie expuesta a ataques.
keywords: Implementación de reglas de reducción de superficie expuesta a ataques, implementación de ASR, habilitación de reglas de asr, configuración de ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades de seguridad, protección contra vulnerabilidades de seguridad, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas asr
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- M365-security-compliance
- m365solution-asr-rules
- highpri
ms.date: 1/18/2022
search.appverid: met150
ms.openlocfilehash: f81d453a6bd1b8d63031c903fc264010fc070209
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698427"
---
# <a name="operationalize-attack-surface-reduction-asr-rules"></a>Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)

Una vez que haya implementado completamente las reglas de reducción de la superficie expuesta a ataques (ASR), es fundamental que tenga procesos en su lugar para supervisar y responder a las actividades relacionadas con ASR.

## <a name="managing-false-positives"></a>Administración de falsos positivos

Los falsos positivos o negativos pueden producirse con cualquier solución de protección contra amenazas. Los falsos positivos son casos en los que una entidad (como un archivo o proceso) se detecta y se identifica como malintencionada, aunque la entidad no es realmente una amenaza. Por el contrario, un falso negativo es una entidad que no se detectó como una amenaza, sino que es malintencionada. Para obtener más información sobre los falsos positivos y los falsos negativos, vea: [Abordar los falsos positivos o negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)

## <a name="keeping-up-with-reports"></a>Mantenerse al día con los informes

La revisión constante y periódica de los informes es un aspecto esencial para mantener la implementación de las reglas de ASR y mantenerse al día de las amenazas recién emergentes. Su organización debe tener revisiones programadas de eventos de reglas de ASR con una cadencia que se mantendrá actualizada con los eventos notificados por reglas de ASR. En función del tamaño de la organización, las revisiones pueden ser diarias, por hora o de supervisión continua.

## <a name="hunting"></a>Búsqueda

Una de las características más eficaces de [Microsoft 365 Defender](https://security.microsoft.com) es la búsqueda avanzada. Si no está familiarizado con la búsqueda avanzada, consulte Búsqueda [proactiva de amenazas con la búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting2.png" alt-text="Página Búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="images/asr-defender365-advanced-hunting2.png":::

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas (Lenguaje de consulta Kusto) que le permite explorar hasta 30 días de los datos capturados (sin procesar) que la detección y respuesta de puntos de conexión de ATP de Microsoft Defender (EDR) recopila de todas las máquinas. Mediante la búsqueda avanzada, puede inspeccionar eventos de forma proactiva con el fin de localizar indicadores y entidades interesantes. El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.

Mediante la búsqueda avanzada, es posible extraer información de reglas de ASR, crear informes y obtener información detallada sobre el contexto de un evento de bloque o auditoría de reglas de ASR determinado.

 Puede consultar eventos de reglas de ASR desde la tabla DeviceEvents en la sección búsqueda avanzada del portal de Microsoft 365 Defender. Por ejemplo, una consulta simple como la siguiente puede notificar todos los eventos que tienen reglas ASR como origen de datos, durante los últimos 30 días, y los resumirá por el recuento ActionType, que en este caso será el nombre de código real de la regla ASR.

Los eventos ASR que se muestran en el portal de búsqueda de avance están limitados a procesos únicos que se ven cada hora. La hora del evento ASR es la primera vez que se ve el evento en esa hora.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting3.png" alt-text="Línea de comandos de consulta de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="images/asr-defender365-advanced-hunting3.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4.png" alt-text="La consulta de búsqueda avanzada da como resultado el portal de Microsoft 365 Defender" lightbox="images/asr-defender365-advanced-hunting4.png":::

Lo anterior muestra que se registraron 187 eventos para AsrLsassCredentialTheft:

- 102 para bloqueado
- 85 para auditados
- 2 eventos para AsrOfficeChildProcess (1 para Auditado y 1 para Block)
- 8 eventos para AsrPsexecWmiChildProcessAudited

Si desea centrarse en la regla AsrOfficeChildProcess y obtener detalles sobre los archivos y procesos reales implicados, cambie el filtro de ActionType y reemplace la línea de resumen por una proyección de los campos deseados (en este caso son DeviceName, FileName, FolderPath, etc.).

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4b.png" alt-text="Ejemplo centrado en consultas de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="images/asr-defender365-advanced-hunting4b.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting5b.png" alt-text="Los resultados centrados en la consulta de búsqueda avanzada en el portal de Microsoft 365 Defender" lightbox="images/asr-defender365-advanced-hunting5b.png":::

La verdadera ventaja de la búsqueda avanzada es que puede dar forma a las consultas a su gusto. Al dar forma a la consulta, puede ver la historia exacta de lo que estaba ocurriendo, independientemente de si desea identificar algo en una máquina individual o si desea extraer información de todo el entorno.

Para obtener más información sobre las opciones de búsqueda, vea: [Desmitificar las reglas de reducción de superficie expuesta a ataques: Parte 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968).

## <a name="topics-in-this-deployment-collection"></a>Temas de esta colección de implementación

[Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment.md)

[Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-plan.md)

[Probar las reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-test.md)

[Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-implement.md)

[Referencia de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-reference.md)
