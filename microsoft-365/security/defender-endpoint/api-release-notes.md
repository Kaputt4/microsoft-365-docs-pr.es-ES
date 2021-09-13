---
title: Notas de la versión de api de Microsoft Defender para endpoint
description: Notas de la versión de las actualizaciones realizadas en el conjunto de API de Microsoft Defender para endpoint.
keywords: Notas de la versión de la API de Microsoft Defender para Endpoint, mde, API, Microsoft Defender para la API de endpoint, actualizaciones, notas, versión
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b547103902a4c4329953ea2fe7aa77b9ee471e1d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59165763"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Notas de la versión de api de Microsoft Defender para endpoint

**Se aplica a:** [Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

La siguiente información enumera las actualizaciones realizadas en Microsoft Defender para las API de punto de conexión y las fechas en que se realizaron.

> [!TIP]
> Fuente RSS: recibe una notificación cuando se actualiza esta página copiando y pegando la siguiente dirección URL en el lector de fuentes:
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Notas de la versión: más reciente a más antigua (dd.mm.yyyyy)

### <a name="06102021"></a>06.10.2021

- Se agregó el nuevo método de la API de evaluación de exportación: evaluación de vulnerabilidades de software de _exportación delta (respuesta JSON) Exportar_ métodos de evaluación y propiedades por [dispositivo.](get-assessment-methods-properties.md)

### <a name="05252021"></a>05.25.2021

- Se agregaron nuevos métodos y propiedades de evaluación de exportación de API [por dispositivo.](get-assessment-methods-properties.md)

### <a name="03052021"></a>03.05.2021

- Se agregó una nueva API: [Propiedades y métodos de actividad de corrección.](get-remediation-methods-properties.md)

### <a name="10022021"></a>10.02.2021

- Se agregó una nueva API: [Alertas de actualización por lotes](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- Limitaciones de velocidad actualizadas para [la API de](run-advanced-query-api.md) búsqueda avanzada de 15 a 45 solicitudes por minuto.

### <a name="21012021"></a>21.01.2021

- Se agregó una nueva API: [Buscar dispositivos por etiqueta.](machine-tags.md)
- Se agregó una nueva API: [Importar indicadores](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Evidencia de alerta actualizada: se agregaron ***detectionStatus** _, _*_parentProcessFilePath_*_ y _ *_parentProcessFileName_** propiedades.
- Entidad [Alert actualizada:](alerts.md)se agregó ***la propiedad detectorId.***

### <a name="15122020"></a>15.12.2020

- Entidad [Device](machine.md) actualizada: lista ***de IpInterfaces*** agregada. Consulte [Enumerar dispositivos](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Se agregó una nueva API: [Establecer el valor del dispositivo](set-device-value.md).
- Entidad [Device](machine.md) actualizada: se agregó ***la propiedad deviceValue.***

### <a name="01092020"></a>01.09.2020

- Se agregó la opción para expandir la entidad Alert con su evidencia relacionada. Vea [Enumerar alertas](get-alerts.md).
