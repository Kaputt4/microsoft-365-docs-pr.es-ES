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
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: El administrador puede obtener información sobre las opciones para configurar el flujo de correo y el enrutamiento en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167244"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que los vean sus trabajadores. Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enrutar a las bandejas de entrada de los trabajadores.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece flexibilidad para enrutar los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Usar el bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica bloqueo perimetral basado en directorios, que permite rechazar mensajes de destinatarios no válidos en el perímetro de la red de servicio.

[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre subdominios en [Habilitar flujo de correo para subdominios en Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Configurar el flujo de correo mediante conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

[El filtrado mejorado para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.

En las organizaciones de EOP independientes, debe realizar un par de pasos de configuración para asegurarse de que el correo no deseado se enruta correctamente a la carpeta de correo no deseado de cada usuario. Estos se detallan en Configurar EOP independiente para entregar correo no deseado a la carpeta correo no deseado [en entornos híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).

Para probar el flujo de correo mediante la validación de los conectores de [Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) se proporcionan instrucciones para probar que el flujo de correo está configurado correctamente.
