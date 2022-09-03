---
title: Configurar y controlar el reenvío de correo electrónico externo en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/18/2022
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
- adminvideo
description: En este artículo se tratan temas como el reenvío de correo electrónico externo, el reenvío automático, los mensajes de acceso denegado 5.7.520, la deshabilitación del reenvío externo, los mensajes "Su administrador ha deshabilitado el reenvío externo", así como la directiva de correo no deseado saliente.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 5a427236386c5afe4f289b8b1eb1ef4045f7f5d6
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598459"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Control del reenvío automático de correo electrónico externo en Microsoft 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Como administrador, es posible que tenga los requisitos de la empresa para restringir o controlar los mensajes reenviados automáticamente a destinatarios externos (destinatarios fuera de su organización). Email reenvío puede ser útil, pero también puede suponer un riesgo de seguridad debido a la posible divulgación de información. Los atacantes pueden usar esta información para atacar a su organización o asociados.

Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:

- Los usuarios pueden configurar [reglas de bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para reenviar automáticamente mensajes a remitentes externos (deliberadamente o como resultado de una cuenta en peligro).
- Los administradores pueden configurar el [reenvío de buzones](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como _reenvío SMTP_) para reenviar automáticamente mensajes a destinatarios externos. El administrador puede elegir si simplemente reenviar mensajes o mantener copias de los mensajes reenviados en el buzón.

> [!NOTE]
> Los usuarios con reenvío automático desde sistemas de correo electrónico locales a través de Microsoft 365 estarán sujetos a los mismos controles de directiva que los buzones de correo en la nube en una próxima actualización. Esta actualización se comunicará a través de la publicación del Centro de mensajes.

Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos. Hay tres opciones disponibles:

- **Automático: controlado por el sistema**: esta es la configuración predeterminada. Esta configuración es ahora la misma que **Desactivado**. Cuando se introdujo originalmente esta configuración, era equivalente a **On**. Con el tiempo, gracias a los principios de [seguridad de forma predeterminada](secure-by-default.md), esta configuración se cambió gradualmente a **Desactivado** para todos los clientes. Para obtener más información, consulte [esta publicación de blog](https://techcommunity.microsoft.com/t5/exchange-team-blog/all-you-need-to-know-about-automatic-email-forwarding-in/ba-p/2074888).
- **Activado**: se permite el reenvío externo automático y no está restringido.
- **Desactivado**: el reenvío externo automático está deshabilitado y dará lugar a un informe de no entrega (también conocido como NDR o mensaje de devolución) al remitente.

Para obtener instrucciones sobre cómo configurar estas opciones, consulte [Configuración del filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Deshabilitar el reenvío automático deshabilita las reglas de bandeja de entrada (usuarios) o el reenvío de buzones (administradores) que redirigen mensajes a direcciones externas.
> - El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Cómo funciona la configuración de la directiva de filtro de correo no deseado saliente con otros controles automáticos de reenvío de correo electrónico

Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico. Por ejemplo:

- [Dominios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.
- Condiciones y acciones en [las reglas de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de Exchange (también conocidas como reglas de transporte) para detectar y bloquear los mensajes reenviados automáticamente a destinatarios externos.

Cuando una configuración permite el reenvío externo, pero otra configuración bloquea el reenvío externo, el bloque normalmente gana. En la tabla siguiente se describen ejemplos:

|Escenario|Resultado|
|---|---|
|<ul><li>Configure los valores de dominio remoto para permitir el reenvío automático.</li><li>El reenvío automático en la directiva de filtro de correo no deseado saliente está establecido en **Desactivado**.</li></ul>|Se bloquean los mensajes reenviados automáticamente a los destinatarios de los dominios afectados.|
|<ul><li>Configure los valores de dominio remoto para permitir el reenvío automático.</li><li>El reenvío automático en la directiva de filtro de correo no deseado saliente se establece en **Automático: controlado por el sistema**.</li></ul>|Se bloquean los mensajes reenviados automáticamente a los destinatarios de los dominios afectados. <p> Como se describió anteriormente, **Automático- controlado por el sistema** se usa para significar **Activado**, pero la configuración ha cambiado con el tiempo para significar **Desactivado** en todas las organizaciones. <p> Para una claridad absoluta, debe configurar la directiva de filtro de correo no deseado saliente **en Activado** o **Desactivado**.|
|<ul><li>El reenvío automático en la directiva de filtro de correo no deseado saliente está establecido en **Activado**</li><li>Use reglas de flujo de correo o dominios remotos para bloquear el correo electrónico reenviado automáticamente.</li></ul>|Las reglas de flujo de correo o los dominios remotos bloquean los mensajes reenviados automáticamente a los destinatarios afectados.|

Puede usar este comportamiento (por ejemplo) para permitir el reenvío automático en las directivas de filtro de correo no deseado saliente, pero usar dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.

## <a name="how-to-find-users-that-are-automatically-forwarding"></a>Cómo buscar usuarios que se reenvíen automáticamente

Puede ver información sobre los usuarios que reenvía automáticamente mensajes a destinatarios externos en el [informe De mensajes reenviados automáticamente](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) para cuentas basadas en la nube. Para los usuarios locales que reenvían automáticamente desde su sistema de correo electrónico local a través de Microsoft 365, debe crear una regla de flujo de correo para realizar un seguimiento de estos usuarios. Para obtener instrucciones sobre cómo crear una regla de flujo de correo, consulte [Uso del EAC para crear una regla de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#use-the-eac-to-create-a-mail-flow-rule).

La siguiente información es necesaria para crear la regla de flujo de correo en el Centro de administración de Exchange (EAC):

- **Aplicar esta regla si** (condición): **un encabezado** \> de mensaje **coincide con estos patrones de texto**. Tenga en cuenta que es posible que tenga que hacer clic en **Más opciones** para ver esta opción.
  - **Nombre del encabezado**: `X-MS-Exchange-Inbox-Rules-Loop`
  - **Valor de encabezado**: `.`

  La condición tiene este aspecto: **el encabezado "X-MS-Exchange-Inbox-Rules-Loop"** coincide con **"."**

  Esta condición coincidirá con cualquier valor del encabezado.

- (Opcional) **Haga lo siguiente** (acción): puede configurar una acción opcional. Por ejemplo, puede usar la acción **Modificar las propiedades** \> del mensaje **para establecer un encabezado de mensaje**, con el nombre de encabezado **X-Forwarded** y el valor **True**. Sin embargo, no es necesario configurar una acción.
- Establezca **Auditar esta rue con el nivel de gravedad** en el valor **Bajo**, **Medio** o **Alto**. Esta configuración le permite usar el [informe de reglas de transporte de Exchange](view-email-security-reports.md#exchange-transport-rule-report) para obtener detalles de los usuarios que están reenviando.

:::image type="content" source="../../media/mail-flow-rule-for-forwarded-messages.png" alt-text="Propiedades de la regla de flujo de correo en el EAC para que una regla identifique los mensajes reenviados." lightbox="../../media/mail-flow-rule-for-forwarded-messages.png":::

## <a name="blocked-email-forwarding-messages"></a>Mensajes de reenvío de correo electrónico bloqueados

Cuando se detecta que un mensaje se reenvía automáticamente y la directiva de [filtro de correo no deseado saliente](configure-the-outbound-spam-policy.md) *bloquea* esa actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
