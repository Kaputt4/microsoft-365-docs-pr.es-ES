---
title: notas de la versión de la API de Microsoft Defender para punto de conexión
description: Notas de la versión de las actualizaciones realizadas en el conjunto Microsoft Defender para punto de conexión de API.
keywords: Microsoft Defender para punto de conexión notas de la versión de la API, mde, API, API de Microsoft Defender para punto de conexión, actualizaciones, notas, versión
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: e59cfc0058a2ad767238f5da0c5ab0cd60aae804
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67322809"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>notas de la versión de la API de Microsoft Defender para punto de conexión

**Se aplica a:** 
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

En la información siguiente se enumeran las actualizaciones realizadas en las API de Microsoft Defender para punto de conexión y las fechas en que se realizaron.

> [!TIP]
> Fuente RSS: para recibir notificaciones cuando esta página se actualice, copie y pegue la dirección URL siguiente en el lector de fuentes: 
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Notas de la versión: más reciente a más antigua (dd.mm.aaaa)

### <a name="08082022"></a>08.08.2022

- Se ha agregado el nuevo método Export Device Health API: GET /api/public/avdevicesHealth [Export device health methods and properties](device-health-api-methods-properties.md)

### <a name="06102021"></a>06.10.2021

- Se ha agregado un nuevo método de API de evaluación de exportación: _evaluación de vulnerabilidades de software de Delta Export (respuesta JSON)_ [Métodos de evaluación de exportación y propiedades por dispositivo](get-assessment-methods-properties.md).

### <a name="05252021"></a>05.25.2021

- Se han agregado nuevos [métodos y propiedades de evaluación de exportación de API por dispositivo](get-assessment-methods-properties.md).

### <a name="03052021"></a>03.05.2021

- Se ha agregado una nueva API: [propiedades y métodos de actividad de corrección](get-remediation-methods-properties.md).

### <a name="10022021"></a>10.02.2021

- Se ha agregado una nueva API: [alertas de actualización por lotes](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- Se han actualizado las limitaciones de velocidad de [Advanced Hunting API](run-advanced-query-api.md) de 15 a 45 solicitudes por minuto.

### <a name="21012021"></a>21.01.2021

- Se ha agregado una nueva API: [Buscar dispositivos por etiqueta](machine-tags.md).
- Se ha agregado una nueva API: [Indicadores de importación](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Evidencia de alerta actualizada: se agregaron las propiedades ***detectionStatus** _, _*_parentProcessFilePath_*_ y _ *_parentProcessFileName_**.
- Entidad [Alert](alerts.md) actualizada: se agregó la propiedad ***detectorId*** .

### <a name="15122020"></a>15.12.2020

- Entidad [device](machine.md) actualizada: se ha agregado ***la lista IpInterfaces*** . Consulte [Lista de dispositivos](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Se ha agregado una nueva API: [establezca el valor del dispositivo](set-device-value.md).
- Entidad [Device](machine.md) actualizada: se agregó la propiedad ***deviceValue*** .

### <a name="01092020"></a>01.09.2020

- Se ha agregado la opción para expandir la entidad Alert con su evidencia relacionada. Consulte [Lista de alertas](get-alerts.md).
