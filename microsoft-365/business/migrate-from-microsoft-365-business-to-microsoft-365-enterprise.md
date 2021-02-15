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
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126209"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Migrar de Microsoft 365 Empresa Premium a Microsoft 365 E3

Microsoft 365 Empresa Premium tiene todo lo que necesita para su pequeña empresa, combinando las mejores aplicaciones de productividad basadas en la nube con seguridad y administración de dispositivos sencillas que permiten a los empleados realizar su mejor trabajo. En algunos casos, sin embargo, es posible que deba migrar su suscripción de Microsoft 365 Empresa Premium a Microsoft 365 E3. 

Por ejemplo, su negocio ha aumentado y necesita más de 300 licencias (enhorabuena, por cierto).

O bien, su empresa necesita características empresariales, como Aplicaciones de Microsoft 365 para empresas, Windows 10 Enterprise E3 o Licencias de acceso de cliente (CAL) de Enterprise.

La actualización es sencilla: puede iniciar la [actualización desde el Centro de administración.](../commerce/subscriptions/upgrade-to-different-plan.md) Se mantienen todos los datos y la configuración de la suscripción actual. No hay nada que hacer para prepararse para la migración y nada que hacer después, excepto aprovechar las nuevas características.

>[!Note]
>También puede usar una suscripción a Microsoft 365 Empresa Premium para un máximo de 300 puestos y obtener una suscripción a Microsoft 365 E3 para más de 300 puestos. Sin embargo, Microsoft Defender para Office 365 no está incluido en Microsoft 365 E3. Para una protección contra amenazas continua, debe agregar licencias adicionales de Defender para Office 365 para que todos los usuarios del ámbito de su Defender para las políticas de Office 365 puedan obtener una licencia.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Diferencias entre Microsoft 365 Empresa Premium y Microsoft 365 Enterprise

En esta tabla se muestran las diferencias entre Microsoft 365 Empresa Premium y Microsoft 365 E3.

| Característica    | Soporte técnico en Microsoft 365 Empresa Premium    | Compatibilidad con Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Local**        | | | 
| Windows 10    | Windows 10 Empresa  |     Windows 10 Enterprise E3| 
| Aplicaciones de Office*    | [Aplicaciones de Microsoft 365 para negocios](#office-365-business)    | Aplicaciones de Microsoft 365 para empresas | 
| **Aplicaciones de productividad en la nube**        | | | 
| Exchange Online y Outlook    | Límite de almacenamiento de 50 GB por buzón y archivado ilimitado de Exchange Online    | Límite de almacenamiento de 100 GB por buzón y archivado ilimitado de Exchange Online | 
| Teams    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive para la Empresa    | Límite de almacenamiento de 1 TB por usuario    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| MileIQ    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | | 
| **Protección contra amenazas**        | | | 
| Capacidades de reducción de superficie de ataque    | [Vea esta lista](#threat-protection) | Administración empresarial del aislamiento basado en hardware para Microsoft Edge | 
| Defender para Office 365 Plan 1 | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | No se incluye, pero se puede agregar en | 
| **Administración de identidades**        | | | 
| Autoservicio de restablecimiento de contraseña para cuentas híbridas de Azure Active Directory (Azure AD), autenticación multifactor (MFA) de Azure AD, acceso condicional, escritura de contraseña para identidades locales|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Aplicaciones de Azure AD Office 365 single Sign-On (SSO): 10 aplicaciones por usuario (aplicaciones SaaS de galería como Salesforce)* | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| SSO de Azure AD Premium 1: sin límite (aplicaciones locales a través del Proxy de aplicación de Azure AD y aplicaciones que no son de galería con Self-Service de integración de aplicaciones)    |     | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| **Datos de administración de dispositivos y aplicaciones**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
|Virtual Desktop Access (VDA)    |  |     ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
|Windows Virtual Desktop (WVD)    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png) |     ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
|Activación en equipos compartidos (SCA)    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png) |     ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Paquete de Optimización de escritorio de Microsoft    | |     ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| **Protección de la información**        | | | 
| Prevención de pérdida de datos de Office 365, Plan 1 de Azure Information Protection    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Protección de información de ventana para DLP de punto de conexión    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| **Licencia de acceso de cliente (derechos cal)**    | | |     
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| **Cumplimiento**        | | | 
| Archivado de correo electrónico ilimitado    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Administrador de cumplimiento    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| eDiscovery    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Retención local y retención por juicio    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
| Etiquetas de retención y directivas de retención de Administración de registros de mensajería (MRM)    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Los usuarios a los que se les ha asignado acceso a las aplicaciones SaaS pueden obtener acceso sso a hasta 10 aplicaciones. Los administradores pueden configurar SSO y cambiar el acceso de usuario a diferentes aplicaciones SaaS, pero el acceso a SSO solo se permite para 10 aplicaciones por usuario a la vez. Todas las aplicaciones de Office 365 se cuentan como una sola aplicación.

## <a name="migration"></a>Migración

Para migrar, trabaje con su partner para mover su suscripción a Microsoft 365 Empresa Premium y las licencias a una suscripción de Microsoft 365 E3 adecuada con sus licencias.

En las secciones siguientes se describen los cambios que debe realizar, si los hay, y lo que puede hacer después de la migración.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Configuración y datos de suscripción de Microsoft 365

No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de migrar, lo que incluye:

- Configuración de suscripción, como nombres de dominio DNS.
- Cuentas de usuario y grupo y configuración de autenticación, como la autenticación multifactor o las directivas de acceso condicional.
- Configuraciones del servicio de productividad y sus datos, como Teams, buzones de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la Empresa y blocs de notas de OneNote.

Ahora, los usuarios pueden disfrutar de un almacenamiento ilimitado en los buzones de Exchange Online y en las carpetas de OneDrive para la Empresa.

Puede empezar a usar Cloud App Discovery, Azure AD Connect Health y SSO para más de 10 aplicaciones.

>[!Note]
>Los usuarios migrados a Microsoft 365 E3 ya no pueden usar MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protección contra amenazas

Windows 10 Business incluye estas protecciones:

- Cumplimiento de integridad del proceso de arranque del sistema operativo
- Cumplimiento de integridad de componentes operativos confidenciales
- Vulnerabilidad avanzada y mitigaciones de vulnerabilidad de seguridad de día cero
- Protección de red basada en la reputación para Microsoft Edge, Internet Explorer y Chrome
- Firewall basado en host
- Mitigaciones de ransomware
- Aislamiento basado en hardware para Microsoft Edge
- Control de aplicaciones con tecnología de Intelligent Security Graph
- Control de dispositivo (USB)
- Protección de red para amenazas basadas en web
- Reglas de prevención de intrusiones de host

Windows 10 Enterprise E3 también incluye la administración empresarial del aislamiento basado en hardware para Microsoft Edge.

>[!Note]
>Los usuarios migrados a Microsoft 365 E3 necesitarán una licencia de Microsoft Defender para Office 365 para la protección contra amenazas continuada. Asegúrese de comprar licencias adicionales de Defender para Office 365 para que todos los usuarios del ámbito de su Defender para las políticas de Office 365 puedan obtener una licencia. 
>

### <a name="device-management-with-intune"></a>Administración de dispositivos con Intune

No es necesario realizar ningún cambio en la configuración actual de Intune antes de migrar, lo que incluye los dispositivos inscritos y la configuración de dispositivos y aplicaciones.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Empresa Premium incluye Windows 10 Empresa, que puedes instalar con Windows AutoPilot. Al migrar a Microsoft 365 E3, cada licencia de usuario incluye Windows 10 Enterprise E3, que también puedes instalar con Windows Autopilot.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Aplicaciones de Microsoft 365 para negocios

El cliente de Aplicaciones de Microsoft 365 para empresas instalado en sus dispositivos empezará a usar automáticamente las características de Aplicaciones de Microsoft 365 para empresas. Después de la migración, ahora puede usar:

 - Soporte para directivas de grupos
 - Comparación y consulta de hojas de cálculo
 - Inteligencia empresarial

