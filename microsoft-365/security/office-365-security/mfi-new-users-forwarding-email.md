---
title: Información de nuevos usuarios que reenvían correo electrónico
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar la información sobre nuevos usuarios que reenvía correo electrónico en el Centro de seguridad & cumplimiento para investigar cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207242"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nuevos usuarios reenviar información de correo electrónico en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Es sospechoso cuando las nuevas cuentas de usuario de la organización comienzan de repente a reenviar mensajes de correo electrónico a dominios externos.

La **información sobre nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo los usuarios recién creados de su organización reenvía mensajes a dominios externos. Esta condición podría indicar que se usaron cuentas de administrador comprometidas para crear los nuevos usuarios. Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico comprometida.](responding-to-a-compromised-email-account.md)

Esta información solo aparece cuando se detecta el problema y aparece en la página [Informe de reenvío.](view-mail-flow-reports.md#forwarding-report)

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más [](#forwarding-modifications-report) detalles sobre los mensajes reenviados, incluido un vínculo al informe de modificaciones de reenvío, tal como se describe más adelante en este artículo.

![El menú desplegable de detalles que aparece después de hacer clic en la información sobre el reenvío de correo electrónico de nuevos usuarios](../../media/mfi-new-users-forwarding-email-details.png)

También puede acceder a esta página de detalles  al seleccionar la información después de hacer clic en Ver todo en el área Información **principal & recomendaciones** en (**Panel** de informes \>  o <https://protection.office.com/insightdashboard> ).

Puede hacer clic en el **vínculo Ver informe asociado a insight** para ir al informe de modificaciones **de** reenvío, tal como se describe en la sección siguiente.

## <a name="forwarding-modifications-report"></a>Informe de modificaciones de reenvío

El **informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvía automáticamente de remitentes de la organización:

- Cuentas recién creadas que reenvía mensajes a dominios externos.
- Cuentas que reenvía mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.

Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar cuentas comprometidas.

El informe contiene datos de hasta 90 días. De forma predeterminada, el informe muestra los datos de los últimos 7 días.

Este informe no está disponible directamente en el panel flujo de [correo](mail-flow-insights-v2.md) ni en el [panel Informes.](view-mail-flow-reports.md) Además de hacer clic en el vínculo **Ver informe asociado a insight** en el vínculo **Nuevos** usuarios que reenvía la información de correo electrónico, puede obtener acceso al informe mediante:

- Haga clic **en el vínculo Informe de notificaciones de reenvío** en los detalles de los nuevos dominios que se [reenvía la](mfi-new-domains-being-forwarded-email.md)información de correo electrónico .
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Vista Informe para el informe de modificaciones de reenvío

Los gráficos siguientes están disponibles en la vista informe:

- **Mostrar datos para: Nuevos usuarios de reenvío:**

  ![Vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar datos para: Nuevos dominios de reenvío:**

  ![Vista Nuevos dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Vista de tabla Detalles para el informe de modificaciones de reenvío

Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:

- **Mostrar datos para: Nuevos usuarios de reenvío:**

  - **Nombre:** la dirección de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección de destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

- **Mostrar datos para: Nuevos dominios de reenvío:**

  - **Nombre:** el dominio de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección de destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**

Si selecciona una fila de la tabla, **aparecerá** un menú desplegable Detalles con la siguiente información:

- **Nombre:** esta es la dirección de correo electrónico del remitente (desde Mostrar datos **para: Vista** Nuevos usuarios de reenvío) o el dominio de correo electrónico del remitente (desde Mostrar datos **para:** Vista Nuevos dominios de reenvío).
- **Tipo de reenvío**
- **Recipient**
- **Detalles**
- **Count**
- **Fecha de comienzo**
- **Recomendación:** Desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.

![Los detalles se desván de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe Modificaciones de reenvío](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel flujo de correo, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).
