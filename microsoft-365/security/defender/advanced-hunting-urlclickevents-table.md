---
title: Tabla UrlClickEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre cómo buscar campañas de phishing y clics sospechosos mediante la tabla UrlClickEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, UrlClickEvents, SafeLinks, phishing, malware, clics malintencionados, outlook, teams, correo electrónico, office365
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 068e083321b465410df9e734660344c03e6b55ce
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67476052"
---
# <a name="urlclickevents"></a>UrlClickEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para Office 365


La `UrlClickEvents` tabla del esquema de búsqueda avanzada contiene información sobre los clics de [vínculos seguros](../office-365-security/safe-links.md) de mensajes de correo electrónico, Microsoft Teams y Office 365 aplicaciones en aplicaciones de escritorio, móviles y web compatibles. 

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que el usuario ha hecho clic en el vínculo |
| `Url` | `string` | Dirección URL completa en la que hizo clic el usuario |
| `ActionType` | `string` | Indica si vínculos seguros permitieron o bloquearon el clic debido a una directiva de inquilino, por ejemplo, en la lista Permitir bloque de inquilinos.|
| `AccountUpn` | `string` | Nombre principal de usuario de la cuenta en la que se ha hecho clic en el vínculo|
| `Workload` | `string` | La aplicación desde la que el usuario ha hecho clic en el vínculo, con los valores Email, Office y Teams|
| `NetworkMessageId` | `string` | Identificador único del correo electrónico que contiene el vínculo en el que se ha hecho clic, generado por Microsoft 365|
| `IPAddress` | `string` | Dirección IP pública del dispositivo desde el que el usuario ha hecho clic en el vínculo|
| `ThreatTypes` | `string` | Veredicto en el momento de hacer clic, que indica si la dirección URL condujo a malware, phish u otras amenazas|
| `DetectionMethods` | `string` | Tecnología de detección que se usó para identificar la amenaza en el momento de hacer clic|
| `IsClickedThrough` | `bool` | Indica si el usuario pudo hacer clic en la dirección URL original o no se permitió|
| `UrlChain` | `string` | En escenarios que implican redireccionamientos, incluye direcciones URL presentes en la cadena de redireccionamiento.|
| `ReportId` | `string` | Este es el identificador único de un evento click. Tenga en cuenta que, para escenarios de clickthrough, el identificador de informe tendría el mismo valor y, por lo tanto, se debe usar para correlacionar un evento click.|

Puede probar esta consulta de ejemplo que usa la `UrlClickEvents` tabla para devolver una lista de vínculos en los que se permitió a un usuario continuar: 

```kusto
// Search for malicious links where user was allowed to proceed through
UrlClickEvents
| where ActionType == "ClickAllowed" or IsClickedThrough !="0"
| where ThreatTypes has "Phish"
| summarize by ReportId, IsClickedThrough, AccountUpn, NetworkMessageId, ThreatTypes, Timestamp
```

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Vínculos seguros en Microsoft Defender para Office 365](../office-365-security/safe-links.md)
- [Realizar acciones en los resultados de consultas de búsqueda avanzadas](advanced-hunting-take-action.md)