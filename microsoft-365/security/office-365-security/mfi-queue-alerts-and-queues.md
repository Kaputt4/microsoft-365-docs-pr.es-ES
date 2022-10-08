---
title: Información sobre colas en el panel flujo de correo
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.custom: ''
ms.localizationpriority: medium
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden aprender a usar el widget Colas en el panel Flujo de correo del Centro de cumplimiento de seguridad & para supervisar el flujo de correo incorrecto a sus organizaciones locales o asociadas a través de conectores salientes.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: a1f6a57a471430cedd934ccfc36f7e78fa356945
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68063934"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Información sobre colas en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cuando los mensajes no se pueden enviar desde su organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se ponen en cola en Microsoft 365. Los ejemplos comunes que provocan esta condición son:

- El conector está configurado incorrectamente.
- Se han producido cambios de red o firewall en el entorno local.

Microsoft 365 seguirá reintentar la entrega durante 24 horas. Después de 24 horas, los mensajes expirarán y se devolverán a los remitentes en los informes de no entrega (también conocidos como NDR o mensajes de devolución).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 200 mensajes), la información está disponible en las siguientes ubicaciones:

- Información sobre **colas** en el [panel Flujo de correo](mail-flow-insights-v2.md) del [Centro de cumplimiento de seguridad &](https://protection.office.com). Para obtener más información, consulte la [información sobre colas en la sección Panel de flujo de correo](#queues-insight-in-the-mail-flow-dashboard) de este artículo.

- Se muestra una alerta en **Alertas recientes** en el panel Alertas del [Centro de cumplimiento de seguridad &](https://protection.office.com) (**Panel de** **alertas** \> o <https://protection.office.com/alertsdashboard>).

  :::image type="content" source="../../media/mfi-queued-messages-alert.png" alt-text="Las alertas recientes del panel Alertas del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-queued-messages-alert.png":::

- Los administradores recibirán una notificación por correo electrónico basada en la configuración de la directiva de alerta predeterminada denominada **Mensajes que se han retrasado**. Para configurar las opciones de notificación de esta alerta, consulte la sección siguiente.

  Para obtener más información sobre las directivas de alerta, vea [Directivas de alerta en el Centro de cumplimiento de seguridad &](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Personalización de alertas de cola

1. En el [Centro de cumplimiento de seguridad &](https://protection.office.com), vaya a **Directivas de alertas** \> o abra . <https://protection.office.com/alertpolicies>

2. En la página **Directivas de alerta** , busque y seleccione la directiva denominada **Mensajes que se han retrasado**.

3. En el control flotante **Mensaje se ha retrasado que se** abre, puede activar o desactivar la alerta y configurar las opciones de notificación.

   :::image type="content" source="../../media/mfi-queued-messages-alert-policy.png" alt-text="Los detalles de la alerta de mensajes se han retrasado" lightbox="../../media/mfi-queued-messages-alert-policy.png":::

   - **Estado**: puede activar o desactivar la alerta.

   - **Email destinatarios** y **límite de notificaciones diarias**: haga clic en **Editar** para configurar las siguientes opciones:

4. Para configurar las opciones de notificación, haga clic en **Editar**. En el control flotante **Editar directiva** que aparece, configure los siguientes valores:

   - **Enviar notificaciones por correo electrónico**: el valor predeterminado está activado.
   - **Email destinatarios**: el valor predeterminado es **TenantAdmins**.
   - **Límite diario de notificaciones**: el valor predeterminado es **Sin límite**.
   - **Umbral**: el valor predeterminado es 200.

     :::image type="content" source="../../media/mfi-queued-messages-alert-policy-notification-settings.png" alt-text="La configuración de notificación de la alerta mensajes se ha retrasado" lightbox="../../media/mfi-queued-messages-alert-policy-notification-settings.png":::

5. Cuando haya terminado, haga clic en **Guardar** y **cerrar**.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Información sobre colas en el panel flujo de correo

Incluso si el volumen de mensajes en cola no ha superado el umbral y ha generado una alerta, puede seguir usando la información **colas** en el [panel flujo de correo](mail-flow-insights-v2.md) para ver los mensajes que se han puesto en cola durante más de una hora y tomar medidas antes de que el número de mensajes en cola sea demasiado grande.

:::image type="content" source="../../media/mfi-queues-widget.png" alt-text="Widget Colas en el panel Flujo de correo del Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-queues-widget.png":::

Si hace clic en el número de mensajes del widget, aparece un control flotante **Mensajes en cola** con la siguiente información:

- **Número de mensajes en cola**
- **Nombre del conector**: seleccione el nombre del conector para administrar el conector en el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com/#/connectors>.
- **Hora de inicio de la cola**
- **Mensajes más antiguos expirados**
- **Servidor de destino**
- **Última dirección IP**
- **Último error**
- **Solución:** hay disponibles problemas y soluciones comunes. Si hay disponible un vínculo **Corregir ahora** , haga clic en él para solucionar el problema. De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.

:::image type="content" source="../../media/mfi-queues-details.png" alt-text="Detalles después de hacer clic en la información de colas en el panel Flujo de correo" lightbox="../../media/mfi-queues-details.png":::

El mismo control flotante se muestra después de hacer clic en **Ver cola** en los detalles de una alerta **de mensajes retrasada** .

:::image type="content" source="../../media/mfi-queued-messages-alert-details.png" alt-text="Los detalles de la alerta de mensajes se han retrasado en el Centro de cumplimiento de seguridad &" lightbox="../../media/mfi-queued-messages-alert-details.png":::

## <a name="see-also"></a>Vea también

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
