---
title: Configurar y controlar el reenvío de correo electrónico externo, reenvío automático, acceso denegado 5.7.520, deshabilitar el reenvío externo, El administrador ha deshabilitado el reenvío externo, la directiva de correo no deseado saliente
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071443"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controlar el reenvío automático de correo electrónico externo en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Como administrador, es posible que tenga requisitos de la empresa para restringir o controlar los mensajes reenviados automáticamente a destinatarios externos (destinatarios fuera de la organización). El reenvío de correo electrónico puede ser útil, pero también puede suponer un riesgo de seguridad debido a la posible divulgación de información. Los atacantes pueden usar esta información para atacar a su organización o socios.


Los siguientes tipos de reenvío automático están disponibles en Microsoft 365:

- Los usuarios pueden configurar [reglas de](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) la Bandeja de entrada para reenviar automáticamente mensajes a remitentes externos (deliberadamente o como resultado de una cuenta comprometida).

- Los administradores pueden configurar [el reenvío de buzones](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (también conocido como reenvío _SMTP)_ para reenviar automáticamente mensajes a destinatarios externos. El administrador puede elegir si simplemente reenviar mensajes o mantener copias de mensajes reenviados en el buzón.

Puede usar las directivas del filtro de correo no deseado saliente para controlar el reenvío automático a destinatarios externos. Hay tres opciones disponibles:

- **Automático:** se bloquea el reenvío externo automático. El reenvío automático interno de mensajes seguirá funcionando. Esta configuración es la predeterminada.
- **On**: El reenvío externo automático está permitido y no restringido.
- **Desactivado:** el reenvío externo automático está deshabilitado y dará como resultado un informe de no entrega (también conocido como NDR o mensaje de desenviamiento) al remitente.

Para obtener instrucciones sobre cómo configurar estas opciones, vea [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Deshabilitar el reenvío automático deshabilita las reglas de la Bandeja de entrada (usuarios) o el reenvío de buzones (administradores) que redirigen los mensajes a direcciones externas.
>
> - El reenvío automático de mensajes entre usuarios internos no se ve afectado por la configuración de las directivas de filtro de correo no deseado saliente.
>
> - Puede ver información sobre los usuarios que reenvía automáticamente mensajes a destinatarios externos en el informe Mensajes reenviados [automáticamente.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Cómo funciona la configuración de directiva de filtro de correo no deseado saliente con otros controles de reenvío automático de correo electrónico

Como administrador, es posible que ya haya configurado otros controles para permitir o bloquear el reenvío automático de correo electrónico. Por ejemplo:

- [Dominios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir o bloquear el reenvío automático de correo electrónico a algunos o todos los dominios externos.

- Condiciones y acciones en las [reglas](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) de flujo de correo de Exchange (también conocidas como reglas de transporte) para detectar y bloquear mensajes reenviados automáticamente a destinatarios externos.

La configuración de dominio remoto y las reglas de flujo de correo son independientes de la configuración de las directivas de filtro de correo no deseado saliente. Por ejemplo:

- Se permite el reenvío automático para un dominio remoto, pero se bloquea el reenvío automático en directivas de filtro de correo no deseado saliente. En este ejemplo, se bloquean los mensajes reenviados automáticamente.

- Permite el reenvío automático en directivas de filtro de correo no deseado saliente, pero usa reglas de flujo de correo o configuración de dominio remoto para bloquear el correo electrónico reenviado automáticamente. En este ejemplo, las reglas de flujo de correo o la configuración de dominio remoto bloquearán los mensajes reenviados automáticamente.

Esta independencia de características le permite (por ejemplo) permitir el reenvío automático en directivas de filtro de correo no deseado saliente, pero usar dominios remotos para controlar los dominios externos a los que los usuarios pueden reenviar mensajes.

## <a name="blocked-email-forwarding-messages"></a>Mensajes de reenvío de correo electrónico bloqueados

Cuando se detecta un mensaje como reenviado  automáticamente y la directiva de filtro de [correo](configure-the-outbound-spam-policy.md) no deseado saliente bloquea esa actividad, el mensaje se devuelve al remitente en un NDR que contiene la siguiente información:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`