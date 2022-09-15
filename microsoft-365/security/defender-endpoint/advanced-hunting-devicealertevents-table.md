---
title: Tabla DeviceAlertEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla DeviceAlertEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, mdatp, atp de microsoft defender, microsoft defender para punto de conexión, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, DeviceAlertEvents, alerta, gravedad, categoría
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 00e794bd5fd2dec783fdbfcf05e84f919369a5a0
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67695869"
---
# <a name="devicealertevents"></a>DeviceAlertEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> Las `AlertInfo` tablas y `AlertEvidence` reemplazan la `DeviceAlertEvents` tabla en el esquema de Microsoft Defender para punto de conexión. Para obtener más información, consulte [Map DeviceAlertEvents Table](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceAlertEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas de Microsoft 365 Defender. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte [la referencia del esquema de búsqueda avanzada](advanced-hunting-schema-reference.md).

|Nombre de columna|Tipo de datos|Descripción|
|---|---|---|
|`AlertId`|string|Identificador único de alerta.|
|`Timestamp`|datetime|Fecha y hora en que se registró el evento.|
|`DeviceId`|cadena|Identificador único del dispositivo en el servicio|
|`DeviceName`|string|Nombre de dominio completo (FQDN) del dispositivo|
|`Severity`|cadena|El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta.|
|`Category`|cadena|Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta|
|`Title`|cadena|Título de la alerta.|
|`FileName`|cadena|Nombre del archivo donde se aplicó la acción registrada|
|`SHA1`|cadena|SHA-1 del archivo donde fue aplicada la acción registrada|
|`RemoteUrl`|cadena|La dirección URL o el nombre de dominio completo (FQDN, según sus siglas en inglés) en el cual se ha estado conectado.|
|`RemoteIP`|cadena|Dirección IP a la que se ha conectado|
|`AttackTechniques`|string|MITRE ATT&técnicas de CK asociadas a la actividad que desencadenó la alerta|
|`ReportId`|largo|Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse con las `DeviceName` columnas y `Timestamp` .|
|`Table`|cadena|Tabla con el contenido detallado del evento|

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
