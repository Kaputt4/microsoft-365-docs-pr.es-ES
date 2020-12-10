---
title: Pone en cola información en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden aprender a usar el widget colas del panel de flujo de correo en el centro de seguridad & cumplimiento para supervisar el flujo de correo incorrecto hacia sus organizaciones locales o de asociados a través de los conectores de salida.
ms.openlocfilehash: c582a7f459d89fa1515713c4f55dea14b619a6ec
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616397"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Pone en cola información en el centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Cuando los mensajes no se pueden enviar desde la organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se colocan en la cola de Microsoft 365. Algunos ejemplos comunes que causan esta condición son:

- El conector está configurado incorrectamente.
- Ha habido cambios en la red o en el firewall en su entorno local.

Microsoft 365 seguirá reintentando la entrega durante 24 horas. Transcurridas las 24 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDR o mensajes de devolución).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es de 200 mensajes), la información está disponible en las siguientes ubicaciones:

- Las **colas** profundizan en el [panel del flujo de correo](mail-flow-insights-v2.md) en el [centro de seguridad & cumplimiento](https://protection.office.com). Para obtener más información, vea la información [sobre las colas en la sección panel de flujo de correo](#queues-insight-in-the-mail-flow-dashboard) de este tema.

- Se muestra una alerta en el panel de alertas del centro de [seguridad & cumplimiento](https://protection.office.com) (panel de **alertas** o) en **Alerts recents** \>  <https://protection.office.com/alertsdashboard> .

  ![Alertas recientes en el panel de alertas del centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert.png)

- Los administradores recibirán una notificación de correo electrónico basada en la configuración de la Directiva de alertas predeterminada denominada **mensajes que se han retrasado**. Para establecer la configuración de las notificaciones para esta alerta, consulte la siguiente sección.

  Para obtener más información acerca de las directivas de alertas, consulte [directivas de alerta en el centro de seguridad & cumplimiento](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Personalizar alertas de cola

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a directivas de alerta de **alertas** \>  o abrir <https://protection.office.com/alertpolicies> .

2. En la página **directivas de alerta** , busque y seleccione la Directiva denominada **mensajes que se han retrasado**.

3. En el **mensaje se ha retrasado** el control flotante que se abre, puede activar o desactivar la alerta y configurar las opciones de notificación.

   ![Los mensajes se han retrasado de la Directiva de alerta detalles del centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy.png)

   - **Estado**: puede activar o desactivar la alerta.

   - **Destinatarios de correo electrónico** y **límite de notificaciones diarias**: haga clic en **Editar** para configurar las opciones siguientes:

4. Para establecer la configuración de las notificaciones, haga clic en **Editar**. En el control flotante **Editar Directiva** que aparece, configure las siguientes opciones:

   - **Enviar notificaciones por correo electrónico**: el valor predeterminado es activado.
   - **Destinatarios de correo electrónico**: el valor predeterminado es **TenantAdmins**.
   - **Límite de notificación diario**: el valor predeterminado es **sin límite**.
   - **Umbral**: el valor predeterminado es 200.

   ![La configuración de notificaciones en los mensajes se ha retrasado detalles de la Directiva de alerta el centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Cuando haya terminado, haga clic en **Guardar** y **cerrar**.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Pone en cola información en el panel de flujo de correo

Incluso si el volumen de mensajes en cola no ha superado el umbral y ha generado una alerta, puede usar la información de las **colas** del [panel del flujo de correo](mail-flow-insights-v2.md) para ver los mensajes que se han puesto en cola durante más de una hora y emprender acciones antes de que el número de mensajes en cola sea demasiado grande.

![Widget colas del panel flujo de correo en el centro de seguridad & cumplimiento](../../media/mfi-queues-widget.png)

Si hace clic en el número de mensajes del widget, aparece un control flotante **en cola de mensajes** con la siguiente información:

- **Número de mensajes en cola**
- **Nombre del conector**: haga clic en el nombre del conector para administrar el conector en el centro de administración de Exchange (EAC).
- **Tiempo de inicio de la cola**
- **Los mensajes más antiguos expiraron**
- **Servidor de destino**
- **Última dirección IP**
- **Último error**
- **Procedimiento para la corrección**: hay disponibles problemas y soluciones comunes. Si es un vínculo **arreglar ahora** está disponible, haga clic en él para solucionar el problema. De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.

![Detalles después de hacer clic en la información sobre las colas del panel flujo de correo](../../media/mfi-queues-details.png)

Se muestra el mismo control flotante después de hacer clic en **Ver cola** en los detalles de los **mensajes se han retrasado** la alerta.

![Se han retrasado los detalles de la alerta en el centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Vea también

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
