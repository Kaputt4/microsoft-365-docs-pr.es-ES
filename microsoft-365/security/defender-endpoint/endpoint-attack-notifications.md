---
title: Notificaciones de ataque de punto de conexión
ms.reviewer: ''
description: Las notificaciones de ataque de punto de conexión proporcionan búsqueda proactiva de las amenazas más importantes para la red.
keywords: Notificación de ataque de punto de conexión, búsqueda de amenazas administrada, servicio de detección y respuesta administrada (MDR), MTE, Expertos en amenazas de Microsoft, notificación de ataque de punto de conexión, Pregunte a expertos de Defender, expertos a petición
search.product: Windows 10
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: fbe9bc01c5006d45a3f3a55c36525294009eb5ba
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68542505"
---
# <a name="endpoint-attack-notifications"></a>Notificaciones de ataque de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Esto cubre la búsqueda de amenazas en el servicio de Microsoft Defender para punto de conexión. Sin embargo, si está interesado en explorar el servicio más allá de la licencia actual y buscar amenazas de forma proactiva no solo en puntos de conexión, sino también en Office 365, aplicaciones en la nube e identidad, consulte [expertos en Microsoft Defender para la búsqueda](/microsoft-365/security/defender/defender-experts-for-hunting). 

Las notificaciones de ataque de punto de conexión (anteriormente conocidas como Expertos en amenazas de Microsoft: notificación de ataque dirigido) proporcionan búsqueda proactiva de las amenazas más importantes para la red, incluidas intrusiones de adversarios humanos, ataques prácticos con teclado o ataques avanzados, como el ciberespionaje. Estas notificaciones se muestran como una nueva alerta. El servicio de búsqueda administrada incluye:

- Supervisión y análisis de amenazas, lo que reduce el tiempo de permanencia y el riesgo para la empresa
- Inteligencia artificial entrenada por hunter para detectar y priorizar ataques conocidos y desconocidos
- Identificar los riesgos más importantes, ayudar a los SOC a maximizar el tiempo y la energía
- Ámbito de riesgo y tanto contexto como se pueda entregar rápidamente para habilitar una respuesta soc rápida


![Captura de pantalla de la alerta de notificaciones de ataque de punto de conexión](../../media/defender-endpoint/endpoint-attack-notification-alert.png)

## <a name="apply-for-endpoint-attack-notifications"></a>Solicitar notificaciones de ataque de punto de conexión
Si es un cliente Microsoft Defender para punto de conexión, puede solicitar notificaciones de ataque de punto de conexión. Vaya a **Configuración** \> **Puntos de conexión** **Características** \> **avanzadas** \> generales \> **Notificaciones de ataque de punto de conexión** para aplicar. Una vez aceptado, obtendrá las ventajas de las notificaciones de ataque de punto de conexión.

![Habilitación de las notificaciones de ataque de punto de conexión en el portal de 365 Defender](../../media/defender-endpoint/enable-endpoint-attack-notifications.png)

## <a name="receive-endpoint-attack-notifications"></a>Recibir notificaciones de ataque de punto de conexión
Las notificaciones de ataque de punto de conexión son alertas creadas a mano por el servicio de búsqueda administrada de Microsoft en función de la actividad sospechosa en su entorno. Se pueden ver a través de varios medios:
- Cola de alertas en el portal de Microsoft 365 Defender
- Uso de la [API](../../security/defender-endpoint/get-alerts.md)
- [Tabla DeviceAlertEvents](../../security/defender-endpoint/advanced-hunting-devicealertevents-table.md) en búsqueda avanzada
- El correo electrónico si [configura una regla de notificaciones por correo electrónico](../../security/defender-endpoint/configure-email-notifications.md)


Las notificaciones de ataque de punto de conexión se pueden identificar mediante:
- Tener una etiqueta denominada **Notificación de ataque de punto de conexión**
- Tener un origen de servicio de **expertos** \> **Microsoft Defender Microsoft Defender para punto de conexión**

> [!NOTE]
> Si se ha inscrito para las notificaciones de ataque de punto de conexión pero no ve ninguna alerta del servicio, indica que tiene una posición de seguridad fuerte y que es menos propenso a ataques.

## <a name="create-an-email-notification-rule"></a>Creación de una regla de notificación por correo electrónico
Puede crear reglas para enviar notificaciones por correo electrónico para los destinatarios de notificaciones. Consulte [Configuración de notificaciones de alerta](configure-email-notifications.md) para crear, editar, eliminar o solucionar problemas de notificaciones por correo electrónico para obtener más información.


## <a name="next-steps"></a>Pasos siguientes
- Para preguntar directamente a los expertos de Defender desde el portal de Microsoft Defender para punto de conexión información sobre ciertas notificaciones de punto de conexión, consulte [Preguntar a expertos de Defender](../defender-endpoint/experts-on-demand.md).
- Para buscar amenazas de forma proactiva entre puntos de conexión, Office 365, aplicaciones en la nube e identidad, consulte [expertos de Microsoft Defender para la búsqueda](../defender/defender-experts-for-hunting.md).
