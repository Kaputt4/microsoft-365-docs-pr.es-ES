---
title: Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365
description: Introducción a la búsqueda de amenazas de correo electrónico mediante la búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965153"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Ejemplo de búsqueda avanzada para Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

¿Quiere empezar a buscar amenazas para correos electrónicos mediante la búsqueda avanzada de amenazas? Pruebe esto:

La sección [Introducción](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) del [artículo de Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tiene fragmentos lógicos de configuración temprana que tienen este aspecto:

1. Configure todo con 'Anti' en el nombre.
   - Antimalware
   - Anti-phishing
   - Contra correo electrónico no deseado
2. Configure todo con "Caja fuerte" en el nombre.
   - Vínculos seguros
   - Archivos adjuntos seguros
3. Defender las cargas de trabajo (ej. SharePoint Online, OneDrive y Teams).
4. Proteger con purga automática de cero horas.

Junto con un [vínculo](../office-365-security/protect-against-threats.md) para entrar directamente y establecer la configuración el primer día.

El último paso de la **Introducción** es proteger a los usuarios con la **Purga automática**, también conocida como ZAP. Puede ser muy importante saber si sus esfuerzos para purgar de manera automática correos electrónicos sospechosos o malintencionados, tras el envío, han tenido éxito.

Poder ir rápidamente al lenguaje de consulta Kusto para buscar problemas es una ventaja de unificar estos dos centros de seguridad. Los equipos de seguridad pueden supervisar las pérdidas de ZAP si toman sus siguientes pasos [aquí](https://security.microsoft.com/advanced-hunting), en **Hunting** \> **Advanced Hunting**.

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

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La página Búsqueda avanzada (en Búsqueda) con Consulta seleccionada en la parte superior del panel de consulta y ejecutando una consulta kusto para capturar acciones de ZAP en los últimos 7 días.":::

Los datos de esta consulta aparecerán en el panel de resultados bajo la propia consulta. Los resultados incluyen información como "DeviceName", "AccountDisplayName" y "ZapTime" en un conjunto de resultados que se puede personalizar. Los resultados también se pueden exportar para sus registros. Si se trata de una consulta que volverá a necesitar, seleccione **Guardar** > **Guardar como** y agregue la consulta a su lista de consultadas, compartidas o consultas de comunidad.

## <a name="related-information"></a>Información relacionada
- [Procedimientos recomendados de búsqueda avanzada](advanced-hunting-best-practices.md)
- [Información general: búsqueda avanzada](advanced-hunting-overview.md)
