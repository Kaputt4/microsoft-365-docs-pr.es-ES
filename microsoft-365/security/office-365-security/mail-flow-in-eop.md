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
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842499"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que los trabajadores los vean. Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enrute a las bandejas de entrada de los trabajadores.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece flexibilidad en la forma en que se enruta los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Usar el bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica bloqueo perimetral basado en directorios que le permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.

[Ver o editar dominios aceptados en EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre los subdominios en [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar el flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

[El filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.

En entornos híbridos en los que EOP protege los buzones de Exchange locales, tiene que configurar las reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local para traducir el veredicto de filtro de correo no deseado de EOP para que la regla de correo no deseado pueda mover el mensaje a la carpeta de correo electrónico no deseado. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Si no desea mover mensajes a la carpeta correo no deseado de cada usuario, puede elegir otra acción editando las directivas contra correo no deseado (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](/exchange/standalone-eop/set-up-your-eop-service).

[Probar el flujo de correo validando los conectores Microsoft 365 proporciona](/exchange/mail-flow-best-practices/test-mail-flow) instrucciones para probar que el flujo de correo está configurado correctamente.
