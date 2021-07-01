---
title: Configure su infraestructura para el trabajo híbrido con Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
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
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: trabajar desde casa, trabajo desde casa, híbrido, trabajador remoto, trabajo híbrido, empleados remotos, conectividad híbrida, acceso remoto, trabajo remoto, teletrabajo, teletrabajar, trabajo móvil, trabajo remoto, empleo remoto, trabajar desde cualquier lugar, lugar de trabajo flexible
description: Desplazarse por las capas de la infraestructura para que los trabajadores híbridos puedan acceder de forma segura a los recursos locales y de Microsoft 365..
ms.openlocfilehash: fed23a4607cfb47049a6540dfb592d9a8baf9d21
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229376"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a>Configure su infraestructura para el trabajo híbrido con Microsoft 365

Para asegurar y optimizar la productividad y la colaboración de sus trabajadores, debe permitir que los trabajadores in situ y remotos accedan de forma fácil y segura a la información, las herramientas y los recursos de su organización, tanto en las instalaciones como en la nube. Esta solución le guían por la implementación de capas clave de infraestructura que permiten a los trabajadores realizar el mejor trabajo posible, dondequiera que estén.

Los trabajadores híbridos pueden trabajar in situ o a distancia en una combinación de lugares. Permitir a los empleados trabajar fuera de una oficina tradicional es importante para muchas organizaciones:

- Contratar y retener a los trabajadores que no están dispuestos a trasladarse o que requieren un entorno de trabajo flexible.
- Reducir los desplazamientos de los trabajadores, dejándoles más tiempo para ser productivos y para actividades que reduzcan el estrés fuera del trabajo.
- Ahorrar en espacio de oficina.

Microsoft 365 cuenta con las capacidades necesarias para que sus trabajadores híbridos puedan trabajar in situ o de forma remota

![Proporcione las herramientas necesarias a sus trabajadores híbridos con Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> Si es nuevo en Microsoft 365, consulte [estos recursos](https://www.microsoft.com/microsoft-365).

Vea este vídeo para obtener información general del proceso de implementación.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Para los profesionales de TI que administran la infraestructura in situ y en la nube para permitir la productividad de los trabajadores híbridos, esta solución proporciona estas capacidades clave:

- Conectados

  Desde cualquier lugar del mundo y en cualquier momento, sus trabajadores pueden acceder:

  - Los servicios basados en la nube y los datos de su suscripción de Microsoft 365.

  - Los recursos de la organización, como los ofrecidos por centros de datos de aplicaciones locales.

- Protegidos

  Los inicios de sesión están protegidos con la autenticación multifactor (MFA). Las características de seguridad integradas de Microsoft 365 y Windows 10 protegen contra el malware, los ataques malintencionados y la pérdida de datos.

- Administrados

  Los dispositivos de sus trabajadores híbridos pueden administrarse desde la nube con ajustes de seguridad, aplicaciones permitidas y para exigir el cumplimiento del estado del sistema.

- Colaborativos y productivos

  Sus trabajadores híbridos pueden ser tan productivos como los locales de una manera altamente colaborativa con:

  - Reuniones en línea y sesiones de chat con Teams.

  - Áreas de trabajo compartidas para almacenar archivos en la nube con accesibilidad global y colaboración en tiempo real con SharePoint y OneDrive.

  - Tareas y flujos de trabajo compartidos para dividir el trabajo y terminarlo de forma más efectiva.

Para una experiencia de inicio de sesión perfecta, las cuentas de usuario de Active Directory Domain Services (AD DS) locales se deben sincronizar con Azure Active Directory (Azure AD). Para proteger sus dispositivos con Windows 10, deben estar inscritos en Intune. Aquí se muestra una vista general de la infraestructura.

![La infraestructura básica para los trabajadores híbridos con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Para habilitar las funcionalidades de Microsoft 365 para sus trabajadores híbridos, utilice estas características de Microsoft 365.

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| MFA aplicada en los valores predeterminados de seguridad   | Protege frente a ataques a identidades y dispositivos, pues obliga a usar una segunda forma de autenticación para iniciar sesión. Los valores predeterminados de seguridad requieren MFA para todas las cuentas de usuario.   | Microsoft 365 E3 o E5 |
| MFA aplicada con acceso condicional| Requerir la MFA según las propiedades del inicio de sesión con directivas de Acceso condicional.    | Microsoft 365 E3 o E5 |
| MFA aplicada con Acceso condicional basado en los riesgos   | Requerir la MFA según el riesgo de inicio de sesión del usuario con Microsoft Defender for Identity. | Microsoft 365 E5 o E3 con las licencias de Azure AD Premium P2 |
| Autoservicio de restablecimiento de contraseña (SSPR)    | Permitir que los usuarios restablezcan o desbloqueen su contraseña o cuenta ellos mismos.  | Microsoft 365 E3 o E5 |
| Proxy de aplicación de Azure AD    | Da acceso remoto seguro para aplicaciones basadas en web que se encuentren en servidores de intranet.   | Se requiere una suscripción de pago de Azure aparte. |
| VPN de Azure de punto a sitio   | Crea una conexión segura desde el dispositivo de un trabajador remoto a la intranet a través de una red virtual de Azure.   | Se requiere una suscripción de pago de Azure aparte. |
| Windows Virtual Desktop   | Apoya a los trabajadores remotos que solo pueden usar sus propios dispositivos personales no administrados ofreciéndoles escritorios virtuales que se ejecutan en Azure. | Se requiere una suscripción de pago de Azure aparte. |
| Servicios de Escritorio remoto (RDS) | Permite que los empleados se conecten a equipos con Windows en la intranet. | Microsoft 365 E3 o E5 |
| Puerta de enlace de Servicios de Escritorio remoto   | Cifra las comunicaciones y evita que los hosts de RDS se expongan directamente a Internet. | Requiere licencias aparte de Windows Server. |
| Microsoft Intune | Administra dispositivos y aplicaciones.   | Microsoft 365 E3 o E5 |
| Configuration Manager | Administra instalaciones, actualizaciones y configuraciones de software en sus dispositivos. | Se requieren licencias aparte de Configuration Manager. |
| Análisis de escritorio | Determina la preparación de la actualización de los clientes de Windows.   | Se requieren licencias aparte de Configuration Manager. |
| Windows Autopilot | Instala y preconfigura nuevos dispositivos con Windows 10 para un uso productivo.   | Microsoft 365 E3 o E5 |
| Microsoft Teams, Exchange Online, SharePoint Online and OneDrive, Aplicaciones de Microsoft 365, Microsoft Power Platform, y Yammer | Crear, comunicar y colaborar. | Microsoft 365 E3 o E5 |
||||

Para ver los criterios de seguridad y cumplimiento consulte [Implementar la seguridad y el cumplimiento para trabajadores remotos](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Para ver un resumen de 2 páginas de esta solución, consulte el póster [Empower hybrid workers](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf).

[![Póster para aumentar la productividad de los trabajadores remotos](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)

También puede descargar este poster en formato [PowerPoint](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pptx)e imprimirlo en papel de tamaño carta, legal o tabloide (11 x 17).

## <a name="provide-hybrid-working-for-all-of-your-workers"></a>Proporcione trabajo híbrido a todos sus trabajadores

Puede permitir que todos sus trabajadores sean más productivos en cualquier lugar con estos dispositivos:

- Un dispositivo moderno, como un portátil Surface con Windows 10, que tiene las características, la seguridad y el rendimiento para utilizar las aplicaciones y servicios en la nube de Microsoft 365 directamente en la web.

- Cualquier dispositivo, incluidos los portátiles antiguos o los equipos de sobremesa domésticos, que puedan acceder a las aplicaciones y servicios en la nube de Microsoft 365 indirectamente a través de [un escritorio virtual basado en Windows 10](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices) que se implementa rápidamente. Esta opción proporciona un alto rendimiento, una seguridad robusta y una administración de TI simplificada.

## <a name="next-steps"></a>Pasos siguientes

Utilice estos pasos para asegurar y optimizar el acceso a los servidores y servicios en la nube de su organización y maximizar la productividad de sus trabajadores híbridos.

1. [Aumentar la seguridad de inicio de sesión con la autenticación multifactor](empower-people-to-work-remotely-secure-sign-in.md)
2. [Proporcionar acceso remoto a los servicios y aplicaciones locales](empower-people-to-work-remotely-remote-access.md)
3. [Implementar servicios de seguridad y cumplimiento](empower-people-to-work-remotely-security-compliance.md)
4. [Implementar la administración de puntos de conexión para dispositivos, equipos y otros puntos de conexión](empower-people-to-work-remotely-manage-endpoints.md)
5. [Implantar aplicaciones y servicios de productividad para trabajadores híbridos](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Forme a sus trabajadores y atienda los comentarios de uso](empower-people-to-work-remotely-train-monitor-usage.md)

[![Los pasos para configurar su infraestructura para el trabajo híbrido con Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Para ver cómo una organización multinacional ficticia, pero representativa, estableció su infraestructura para el trabajo híbrido, consulte la [respuesta COVID-19 de Contoso y la infraestructura para el trabajo híbrido](contoso-remote-onsite-work.md).
