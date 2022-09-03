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
description: Los administradores pueden aprender a usar la información sobre el reenvío de correo electrónico de nuevos usuarios en el Centro de cumplimiento de seguridad & para investigar cuándo los usuarios de su organización reenvían mensajes a nuevos dominios.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: a95c353ac64160d03f8ae54bad46079bd9594a3c
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597832"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Información sobre el reenvío de correo electrónico de nuevos usuarios en el Centro de cumplimiento de seguridad &

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Es sospechoso cuando las nuevas cuentas de usuario de su organización empiezan a reenviar mensajes de correo electrónico a dominios externos de forma repentina.

La información de **los nuevos usuarios que reenvía correo electrónico** en el [Centro de cumplimiento de seguridad &](https://protection.office.com) le notifica cuando los usuarios recién creados de su organización están reenviando mensajes a dominios externos. Esta condición podría indicar que se usaron cuentas de administrador en peligro para crear los nuevos usuarios. Si sospecha que las cuentas se han puesto en peligro, consulte [Respuesta a una cuenta de correo electrónico en peligro](responding-to-a-compromised-email-account.md).

Esta información aparece solo cuando se detecta el problema y aparece en la página [del informe de reenvío](view-mail-flow-reports.md#forwarding-report) .

:::image type="content" source="../../media/mfi-new-users-forwarding-email.png" alt-text="Información sobre el reenvío de correo electrónico de nuevos usuarios" lightbox="../../media/mfi-new-users-forwarding-email.png":::

Al hacer clic en el widget, aparece un control flotante donde puede encontrar más detalles sobre los mensajes reenviados, incluido un vínculo al [informe de modificaciones de reenvío](#forwarding-modifications-report) , como se describe más adelante en este artículo.

:::image type="content" source="../../media/mfi-new-users-forwarding-email-details.png" alt-text="El control flotante Detalles que aparece después de hacer clic en la información sobre el reenvío de correo electrónico de nuevos usuarios" lightbox="../../media/mfi-new-users-forwarding-email-details.png":::

También puede acceder a esta página de detalles al seleccionar la información después de hacer clic en **Ver todo** en el área **Conclusiones principales & recomendaciones** en (**Panel de** **informes** \> o <https://protection.office.com/insightdashboard>).

Puede hacer clic en el vínculo **Ver informe asociado a información** para ir al **informe de modificaciones de reenvío** , tal como se describe en la sección siguiente.

## <a name="forwarding-modifications-report"></a>Informe de modificaciones de reenvío

El **informe de modificaciones de reenvío muestra detalles** sobre los mensajes que se reenvía automáticamente desde los remitentes de la organización:

- Cuentas recién creadas que reenvía mensajes a dominios externos.
- Cuentas que reenvía mensajes a dominios externos a los que otros remitentes de la organización nunca han reenviado.

Estos tipos de mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento e indicar cuentas en peligro.

El informe contiene datos durante un máximo de 90 días. De forma predeterminada, el informe muestra los datos de los últimos 7 días.

Este informe no está disponible directamente en el [panel Flujo de correo](mail-flow-insights-v2.md) ni en el [panel Informes](view-mail-flow-reports.md). Además de hacer clic en el vínculo **Ver informe asociado con información** del vínculo **Nuevos usuarios que reenvía información de correo electrónico** , puede acceder al informe mediante:

- Haga clic en el vínculo **Informe de notificaciones de reenvío** en los detalles de la [información de correo electrónico Nuevos dominios que se reenvía](mfi-new-domains-being-forwarded-email.md).
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.

### <a name="report-view-for-the-forwarding-modifications-report"></a>Vista de informe para el informe de modificaciones de reenvío

Los siguientes gráficos están disponibles en la vista de informe:

- **Mostrar datos para: Nuevos usuarios de reenvío**:

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarding-users.png" alt-text="Vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío" lightbox="../../media/forwarding-modifications-report-new-forwarding-users.png":::

- **Mostrar datos para: Nuevos dominios de reenvío**:

    :::image type="content" source="../../media/forwarding-modifications-report-new-forwarded-domains.png" alt-text="Vista Nuevos dominios reenviados en el informe de modificaciones de reenvío" lightbox="../../media/forwarding-modifications-report-new-forwarded-domains.png":::

Si hace clic en **Filtros** en una vista de informe, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Vista de tabla de detalles para el informe de modificaciones de reenvío

Si hace clic en **Ver tabla de detalles**, la información que se muestra depende del gráfico que esté examinando:

- **Mostrar datos para: Nuevos usuarios de reenvío**:

  - **Nombre**: dirección de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

- **Mostrar datos para: Nuevos dominios de reenvío**:

  - **Nombre**: dominio de correo electrónico del remitente.
  - **Tipo de reenvío**
  - **Dirección del destinatario**
  - **Detalles**
  - **Count**
  - **Primera fecha de reenvío**

Si hace clic en **Filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **Fecha de inicio** y **Fecha de finalización**.

Si selecciona una fila de la tabla, aparecerá un control flotante **Detalles** con la siguiente información:

- **Nombre**: se trata de la dirección de correo electrónico del remitente (de **Mostrar datos para: Vista de nuevos usuarios de reenvío** ) o del dominio de correo electrónico del remitente (desde **la vista Mostrar datos para: Nuevos dominios de reenvío** ).
- **Tipo de reenvío**
- **Destinatario**
- **Detalles**
- **Count**
- **Fecha de comienzo**
- **Recomendación**: desde aquí, puede hacer clic en el vínculo para administrar el usuario en el Centro de administración de Microsoft 365.

  :::image type="content" source="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png" alt-text="El control flotante Detalles de la tabla de detalles de la vista Nuevos usuarios de reenvío en el informe de modificaciones de reenvío" lightbox="../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png":::

Para volver a la vista de informes, haga clic en **Ver informe**.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre otras conclusiones en el panel Flujo de correo, consulte [Información de flujo de correo en el Centro de cumplimiento de seguridad &](mail-flow-insights-v2.md).
