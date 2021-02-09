---
title: Información sobre colas en el panel de flujo de correo
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Los administradores pueden aprender a usar el widget Colas en el panel flujo de correo del Centro de seguridad & y cumplimiento para supervisar el flujo de correo fallido a sus organizaciones locales o asociadas a través de conectores salientes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94e8a1f3b54c3738c21e94ba85ae4f1d3f953498
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150176"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>Información de colas en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plan 1 y plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Cuando los mensajes no se pueden enviar desde su organización a los servidores de correo electrónico locales o asociados mediante conectores, los mensajes se ponen en cola en Microsoft 365. Algunos ejemplos comunes que provocan esta condición son:

- El conector no está configurado correctamente.
- Se han realizado cambios de red o firewall en el entorno local.

Microsoft 365 seguirá reintentar la entrega durante 24 horas. Después de 24 horas, los mensajes expirarán y se devolverán a los remitentes en informes de no entrega (también conocidos como NDRs o mensajes de devolución).

Si el volumen de correo electrónico en cola supera el umbral predefinido (el valor predeterminado es 200 mensajes), la información está disponible en las siguientes ubicaciones:

- La **información de colas** en el panel flujo de [correo](mail-flow-insights-v2.md) en el Centro de [& cumplimiento.](https://protection.office.com) Para obtener más información, vea la información [sobre colas en la sección del](#queues-insight-in-the-mail-flow-dashboard) panel de flujo de correo de este artículo.

- Se muestra una alerta en **alertas** recientes en el panel Alertas del Centro de [seguridad & cumplimiento](https://protection.office.com) (Panel **de** \> **alertas** o <https://protection.office.com/alertsdashboard> ).

  ![Alertas recientes en el panel alertas del Centro de & cumplimiento](../../media/mfi-queued-messages-alert.png)

- Los administradores recibirán una notificación por correo electrónico en función de la configuración de la directiva de alerta predeterminada denominada **Mensajes.** Para configurar las opciones de notificación de esta alerta, consulta la sección siguiente.

  Para obtener más información acerca de las directivas de alerta, vea [Directivas de alerta en el Centro de & cumplimiento.](../../compliance/alert-policies.md)

## <a name="customize-queue-alerts"></a>Personalizar alertas de cola

1. En el [Centro de & cumplimiento,](https://protection.office.com)vaya **a** Directivas de \> **alertas o** abra <https://protection.office.com/alertpolicies> .

2. En la **página Directivas de** alerta, busque y seleccione la directiva denominada Mensajes que se ha **retrasado.**

3. En el **menú desplegable Mensaje se ha** retrasado y se abre, puedes activar o desactivar la alerta y configurar las opciones de notificación.

   ![Se han retrasado los detalles de la directiva de alerta en el Centro de & cumplimiento](../../media/mfi-queued-messages-alert-policy.png)

   - **Estado:** puede activar o desactivar la alerta.

   - **Destinatarios de correo electrónico** y **límite de notificaciones diarias:** haga clic **en Editar** para configurar las siguientes opciones:

4. Para configurar las opciones de notificación, haga clic **en Editar**. En el **control desplegable Editar** directiva que aparece, configura las siguientes opciones:

   - **Enviar notificaciones por correo** electrónico: el valor predeterminado está en.
   - **Destinatarios de correo** electrónico: el valor predeterminado es **TenantAdmins**.
   - **Límite de notificación diario:** el valor predeterminado **es Sin límite.**
   - **Umbral:** el valor predeterminado es 200.

   ![La configuración de notificaciones en la directiva de alertas de mensajes se ha retrasado y el Centro de seguridad & cumplimiento](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. Cuando haya terminado, haga clic en **Guardar** y **cerrar.**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>Información sobre colas en el panel de flujo de correo

Incluso si el volumen de mensajes en cola no ha superado el  umbral y ha [](mail-flow-insights-v2.md) generado una alerta, puede seguir utilizando la información colas en el panel de flujo de correo para ver los mensajes que se han puesto en cola durante más de una hora y tomar medidas antes de que el número de mensajes en cola sea demasiado grande.

![Widget Colas en el panel Flujo de correo del Centro de & cumplimiento](../../media/mfi-queues-widget.png)

Si hace clic en el número de mensajes del widget, aparecerá un **control** flotante Mensajes en cola con la siguiente información:

- **Número de mensajes en cola**
- **Nombre del conector:** haga clic en el nombre del conector para administrarlo en el Centro de administración de Exchange (EAC).
- **Hora de inicio de cola**
- **Los mensajes más antiguos expiraron**
- **Servidor de destino**
- **Última dirección IP**
- **Último error**
- **Cómo corregir:** hay problemas y soluciones comunes disponibles. Si está disponible **un vínculo Corregirlo** ahora, haga clic en él para solucionar el problema. De lo contrario, haga clic en los vínculos disponibles para obtener más información sobre el error y las posibles soluciones.

![Detalles después de hacer clic en la información de colas en el panel de flujo de correo](../../media/mfi-queues-details.png)

Se muestra el mismo menú desplegable después de hacer clic en Ver **cola** en los detalles de una alerta de mensajes **retrasada.**

![Se han retrasado los detalles de las alertas en el Centro de & cumplimiento](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>Recursos adicionales

Para obtener información sobre otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
