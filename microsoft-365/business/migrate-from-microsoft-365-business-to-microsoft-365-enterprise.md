---
title: Migrar de Microsoft 365 Empresa a Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Obtenga información sobre cómo mover su empresa de Microsoft 365 Empresa Premium a Microsoft 365 E3.
ms.openlocfilehash: d3030518f7f4467c7b2e16897dc7b100764d9d5a36c50169b58f1adcd7bef209
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837645"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar de Microsoft 365 Empresa Premium a Microsoft 365 E3

Microsoft 365 Empresa Premium tiene todo lo que necesita para su pequeña empresa, combinando las mejores aplicaciones de productividad basadas en la nube con una administración de dispositivos sencilla y seguridad que permiten a los empleados realizar su mejor trabajo. Sin embargo, en algunos casos, es posible que deba migrar su Microsoft 365 Empresa Premium a Microsoft 365 E3.

Por ejemplo, su empresa ha crecido y necesita más de 300 licencias (enhorabuena, por cierto).

O bien, su empresa necesita características empresariales, como Aplicaciones Microsoft 365 para empresas, Windows 10 Enterprise E3 o Enterprise licencias de acceso de cliente (CAL).

La actualización es fácil: puede iniciar la actualización [desde el Centro de administración.](../commerce/subscriptions/upgrade-to-different-plan.md) Se mantienen todos los datos y la configuración de la suscripción actual. No hay nada que hacer para preparar la migración y nada que hacer después, excepto aprovechar las nuevas características.

> [!NOTE]
> También puedes usar una suscripción Microsoft 365 Empresa Premium hasta 300 puestos y obtener una suscripción Microsoft 365 E3 más de 300 puestos. Sin embargo, Microsoft Defender para Office 365 no se incluye con Microsoft 365 E3. Para la protección contra amenazas continua, debe agregar más defender para Office 365 licencias para que todos los usuarios en el ámbito de defender para Office 365 las policías tienen licencia.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferencias entre Microsoft 365 Empresa Premium y Microsoft 365 Enterprise

En esta tabla se muestran las diferencias entre Microsoft 365 Empresa Premium y Microsoft 365 E3.

| Característica    | Compatibilidad con Microsoft 365 Empresa Premium    | Compatibilidad con Microsoft 365 E3 |
|:-------|:-----|:-----|
| **Local**        | | |
| Windows 10    | Windows 10 Empresa  |     Windows 10 Enterprise E3|
| Office aplicaciones*    | [Aplicaciones de Microsoft 365 para negocios](#office-365-business)    | Aplicaciones de Microsoft 365 para empresas |
| **Aplicaciones de productividad en la nube**        | | |
| Exchange Online y Outlook    | Límite de almacenamiento de 50 GB por buzón y archivado Exchange Online almacenamiento ilimitado    | Límite de almacenamiento de 100 GB por buzón de correo y almacenamiento Exchange Online archivo |
| Teams    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| OneDrive para la Empresa    | Límite de almacenamiento de 1 TB por usuario    | Ilimitado |
| Yammer, SharePoint Online, Planner, Stream    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| **Protección contra amenazas**        | | |
| Capacidades de reducción de superficie de ataque    | [Vea esta lista](#threat-protection) | Enterprise administración de aislamiento basado en hardware para Microsoft Edge |
| Defender para Office 365 Plan 1 | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | No se incluye, pero se puede agregar en |
| **Administración de identidades**        | | |
| Restablecimiento de contraseñas de autoservicio para cuentas Azure Active Directory híbridas (Azure AD), autenticación multifactor (MFA) de Azure AD, acceso condicional, escritura de contraseña para identidades locales|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Cloud App Discovery, Azure AD Conectar Health    |     | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Aplicaciones de Office 365 azure AD Single Sign-On (SSO): 10 aplicaciones por usuario (aplicaciones SaaS de galería como Salesforce)* | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: sin límite (aplicaciones locales a través del proxy de aplicación de Azure AD y aplicaciones que no son de galería con Self-Service de integración de aplicaciones)    |     | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| **Administración de aplicaciones y dispositivos**        | | |
| Microsoft Intune, Windows Autopilot|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
|Acceso a escritorio virtual (VDA)    |  |     ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
|Windows Escritorio virtual (WVD)    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png) |     ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
|Activación de equipos compartidos (SCA)    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png) |     ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Paquete de optimización de escritorio de Microsoft    | |     ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| **Protección de la información**        | | |
| Office 365 Prevención de pérdida de datos, Plan 1 de Azure Information Protection    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Protección de información de ventana para DLP de extremo    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| **Licencia de acceso de cliente (derechos CAL)**    | | |
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| **Cumplimiento**        | | |
| Archivado de correo electrónico ilimitado    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Administrador de cumplimiento    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| eDiscovery    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Retención local y retención por juicio    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
| Etiquetas de retención y directivas de retención de administración de registros de mensajería (MRM)    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Se incluye con Microsoft 365 E3](../media/check-mark.png) |
||||

\* Los usuarios a los que se les ha asignado acceso a aplicaciones SaaS pueden obtener acceso sso a hasta 10 aplicaciones. Los administradores pueden configurar SSO y cambiar el acceso de usuario a diferentes aplicaciones SaaS, pero el acceso sso solo se permite para 10 aplicaciones por usuario a la vez. Todas Office 365 se cuentan como una sola aplicación.

## <a name="migration"></a>Migración

Para migrar, trabaje con su partner para mover su Microsoft 365 Empresa Premium y licencias a una suscripción Microsoft 365 E3 con sus licencias.

En las secciones siguientes se describen los cambios que debe realizar, si los hay, y lo que puede hacer después de la migración.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 configuración de suscripción y datos

No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de migrar, lo que incluye:

- Configuración de suscripción, como nombres de dominio DNS.
- Cuentas de usuario y grupo y configuración de autenticación, como la autenticación multifactor o las directivas de acceso condicional.
- Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de Exchange Online, sitios de SharePoint online, OneDrive para la Empresa carpetas y blocs de notas OneNote usuario.

Los usuarios ahora pueden disfrutar de almacenamiento ilimitado en Exchange Online buzones de correo y OneDrive para la Empresa carpetas.

Puede empezar a usar Cloud App Discovery, Azure AD Conectar Health y SSO para más de 10 aplicaciones.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protección contra amenazas

Windows 10 Business incluye estas protecciones:

- Cumplimiento de integridad del proceso de arranque del sistema operativo
- Cumplimiento de integridad de componentes operativos confidenciales
- Mitigaciones avanzadas de vulnerabilidad y vulnerabilidad de día cero
- Protección de red basada en reputación para Microsoft Edge, Internet Explorer y Chrome
- Firewall basado en host
- Mitigaciones de ransomware
- Aislamiento basado en hardware para Microsoft Edge
- Control de aplicaciones con tecnología de la Graph
- Control de dispositivo (USB)
- Protección de red para amenazas basadas en web
- Reglas de prevención de intrusiones de host

Windows 10 Enterprise E3 también incluye la administración empresarial del aislamiento basado en hardware para Microsoft Edge.

> [!NOTE]
> Los usuarios migrados a Microsoft 365 E3 necesitarán una licencia de Microsoft Defender Office 365 para la protección contra amenazas continua. Asegúrese de comprar Defender adicional para Office 365 licencias para que todos los usuarios en el ámbito de defender para Office 365 las policías tienen licencia.

### <a name="device-management-with-intune"></a>Administración de dispositivos con Intune

No es necesario realizar ningún cambio en la configuración actual de Intune antes de migrar, que incluye dispositivos inscritos y configuración de dispositivos y aplicaciones.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Empresa Premium incluye Windows 10 Business, que puede instalar con Windows AutoPilot. Al migrar a Microsoft 365 E3, cada licencia de usuario incluye Windows 10 Enterprise E3, que también puede instalar con Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Aplicaciones de Microsoft 365 para negocios

El Aplicaciones Microsoft 365 para negocios instalado en los dispositivos empezará a usar automáticamente las características de Aplicaciones Microsoft 365 para empresas. Después de la migración, ahora puede usar:

- Soporte para directivas de grupos
- Comparación e consulta de hojas de cálculo
- Inteligencia empresarial
