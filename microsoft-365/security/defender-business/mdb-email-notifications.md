---
title: Configurar notificaciones de correo electrónico para el equipo de seguridad
description: Configurar notificaciones de correo electrónico para que los usuarios le informen sobre alertas y vulnerabilidades con Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 5ccad3a8765c18e1768f8245d90b255d50ee5182
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507373"
---
# <a name="set-up-email-notifications"></a>Configurar notificaciones por correo electrónico

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 


Puede configurar las notificaciones por correo electrónico para su equipo de seguridad. A continuación, a medida que se generen alertas o se descubran nuevas vulnerabilidades, se notificará automáticamente a los usuarios del equipo de seguridad. 

## <a name="what-to-do"></a>Qué hacer

1. [Obtenga información sobre los tipos de notificaciones de correo electrónico](#types-of-email-notifications).

2. [Ver y editar la configuración de notificación de correo electrónico](#view-and-edit-email-notifications).

3. [Continúe con los pasos siguientes](#next-steps).


## <a name="types-of-email-notifications"></a>Tipos de notificaciones de correo electrónico

Al configurar las notificaciones por correo electrónico, puede elegir entre dos tipos, como se describe en la tabla siguiente: <br/><br/>

| Tipo de notificación  | Descripción  |
|---------|---------|
| Vulnerabilidades  | Cada vez que se detectan nuevos eventos de vulnerabilidad o vulnerabilidad, los destinatarios reciben un correo electrónico. |
| Alertas & vulnerabilidades  | Cuando se generan alertas porque se detectan amenazas en dispositivos o cuando se detectan nuevos eventos de vulnerabilidad o vulnerabilidad, los destinatarios reciben un correo electrónico. |

> [!TIP]
> Las notificaciones por correo electrónico no son la única forma en que el equipo de **seguridad puede averiguar sobre nuevas alertas o vulnerabilidades.**
> 
> Las notificaciones por correo electrónico son una forma cómoda de ayudar a mantener informado a su equipo de seguridad en tiempo real. Pero hay otros. Por ejemplo, siempre que el equipo de seguridad inicia sesión en el portal de Microsoft 365 Defender ( ), verá tarjetas que resaltan nuevas [https://security.microsoft.com](https://security.microsoft.com) amenazas, alertas y vulnerabilidades. Defender para empresas (versión preliminar) está diseñado para resaltar información importante que le importa al equipo de seguridad tan pronto como inicie sesión.
> 
> El equipo de seguridad también puede elegir **Incidentes** en el panel de navegación para ver información. Para obtener más información, [vea Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar).](mdb-view-manage-incidents.md)

## <a name="view-and-edit-email-notifications"></a>Ver y editar notificaciones de correo electrónico

Para ver o editar la configuración de notificaciones por correo electrónico de su empresa, siga estos pasos:

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, **seleccione Configuración** y, a continuación, seleccione **Extremos**. A continuación, **en General**, seleccione **Notificaciones de correo electrónico**. 

3. Revise la información de las **pestañas Alertas** **y** vulnerabilidades.

   - Si no ve ningún elemento en  la pestaña Alertas, puede crear una regla para que se notifique a las personas cuando se generen alertas. Para obtener ayuda con esta tarea, vea [Create rules for alert notifications](../defender-endpoint/configure-email-notifications.md).

   - Si no ve ningún elemento enumerado  en la pestaña Vulnerabilidades, puede crear una regla para que se notifique a las personas cada vez que se descubra una nueva vulnerabilidad. Para obtener ayuda con esta tarea, vea [Create rules for vulnerability events](../defender-endpoint/configure-vulnerability-email-notifications.md).

   - Si tiene reglas creadas, seleccione una regla para editarla. También puede eliminar una regla. 

## <a name="next-steps"></a>Pasos siguientes

Continúe con:

- [Paso 4: Incorporar dispositivos a Microsoft Defender para empresas (versión preliminar)](mdb-onboard-devices.md)

