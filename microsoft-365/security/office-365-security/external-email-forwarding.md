---
title: Configurar y controlar el reenvío de correo electrónico externo en Microsoft 365.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2021
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: En este artículo se tratan temas como reenvío de correo electrónico externo, reenvío automático, 5.7.520 Acceso denegado, deshabilitación del reenvío externo, mensajes "El administrador ha deshabilitado el reenvío externo", así como la directiva de correo no deseado saliente.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 228bb4402fd67ba8e56dd84b270c64977667ff2d
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401026"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controlar el reenvío automático de correo electrónico externo en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Como administrador, es posible que tenga requisitos de la empresa para restringir o controlar los mensajes reenviados automáticamente a destinatarios externos (destinatarios fuera de la organización). El reenvío de correo electrónico puede ser útil, pero también puede suponer un riesgo de seguridad debido a la posible divulgación de información. Los atacantes pueden usar esta información para atacar a su organización o socios.

Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:

- Los usuarios pueden configurar [reglas de la Bandeja](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) de entrada para reenviar automáticamente mensajes a remitentes externos (deliberadamente o como resultado de una cuenta comprometida).
- Los administradores pueden configurar [el reenvío de buzones](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como reenvío _SMTP_) para reenviar automáticamente mensajes a destinatarios externos. El administrador puede elegir si simplemente reenviar mensajes o mantener copias de mensajes reenviados en el buzón.

> [!NOTE]
> Los usuarios con reenvío automático desde sistemas de correo electrónico locales a través de Microsoft 365 estarán sujetos a los mismos controles de directiva que los buzones de correo en la nube en una próxima actualización. Esta actualización se comunicará a través de la publicación del Centro de mensajes.

Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos. Hay tres opciones disponibles:

- **Automático: controlado por el sistema**: esta es la configuración predeterminada. Esta configuración es ahora la misma que **Off**. Cuando esta configuración se introdujo originalmente, era equivalente a **On**. Con el tiempo, gracias a los principios de seguridad de forma [predeterminada](secure-by-default.md), esta configuración se cambió gradualmente a **Desactivado** para todos los clientes. Para obtener más información, consulta [esta entrada de blog](https://techcommunity.microsoft.com/t5/exchange-team-blog/all-you-need-to-know-about-automatic-email-forwarding-in/ba-p/2074888). 
- **On**: El reenvío externo automático está permitido y no restringido.
- **Desactivado**: el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (también conocido como NDR o mensaje de desenviamiento) al remitente.

Para obtener instrucciones sobre cómo configurar estas opciones, consulte [Configurar el filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Deshabilitar el reenvío automático deshabilita las reglas de la Bandeja de entrada (usuarios) o el reenvío de buzones (administradores) que redirigen los mensajes a direcciones externas.
>
> - El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.


## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Cómo funciona la configuración de directiva de filtro de correo no deseado saliente con otros controles de reenvío automático de correo electrónico

Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico. Por ejemplo:

- [Dominios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.
- Las condiciones y las acciones Exchange reglas de flujo de [correo (también](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) conocidas como reglas de transporte) para detectar y bloquear mensajes reenviados automáticamente a destinatarios externos.

Cuando una configuración permite el reenvío externo, pero otra bloquea el reenvío externo, el bloque suele ganar. En la tabla siguiente se describen ejemplos:

<br>

****

|Escenario|Resultado|
|---|---|
|<ul><li>Configure las opciones de dominio remoto para permitir el reenvío automático.</li><li>El reenvío automático en la directiva de filtro de correo no deseado saliente se establece en **Desactivado**.</li></ul>|Se bloquean los mensajes reenviados automáticamente a los destinatarios de los dominios afectados.|
|<ul><li>Configure las opciones de dominio remoto para permitir el reenvío automático.</li><li>El reenvío automático en la directiva de filtro de correo no deseado saliente se establece en **Automático: controlado por el sistema**.</li></ul>|Se bloquean los mensajes reenviados automáticamente a los destinatarios de los dominios afectados. <p> Como se describió anteriormente, **Automático: controlado** por el sistema se usa para **significar On**, pero la configuración ha cambiado con el tiempo para **significar Desactivado** en todas las organizaciones. <p> Para mayor claridad, debe configurar la directiva de filtro de correo no deseado saliente en **On** o **Off**.|
|<ul><li>El reenvío automático en la directiva de filtro de correo no deseado saliente se establece en **On**</li><li>Se usan reglas de flujo de correo o dominios remotos para bloquear el correo electrónico reenviado automáticamente.</li></ul>|Los mensajes reenviados automáticamente a los destinatarios afectados se bloquean mediante reglas de flujo de correo o dominios remotos.|
|

Puede usar este comportamiento (por ejemplo) para permitir el reenvío automático en directivas de filtro de correo no deseado saliente, pero usar dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.

## <a name="how-to-find-users-that-are-automatically-forwarding"></a>Cómo buscar usuarios que se reenvía automáticamente

Puede ver información sobre los usuarios que reenvía automáticamente mensajes a destinatarios externos en el [informe](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) Mensajes reenviados automáticos para cuentas basadas en la nube. Para los usuarios locales que reenván automáticamente desde su sistema de correo electrónico local a través de Microsoft 365, debe crear una regla de flujo de correo para realizar un seguimiento de estos usuarios. Para obtener instrucciones sobre cómo crear una regla de flujo de correo, vea [Usar el EAC para crear una regla de flujo de correo](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#use-the-eac-to-create-a-mail-flow-rule).

La siguiente información es necesaria para crear la regla de flujo de correo en el Centro Exchange administración (EAC):

- **Aplicar esta regla si** (condición): **un encabezado de mensaje** \> **coincide con estos patrones de texto**. Ten en cuenta que es posible que deba hacer clic **en Más opciones** para ver esta opción.
  - **Nombre del encabezado**: `X-MS-Exchange-Inbox-Rules-Loop`
  - **Valor de encabezado**: `.`

  La condición tiene este aspecto: **el encabezado 'X-MS-Exchange-Inbox-Rules-Loop'** coincide **con '.'**

  Esta condición coincidirá con cualquier valor del encabezado.

- (Opcional) **Haga lo siguiente** (acción): puede configurar una acción opcional. Por ejemplo, puede usar la  \> acción Modificar las propiedades del mensaje establecer un encabezado de **mensaje, con** el nombre de encabezado **X-Forwarded** y el valor **True**. Sin embargo, no es necesario configurar una acción.
- Establezca **Auditar esta calle con el nivel de gravedad** en el valor **Low**, **Medium** o **High**. Esta configuración le permite usar el informe Exchange [regla de transporte para](view-email-security-reports.md#exchange-transport-rule-report) obtener detalles de los usuarios que están reenviando.

![Propiedades de regla de flujo de correo en el EAC para que una regla identifique los mensajes reenviados.](../../media/mail-flow-rule-for-forwarded-messages.png)

## <a name="blocked-email-forwarding-messages"></a>Mensajes de reenvío de correo electrónico bloqueados

Cuando se detecta un mensaje como reenviado automáticamente y la directiva de filtro de  [correo](configure-the-outbound-spam-policy.md) no deseado saliente bloquea esa actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
