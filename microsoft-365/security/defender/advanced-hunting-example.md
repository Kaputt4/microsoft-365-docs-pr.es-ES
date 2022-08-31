---
title: Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365
description: Introducción a la búsqueda de amenazas por correo electrónico mediante la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 014802107d564fc24cf5e50a7513c390dcc943d5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480070"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

¿Quiere empezar a buscar amenazas para correos electrónicos mediante la búsqueda avanzada de amenazas? Pruebe esto:

La sección [Introducción](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) del [artículo de Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tiene fragmentos lógicos de configuración temprana que tienen este aspecto:

1. Configure todo con "Anti" en el nombre.
   - Antimalware
   - Protección contra la suplantación de identidad (anti-phishing)
   - Contra correo electrónico no deseado
2. Configure todo con "Safe" en el nombre.
   - Vínculos seguros
   - Archivos adjuntos seguros
3. Defender las cargas de trabajo (ej. SharePoint Online, OneDrive y Teams).
4. Proteja con la purga automática de cero horas.

Junto con un [vínculo](../office-365-security/protect-against-threats.md) para entrar directamente y establecer la configuración el primer día.

El último paso de la **Introducción** es proteger a los usuarios con la **Purga automática**, también conocida como ZAP. Puede ser muy importante saber si sus esfuerzos para purgar de manera automática correos electrónicos sospechosos o malintencionados, tras el envío, han tenido éxito.

Poder ir rápidamente al lenguaje de consulta Kusto para buscar problemas es una ventaja de unificar estos dos centros de seguridad. Los equipos de seguridad pueden supervisar los errores de ZAP si realizan sus pasos siguientes [aquí](https://security.microsoft.com/advanced-hunting), en **Búsqueda** **de búsqueda**\> avanzada.

1. En la página Búsqueda avanzada, haga clic en **Consulta**.
1. Copie la consulta siguiente en la ventana de consulta:
1. Seleccione **Ejecutar consulta**.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/ah-query-example-new.png" alt-text="La página Búsqueda avanzada (en Búsqueda) con Consulta seleccionada en la parte superior del panel de consulta y ejecutando una consulta kusto para capturar acciones ZAP en los últimos 7 días." lightbox="../../media/ah-query-example-new.png":::

Los datos de esta consulta aparecerán en el panel de resultados bajo la propia consulta. Los resultados incluyen información como "DeviceName", "AccountDisplayName" y "ZapTime" en un conjunto de resultados que se puede personalizar. Los resultados también se pueden exportar para sus registros. Si se trata de una consulta que volverá a necesitar, seleccione **Guardar** > **Guardar como** y agregue la consulta a su lista de consultadas, compartidas o consultas de comunidad.

## <a name="related-information"></a>Información relacionada
- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Información general: Búsqueda avanzada](advanced-hunting-overview.md)
