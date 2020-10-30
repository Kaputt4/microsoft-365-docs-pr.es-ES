---
title: Configurar y controlar el reenvío externo de correo electrónico, el reenvío automático, 5.7.520 acceso denegado, deshabilitar el reenvío externo, el administrador deshabilitó el reenvío externo, la Directiva de correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 59e2c938c70dd8e3060fd85d084acbe8f79856ad
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806641"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controlar el reenvío de correo electrónico externo automático en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Como administrador, puede tener los requisitos de la compañía para restringir o controlar los mensajes reenviados automáticamente a los destinatarios externos (destinatarios fuera de la organización). El reenvío de correo electrónico puede resultar útil, pero también puede suponer un riesgo de seguridad debido a la posible revelación de información. Los atacantes podrían usar esta información para atacar a su organización o a sus socios.

Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:

- Los usuarios pueden configurar [las reglas](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) de la bandeja de entrada para reenviar mensajes de forma automática a los remitentes externos (deliberadamente o como resultado de una cuenta en peligro).

- Los administradores pueden configurar el [reenvío de buzón](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como reenvío _SMTP_ ) para reenviar mensajes automáticamente a los destinatarios externos.

Puede usar las directivas de filtro de correo no deseado saliente para controlar el reenvío automático a los destinatarios externos. Hay tres opciones de configuración disponibles:

- **Automático** : el reenvío externo automático está bloqueado. El reenvío automático interno de los mensajes seguirá funcionando. Esta configuración es la predeterminada.

- **On** : el reenvío externo automático está permitido y no está restringido.

- **Desactivado** : el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (también conocido como mensaje NDR o de devolución) al remitente.

Para obtener instrucciones sobre cómo configurar estas opciones, vea [configurar el filtrado de correo no deseado saliente en EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
> 
> - Al deshabilitar el reenvío automático se deshabilita cualquier regla de la bandeja de entrada (usuarios) o reenvío de buzón (administradores) que redirigen mensajes a direcciones externas.
> 
> - El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.
> 
> - Puede ver información sobre los usuarios que reenvían automáticamente los mensajes a los destinatarios externos en el [Informe de mensajes reenviados automáticamente](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Cómo funciona la configuración de la Directiva de filtro de correo no deseado saliente con otros controles de reenvío de correo electrónico automático

Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico. Por ejemplo:

- [Dominios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.

- Condiciones y acciones de [las reglas de flujo de correo](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de Exchange (también conocidas como reglas de transporte) para detectar y bloquear mensajes reenviados automáticamente a destinatarios externos.

La configuración del dominio remoto y las reglas de flujo de correo son independientes de la configuración en las directivas de filtro de correo no deseado saliente. Por ejemplo:

- Permite el reenvío automático para un dominio remoto, pero bloquea el reenvío automático en las directivas de filtro de correo no deseado saliente. En este ejemplo, los mensajes reenviados automáticamente están bloqueados.

- Permite el reenvío automático en las directivas de filtro de correo no deseado saliente, pero usa reglas de flujo de correo o la configuración de dominio remoto para bloquear el correo electrónico reenviado automáticamente. En este ejemplo, las reglas de flujo de correo o la configuración de dominio remoto bloquearán los mensajes que se reenviarán automáticamente.

Esta independencia de características le permite (por ejemplo) permitir el reenvío automático en las directivas de filtro de correo no deseado salientes, pero usa dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.

## <a name="the-blocked-email-forwarding-message"></a>Mensaje de reenvío de correo electrónico bloqueado

Cuando se detecta un mensaje como reenviado automáticamente y la Directiva de la organización *bloquea* dicha actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
