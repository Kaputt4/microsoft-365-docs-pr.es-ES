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
ms.localizationpriority: medium
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Administración puede obtener información sobre las opciones para configurar el flujo de correo y el enrutamiento en Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: 15a0bf969a1b1c8254845be3c4c06eb556366bf1
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597876"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, todos los mensajes enviados a su organización pasan a través de EOP antes de que los usuarios los vean. Tiene opciones sobre cómo enrutar los mensajes que pasan a través de EOP para su procesamiento antes de que se enruten a buzones de usuario.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece flexibilidad en la forma en que se enrutan los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Uso del bloqueo perimetral basado en directorios para rechazar los mensajes enviados a destinatarios no válidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica de bloqueo perimetral basado en directorios, que permite rechazar mensajes de destinatarios no válidos en el perímetro de red del servicio.

[Ver o editar dominios aceptados en EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre los subdominios en [Habilitar el flujo de correo para subdominios en Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configurar el flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta conectores y muestra cómo puede usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

[Filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describe cómo configurar conectores si el correo se enruta a un servicio o dispositivo antes de EOP.

En entornos híbridos donde EOP protege los buzones de Exchange locales, debe configurar reglas de flujo de correo (también conocidas como reglas de transporte) en Exchange local. Estas reglas de flujo de correo traducen el veredicto de filtrado de correo no deseado de EOP para que la regla de correo no deseado del buzón pueda mover el mensaje a la carpeta De correo no deseado Email. Para obtener información, consulte [Configuración de un EOP para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Si no desea mover mensajes a la carpeta de Email no deseado de cada usuario, puede elegir otra acción editando las directivas de antispam (también conocidas como directivas de filtro de contenido). Para obtener más información, consulte [Configurar directivas contra correo electrónico no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](/exchange/standalone-eop/set-up-your-eop-service).

[Probar el flujo de correo mediante la validación de los conectores de Microsoft 365](/exchange/mail-flow-best-practices/test-mail-flow) proporciona instrucciones para probar que el flujo de correo está configurado correctamente.
