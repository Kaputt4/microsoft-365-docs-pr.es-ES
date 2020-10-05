---
title: Proporcionar Microsoft 365 a los trabajadores remotos
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/02/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
ms.custom: ''
description: Configure una infraestructura de servicios y seguridad que permita a los trabajadores trabajar de forma remota desde cualquier lugar y en cualquier momento.
ms.openlocfilehash: f5364103610fbac8efe47b9ae7e776d215fc0733
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327740"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Proporcionar Microsoft 365 a los trabajadores remotos

Es posible que su empresa necesite habilitar el acceso seguro a los recursos, herramientas e información locales y basados en la nube de la organización para que los empleados puedan trabajar desde sus casas. Permitir que los empleados trabajen de manera remota es importante en muchas organizaciones para lo siguiente:

- Ahorrar en espacio de oficina.
- Contratar y conservar trabajadores que no estén dispuestos a reubicarse.
- Reducir los desplazamientos de los trabajadores, dejándoles más tiempo para ser productivos y para actividades que reducen el estrés fuera del trabajo.

Microsoft 365 tiene las capacidades para permitir que los empleados trabajen de manera remota.

![Proporcionar las capacidades necesarias a sus trabajadores remotos con Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

Vea este vídeo para obtener información general del proceso.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Esta solución proporciona estas funciones clave.

- Conectados

  Desde cualquier parte del mundo y en cualquier momento, los trabajadores remotos pueden acceder a: 

  - Los servicios basados en la nube y los datos de su suscripción de Microsoft 365. 
  - Los recursos de la organización, como los ofrecidos por centros de datos de aplicaciones locales.

- Protegidos

  Los inicios de sesión están protegidos con la autenticación multifactor (MFA). Las características de seguridad integradas de Microsoft 365 y Windows 10 protegen contra el malware, los ataques malintencionados y la pérdida de datos.

- Administrados

  Los dispositivos de su trabajador remoto se pueden administrar desde la nube mediante configuraciones de seguridad, aplicaciones permitidas y requerimientos de cumplimiento con el estado del sistema.

- Colaborativos y productivos

  Sus trabajadores remotos pueden ser tan productivos como lo son en la oficina de un modo altamente colaborativo gracias a las siguientes características:
  - Reuniones en línea y sesiones de chat con Teams. 
  - Áreas de trabajo compartidas para almacenar archivos en la nube con accesibilidad global y colaboración en tiempo real con SharePoint y OneDrive.
  - Tareas y flujos de trabajo compartidos para dividir el trabajo y terminarlo de forma más efectiva. 

Para una experiencia de inicio de sesión perfecta, las cuentas de usuario de Active Directory Domain Services (AD DS) locales se deben sincronizar con Azure Active Directory (Azure AD). Para proteger sus dispositivos con Windows 10, deben estar inscritos en Intune. Aquí se muestra una vista general de la infraestructura.

![La infraestructura básica para trabajadores remotos con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Las siguientes características y opciones de Microsoft 365 le permiten cumplir con estos criterios para sus trabajadores remotos:

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| MFA aplicada en los valores predeterminados de seguridad   | Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.   | Microsoft 365 E3 o E5 |
| MFA aplicada con acceso condicional| Requerir la MFA según las propiedades del inicio de sesión con directivas de Acceso condicional.    | Microsoft 365 E3 o E5 | 
| MFA aplicada con Acceso condicional basado en los riesgos   | Requerir la MFA según el riesgo de inicio de sesión del usuario con Azure Advanced Threat Protection. | Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2 | 
| Autoservicio de restablecimiento de contraseña (SSPR)    | Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.  | Microsoft 365 E3 o E5 |
| Proxy de aplicación de Azure AD    | Da acceso remoto seguro para aplicaciones basadas en web que se encuentren en servidores de intranet.   | Se requiere una suscripción de pago de Azure aparte. |
| VPN de Azure de punto a sitio   | Crea una conexión segura desde el dispositivo de un trabajador remoto a la intranet a través de una red virtual de Azure.   | Se requiere una suscripción de pago de Azure aparte. |
| Windows Virtual Desktop   | Apoya a los trabajadores remotos que solo pueden usar sus propios dispositivos personales no administrados ofreciéndoles escritorios virtuales que se ejecutan en Azure. | Se requiere una suscripción de pago de Azure aparte. |
| Servicios de Escritorio remoto (RDS) | Permite que los empleados se conecten a equipos con Windows en la intranet. | Microsoft 365 E3 o E5 | 
| Puerta de enlace de Servicios de Escritorio remoto   | Cifra las comunicaciones y evita que los hosts de RDS se expongan directamente a Internet. | Requiere licencias aparte de Windows Server. |
| Microsoft Intune | Administra dispositivos y aplicaciones.   | Microsoft 365 E3 o E5 | 
| Configuration Manager | Administra instalaciones, actualizaciones y configuraciones de software en sus dispositivos. | Se requieren licencias aparte de Configuration Manager. |
| Análisis de escritorio | Determina la preparación de la actualización de los clientes de Windows.   | Se requieren licencias aparte de Configuration Manager. |
| Windows Autopilot | Instala y preconfigura nuevos dispositivos con Windows 10 para un uso productivo.   | Microsoft 365 E3 o E5 |
| Microsoft Teams, Exchange Online, SharePoint Online y OneDrive, Aplicaciones de Microsoft 365, Microsoft Power Platform, Yammer y Power Apps. | Crear, comunicar y colaborar. | Microsoft 365 E3 o E5 |
||||

Para ver los criterios de seguridad y cumplimiento consulte [Implementar la seguridad y el cumplimiento para trabajadores remotos](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Para obtener un resumen de dos páginas sobre esta solución, consulte el [Póster para aumentar la productividad de los trabajadores remotos](../downloads/empower-remote-workers.pdf).

[![Póster para aumentar la productividad de los trabajadores remotos](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

También puede descargar este póster en [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) e imprimirlo en tamaño de carta, legal o tabloide (11 x 17).

Siga los pasos que se indican a continuación para proteger y optimizar el acceso a los servidores, datos y servicios en la nube de la organización y optimizar la productividad de sus empleados.

1. [Aumentar la seguridad de inicio de sesión con la autenticación multifactor](empower-people-to-work-remotely-secure-sign-in.md)
2. [Proporcionar acceso remoto a los servicios y aplicaciones locales](empower-people-to-work-remotely-remote-access.md)
3. [Implementar servicios de seguridad y cumplimiento](empower-people-to-work-remotely-security-compliance.md)
4. [Implementar la administración de puntos de conexión para dispositivos, equipos y otros puntos de conexión](empower-people-to-work-remotely-manage-endpoints.md)
5. [Implementar servicios y aplicaciones de productividad para los trabajadores remotos](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Proporcionar formación a los trabajadores remotos y dar respuesta a los comentarios sobre el uso](empower-people-to-work-remotely-train-monitor-usage.md)

![Los pasos para proporcionar Microsoft 365 a los trabajadores remotos](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Para obtener la información más reciente de Microsoft sobre el soporte para trabajadores remotos, consulte el [sitio Habilitar trabajo remoto de Tech Community](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
