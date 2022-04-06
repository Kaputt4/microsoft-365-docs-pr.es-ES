---
title: Información de nuevos usuarios que reenvían correo electrónico
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.assetid: ''
description: Los administradores pueden aprender a usar la información sobre nuevos usuarios que reenvía correo electrónico en el Centro de seguridad y cumplimiento de & para investigar cuándo los usuarios de su organización reenvía mensajes a nuevos dominios.
ms.technology: mdo
ms.prod: m365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 35ec1573096ecce392979cba11c6e55b1a1adcce
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681774"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nuevos usuarios que reenviarán información de correo electrónico en el Centro de seguridad & cumplimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Es sospechoso cuando las nuevas cuentas de usuario de la organización comienzan de repente a reenviar mensajes de correo electrónico a dominios externos.

La **información sobre nuevos** dominios que se reenvía de correo electrónico en el Centro de seguridad [& cumplimiento](https://protection.office.com) le notifica cuándo los usuarios recién creados de su organización reenvía mensajes a dominios externos. Esta condición podría indicar que se usaron cuentas de administrador comprometidas para crear los nuevos usuarios. Si sospecha que las cuentas se han visto comprometidas, consulte [Responder a una cuenta de correo electrónico comprometida](responding-to-a-compromised-email-account.md).

Esta información solo aparece cuando se detecta el problema y aparece en la página [Informe de reenvío](view-mail-flow-reports.md#forwarding-report) .

![Nuevos usuarios que reenván información de correo electrónico.](../../media/mfi-new-users-forwarding-email.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [](#forwarding-modifications-report) informe de modificaciones de reenvío, tal como se describe más adelante en este artículo.

![El menú desplegable de detalles que aparece después de hacer clic en la información sobre el reenvío de correo electrónico de nuevos usuarios.](../../media/mfi-new-users-forwarding-email-details.png)

También puede acceder a esta página de detalles al seleccionar la información después de hacer clic  en Ver todo en  el área Principales & **recomendaciones en (** \> Panel de **informes o ).** <https://protection.office.com/insightdashboard>

Puede hacer clic en el **vínculo Ver informe asociado a insight** para ir al informe de modificaciones **de** reenvío, tal como se describe en la sección siguiente.

## <a name="forwarding-modifications-report"></a>Informe de modificaciones de reenvío

El **informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvía automáticamente de remitentes de la organización:

- Cuentas recién creadas que reenvía mensajes a dominios externos.
- Cuentas que reenvía mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.

Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, y pueden indicar cuentas comprometidas.

El informe contiene datos de hasta 90 días. De forma predeterminada, el informe muestra los datos de los últimos 7 días.

Este informe no está disponible directamente en el panel flujo de [correo](mail-flow-insights-v2.md) ni en el [panel Informes](view-mail-flow-reports.md). Además de hacer clic en el vínculo **Ver informe asociado a insight** en **el vínculo Nuevos** usuarios que reenvía la información de correo electrónico, puede obtener acceso al informe mediante:

- Haga clic **en el vínculo Informe de notificaciones de reenvío** en los detalles de [la información de correo electrónico nuevos dominios que se reenviarán](mfi-new-domains-being-forwarded-email.md).
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.

### <a name="report-view-for-the-forwarding-modifications-report"></a>Vista Informe para el informe de modificaciones de reenvío

Los gráficos siguientes están disponibles en la vista informe:

- **Mostrar datos para: Nuevos usuarios de reenvío**:

  ![Nueva vista de usuarios de reenvío en el informe de modificaciones de reenvío.](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar datos para: Nuevos dominios de reenvío**:

  ![Vista Nuevos dominios reenviados en el informe de modificaciones de reenvío.](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Si hace clic **en Filtros en** una vista de informe, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Vista de tabla Detalles para el informe de modificaciones de reenvío

Si hace clic **en Ver tabla de detalles**, la información que se muestra depende del gráfico que estaba mirando:

- **Mostrar datos para: Nuevos usuarios de reenvío**:

  - **Nombre**: la dirección de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

- **Mostrar datos para: Nuevos dominios de reenvío**:

  - **Nombre**: el dominio de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Si selecciona una fila de la tabla **, aparecerá un** menú desplegable Detalles con la siguiente información:

- **Nombre**: esta es la dirección de correo electrónico del remitente (desde Mostrar datos para **: Vista** Nuevos usuarios de reenvío) o el dominio de correo electrónico del remitente (desde **Mostrar datos para:** Vista Nuevos dominios de reenvío).
- **Tipo de reenvío**
- **Destinatario**
- **Detalles**
- **Count**
- **Fecha de comienzo**
- **Recomendación**: Desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.

![Los detalles se desván de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe Modificaciones de reenvío.](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para volver a la vista informes, haga clic **en Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras perspectivas en el panel flujo de correo, vea Información sobre el flujo de correo en el [Centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
