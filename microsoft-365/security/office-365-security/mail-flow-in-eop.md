---
title: Flujo de correo en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Como cliente de Exchange Online Protection (EOP), todos los mensajes enviados a su organización pasan a través de EOP antes de sus trabajadores los vean. Tanto si hospeda todos los buzones en la nube con Exchange Online, como si los hospeda localmente (lo que se denomina escenario independiente), quizás para continuar aprovechando las ventajas de la infraestructura existente, puede elegir cómo enrutar los mensajes que pasarán por EOP para procesarlos antes de que se enruten a los buzones de los trabajadores.
ms.openlocfilehash: cbe369e5bf522cb966fd448970f07a34a141d610
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630484"
---
# <a name="mail-flow-in-eop"></a>Flujo de correo en EOP

Como cliente de Exchange Online Protection (EOP), todos los mensajes enviados a su organización pasan a través de EOP antes de sus trabajadores los vean. Tanto si hospeda todos los buzones en la nube con Exchange Online, como si los hospeda localmente (lo que se denomina escenario independiente), quizás para continuar aprovechando las ventajas de la infraestructura existente, puede elegir cómo enrutar los mensajes que pasarán por EOP para procesarlos antes de que se enruten a los buzones de los trabajadores.

Quizás quiera configurar un enrutamiento de correo personalizado para que su mensajería cumpla los requisitos de la empresa. Por ejemplo, se puede pasar todo el correo electrónico saliente a través de un dispositivo de filtrado de directivas.

## <a name="working-with-messages-and-message-access-options"></a>Trabajar con mensajes y opciones de acceso de mensajes

EOP ofrece mucha flexibilidad para enrutar los mensajes. Los temas siguientes explican los pasos del proceso de flujo de correo.

[Usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describe la característica de bloqueo perimetral basado en directorios que permite rechazar mensajes para destinatarios no válidos en el perímetro de la red de servicio.

[Ver o editar dominios administrados en EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describe cómo administrar dominios asociados con el servicio de EOP.

Si agrega subdominios a la organización, el servicio de EOP también puede ayudarle a administrarlos. Obtenga más información sobre subdominios en [enable mail Flow for Subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) presenta los conectores y muestra cómo usarlos para personalizar el enrutamiento de correo. Los escenarios incluyen garantizar una comunicación segura con una organización asociada y configurar un host inteligente.

Para asegurarse de que el correo electrónico no deseado se enruta correctamente a la carpeta de correo electrónico no deseado de cada usuario, debe realizar un par de pasos de configuración. Se describen en [Configure Standalone EOP para entregar el correo no deseado a la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Si no desea mover mensajes a la carpeta de correo electrónico no deseado de cada usuario, puede elegir otra acción editando las directivas de filtro de contenido en el centro de administración de Exchange. Para obtener más información, consulte [configurar directivas contra correo no deseado](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Comprobar el flujo de correo

Para comprobar que la configuración de EOP, incluida la configuración de conectores, esté funcionando correctamente, consulte la sección "¿Cómo sabe si esta tarea se ha completado correctamente?" en [Configurar un servicio de EOP](set-up-your-eop-service.md).

[Probar el flujo de correo mediante la validación de los conectores de 365 de Microsoft](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) proporciona instrucciones para probar que el flujo de correo está configurado correctamente.
