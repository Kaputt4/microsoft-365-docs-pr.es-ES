---
title: Usar el asistente para configurar Microsoft Defender para empresas (versión preliminar)
description: Defender para empresas incluye un proceso de configuración y configuración parecido a un asistente. Use el asistente para ahorrar tiempo y esfuerzo.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/08/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 1659925081a96b4122910319b5c0a294d007f0b9
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62465359"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business-preview"></a>Usar el asistente para configurar Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Microsoft Defender para empresas (versión preliminar) se diseñó para ahorrar tiempo y esfuerzo a pequeñas y medianas empresas con una experiencia de asistente para la configuración y configuración iniciales. En este artículo se describen los pasos del asistente y las opciones para configurar y configurar Defender para empresas manualmente.

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Captura de pantalla de inicio del asistente para configurar Defender para empresas.":::

## <a name="overview-of-the-wizard"></a>Información general del asistente

El asistente está diseñado para ayudarle a configurar Defender for Business de forma rápida y eficaz. El asistente le guiará por los siguientes pasos:

1. **Asignar permisos de usuario**. En este paso, concederá a su equipo de seguridad acceso al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). El acceso al portal se concede a través de roles que implican ciertos permisos. [Obtenga más información sobre roles y permisos](mdb-roles-permissions.md).

   - Un administrador global puede ver y editar todas las opciones de configuración en Microsoft 365 inquilino. 
   - Un administrador de seguridad puede ver y editar la configuración de seguridad. 
   - Un lector de seguridad solo puede ver información en los informes. 

2. **Configurar notificaciones por correo electrónico**. En este paso, se determina quién debe recibir notificaciones por correo electrónico en caso de vulnerabilidad detectada o una nueva alerta. Las notificaciones por correo electrónico pueden ayudar a mantener informado a su equipo de seguridad, incluso si están lejos de su escritorio. [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). 

3. **Incorpore y configure Windows dispositivos**. En este paso, puede incorporar rápidamente los dispositivos de Windows de la organización a Defender para empresas. La incorporación de dispositivos de inmediato ayuda a proteger esos dispositivos desde el primer día. [Obtén más información sobre la incorporación de dispositivos](mdb-onboard-devices.md).

   - Si ya estás usando Microsoft Endpoint Manager (que incluye Microsoft Intune), se te preguntará si quieres usar la incorporación automática, que establece una conexión entre Endpoint Manager y Defender para empresas y, a continuación, incorpora todos los dispositivos Windows que están inscritos en Endpoint Manager. 
   - Si aún no estás usando Endpoint Manager, puedes usar la incorporación gradual de dispositivos y elegir un conjunto de dispositivos para incorporarse a Defender para empresas. 
   
4. **Configure las directivas de seguridad**. Defender para empresas incluye directivas de seguridad predeterminadas que se pueden aplicar a los dispositivos de la organización. Estas directivas predeterminadas usan la configuración recomendada y están diseñadas para proporcionar una protección segura para los dispositivos. Sin embargo, también puede crear sus propias directivas de seguridad si lo desea. Y, si ya está usando Endpoint Manager, puede seguir usándolo para administrar las directivas de seguridad. 

   - [Obtenga más información sobre la configuración simplificada](mdb-simplified-configuration.md).
   - [Elige dónde administrar dispositivos y directivas de seguridad](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices).

## <a name="what-happens-if-i-dont-use-the-wizard"></a>¿Qué sucede si no uso el asistente?

Si decide no usar el asistente o si sale del asistente antes de que finalice el proceso de instalación, podrá completar el proceso de configuración y configuración por su cuenta. Consulta [Configurar y configurar Microsoft Defender para empresas (versión preliminar)](mdb-setup-configuration.md) para seguir los pasos.

## <a name="next-steps"></a>Siguientes pasos

- [Introducción al uso del portal Microsoft 365 Defender web](mdb-get-started.md)

- [Usar el panel de administración & vulnerabilidades](mdb-view-tvm-dashboard.md)