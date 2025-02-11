---
title: Ejemplo de ataque de correo electrónico de suplantación de identidad
description: Realice un análisis de ejemplo de un ataque de suplantación de identidad (phishing).
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
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
ms.openlocfilehash: bb7476a4608d7d89fa522529914a0f075311b8cd
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68297868"
---
# <a name="example-of-a-phishing-email-attack"></a>Ejemplo de ataque de correo electrónico de suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender puede ayudar a detectar datos adjuntos malintencionados que se entregan por correo electrónico y los analistas de seguridad pueden tener visibilidad sobre las amenazas procedentes de Office 365, como a través de datos adjuntos de correo electrónico.

Por ejemplo, a un analista se le asignó un incidente de varias fases.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Un incidente de varias fases" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-incident.png":::

En la pestaña **Alertas** del incidente, se muestran las alertas de Defender para Office 365 y Microsoft Defender for Cloud Apps. El analista puede explorar en profundidad las alertas de Defender para Office 365 seleccionando las alertas de mensajes de correo electrónico. Los detalles de la alerta se muestran en el panel lateral.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Una alerta de correo electrónico" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png":::
 
Al desplazarse más hacia abajo, se muestra más información, que muestra los archivos malintencionados y el usuario que se ha visto afectado.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Impacto de usuario y archivo de una alerta de correo electrónico" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-impact.png":::
  
Al seleccionar **abrir la página de alertas** , se le lleva a la alerta específica, donde se puede ver con mayor detalle información; para ello, seleccione el vínculo. Para ver el mensaje de correo electrónico real, seleccione **Ver mensajes en el Explorador** hacia la parte inferior del panel.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Detalles de una alerta" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png"::: 

Esto lleva al analista a la página Administración de amenazas donde se muestran el asunto del correo electrónico, el destinatario, el remitente y otra información. **ZAP** en **Acciones especiales** indica al analista que se implementó la característica de purga automática de hora cero. ZAP detecta y quita automáticamente los mensajes malintencionados y de correo no deseado de los buzones de correo de toda la organización. Para obtener más información, vea [Purga automática de hora cero (ZAP) en Exchange Online](../office-365-security/zero-hour-auto-purge.md).

Para realizar otras acciones en mensajes específicos, seleccione **Acciones**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Otras acciones que se pueden realizar en los mensajes de correo electrónico" lightbox="../../media/first-incident-path-phishing/first-incident-phishing-actions.png"::: 

## <a name="next-step"></a>Paso siguiente

Consulte la ruta [de acceso de investigación de ataques basada en identidades](first-incident-path-identity.md) .

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
