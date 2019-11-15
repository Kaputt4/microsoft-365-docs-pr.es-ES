---
title: Migrar de Microsoft 365 empresa a Microsoft 365 Enterprise
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Obtenga información sobre cómo mover su empresa de Microsoft 365 Business a Microsoft 365 Enterprise E3.
ms.openlocfilehash: 77760aa8ea5b79f39d4c069d86e79a3cec6844e9
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640789"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a>Migrar de Microsoft 365 Empresa a Microsoft 365 Enterprise E3

Microsoft 365 Business tiene todo lo que necesita para su pequeña empresa, ya que combina las mejores aplicaciones de productividad basadas en la nube con la administración de dispositivos sencilla y la seguridad que les permite a sus empleados realizar el mejor trabajo posible. Sin embargo, en algunos casos, es posible que tenga que migrar su suscripción de Microsoft 365 empresa a Microsoft 365 Enterprise. 

Por ejemplo, su empresa ha crecido y necesita más de 300 licencias (Enhorabuena, por cierto).

O bien, su empresa necesita características empresariales, como Office 365 ProPlus, Windows 10 Enterprise E3 o licencias de acceso de cliente (cal) de empresa.

La actualización es sencilla: puede iniciar la actualización [desde el centro de administración](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide). Se mantienen todos los datos y la configuración de la suscripción actual. No hay nada que hacer para prepararse para la migración, ni nada más hacerlo, a menos que se beneficie de las nuevas características. 

>[!Note]
>También puede usar una suscripción de Microsoft 365 empresa para un máximo de 300 puestos y obtener una suscripción a Microsoft 365 Enterprise E3 para más de 300 plazas. Sin embargo, Office 365 ATP no se incluye con Microsoft 365 Enterprise E3. Para la protección contra amenazas continuas, debe agregar licencias de ATP de Office 365 adicionales para que todos los usuarios en el ámbito de las directivas de ATP de Office 365 tengan una licencia.
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Diferencias entre Microsoft 365 Business y Microsoft 365 Enterprise

En esta tabla se muestran las diferencias entre Microsoft 365 Business y Microsoft 365 Enterprise E3.

| Característica   | Soporte en Microsoft 365 Business | Soporte técnico de Microsoft 365 Enterprise E3 | 
|:-------|:-----|:-----|
| **Local**       | | | 
| Windows 10    | Windows 10 Empresa  |    Windows 10 Enterprise E3| 
| Aplicaciones de Office *  | [Office 365 Empresa](#office-365-business)   | Office 365 ProPlus | 
| **Aplicaciones de productividad en la nube**       | | | 
| Exchange Online y Outlook   | límite de almacenamiento de 50 GB por buzón y archivado ilimitado de Exchange Online   | límite de almacenamiento de 100 GB por buzón y archivado ilimitado de Exchange Online | 
| Teams | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| OneDrive para la Empresa | límite de almacenamiento de 1 TB por usuario   | Ilimitado | 
| Yammer, SharePoint Online, Planner, stream    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| StaffHub  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Administrador de clientes de Outlook, MileIQ  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | | 
| **Protección contra amenazas**     | | | 
| Capacidades de reducción de superficie de ataques | [Vea esta lista](#threat-protection) | Administración empresarial del aislamiento basado en hardware para Microsoft Edge | 
| Plan 1 de protección avanzada contra amenazas (ATP) de Office 365 | ![Incluido en Microsoft 365 Business](./media/check-mark.png)  | No se incluye, pero puede agregarse en | 
| **Administración de identidades**       | | | 
| Restablecimiento de contraseña de autoservicio para cuentas híbridas de Azure Active Directory (Azure AD), Azure multi-factor Authentication (MFA), acceso condicional, escritura diferida de contraseñas para identidades locales|    ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Detección de aplicaciones en la nube, Azure AD Connect Health  |   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| El inicio de sesión único (SSO) de las aplicaciones Office 365 de Azure AD: 10 aplicaciones por usuario (Galería de aplicaciones SaaS como Salesforce) * | ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Azure AD Premium 1 SSO: sin límite (aplicaciones locales a través de proxy de aplicación de Azure AD y aplicaciones que no son de galería con plantillas de integración de aplicaciones de autoservicio)  |   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| **Administración de dispositivos y aplicaciones**     | | | 
| Microsoft Intune, Windows AutoPilot|  ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|Acceso de escritorio virtual (VDA)   |  |    ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|Escritorio virtual de Windows (WVD)  | ![Incluido en Microsoft 365 Business](./media/check-mark.png) |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|Activación en equipos compartidos (SCA)   | ![Incluido en Microsoft 365 Business](./media/check-mark.png) |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Paquete de optimización del escritorio de Microsoft    | |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| **Protección de la información**        | | | 
| Prevención de pérdida de datos de Office 365, plan 1 de Azure Information Protection  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Protección de la información de ventanas para DLP de punto de conexión    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| **Licencia de acceso de cliente (derechos de CAL)**    | | |   
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)| |        ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| **Cumplimiento**        | | | 
| Archivado de correo electrónico ilimitado | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Administrador de cumplimiento    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| eDiscovery    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Conservación local y retención por juicio | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| Etiquetas de retención y directivas de retención de administración de registros de mensajería (MRM)  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
||||

\*Los usuarios a los que se les asignó acceso a las aplicaciones de SaaS pueden obtener acceso SSO a un máximo de 10 aplicaciones. Los administradores pueden configurar el SSO y cambiar el acceso del usuario a distintas aplicaciones de SaaS, pero el acceso SSO solo se permite para 10 aplicaciones por usuario a la vez. Todas las aplicaciones de Office 365 se cuentan como una aplicación única.

## <a name="migration"></a>Migración

Para migrar, trabaje con su partner para transferir su suscripción y licencias de Microsoft 365 Business a una suscripción adecuada de Microsoft 365 Enterprise E3 con sus licencias.

En las secciones siguientes se describen los cambios que debe realizar, si los hay, y qué puede hacer después de la migración.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Datos y configuración de suscripción de Microsoft 365

No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de la migración, lo que incluye:

- Configuración de la suscripción, como los nombres de dominio DNS.
- Configuración de autenticación y cuentas de usuario y de grupo, como la autenticación multifactor o las directivas de acceso condicional.
- Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de correo de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la empresa y blocs de notas de OneNote.

Los usuarios ahora pueden disfrutar de un almacenamiento ilimitado en las carpetas de buzones de Exchange Online y OneDrive para la empresa.

Puede empezar a usar Cloud App Discovery, Azure AD Connect Health y SSO para más de 10 aplicaciones.

>[!Note]
>Los usuarios migrados a Microsoft 365 Enterprise E3 ya no pueden usar el administrador de clientes de Outlook y MileIQ.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Protección contra amenazas

Windows 10 Business incluye estas protecciones:

- Aplicación de integridad del proceso de inicio del sistema operativo
- Aplicación de integridad de componentes operativos confidenciales
- Vulnerabilidades avanzadas y mitigaciones de ataques de día cero
- Protección de red basada en la reputación para Microsoft Edge, Internet Explorer y Chrome
- Firewall basado en host
- Mitigaciones de ransomware
- Aislamiento basado en hardware para Microsoft Edge
- Control de aplicaciones basado en el gráfico de seguridad inteligente
- Control de dispositivo (USB)
- Protección de red para amenazas basadas en la web
- Reglas de Host Intrusion Prevention

Windows 10 Enterprise E3 también incluye administración empresarial del aislamiento basado en hardware para Microsoft Edge.

>[!Note]
>Los usuarios migrados a Microsoft 365 Enterprise E3 necesitarán una licencia ATP de Office 365 para una protección contra amenazas continuada. Asegúrese de comprar licencias de ATP de Office 365 adicionales para que todos los usuarios en el ámbito de las directivas de ATP de Office 365 estén autorizados. 
>

### <a name="device-management-with-intune"></a>Administración de dispositivos con Intune

No es necesario realizar ningún cambio en la configuración de Intune actual antes de la migración, lo que incluye los dispositivos inscritos y la configuración de dispositivos y aplicaciones.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business incluye Windows 10 Business, que puede instalar con Windows AutoPilot. Al migrar a Microsoft 365 Enterprise E3, cada licencia de usuario incluye Windows 10 Enterprise E3, que también puede instalar con Windows AutoPilot.

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 Empresa

El cliente de Office 365 empresa instalado en los dispositivos comenzará a usar automáticamente las características de Office 365 ProPlus. Después de la migración, ahora puede usar:

 - Activación por volumen mediante la Directiva de grupo
 - Telemetría de aplicaciones
 - Controles de actualización
 - Comparación de hojas de cálculo y consulta
 - Inteligencia empresarial

