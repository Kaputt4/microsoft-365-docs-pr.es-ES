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
description: Los administradores pueden aprender a usar el widget Colas en el panel flujo de correo del Centro de seguridad y cumplimiento de & para supervisar el flujo de correo fallido a sus organizaciones locales o asociadas a través de conectores salientes.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 62da2d9654174bc2572a6d7cbb3acbd638757a6c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469479"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Información sobre colas en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Cuando los mensajes no se pueden enviar desde su organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se ponen en cola en Microsoft 365. Algunos ejemplos comunes que causan esta condición son:

- El conector está configurado incorrectamente.
- Ha habido cambios de red o firewall en el entorno local.

Microsoft 365 volverá a intentar la entrega durante 24 horas. Después de 24 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDR o mensajes de devolución).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 200 mensajes), la información estará disponible en las siguientes ubicaciones:

- Información **sobre colas en** el panel [Flujo de correo](mail-flow-insights-v2.md) del [Centro de seguridad & cumplimiento](https://protection.office.com). Para obtener más información, vea la sección [Queues insight en la sección Panel de flujo de correo](#queues-insight-in-the-mail-flow-dashboard) de este artículo.

- Una alerta se muestra en **Alertas** recientes en el panel Alertas del [Centro de seguridad & cumplimiento](https://protection.office.com) (**Panel de** \> **alertas** o <https://protection.office.com/alertsdashboard>).

  :::image type="content" source="../../media/mfi-queued-messages-alert.png" alt-text="Las alertas recientes en el panel De alertas del Centro de seguridad y & cumplimiento" lightbox="../../media/mfi-queued-messages-alert.png":::


- Los administradores recibirán una notificación por correo electrónico en función de la configuración de la directiva de alerta predeterminada denominada **Mensajes que se han retrasado**. Para configurar las opciones de notificación de esta alerta, consulte la siguiente sección.

  Para obtener más información acerca de las directivas de alerta, vea [Directivas de alerta en el Centro de seguridad & cumplimiento](../../compliance/alert-policies.md).

## <a name="customize-queue-alerts"></a>Personalizar alertas de cola

1. En el [Centro de & cumplimiento](https://protection.office.com), vaya a **Directivas de** \> **alertas o** abra <https://protection.office.com/alertpolicies>.

2. En la **página Directivas de** alerta, busque y seleccione la directiva denominada **Mensajes que se ha retrasado**.

3. En el **menú desplegable Mensaje se ha** retrasado que se abre, puede activar o desactivar la alerta y configurar las opciones de notificación.

   :::image type="content" source="../../media/mfi-queued-messages-alert-policy.png" alt-text="Los detalles de la alerta mensajes se han retrasado" lightbox="../../media/mfi-queued-messages-alert-policy.png":::

   - **Estado**: puede activar o desactivar la alerta.

   - **Destinatarios de correo electrónico** y **límite de notificaciones diarias**: haga clic **en Editar** para configurar las siguientes opciones:

4. Para configurar las opciones de notificación, haga clic en **Editar**. En el **control desplegable Editar** directiva que aparece, configure las siguientes opciones:

   - **Enviar notificaciones por correo** electrónico: el valor predeterminado está en.
   - **Destinatarios de correo** electrónico: el valor predeterminado es **TenantAdmins**.
   - **Límite de notificación diario**: el valor predeterminado **es No limit**.
   - **Umbral**: el valor predeterminado es 200.

     :::image type="content" source="../../media/mfi-queued-messages-alert-policy-notification-settings.png" alt-text="La configuración de notificación de la alerta Mensajes se ha retrasado" lightbox="../../media/mfi-queued-messages-alert-policy-notification-settings.png":::

5. Cuando haya terminado, haga clic en **Guardar** y **cerrar**.

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Información sobre colas en el panel flujo de correo

Incluso si el volumen de mensajes en cola no ha superado el umbral y ha generado una alerta, puede usar la información de  colas en el panel flujo [](mail-flow-insights-v2.md) de correo para ver los mensajes que se han puesto en cola durante más de una hora y realizar acciones antes de que el número de mensajes en cola sea demasiado grande.

:::image type="content" source="../../media/mfi-queues-widget.png" alt-text="El widget Colas en el panel Flujo de correo del Centro de seguridad & cumplimiento" lightbox="../../media/mfi-queues-widget.png":::

Si hace clic en el número de mensajes del widget, aparecerá **un control flotante** Mensajes en cola con la siguiente información:

- **Número de mensajes en cola**
- **Nombre del conector**: seleccione el nombre del conector para administrar el conector en el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com/#/connectors>.
- **Hora de inicio de cola**
- **Mensajes más antiguos expirados**
- **Servidor de destino**
- **Última dirección IP**
- **Último error**
- **Cómo corregir**: hay problemas y soluciones comunes disponibles. Si un **vínculo Corregir ahora** está disponible, haga clic en él para solucionar el problema. De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.

:::image type="content" source="../../media/mfi-queues-details.png" alt-text="Detalles después de hacer clic en la información de colas en el panel flujo de correo" lightbox="../../media/mfi-queues-details.png":::

Se muestra el mismo menú desplegable después de hacer clic en **Ver cola** en los detalles de una alerta de retraso de **mensajes** .

:::image type="content" source="../../media/mfi-queued-messages-alert-details.png" alt-text="Los detalles de los mensajes se han retrasado en el Centro de seguridad & cumplimiento" lightbox="../../media/mfi-queued-messages-alert-details.png":::

## <a name="see-also"></a>Vea también

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
