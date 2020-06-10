---
title: Proporcionar Microsoft 365 a los trabajadores remotos
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Configure una infraestructura de servicios y seguridad que permita a los trabajadores trabajar de forma remota desde cualquier lugar y en cualquier momento.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560467"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Proporcionar Microsoft 365 a los trabajadores remotos

Es posible que su empresa necesite habilitar el acceso seguro a los recursos, herramientas e información locales y basados en la nube de la organización para que los empleados puedan trabajar desde sus casas. Permitir que los trabajadores trabajen fuera de la oficina de manera fluida y segura es importante en muchas organizaciones para:

- Ahorrar en espacio de oficina.
- Contratar y conservar trabajadores que no estén dispuestos a reubicarse.
- Reducir los desplazamientos de los trabajadores, dejándoles más tiempo para ser productivos y para actividades que reducen el estrés fuera del trabajo.

El trabajo remoto, también conocido como teletrabajo, abarca un gran espectro. Estos son algunos ejemplos:

- trabajadores que en ocasiones salen de la oficina para ir a conferencias o reuniones con los clientes.
- Algunos trabajadores que trabajan de forma remota a tiempo completo.
- Una empresa completamente remota en la que no hay ninguna oficina y todos los trabajadores trabajan a distancia.

Desde cualquier parte del mundo y en cualquier momento, los trabajadores remotos deben poder tener acceso a:

- Los recursos de la organización, como los ofrecidos por centros de datos de aplicaciones locales.
- Los servicios basados en la nube y los datos de suscripción de Microsoft 365, como Teams, Exchange Online, SharePoint y OneDrive.

Para obtener una experiencia de inicio de sesión perfecta, las cuentas de usuario de Active Directory Domain Services (AD DS) se deben sincronizar con Azure Active Directory (Azure AD). Para proteger sus dispositivos con Windows 10, deben estar inscritos en Intune. Aquí se muestra una vista general de la infraestructura.

![La infraestructura básica para trabajadores remotos con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


Para apoyar a los trabajadores remotos, por ejemplo, en respuesta a la crisis de la COVID-19, una combinación de características en Microsoft 365 habilita a sus trabajadores remotos en un modo altamente colaborativo, como:

- Reuniones en línea y sesiones de chat.
- Áreas de trabajo compartidas para almacenar archivos en la nube con accesibilidad global y colaboración en tiempo real.
- Tareas y flujos de trabajo compartidos para dividir el trabajo y terminarlo de forma más efectiva.

Para un alto nivel de seguridad, Microsoft 365 incluye:

- Requisitos de autenticación obligatorios, detección y respuesta a los inicios de sesión de alto riesgo, y bloqueo de aplicaciones específicas y dispositivos no compatibles.
- Conexiones cifradas y recursos digitales en la nube.
- Permisos para definir qué acciones se permiten a qué usuarios con ciertos archivos.
- Características de seguridad integrales para proteger dispositivos con Windows 10.

Las siguientes características y opciones de Microsoft 365 le permiten aplicar estos criterios a sus trabajadores remotos:

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| MFA aplicada en los valores predeterminados de seguridad   | Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.   | Microsoft 365 E3 y E5 |
| MFA aplicada con acceso condicional| Requerir la MFA según las propiedades del inicio de sesión con directivas de Acceso condicional.    | Microsoft 365 E3 y E5 | 
| MFA aplicada con Acceso condicional basado en los riesgos   | Requerir la MFA según el riesgo de inicio de sesión del usuario con Azure Advanced Threat Protection. | Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2 | 
| Autoservicio de restablecimiento de contraseña (SSPR)    | Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.  | Microsoft 365 E3 y E5 |
| Proxy de aplicación de Azure AD    | Da acceso remoto seguro para aplicaciones basadas en web que se encuentren en servidores de intranet.   | Se requiere una suscripción de pago de Azure aparte. |
| VPN de Azure de punto a sitio   | Crea una conexión segura desde el dispositivo de un trabajador remoto a la intranet a través de una red virtual de Azure.   | Se requiere una suscripción de pago de Azure aparte. |
| Windows Virtual Desktop   | Apoya a los trabajadores remotos que solo pueden usar sus propios dispositivos personales no administrados ofreciéndoles escritorios virtuales que se ejecutan en Azure. | Se requiere una suscripción de pago de Azure aparte. |
| Servicios de Escritorio remoto (RDS) | Permite que los empleados se conecten a equipos con Windows en la intranet. | Microsoft 365 E3 y E5 | 
| Puerta de enlace de Servicios de Escritorio remoto   | Cifra las comunicaciones y evita que los hosts de RDS se expongan directamente a Internet. | Requiere licencias aparte de Windows Server. |
| Microsoft Intune | Administra dispositivos y aplicaciones.   | Microsoft 365 E3 y E5 | 
| Configuration Manager | Administra instalaciones, actualizaciones y configuraciones de software en sus dispositivos. | Se requieren licencias aparte de Configuration Manager. |
| Análisis de escritorio | Determina la preparación de la actualización de los clientes de Windows.   | Se requieren licencias aparte de Configuration Manager. |
| Windows Autopilot | Instala y preconfigura nuevos dispositivos con Windows 10 para un uso productivo.   | Microsoft 365 E3 y E5 |
| Microsoft Teams, Exchange Online, SharePoint Online y OneDrive, Aplicaciones de Microsoft 365, Microsoft Power Platform, Yammer y Power Apps. | Crear, comunicar y colaborar. | Microsoft 365 E3 y E5 |
||||

Siga los pasos que se indican a continuación para proteger y optimizar el acceso a los servidores, datos y servicios en la nube de la organización y optimizar la productividad de sus empleados.

1. [Aumentar la seguridad de inicio de sesión con la autenticación multifactor](empower-people-to-work-remotely-secure-sign-in.md)
2. [Proporcionar acceso remoto a los servicios y aplicaciones locales](empower-people-to-work-remotely-remote-access.md)
3. [Implementar la administración de puntos de conexión para dispositivos, equipos y otros puntos de conexión](empower-people-to-work-remotely-manage-endpoints.md)
4. [Implementar servicios y aplicaciones de productividad para los trabajadores remotos](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [Crear espacios de comunicación](empower-people-to-work-remotely-communication-venues.md)
6. [Proporcionar formación a los trabajadores remotos y dar respuesta a los comentarios sobre el uso](empower-people-to-work-remotely-train-monitor-usage.md)

![Los pasos para proporcionar Microsoft 365 a los trabajadores remotos](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Para obtener la información más reciente de Microsoft sobre el soporte para trabajadores remotos, consulte el [sitio Habilitar trabajo remoto de Tech Community](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
