---
title: Uso del Asistente para instalación en Microsoft Defender para Empresas
description: Defender para empresas incluye un proceso de configuración y configuración similar a un asistente. Use el asistente para ahorrar tiempo y esfuerzo.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: ad070273567d350973037f1ac5a0192036d22187
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746653"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>Uso del asistente para la instalación en Microsoft Defender para Empresas

> [!IMPORTANT]
> Microsoft Defender para Empresas se está implementando para [Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender for Business como una suscripción independiente está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarla. La versión preliminar incluye un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí. 

Microsoft Defender para Empresas se diseñó para ahorrar tiempo y esfuerzo a las pequeñas y medianas empresas con una experiencia similar a un asistente para la configuración y configuración iniciales. El asistente para la configuración le guía a través de la concesión de acceso al equipo de seguridad, la configuración de notificaciones por correo electrónico para el equipo de seguridad y la incorporación de los dispositivos de Windows de su empresa.

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Captura de pantalla de la pantalla principal del asistente para configurar Defender para empresas.":::

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre Microsoft Defender para Empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="overview-of-the-setup-wizard"></a>Información general del asistente para la instalación

> [!IMPORTANT]
> Antes de empezar, asegúrese de que ya ha agregado usuarios a la suscripción de Microsoft 365. Para obtener ayuda con esta tarea, consulte [Agregar usuarios y asignar licencias al mismo tiempo](../../admin/add-users/add-users.md).

El asistente está diseñado para ayudarle a configurar Defender para empresas de forma rápida y eficaz. El asistente le guiará por los pasos siguientes:

1. **Asignar permisos de usuario**. En este paso, concederá acceso al equipo de seguridad al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este portal, usted y su equipo de seguridad administrarán sus funcionalidades de seguridad, verán alertas y realizarán las acciones necesarias en las amenazas detectadas. El acceso al portal se concede a través de roles que implican ciertos permisos.

   En Defender para empresas, a los miembros del equipo de seguridad se les puede asignar uno de los tres roles:<br/>
   
      - **Administrador global**: un administrador global puede ver y editar toda la configuración en el inquilino de Microsoft 365. El administrador global realiza la configuración y configuración iniciales de la suscripción de Microsoft 365 de la empresa. 
      - **Administrador de** seguridad: un administrador de seguridad puede ver y editar la configuración de seguridad y tomar medidas cuando se detectan amenazas.
      - **Lector de** seguridad: un lector de seguridad puede ver información en los informes, pero no puede cambiar ninguna configuración de seguridad. 
      
      [Obtenga más información sobre los roles y permisos](mdb-roles-permissions.md). 

2. **Configurar notificaciones por correo electrónico**. En este paso, puede configurar notificaciones por correo electrónico para el equipo de seguridad. A continuación, cuando se genera una alerta o se detecta una nueva vulnerabilidad, el equipo de seguridad no lo hará aunque esté fuera de su escritorio. 

   [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). 

3. **Incorporación y configuración de dispositivos Windows**. En este paso, puede incorporar rápidamente los dispositivos Windows de su empresa a Defender for Business. La incorporación de dispositivos de inmediato ayuda a proteger esos dispositivos desde el primer día. 

   - **Si ya usa Microsoft Endpoint Manager** (que incluye Microsoft Intune) y su empresa tiene dispositivos inscritos en Endpoint Manager, se le preguntará si desea usar la [incorporación automática](mdb-onboard-devices.md#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager) para algunos o todos los dispositivos Windows inscritos. La incorporación automática configura una conexión entre Endpoint Manager y Defender for Business y, a continuación, incorpora Windows dispositivos a Defender for Business sin problemas. 
   - **Si aún no usa Endpoint Manager**, puede [incorporar dispositivos a Defender for Business mediante un script local](mdb-onboard-devices.md#local-script-in-defender-for-business). 
   
   Consulte [Más información sobre la incorporación de dispositivos a Microsoft Defender para Empresas](mdb-onboard-devices.md).
   
4. **Configure las directivas de seguridad**. Defender for Business incluye directivas de seguridad predeterminadas para la protección de próxima generación y la protección de firewall que se pueden aplicar a los dispositivos de la empresa. Estas directivas predeterminadas usan la configuración recomendada y están diseñadas para proporcionar una protección segura para los dispositivos. También puede crear sus propias directivas de seguridad. Y, si ya usa Endpoint Manager, puede seguir usándolo para administrar las directivas de seguridad.

   Para obtener más información, consulte [Visualización y edición de las directivas y la configuración de seguridad](mdb-configure-security-settings.md). |

## <a name="what-happens-if-i-dont-use-the-wizard"></a>¿Qué ocurre si no uso el asistente?

El uso del asistente para la instalación es opcional. Si decide no usar el asistente o si el asistente se cierra antes de que se complete el proceso de instalación, puede completar el proceso de instalación y configuración por su cuenta. Consulte [Configuración y configuración de Microsoft Defender para Empresas](mdb-setup-configuration.md) para seguir estos pasos:

1. **[Asigne roles y permisos](mdb-roles-permissions.md)** para que el equipo de seguridad pueda acceder y usar el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)).

2. **[Configure las notificaciones por correo electrónico para el equipo de seguridad para](mdb-email-notifications.md)** que estén en el bucle sobre nuevas alertas o vulnerabilidades.

3. **[Incorpore dispositivos](mdb-onboard-devices.md)** para que estén protegidos por Defender para empresas.

4. **[Administre las directivas de seguridad](mdb-configure-security-settings.md)**, que incluyen protección de última generación, protección contra firewalls y filtrado de contenido web.

## <a name="next-steps"></a>Siguientes pasos

- [Configuración de notificaciones por correo electrónico para el equipo de seguridad](mdb-email-notifications.md)

- [Comenzar mediante el portal de Microsoft 365 Defender](mdb-get-started.md)

- [Uso del panel de administración de vulnerabilidades & amenazas](mdb-view-tvm-dashboard.md)