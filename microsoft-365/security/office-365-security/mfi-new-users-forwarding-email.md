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
description: Los administradores pueden aprender a usar los nuevos usuarios que reenvía información de correo electrónico en el Centro de seguridad & Cumplimiento para investigar cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029875"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nuevos usuarios que reenvía información de correo electrónico en el Centro de & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Es sospechoso cuando las nuevas cuentas de usuario de su organización comienzan de pronto a reenviar mensajes de correo electrónico a dominios externos.

La **información sobre nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad y cumplimiento de [&](https://protection.office.com) le notifica cuándo los usuarios recién creados de su organización están reenviando mensajes a dominios externos. Esta condición podría indicar que se usaron cuentas de administrador comprometidas para crear los nuevos usuarios. Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico en peligro.](responding-to-a-compromised-email-account.md)

Esta información solo aparece cuando se detecta el problema y aparece en la [página del informe de reenvío.](view-mail-flow-reports.md#forwarding-report)

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más [](#forwarding-modifications-report) detalles sobre los mensajes reenviados, incluido un vínculo al informe de modificaciones de reenvío, como se describe más adelante en este artículo.

![Menú desplegable de detalles que aparece después de hacer clic en la información de reenvío de correo electrónico de nuevos usuarios](../../media/mfi-new-users-forwarding-email-details.png)

También puede acceder a esta página de detalles  cuando seleccione la información después de hacer clic en Ver todo en el área de información **superior &** recomendaciones **(** Panel de informes \>  o <https://protection.office.com/insightdashboard> ).

Puede hacer clic en el **vínculo Ver informe asociado con** información para ir al informe de modificaciones **de** reenvío, tal como se describe en la sección siguiente.

## <a name="forwarding-modifications-report"></a>Informe de modificaciones de reenvío

El **informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvía automáticamente de los remitentes de su organización:

- Cuentas recién creadas que reenvía mensajes a dominios externos.
- Cuentas que reenvía mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.

Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar cuentas comprometidas.

El informe contiene datos de hasta 90 días. De forma predeterminada, el informe muestra los datos de los últimos 7 días.

Este informe no está disponible directamente en el [panel](mail-flow-insights-v2.md) flujo de correo o en el panel [informes.](view-mail-flow-reports.md) Además de hacer clic en el vínculo  Ver **informe asociado** a la información en la información de nuevos usuarios que reenvía correo electrónico, puede obtener acceso al informe mediante:

- Haga clic **en el vínculo informe de notificaciones de** reenvío en los detalles de la información de correo electrónico de nuevos dominios que se [reenvía.](mfi-new-domains-being-forwarded-email.md)
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Vista de informe para el informe de modificaciones de reenvío

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: Nuevos usuarios de reenvío:**

  ![Nueva vista de usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar datos para: Nuevos dominios de reenvío:**

  ![Nueva vista de dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con fecha **de inicio** y fecha **de finalización.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Vista de tabla de detalles del informe de modificaciones de reenvío

Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba viendo:

- **Mostrar datos para: Nuevos usuarios de reenvío:**

  - **Nombre:** la dirección de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

- **Mostrar datos para: Nuevos dominios de reenvío:**

  - **Nombre:** el dominio de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con fecha de **inicio** y fecha **de finalización.**

Si selecciona una fila de la tabla, **aparecerá** un menú desplegable Detalles con la siguiente información:

- **Nombre:** se trata de la dirección de correo electrónico del remitente (desde Mostrar datos **para:** vista Nuevos usuarios de reenvío) o el dominio de correo electrónico del remitente (desde Mostrar datos **para:** Vista Nuevos dominios de reenvío).
- **Tipo de reenvío**
- **Recipient**
- **Detalles**
- **Count**
- **Fecha de comienzo**
- **Recomendación:** desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.

![Menú desplegable de detalles de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para volver a la vista informes, haga clic **en Ver informe.**

## <a name="related-topics"></a>Temas relacionados

Para obtener información acerca de otras perspectivas en el panel de flujo de correo, vea Información sobre el flujo de correo en el Centro de [& cumplimiento.](mail-flow-insights-v2.md)
