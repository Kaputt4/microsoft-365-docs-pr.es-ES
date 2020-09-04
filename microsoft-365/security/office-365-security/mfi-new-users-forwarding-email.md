---
title: Información de nuevos usuarios que reenvían correo electrónico
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Los administradores pueden aprender a usar los nuevos usuarios que reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento para investigar Cuándo los usuarios de la organización reenvían mensajes a nuevos dominios.
ms.openlocfilehash: 4d8c88cef182ab1c521d23970797e4746e188916
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357371"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Nuevos usuarios que reenvían el conocimiento del correo electrónico en el centro de seguridad & cumplimiento

Es sospechoso cuando las nuevas cuentas de usuario de la organización inician repentinamente el reenvío de mensajes de correo electrónico a dominios externos.

Los **nuevos dominios que se reenvían** el conocimiento de correo electrónico del [centro de seguridad & cumplimiento](https://protection.office.com) le notifican cuando los usuarios recién creados en la organización reenvían mensajes a dominios externos. Esta condición podría indicar que se usaron cuentas de administrador en peligro para crear los nuevos usuarios. Si sospecha que las cuentas se han puesto en peligro, consulte [responder a una cuenta de correo electrónico en peligro](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

Esta información sólo aparece cuando se detecta el problema y aparece en la página de [reenvío del informe](view-mail-flow-reports.md#forwarding-report) .

![Información de nuevos usuarios que reenvían correo electrónico](../../media/mfi-new-users-forwarding-email.png)

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [Informe de modificaciones de reenvío](#forwarding-modifications-report) tal y como se describe más adelante en este tema.

![Control flotante de detalles que aparece después de hacer clic en los nuevos usuarios Reenviar información sobre el correo electrónico](../../media/mfi-new-users-forwarding-email-details.png)

También puede obtener acceso a esta página de detalles si selecciona la información después de hacer clic en **ver todo** en el área de **recomendaciones &** información sobre (**Reports** \> **Panel** de informes o <https://protection.office.com/insightdashboard> ).

Puede hacer clic en el vínculo **Ver informe asociado con conocimiento** para ir al **Informe de modificaciones de reenvío** , como se describe en la siguiente sección.

## <a name="forwarding-modifications-report"></a>Reenvío del informe de modificaciones

El **Informe de modificaciones de reenvío** muestra detalles sobre los mensajes que se reenvían automáticamente a los remitentes de la organización:

- Cuentas recién creadas que reenvían mensajes a dominios externos.
- Cuentas que reenvían mensajes a dominios externos que nunca han sido reenviados por otros remitentes de la organización.

Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar cuentas comprometidas.

El informe contiene datos de hasta 90 días. De forma predeterminada, el informe muestra los datos de los últimos 7 días.

Este informe no está directamente disponible en el [Panel de flujo de correo](mail-flow-insights-v2.md) ni en el panel de [informes](view-mail-flow-reports.md). Además de hacer clic en el vínculo **vea el informe asociado con el conocimiento** en el **nuevo usuario Reenviar información sobre el correo electrónico de reenvío** , obtenga acceso al informe de la siguiente manera:

- Haga clic en el vínculo **reenviar notificaciones del informe** en los detalles de los [nuevos dominios que se reenviarán el conocimiento de correo electrónico](mfi-new-domains-being-forwarded-email.md).
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Vista informes para el informe de modificaciones de reenvío

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: nuevos usuarios de reenvío**:

  ![Vista de nuevos usuarios de reenvío en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar datos para: nuevos dominios de reenvío**:

  ![Vista de nuevos dominios reenviados en el informe de modificaciones de reenvío](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Vista de tabla de detalles para el informe de modificaciones de reenvío

Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:

- **Mostrar datos para: nuevos usuarios de reenvío**:

  - **Name**: la dirección de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

- **Mostrar datos para: nuevos dominios de reenvío**:

  - **Name**: el dominio de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.

Si selecciona una fila de la tabla, aparece un flotante de **detalles** con la siguiente información:

- **Name**: esta es la dirección de correo electrónico del remitente (de **Mostrar datos para: nuevos usuarios de reenvío** ) o el dominio de correo electrónico del remitente (de la vista **Mostrar datos para: nuevos dominios de reenvío** ).
- **Tipo de reenvío**
- **Destinatario**
- **Detalles**
- **Count**
- **Fecha de comienzo**
- **Recomendación**: desde aquí, puede hacer clic en el vínculo para administrar el usuario en el centro de administración de Microsoft 365.

![Control flotante de la tabla detalles de la vista nuevos usuarios de reenvío en el informe de reenvío de modificaciones](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para volver a la vista informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras informaciones del panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
