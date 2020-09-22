---
title: Flujo de correo en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: El administrador puede obtener información sobre las opciones para configurar el flujo de correo y el enrutamiento en Exchange Online Protection (EOP).
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200708"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En Microsoft 365 organizaciones con buzones de Exchange online o con organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a la organización pasan a través de EOP antes de que los trabajadores los vean. Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enruten a sus buzones de trabajo.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece flexibilidad en el modo en que se enrutan los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica de bloqueo perimetral basado en directorios que permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.

[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre subdominios en [enable mail Flow for Subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar el flujo de correo mediante conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta los conectores y muestra cómo se pueden usar para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

El [filtrado mejorado para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.

En las organizaciones independientes de EOP, debe realizar un par de pasos de configuración para asegurarse de que el correo no deseado se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario. Se describen en [Configure Standalone EOP para entregar el correo no deseado a la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta de correo electrónico no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).

[Probar el flujo de correo mediante la validación de los conectores de 365 de Microsoft](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) proporciona instrucciones para probar que el flujo de correo está configurado correctamente.
