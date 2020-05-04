---
title: 3. Implementar la administración de puntos de conexión para dispositivos, equipos y otros puntos de conexión
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Use Microsoft Endpoint Manager para administrar sus dispositivos, equipos y otros puntos de conexión.
ms.openlocfilehash: 76e18d65865f4ec2bbc8a8d1554bb4cad6fee553
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011608"
---
# <a name="3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a>3. Implementar la administración de puntos de conexión para dispositivos, equipos y otros puntos de conexión

Con los trabajadores remotos, hay que dar soporte a un número cada vez mayor de dispositivos personales. La administración de puntos de conexión es un planteamiento de seguridad basado en directivas que requiere que los dispositivos cumplan determinados criterios antes de que se les conceda acceso a los recursos. Microsoft Endpoint Manager ofrece un espacio de trabajo moderno y funcionalidades de administración modernas para proteger los datos en la nube y en los entornos locales. 

Endpoint Manager proporciona servicios y herramientas para administrar dispositivos móviles, equipos de escritorio, equipos virtuales, dispositivos incorporados y servidores mediante la combinación de los siguientes servicios, los cuales puede que ya conozca o esté usando.

## <a name="microsoft-intune"></a>Microsoft Intune

Intune está diseñado para facilitar la protección de los datos cuando no se tiene control administrativo sobre los dispositivos que se usan para acceder a los datos de la organización. Las directivas de protección de aplicaciones de Intune, junto con el acceso condicional de Azure AD, proporcionan un control detallado sobre los datos en dispositivos móviles. Intune también permite definir directivas exhaustivas que limiten el acceso a los datos de la empresa, de modo que solo puedan acceder a ellos los usuarios adecuados y en las condiciones adecuadas, y que garanticen la protección de los datos mediante el control de su uso en Office, Outlook y otras aplicaciones móviles.

Para obtener más información, vea esta [introducción a Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).

## <a name="configuration-manager"></a>Configuration Manager

Configuration Manager es una solución de administración local que permite administrar equipos de escritorio, servidores y portátiles en la red o en Internet. Puede habilitarlo en la nube para integrarlo con Intune, Azure AD, Protección contra amenazas avanzada de Microsoft Defender y otros servicios en la nube. Puede usar Configuration Manager para implementar aplicaciones, actualizaciones de software y sistemas operativos. También puede supervisar el cumplimiento, hacer consultas y realizar acciones en los clientes en tiempo real, y mucho más.

Para obtener más información, vea esta [introducción a Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).

## <a name="co-management"></a>Administración conjunta

La coadministración combina la inversión local existente de Configuration Manager con la nube por medio de Intune y otros servicios en la nube de Microsoft 365. Puede usar tanto Configuration Manager como Intune como autoridad de administración para los siete grupos de cargas de trabajo diferentes.

Como parte de Endpoint Manager, la coadministración usa las características de la nube, incluido el acceso condicional. Puede mantener algunas de las tareas en el entorno local y ejecutar las demás en la nube con Intune.

Para obtener más información, vea esta [introducción a la administración conjunta](https://docs.microsoft.com/mem/configmgr/comanage/overview).

## <a name="desktop-analytics"></a>Análisis de escritorio

Análisis de escritorio es un servicio basado en la nube que se integra con Configuration Manager y proporciona información e inteligencia que permiten fundamentar la toma de decisiones con respecto a los clientes de Windows. Combina datos de la organización con datos agregados de millones de dispositivos conectados a los servicios en la nube de Microsoft. Con Análisis de escritorio, puede crear un inventario de las aplicaciones que se ejecutan en la organización, evaluar la compatibilidad de las aplicaciones con las últimas actualizaciones de características de Windows 10, determinar problemas de compatibilidad y recibir sugerencias de mitigación en función de la información sobre los datos habilitada en la nube, crear grupos piloto que representen la totalidad de la aplicación y el estado de los controladores en un conjunto mínimo de dispositivos, e implementar Windows 10 en dispositivos piloto y administrados para la producción.

Para obtener más información, vea esta [introducción a Análisis de escritorio](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview).

## <a name="windows-autopilot"></a>Windows Autopilot

Windows Autopilot es una plataforma autoservicio de implementación de Windows que no requiere intervención. Incluye una colección de tecnologías para configurar y preconfigurar nuevos dispositivos, así como para prepararlos para un uso productivo. También se puede usar Windows Autopilot para restablecer, reasignar y recuperar dispositivos. Esta solución permite a un departamento de TI lograr lo anterior con poca o ninguna infraestructura que administrar, con un proceso fácil y sencillo. Desde el punto de vista del usuario, solo se requieren algunas operaciones sencillas para que el dispositivo esté listo para su uso. Desde el punto de vista de los profesionales de TI, la única interacción necesaria por parte del usuario final es conectarse a una red y comprobar sus credenciales.

Para obtener más información, vea esta [introducción a Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).

## <a name="admin-technical-resources-for-endpoint-management"></a>Recursos técnicos administrativos para la administración de puntos de conexión

- [Inscribir dispositivos administrados por razones de seguridad, aprovechar la configuración de aplicaciones para los dispositivos no administrados y usar directivas de dispositivos y aplicaciones](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [Cómo inscribir diferentes tipos de dispositivos para la administración de dispositivos móviles (MDM)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [Cómo instruir a los usuarios finales sobre Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a>Resultados del paso 3

Ya está usando el conjunto de características y funcionalidades de Endpoint Manager para administrar dispositivos móviles, equipos de escritorio, máquinas virtuales, dispositivos incorporados y servidores.

## <a name="next-step"></a>Paso siguiente

Continúe con el [paso 4](empower-people-to-work-remotely-teams-productivity-apps.md) para proporcionar acceso remoto a aplicaciones y servicios locales.
