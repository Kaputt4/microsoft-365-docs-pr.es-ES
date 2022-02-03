---
title: 'Implementación de reglas de reducción de superficie de ataque Fase 4: operativa'
description: Proporciona instrucciones para implementar las reglas de reducción de superficie de ataque.
keywords: Implementación de reglas de reducción de superficie de ataque, implementación de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades, anti exploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR
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
ms.collection: m365solution-scenario
ms.date: 1/18/2022
ms.openlocfilehash: 567a6b8c2793853fc5240a271e510bae6a561ba2
ms.sourcegitcommit: 726a72f135358603c2fde3f4067d834536e6deb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62327611"
---
# <a name="phase-4---operationalize"></a>Fase 4: operativa

Después de implementar completamente las reglas ASR, es fundamental que tenga procesos para supervisar y responder a las actividades relacionadas con ASR.

## <a name="manage-false-positives"></a>Administrar falsos positivos

Los falsos positivos/negativos pueden producirse con cualquier solución de protección contra amenazas. Los falsos positivos son casos en los que se detecta e identifica una entidad (como un archivo o un proceso) como malintencionada, aunque la entidad no es realmente una amenaza. En cambio, un falso negativo es una entidad que no se detectó como una amenaza pero que es malintencionada. Para obtener más información sobre falsos positivos y falsos negativos, vea: [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md)

## <a name="keeping-up-with-reports"></a>Mantenerse al día con los informes

La revisión periódica y coherente de los informes es un aspecto esencial para mantener la implementación de reglas ASR y mantenerse al tanto de las amenazas recién emergentes. Su organización debe tener revisiones programadas de los eventos de reglas ASR en una cadencia que se mantenga actualizada con los eventos notificados por reglas ASR. Según el tamaño de la organización, las revisiones pueden ser de supervisión diaria, por hora o continua.

## <a name="hunting"></a>Búsqueda

Una de las características más eficaces de [Microsoft 365 Defender](https://security.microsoft.com) es la búsqueda avanzada. Si no estás familiarizado con la búsqueda avanzada, consulta: [Búsqueda proactiva de amenazas con búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender búsqueda avanzada](images/asr-defender365-advanced-hunting2.png)

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas (Kusto Query Language) que le permite explorar hasta 30 días de los datos capturados (sin procesar) que Microsoft Defender ATP Endpoint Detection and Response (EDR) recopila de todas las máquinas. A través de la búsqueda avanzada, puede inspeccionar de forma proactiva los eventos con el fin de localizar indicadores y entidades interesantes. El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.

Mediante la búsqueda avanzada, es posible extraer información de reglas ASR, crear informes y obtener información detallada sobre el contexto de un evento de bloqueo o auditoría de regla ASR determinado.

 Puede consultar eventos de reglas ASR desde la tabla DeviceEvents en la sección de búsqueda avanzada del portal Microsoft 365 Defender web. Por ejemplo, una consulta sencilla, como la siguiente, puede informar de todos los eventos que tienen reglas ASR como origen de datos durante los últimos 30 días y los resumirá mediante el recuento ActionType, que en este caso será el nombre de código real de la regla ASR.

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender línea de comandos consulta de búsqueda avanzada](images/asr-defender365-advanced-hunting3.png)

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender de consulta de búsqueda avanzada](images/asr-defender365-advanced-hunting4.png)

Lo anterior muestra que se registraron 187 eventos para AsrLsassCredentialTheft:

- 102 para bloqueado
- 85 para auditados
- 2 eventos para AsrOfficeChildProcess (1 para Auditado y 1 para Bloque)
- 8 eventos para AsrPsexecWmiChildProcessAudited

Si desea centrarse en la regla AsrOfficeChildProcess y obtener detalles sobre los archivos y procesos reales implicados, cambie el filtro de ActionType y reemplace la línea de resumen por una proyección de los campos deseados (en este caso son DeviceName, FileName, FolderPath, etc.).

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender consulta de búsqueda avanzada centrada](images/asr-defender365-advanced-hunting4b.png)

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender de búsqueda avanzada](images/asr-defender365-advanced-hunting5b.png)

La verdadera ventaja de la búsqueda avanzada es que puedes dar forma a las consultas a tu gusto. Al dar forma a la consulta, puede ver la historia exacta de lo que estaba sucediendo, independientemente de si desea identificar algo en una máquina individual o si desea extraer información de todo el entorno.

Para obtener más información acerca de las opciones de búsqueda, consulta: [Desmitificando](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968) reglas de reducción de superficie de ataque - Parte 3.

## <a name="topics-in-this-deployment-collection"></a>Temas de esta colección de implementación

[Introducción a la implementación de reglas de ASR](attack-surface-reduction-rules-deployment.md)

[Fase 1: Planificar](attack-surface-reduction-rules-deployment-plan.md)

[Fase 2: Probar](attack-surface-reduction-rules-deployment-test.md)

[Fase 3: Implementar](attack-surface-reduction-rules-deployment-implement.md)
