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
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907031"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que los trabajadores los vean. Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enrute a las bandejas de entrada de los trabajadores.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece flexibilidad en la forma en que se enruta los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Usar el bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica bloqueo perimetral basado en directorios que le permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.

[Ver o editar dominios administrados en EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre los subdominios en [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar el flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

[El filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.

En organizaciones EOP independientes, debe realizar un par de pasos de configuración para asegurarse de que el correo no deseado se enruta correctamente a la carpeta de correo no deseado de cada usuario. Estos se detallan en [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta de correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).

[Probar el flujo de correo validando los conectores de Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow) proporciona instrucciones para probar que el flujo de correo está configurado correctamente.