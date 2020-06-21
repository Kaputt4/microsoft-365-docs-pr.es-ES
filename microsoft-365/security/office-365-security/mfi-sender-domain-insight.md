---
title: Solucionar la información del dominio del remitente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre la información sobre el dominio del remitente en el panel de flujo de correo en el centro de seguridad & cumplimiento.
ms.openlocfilehash: c4cf4a87ad770325ca6ad2f0b87ac8ce52c345c2
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818836"
---
# <a name="fix-sender-domain-insight"></a>Solucionar la información del dominio del remitente

Microsoft 365 requiere mensajes que envíen desde entornos de correo electrónico locales internos a Microsoft 365 para cumplir ciertos criterios de seguridad:

- Ha creado un conector de entrada en Microsoft 365 para autenticar las conexiones SMTP desde el servidor de correo electrónico local mediante el uso de la dirección IP de origen o un certificado.

- Ha configurado su servidor de correo electrónico local para retransmitir el correo electrónico a través de Microsoft 365 a un mundo externo.

- En la configuración, se cumple una de las siguientes instrucciones:

  - El dominio de correo electrónico del remitente está registrado en la organización. Para obtener más información, consulte Agregar dominios a Office 365.

  - El servidor de correo electrónico local está configurado para usar un certificado para enviar correo electrónico a Microsoft 365, el certificado contiene o coincide exactamente con un nombre de dominio que se ha registrado en Microsoft 365, y ha creado un conector basado en certificado en Microsoft 365 con ese dominio. 

Los mensajes que no cumplen los criterios no se atribuirán a la organización y podrían rechazarse.

La introducción a **Fix Domain Sender** le muestra el correo electrónico de su entorno local que no cumple con los criterios, le ayuda a identificar las cuentas de usuario y equipos potencialmente comprometidos en su entorno de correo electrónico local y le ayuda a tomar medidas de corrección.

![La información del dominio del remitente Fix del panel del flujo de correo del centro de seguridad & cumplimiento](../../media/sender-domain-insight-selected.png)

Al hacer clic en **Ver detalles**, se le lleva a otro widget con más detalles como se muestra en el siguiente diagrama:

![Widget de detalles en el información sobre la solución de dominio del remitente](../../media/sender-domain-view-details.png)

Verá el conector de entrada que se usó para entregar los mensajes a Office 365. También puede hacer clic en **ver identificadores de mensaje de ejemplo** para ver los detalles de los mensajes que se enviaron desde su entorno de correo electrónico local. Debido a que estos mensajes fueron rechazados por Office 365, no puede usar el seguimiento de mensajes, pero puede usar los identificadores de mensaje de ejemplo para realizar un seguimiento de los mensajes en su entorno de correo electrónico local.

![Ver identificadores de mensaje de ejemplo en el información de dominio del remitente de corrección](../../media/sender-domain-view-sample-message-ids.png)

## <a name="related-topics"></a>Temas relacionados

Para obtener más información acerca de otras indicaciones del flujo de correo en el panel de flujo de correo, consulte [mail Flow Insights en el centro de seguridad & cumplimiento](mail-flow-insights-v2.md).
