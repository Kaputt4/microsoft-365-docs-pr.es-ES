---
title: Paso 4. Implementar la administración de puntos de conexión para sus dispositivos, PCs y otros puntos de conexión
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Use Microsoft Endpoint Manager para administrar sus dispositivos, equipos y otros puntos de conexión.
ms.openlocfilehash: d18a001021486c617aaf0fa04972e9464a5c2016
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63328629"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>Paso 4. Implementar la administración de puntos de conexión para sus dispositivos, PCs y otros puntos de conexión

Con los trabajadores remotos, es necesario admitir un número creciente de dispositivos personales. La administración de puntos de conexión es un planteamiento de seguridad basado en directivas que requiere que los dispositivos cumplan determinados criterios antes de que se les conceda acceso a los recursos. Microsoft Endpoint Manager ofrece funcionalidades de administración modernas para proteger los datos en la nube y en los entornos locales. 

[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) proporciona servicios y herramientas para administrar dispositivos móviles, equipos de escritorio, equipos virtuales, dispositivos incorporados y servidores mediante la combinación de los siguientes servicios, los cuales puede que ya conozca o esté usando.

:::image type="content" source="../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png" alt-text="Los componentes de la administración de puntos de conexión para Microsoft 365" lightbox="../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png":::

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft Intune es un servicio basado en la nube que se centra en la administración de dispositivos móviles (MDM) y en la administración de aplicaciones móviles (MAM) y está incluido con Microsoft 365. 

- **MDM:** Para los dispositivos que pertenecen a la organización, puede ejercer un control total que incluya la configuración, las características y la seguridad. Los dispositivos se "inscriben" en Intune, donde reciben las directivas de Intune con reglas y configuraciones. Por ejemplo, puede establecer requisitos para la contraseña y el PIN, crear una conexión VPN, configurar la protección contra amenazas y mucho más.

- **MAM:** es posible que los trabajadores remotos no quieran que usted tenga el control total de sus dispositivos personales, conocidos también como dispositivos Bring Your Own Device (BYOD). Puede dar opciones a sus trabajadores remotos y seguir protegiendo a su organización. Por ejemplo, los trabajadores remotos pueden inscribir sus dispositivos si quieren tener acceso completo a los recursos de su organización. O bien, si estos usuarios solo quieren tener acceso al correo electrónico o a Microsoft Teams, entonces use las directivas de protección de aplicaciones que requieren la autenticación multifactor (MFA) para usar estas aplicaciones.

Para obtener más información, consulte la solución de la fundación [Administrar dispositivos con Intune](manage-devices-with-intune-overview.md).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager es una solución de administración local que permite administrar equipos de escritorio, servidores y portátiles en la red o en Internet. Puede usar Configuration Manager para implementar aplicaciones, actualizaciones de software y sistemas operativos. También puede supervisar el cumplimiento, hacer consultas y realizar acciones en los clientes en tiempo real, y mucho más. Puede habilitarlo en la nube para integrarlo con Intune, Azure AD, Microsoft Defender para punto de conexión y otros servicios en la nube. 

Para obtener más información, vea esta [introducción a Configuration Manager](/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Administración conjunta

La coadministración combina la inversión local existente de Configuration Manager con la nube por medio de Intune y otros servicios en la nube de Microsoft 365. Puede usar tanto el administrador de configuración como Intune como autoridad de administración para las diferentes cargas de trabajo. 

La administración conjunta usa las características en la nube basadas en Intune, incluyendo el acceso condicional y la aplicación de la conformidad con los dispositivos. Puede mantener algunas de las tareas en el entorno local y ejecutar las demás en la nube.

Para obtener más información, vea esta [introducción a la administración conjunta](/mem/configmgr/comanage/overview).

## <a name="endpoint-analytics"></a>Análisis de puntos de conexión

Análisis de puntos de conexión pretende mejorar la productividad de los usuarios y disminuir los costos de soporte técnico de TI al proporcionar información sobre la experiencia del usuario. La información permite que TI optimice la experiencia del usuario final con un soporte técnico proactivo y detecte regresiones a la experiencia del usuario mediante la evaluación del impacto de los cambios de configuración en el usuario.

Para más información, consulte esta [Información general sobre Análisis de puntos de conexión](/mem/analytics/overview)

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot es una plataforma autoservicio de implementación de Windows que no requiere intervención. Incluye una colección de tecnologías para configurar y preconfigurar nuevos dispositivos, así como para prepararlos para un uso productivo. También se puede usar Windows Autopilot para restablecer, reasignar y recuperar dispositivos. 

Windows Autopilot le permite a un departamento de TI preconfigurar los dispositivos con poca o ninguna infraestructura que administrar y con un proceso fácil y sencillo. 

- Desde el punto de vista del usuario, solo se requieren algunas operaciones sencillas para que el dispositivo esté listo para su uso. 
- Desde el punto de vista de los profesionales de TI, la única interacción necesaria por parte del usuario final es conectarse a una red y comprobar sus credenciales.

Para obtener más información, vea esta [introducción a Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Recursos técnicos administrativos para la administración de puntos de conexión

- [Guía básica de administración de dispositivos para Microsoft 365](../enterprise/device-management-roadmap-microsoft-365.md)
- [Cómo inscribir diferentes tipos de dispositivos para la administración de dispositivos móviles](/mem/intune/enrollment/device-enrollment)
- [Cómo instruir a los usuarios finales sobre Microsoft Intune](/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a>Resultados del paso 4

Ya está usando el conjunto de características y funcionalidades de Endpoint Manager para administrar dispositivos móviles, equipos de escritorio, máquinas virtuales, dispositivos incorporados y servidores.

## <a name="next-step"></a>Paso siguiente

[![Paso 5: Implementar servicios y aplicaciones de productividad para los trabajadores remotos](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md).

Continúe con el [paso 5](empower-people-to-work-remotely-teams-productivity-apps.md)para que sus trabajadores remotos utilicen las aplicaciones de productividad de Microsoft 365, como Microsoft Teams.