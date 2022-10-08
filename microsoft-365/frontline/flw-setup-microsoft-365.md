---
title: Microsoft 365 para trabajadores de primera línea
author: samanro
ms.author: samanro
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo configurar Microsoft 365 con los servicios y características que necesita para los trabajadores de primera línea.
ms.localizationpriority: high
ms.collection:
- m365-frontline
- highpri
- m365solution-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: fe5610387744c9a9a0dcfa9c87e82741b0847a8d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68057335"
---
# <a name="set-up-microsoft-365-for-frontline-workers"></a>Microsoft 365 para trabajadores de primera línea

Para configurar Microsoft 365 para trabajadores de primera línea, siga este proceso general:

1. **[Identificar los escenarios](#step-1-identify-your-scenarios)**: ¿Qué escenarios desea implementar para los trabajadores de primera línea? Después de determinar qué escenarios desea, use la tabla siguiente para identificar las aplicaciones y los servicios necesarios para cada escenario que quiera implementar.
1. **[Configuración del entorno y núcleo de Microsoft 365](#step-2-set-up-your-environment-and-core-microsoft-365)**: siga las guías de configuración del Centro de administración de Microsoft 365 para configurar Microsoft 365. Siga leyendo para obtener información sobre cómo acceder a estas guías.
1. **[Configurar Microsoft Teams](#step-3-set-up-microsoft-teams)**: use el asistente para la incorporación o el proceso de implementación de equipos a escala para configurar el servicio y crear los equipos.
1. **[Configurar cualquier otro servicio necesario para su escenario](#step-4-set-up-other-services)**: siga las instrucciones de las secciones siguientes para configurar estos servicios.
1. **[Configurar aplicaciones](#step-5-configure-apps-for-your-scenario)**: una vez configurado y configurado todo en el centro de administración, puede seguir las instrucciones de los escenarios para configurar aún más las aplicaciones que necesita para cada escenario.
1. **[Dispositivos](#step-6-set-up-devices)**: configure dispositivos compartidos y personales para que funcionen con Microsoft 365 y Microsoft Teams y para permitir que los trabajadores de primera línea se comuniquen de forma más segura dentro de su organización.

:::image type="content" source="media/m365-frontline-setup-steps.png" alt-text="Pasos para configurar Microsoft 365 para trabajadores de primera línea." lightbox="media/m365-frontline-setup-steps.png":::

## <a name="step-1-identify-your-scenarios"></a>Paso 1: identifique los escenarios

En la tabla siguiente se enumeran los escenarios de los trabajadores de primera línea. Puede leer un resumen de cada escenario en [elegir los escenarios](flw-choose-scenarios.md) y averiguar exactamente lo que necesita configurar siguiendo los vínculos a cada escenario y a cada aplicación o servicio que sea necesario.

| Escenario | Servicios requeridos |
|  ------- | -------  |
| [Comunicación y colaboración en equipo](flw-team-collaboration.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Email con Exchange Online](#set-up-email-with-exchange-online) |
| [Comunicaciones corporativas](flw-corp-comms.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Conexiones Viva](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [Citas virtuales](virtual-appointments.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [Interactúe con sus empleados y céntrese en su bienestar](flw-wellbeing-engagement.md)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Conexiones Viva](#set-up-viva-connections) <br>[Yammer](#set-up-your-organizations-social-network-with-yammer) |
| [Programe el equipo con Turnos](shifts-for-teams-landing-page.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) |
| [Incorporación de nuevos empleados a la organización](/sharepoint/onboard-employees)| [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[SharePoint](#set-up-sites-with-sharepoint-in-microsoft-365) <br>[Conexiones Viva](#set-up-viva-connections) <br>[Viva Learning](#set-up-viva-learning)|
| [Aprendizaje continuo](flw-onboarding-training.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Viva Learning](#set-up-viva-learning) |
| [Simplificar procesos empresariales](simplify-business-processes.md) | [Microsoft Teams](#step-3-set-up-microsoft-teams) <br>[Power Apps, Power Automate y Power BI](#set-up-power-apps-power-automate-and-power-bi) |

Algunos servicios solo se incluyen con licencias F3, como el correo electrónico y Power Platform. Consulte [Descripción de los tipos de usuario de trabajo de primera línea y las licencias](flw-licensing-options.md) para determinar el tipo de licencias que necesitará para los usuarios.

## <a name="step-2-set-up-your-environment-and-core-microsoft-365"></a>Paso 2: Configurar el entorno y el núcleo de Microsoft 365

El Centro de administración de Microsoft 365 tiene un conjunto de [guías de instalación](/microsoft-365/enterprise/setup-guides-for-microsoft-365) que le guiarán por los pasos para configurar los productos, las características de seguridad y las herramientas de colaboración en Microsoft 365. Las guías de configuración son accesibles desde la [página Guía de instalación](https://aka.ms/setupguidance) de la Centro de administración de Microsoft 365.

1. Use la guía [Preparar el entorno](https://aka.ms/prepareyourenvironment) para preparar el entorno de su organización para Microsoft 365 y Office 365 servicios.
1. Use la guía [Configuración de Microsoft 365](https://aka.ms/microsoft365setupguide) para configurar herramientas de productividad, directivas de seguridad y funcionalidades de administración de dispositivos. También puede usar este asesor para configurar y configurar los dispositivos de su organización.

## <a name="step-3-set-up-microsoft-teams"></a>Paso 3: Configurar Microsoft Teams para educación

Para un proyecto piloto, puede usar el Asistente para la incorporación de trabajadores de primera línea para configurar un único equipo, configurado para los trabajadores de primera línea. Para obtener instrucciones paso a paso, consulte [Uso del Asistente para la incorporación de trabajadores de primera línea para poner en funcionamiento el personal de primera línea](flw-onboarding-wizard.md).

Para implementaciones completas, siga las instrucciones de [Implementación de Teams a escala para trabajadores de primera línea](deploy-teams-at-scale.md).

## <a name="step-4-set-up-other-services"></a>Paso 4: Configurar otros servicios

### <a name="set-up-email-with-exchange-online"></a>Configure el correo electrónico con Exchange Online

Si quiere que los administradores y los trabajadores de primera línea tengan acceso al correo electrónico, debe configurar el correo electrónico en Microsoft 365. Los usuarios deben tener una licencia F3 para obtener acceso al correo electrónico. Siga la [guía de configuración del correo electrónico](https://aka.ms/office365setup) para configurarla.

Tenga en cuenta que los usuarios también pueden instalar la aplicación de Outlook para su correo electrónico, por lo que querrá asegurarse de compartir dónde descargar la aplicación de Outlook con ellos.

### <a name="set-up-sites-with-sharepoint-in-microsoft-365"></a>Configuración de sitios con SharePoint en Microsoft 365

[SharePoint](/sharepoint/sharepoint-online) le permite compartir documentos y crear sitios. Use la [guía de instalación de SharePoint](https://aka.ms/spoguidance) en el Centro de administración de Microsoft 365 para configurarla.

### <a name="set-up-employee-experiences-with-viva-modules"></a>Configuración de experiencias de empleados con módulos Viva

[Microsoft Viva](/viva/microsoft-viva-overview) ayuda a conectar a los empleados con una experiencia integrada de empleados que aúne comunicaciones, conocimientos, aprendizaje, recursos e información sobre el flujo de trabajo. Microsoft Viva tiene varios módulos que se pueden usar con Microsoft Teams para crear experiencias de empleados.

#### <a name="set-up-viva-connections"></a>Configurar Conexiones Viva

Use [Conexiones Viva](/viva/connections/viva-connections-overview) para crear un panel que ayude a interactuar e informar a los trabajadores de primera línea. Conexiones Viva es una aplicación personalizable de Microsoft Teams que ofrece a todos los usuarios un destino personalizado para descubrir noticias, conversaciones y las herramientas pertinentes que necesitan para tener éxito. 

Siga la [guía de configuración de construcción de la experiencia del empleado](https://aka.ms/EmployeeExperienceDashboard) para configurarla. Más información sobre [la configuración de Conexiones Viva](/viva/connections/guide-to-setting-up-viva-connections)

#### <a name="set-up-viva-learning"></a>Configurar Aprendizaje Viva

[Aprendizaje Viva](/viva/learning/) es una aplicación de Microsoft Teams que permite incorporar el aprendizaje como parte natural del día a día de los empleados, al incorporar el aprendizaje al flujo de trabajo dentro de las herramientas y plataformas que ya usan. Consulte [Configuración de Aprendizaje Microsoft Viva en el Centro de administración de Teams](/viva/learning/set-up-viva-learning) para obtener información sobre cómo configurar Aprendizaje Viva.

### <a name="set-up-your-organizations-social-network-with-yammer"></a>Configuración de la red social de la organización con Yammer

[Yammer](/yammer) ayuda a conectar a sus empleados en toda la empresa. Use el [asesor de implementación de Yammer](https://aka.ms/yammerdeploymentguide) para configurarlo.

### <a name="set-up-power-apps-power-automate-and-power-bi"></a>Configuración de Power Apps, Power Automate y Power BI

Puede usar todas estas aplicaciones en Microsoft Teams. Para obtener más información sobre la administración conjunta y cómo configurarla, consulte:

- [Power Apps e Integración de Power Apps y Microsoft Teams](/powerapps/teams/overview).
- [Power Automate: uso de flujos en Microsoft Teams](/power-automate/teams/overview)
- [Colaborar en Microsoft Teams con Power BI](/power-bi/collaborate-share/service-collaborate-microsoft-teams).
- ‎[Aplicación Power Virtual Agents en Microsoft Teams.](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)
- [Power Apps](/microsoftteams/manage-power-platform-apps)

## <a name="step-5-configure-apps-for-your-scenario"></a>Paso 5: Configuración de aplicaciones para su escenario

Una vez configurado y configurado todo en el centro de administración, puede seguir las instrucciones de los escenarios para configurar aún más las aplicaciones que necesita para cada escenario.

Escenarios y aplicaciones

| Escenario | Aprobaciones | Bookings | Listas | Elogios | Turnos | Tareas | Actualizaciones |
| :---- | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [Comunicación y colaboración en equipo](flw-team-collaboration.md) | &#x2705; | &nbsp; | &#x2705; | &#x2705; | &nbsp; | &#x2705; | &#x2705; |
| [Comunicaciones corporativas](flw-corp-comms.md) |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |  &nbsp; |
| [Citas virtuales con Microsoft Teams y la aplicación Bookings](bookings-virtual-visits.md) |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp;|  &nbsp; |
| Bienestar y compromiso |  &nbsp; |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; |
| [Programe el equipo con Turnos](shifts-for-teams-landing-page.md) |  &nbsp; | &nbsp; | &#x2705; |  &nbsp; | &#x2705; | &#x2705; | &#x2705; |
| [Formación: Incorporación de nuevos empleados](/sharepoint/onboard-employees) |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| Formación continua |  &nbsp; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| [Simplificar procesos empresariales](simplify-business-processes.md) | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; |  &nbsp; | &#x2705; | &#x2705; |
| Administración de sitios, tiendas y proyectos | &#x2705; |  &nbsp; | &#x2705; |  &nbsp; | &nbsp; | &#x2705; | &#x2705; |

## <a name="step-6-set-up-devices"></a>Paso 6: Configuración de dispositivos

Para configurar dispositivos compartidos y personales para que funcionen con Microsoft 365 y Microsoft Teams y para permitir que los trabajadores de primera línea se comuniquen de forma más segura dentro de su organización, consulte [Administración de dispositivos móviles para trabajadores de primera línea](flw-devices.md).
