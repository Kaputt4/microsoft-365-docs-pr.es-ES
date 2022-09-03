---
title: Uso del Asistente para instalación en Microsoft Defender para Empresas
description: Defender for Business facilita la configuración con un asistente que se ejecuta la primera vez que usa Defender para empresas. Vea cómo funciona el asistente para la instalación.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: c0b9666a280b159df4e1b985b733c73565477241
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597534"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>Uso del asistente para la instalación en Microsoft Defender para Empresas

Defender para Empresas fue diseñado para ahorrar tiempo y esfuerzo a las pequeñas y medianas empresas. Por ejemplo, puede realizar la configuración y la configuración iniciales con un asistente para la instalación. El asistente de configuración le guía a través de la concesión de acceso al equipo de seguridad, la configuración de notificaciones por correo electrónico para el equipo de seguridad y la incorporación de los dispositivos Windows de su empresa.

> [!TIP]
> El uso del asistente de configuración es opcional. Puede optar por trabajar manualmente en el proceso de configuración y configuración. Para más información, vea:
> - [¿Qué ocurre si no uso el asistente?](#what-happens-if-i-dont-use-the-wizard)
> - [Configuración y configuración de Defender para empresas](mdb-setup-configuration.md)

## <a name="how-to-start-the-setup-wizard"></a>Cómo iniciar el asistente para la instalación

El asistente para la instalación está diseñado para ejecutarse la primera vez que alguien de la empresa inicia sesión en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). 

Si su empresa ha estado usando Microsoft 365 Empresa Premium, el Asistente para la configuración de Defender para empresas se ejecutará la primera vez que alguien vaya al **inventario de** **dispositivos de puntos de conexión** > . 

La pantalla de inicio del asistente para la instalación es similar a la siguiente imagen:

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Captura de pantalla de la pantalla principal del asistente para configurar Defender para empresas.":::

## <a name="the-setup-wizard-flow"></a>Flujo del asistente de instalación

> [!IMPORTANT]
> Debe ser administrador global para ejecutar el asistente de instalación. La persona que registró su empresa para Microsoft 365 o para Defender para empresas es un administrador global de forma predeterminada.

El asistente para la instalación está diseñado para ayudarle a configurar Defender for Business de forma rápida y eficaz. El asistente le guiará por los pasos siguientes:

1. **Asignar permisos de usuario**. En este paso, concederá acceso al equipo de seguridad al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). En este portal, usted y su equipo de seguridad administrarán sus funcionalidades de seguridad, verán alertas y realizarán las acciones necesarias en las amenazas detectadas. El acceso al portal se concede a través de roles que implican ciertos permisos.

   En Defender para empresas, a los miembros del equipo de seguridad se les puede asignar uno de los tres roles siguientes:<br/>
   
   - **Administración global**: un administrador global puede ver y editar toda la configuración en el inquilino de Microsoft 365. El administrador global realiza la configuración inicial de la suscripción de Microsoft 365 de su empresa. 
   - **Administrador de** seguridad: un administrador de seguridad puede ver y editar la configuración de seguridad y tomar medidas cuando se detectan amenazas.
   - **Lector de** seguridad: un lector de seguridad puede ver información en los informes, pero no puede cambiar ninguna configuración de seguridad. 

   [Más información acerca de los roles y permisos](mdb-roles-permissions.md). 

2. **Configurar notificaciones por correo electrónico**. En este paso, puede configurar notificaciones por correo electrónico para el equipo de seguridad. A continuación, cuando se genera una alerta o se detecta una nueva vulnerabilidad, el equipo de seguridad no la perderá aunque esté fuera de su escritorio. [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). 

3. **Incorporar y configurar dispositivos Windows**. En este paso, puede incorporar rápidamente los dispositivos Windows de su empresa a Defender for Business. La incorporación de dispositivos de inmediato ayuda a proteger esos dispositivos desde el primer día. [Obtenga más información sobre la incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md).

   - **Si no usa Intune**, puede incorporar dispositivos en el portal de Microsoft 365 Defender. 
   - **Si ya usa Microsoft Intune** y su empresa tiene dispositivos inscritos en Intune, puede seguir usando Intune. Consulte [Administración de la seguridad del punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security).
   
4. **Configure las directivas de seguridad**. Defender para Empresas incluye directivas de seguridad predeterminadas para una protección de próxima generación y protección de firewall que se pueden aplicar a los dispositivos de la empresa. Estas directivas predeterminadas usan la configuración recomendada y están diseñadas para proporcionar una protección segura para los dispositivos. También puede crear sus propias directivas de seguridad. Consulte [Visualización y edición de las directivas de seguridad y la configuración](mdb-configure-security-settings.md).

   > [!NOTE]
   > Si ya usa Intune para administrar los dispositivos y las directivas de seguridad, puede seguir usando el Centro de administración de Microsoft Endpoint Manager. Consulte [Administración de la seguridad del punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="what-is-automatic-onboarding"></a>¿Qué es la incorporación automática?

La incorporación automática es una manera simplificada de incorporar dispositivos Windows a Defender para empresas. La incorporación automática solo está disponible para dispositivos Windows que ya están inscritos en Microsoft Intune. 

Mientras usa el asistente para la instalación, el sistema detectará si los dispositivos Windows ya están inscritos en Intune. Se le preguntará si quiere usar la incorporación automática para todos los dispositivos Windows o solo para algunos de ellos. Puede incorporar todos los dispositivos Windows a la vez o seleccionar dispositivos específicos con los que empezar y, a continuación, agregar más dispositivos más adelante. 

Para incorporar otros dispositivos, consulte [Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md).

> [!TIP]
> - Se recomienda seleccionar los "todos los dispositivos inscritos". Opción. De este modo, cuando los dispositivos Windows se inscriban en Intune posteriormente, se incorporarán automáticamente a Defender para empresas. 
> - Si ha estado administrando directivas y configuraciones de seguridad en el centro de administración de Endpoint Manager, se recomienda cambiar al portal de Microsoft 365 Defender para administrar los dispositivos, las directivas y la configuración. Para más información, consulte [Elegir dónde administrar directivas y dispositivos de seguridad](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices).

## <a name="what-happens-if-i-dont-use-the-wizard"></a>¿Qué ocurre si no uso el asistente?

El uso del asistente de configuración es opcional. Si decide no usar el asistente o si el asistente se cierra antes de que se complete el proceso de instalación, puede completar el proceso de instalación y configuración por su cuenta. 

Consulte [Configuración y configuración de Defender para empresas para](mdb-setup-configuration.md) seguir estos pasos:

1. **[Asigne roles y permisos](mdb-roles-permissions.md)** para que el equipo de seguridad pueda acceder y usar el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)).

2. **[Configure las notificaciones por correo electrónico para el equipo de seguridad para](mdb-email-notifications.md)** que estén en el bucle sobre nuevas alertas o vulnerabilidades.

3. **[Incorpore dispositivos](mdb-onboard-devices.md)** para que estén protegidos por Defender para empresas.

4. **[Administre las directivas de seguridad](mdb-configure-security-settings.md)**, que incluyen protección de última generación, protección contra firewalls y filtrado de contenido web.

## <a name="next-steps"></a>Pasos siguientes

- [Incorporación de más dispositivos a Defender for Business](mdb-onboard-devices.md)
- [Visualización y edición de las directivas de seguridad y la configuración en Defender para empresas](mdb-configure-security-settings.md)