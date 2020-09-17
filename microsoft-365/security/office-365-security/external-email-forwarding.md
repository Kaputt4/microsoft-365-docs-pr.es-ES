---
title: Configurar y controlar el reenvío externo de correo electrónico, el reenvío automático, 5.7.520 acceso denegado, deshabilitar el reenvío externo, el administrador deshabilitó el reenvío externo, la Directiva de correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 727f14e8158f7e024b6029231fed18adb2d56a62
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949703"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Configurar el reenvío externo de correo electrónico en Office 365

El reenvío externo se controla mediante la *Directiva de correo no deseado saliente* y se establece en el ámbito de los usuarios en función de la configuración configurada. Actualmente se admite la configuración de 3:

- **Automático** : en este modo, el sistema es responsable de decidir si se permite o no un mensaje reenviado.  Este es el modo predeterminado y, en este modo, el sistema bloqueará el reenvío externo automático.

- **Activado** : el reenvío externo automático se permite y no está restringido.

- **Desactivado** : el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (NDR) al usuario final.

Para obtener más información sobre cómo configurar estas opciones, vea [configurar el filtrado de correo no deseado saliente en EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .

> [!NOTE]
> Al deshabilitar el reenvío automático también se dsable las reglas de la bandeja de entrada que redirigen los mensajes a direcciones externas.

## <a name="controlling-external-email-forwarding"></a>Controlar el reenvío de correo electrónico externo

Como administrador de una organización, es posible que los requisitos de la compañía tengan que restringir o controlar quién puede reenviar automáticamente los correos electrónicos con las reglas de la bandeja de entrada o el reenvío SMTP, fuera de la organización. El reenvío de correo electrónico puede ser una característica útil, pero también puede suponer un riesgo a través de la posible revelación de información, incluso proporcionando información a los atacantes que pueden aprovecharse para atacar a la organización o a sus asociados.

Office 365 no permite el reenvío externo automático por reglas de la bandeja de entrada o por la configuración de buzón de correo, lo que proporciona una directiva predeterminada segura. Sin embargo, el administrador puede modificar esta configuración para todos o algunos de los usuarios de la organización. El reenvío de mensajes entre usuarios internos no se ve afectado por esta modificación.

> [!NOTE]
> Deshabilitar el reenvío automático a direcciones externas en Office 365 se está implementando en fases con detalles que se comunican a través de las publicaciones del [centro de mensajes](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) . Para ayudar a los administradores a preparar estos cambios, pídales que modifiquen las directivas con anticipación para asegurarse de que no hay interrupciones para sus usuarios.

Puede encontrar más información acerca de los usuarios que usan el reenvío automático (reglas de la bandeja de entrada o reenvío SMTP) en el [Informe de mensajes reenviados automáticamente](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>Cómo funciona esta directiva con otros controles de reenvío automático

Como administrador, es posible que ya tenga otros tipos de controles en su ubicación, lo que bloquea el reenvío automático en [dominios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) y el uso de una regla de transporte de Exchange (ETR). Ambos controles son independientes de esta característica, por ejemplo, si se permite el reenvío automático para un dominio remoto, pero se bloquea el desvío automático a través de la Directiva de correo no deseado saliente, el resultado será que el mensaje reenviado automáticamente está bloqueado. De forma similar, si se permite el reenvío automático en la Directiva de correo no deseado saliente, pero se bloquea en un dominio de ETR o remoto, cualquiera de estos controles bloqueará el mensaje. Esto le permite, por ejemplo, permitir el reenvío automático en la Directiva de correo no deseado saliente y usar dominios remotos para controlar los dominios a los que los usuarios pueden reenviar mensajes automáticamente.


## <a name="the-blocked-email-forwarding-message"></a>Mensaje de reenvío de correo electrónico bloqueado

Cuando se detecta un mensaje como reenviado automáticamente y la directiva organizativa *bloquea* dicha actividad, se generará un **Informe de no entrega (NDR)** para el usuario final. El informe indicará que el mensaje no se entregó. El NDR tendrá el siguiente formato: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
