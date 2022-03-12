---
title: Usar el asistente para configurar Microsoft Defender para empresas
description: Defender para empresas incluye un proceso de configuración y configuración parecido a un asistente. Use el asistente para ahorrar tiempo y esfuerzo.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/10/2022
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
ms.openlocfilehash: 2cc157e363c42b94cac750b19a6122ed0a22c3de
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "63450764"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business"></a>Usar el asistente para configurar Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Microsoft Defender para empresas se diseñó para ahorrar tiempo y esfuerzo a pequeñas y medianas empresas con una experiencia de asistente para la configuración y configuración iniciales. En este artículo se describen los pasos del asistente y las opciones para configurar y configurar Defender para empresas manualmente.

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Captura de pantalla de inicio del asistente para configurar Defender para empresas.":::

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="overview-of-the-wizard"></a>Información general del asistente

El asistente está diseñado para ayudarle a configurar Defender for Business de forma rápida y eficaz. El asistente le guiará por los siguientes pasos:

1. **Asignar permisos de usuario**. En este paso, concederá a su equipo de seguridad acceso al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). El acceso al portal se concede a través de roles que implican ciertos permisos. [Obtenga más información sobre roles y permisos](mdb-roles-permissions.md).

   - Un administrador global puede ver y editar toda la configuración en Microsoft 365 inquilino. 
   - Un administrador de seguridad puede ver y editar la configuración de seguridad. 
   - Un lector de seguridad solo puede ver información en los informes. 

2. **Incorpore y configure Windows dispositivos.** En este paso, puede incorporar rápidamente los dispositivos de Windows de la organización a Defender para empresas. La incorporación de dispositivos de inmediato ayuda a proteger esos dispositivos desde el primer día. Consulta [Incorporar dispositivos a Microsoft Defender para empresas](mdb-onboard-devices.md) para obtener más información.

   - Si ya usa Microsoft Intune (parte de Microsoft Endpoint Manager) y su organización tiene dispositivos inscritos en Endpoint Manager, se le preguntará si desea usar la incorporación automática para algunos o todos los dispositivos Windows inscritos.[](mdb-onboard-devices.md#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager) La incorporación automática configura una conexión entre Endpoint Manager y Defender para empresas y, a continuación, incorpora Windows dispositivos a Defender para empresas sin problemas.

   - Si aún no estás usando Endpoint Manager, o si tienes dispositivos que no son de Windows inscritos en Endpoint Manager, puedes incorporar dispositivos a [Defender para empresas manualmente](mdb-onboard-devices.md#local-script-in-defender-for-business). 
   
3. **Configure las directivas de seguridad**. Defender para empresas incluye directivas de seguridad predeterminadas para protección de última generación y protección de firewall que se pueden aplicar a los dispositivos de su organización. Estas directivas predeterminadas usan la configuración recomendada y están diseñadas para proporcionar una protección segura para los dispositivos. 

   También puede crear sus propias directivas de seguridad si lo desea. Y, si ya está usando Endpoint Manager, puede seguir usándolo para administrar las directivas de seguridad. 

   Para obtener más información, consulta [Ver y editar las directivas y la configuración de seguridad](mdb-configure-security-settings.md).

## <a name="what-happens-if-i-dont-use-the-wizard"></a>¿Qué sucede si no uso el asistente?

Si decide no usar el asistente o si el asistente se cierra antes de que finalice el proceso de configuración, puede completar el proceso de configuración y configuración por su cuenta. 

Consulta [Configurar y configurar Microsoft Defender para empresas](mdb-setup-configuration.md) para seguir estos pasos:

1. [Asigne roles y permisos para](mdb-roles-permissions.md) que el equipo de seguridad pueda tener acceso al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)).

2. [Configure las notificaciones de correo electrónico para su](mdb-email-notifications.md) equipo de seguridad para que se den cuenta de nuevas alertas o vulnerabilidades.

3. [Incorpore](mdb-onboard-devices.md) dispositivos para que estén protegidos por Defender para empresas.

4. [Administre las directivas de seguridad](mdb-configure-security-settings.md), que incluyen protección de última generación, protección de firewall y filtrado de contenido web.

## <a name="next-steps"></a>Siguientes pasos

- [Configurar notificaciones de correo electrónico para el equipo de seguridad](mdb-email-notifications.md)

- [Introducción al uso del portal Microsoft 365 Defender web](mdb-get-started.md)

- [Usar el panel de administración & vulnerabilidades](mdb-view-tvm-dashboard.md)