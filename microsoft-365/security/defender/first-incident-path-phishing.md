---
title: Ejemplo de un ataque de correo electrónico de suplantación de identidad
description: Paso a paso por un análisis de ejemplo de un ataque de suplantación de identidad.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299993"
---
# <a name="example-of-a-phishing-email-attack"></a>Ejemplo de un ataque de correo electrónico de suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender puede ayudar a detectar datos adjuntos malintencionados entregados por correo electrónico. Dado que [el Centro](https://protection.office.com/) de seguridad y cumplimiento de Office 365 se integra con Microsoft 365 Defender, los analistas de seguridad pueden tener visibilidad de las amenazas procedentes de Office 365, como los datos adjuntos de correo electrónico.

Por ejemplo, a un analista se le asignó un incidente de varias fases.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Ejemplo de un incidente de varias fases"::: 

En la **pestaña** Alertas del incidente, se muestran las alertas de Defender Office 365 y Microsoft Cloud App Security. El analista puede profundizar en defender para obtener Office 365 mediante la selección de las alertas de mensajes de correo electrónico. Los detalles de la alerta se muestran en el panel lateral.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Ejemplo de una alerta de correo electrónico":::
 
Al desplazarse hacia abajo más adelante, se muestra más información, que muestra los archivos malintencionados y el usuario que se ha afectado.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Ejemplo de impacto de usuario y archivo de una alerta de correo electrónico":::
  
Al seleccionar **Abrir página de alertas,** selecciona el vínculo para ver la alerta específica en la que se puede ver información diversa con mayor detalle. El mensaje de correo electrónico real se puede ver seleccionando Ver **mensajes en el Explorador** hacia la parte inferior del panel.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Ejemplo de los detalles de una alerta"::: 

Esto lleva al analista a la página Administración de amenazas donde se muestran el asunto de correo electrónico, el destinatario, el remitente y otra información. **ZAP** en **Acciones especiales** indica al analista que se implementó la característica de purga automática de hora cero. ZAP detecta y quita automáticamente mensajes malintencionados y de correo no deseado de los buzones de toda la organización. Para obtener más información, vea [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).

Otras acciones se pueden realizar en mensajes específicos seleccionando **Acciones**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Ejemplo de las otras acciones que se pueden realizar en los mensajes de correo electrónico"::: 

## <a name="next-step"></a>Paso siguiente

Consulta la [ruta de investigación de ataques basada](first-incident-path-identity.md) en identidades.

## <a name="see-also"></a>Consulte también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
