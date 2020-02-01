---
title: Migrar a Microsoft 365 Business desde Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo mover su empresa a Microsoft 365 Business desde Office 365 E3.
ms.openlocfilehash: 210f3ebf76da49349dfb6d61d0b8ce88d15d3734
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593709"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>Migración de Office 365 E3 a Microsoft 365 Business 

Microsoft 365 Business tiene todo lo que necesita para su pequeña empresa, ya que combina las mejores aplicaciones de productividad basadas en la nube con la administración de dispositivos sencilla y la seguridad. Si actualmente tiene una suscripción de Office 365 E3, pero no tiene más de 300 empleados, considere la posibilidad de cambiar a Microsoft 365 Business para obtener características de seguridad adicionales.

La migración es sencilla: primero cambia las licencias y todos los datos y la información de usuario de su suscripción actual se mantiene. Después de la migración, deberá configurar las características que se agregan en Microsoft 365 Business.

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Diferencias entre Office 365 E3 y Microsoft 365 Business

En esta tabla se muestran las diferencias entre Microsoft 365 Business y Office 365 E3.

| Característica   | Soporte en Microsoft 365 Business | Soporte técnico en Office 365 E3 | 
|:-------|:-----|:-----|
| **Local**       | | | 
| Aplicaciones de Office<sup>1</sup>   | Office 365 Empresa   | Office 365 ProPlus | 
| **Aplicaciones de productividad en la nube**       | | | 
| Exchange Online y Outlook   | límite de almacenamiento de 50 GB por buzón y archivado ilimitado de Exchange Online   | límite de almacenamiento de 100 GB por buzón y archivado ilimitado de Exchange Online | 
| Teams | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido con Office 365 E3](./media/check-mark.png) | 
| OneDrive para la Empresa | límite de almacenamiento de 1 TB por usuario   | Ilimitado | 
| Yammer, SharePoint Online, Planner, stream    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido con Office 365 E3](./media/check-mark.png) | 
| StaffHub  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido con Office 365 E3](./media/check-mark.png) | 
| Administrador de clientes de Outlook, MileIQ  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | | 
| **Protección contra amenazas**     | | | 
| Plan 1 de protección avanzada contra amenazas (ATP) de Office 365 | ![Incluido en Microsoft 365 Business](./media/check-mark.png)  | No se incluye, pero puede agregarse en | 
| **Administración de identidades**       | | | 
| Restablecimiento de contraseña de autoservicio para cuentas híbridas de Azure Active Directory (Azure AD), Azure multi-factor Authentication (MFA), acceso condicional, escritura diferida de contraseñas para identidades locales|    ![Incluido en Microsoft 365 Business](./media/check-mark.png) |  | 
| **Administración de dispositivos y aplicaciones**     | | |
| Microsoft Intune, Windows AutoPilot|  ![Incluido en Microsoft 365 Business](./media/check-mark.png) |  |
| Activación en equipos compartidos|   ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido con Office 365 E3](./media/check-mark.png)| 
| Derechos de actualización a Windows 10 Pro desde licencias Win 7/8.1 Pro|     ![Incluido en Microsoft 365 Business](./media/check-mark.png) || 
| **Protección de la información**        | | |
|Prevención de pérdida de datos de Office 365|   ![Incluido en Microsoft 365 Business](./media/check-mark.png)|![Incluido con Office 365 E3](./media/check-mark.png)|
|Plan 1 de Azure Information Protection, cumplimiento de BitLocker|![Incluido en Microsoft 365 Business](./media/check-mark.png)||
|Plan 1 de Azure Information Protection, etiquetas de confidencialidad|![Incluido en Microsoft 365 Business](./media/check-mark.png)||
|**Licencia de acceso de cliente (derechos de CAL)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Incluido con Office 365 E3](./media/check-mark.png)|

<sup>1</sup> la versión de Microsoft 365 Business de las aplicaciones de Office no incluye la activación por volumen a través de la Directiva de grupo, la telemetría de aplicaciones, los controles de actualización, la comparación de hojas de cálculo y las consultas o la inteligencia empresarial.

## <a name="migration"></a>Migración

Para migrar la suscripción, vea [cambiar a un plan diferente manualmente](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) para obtener instrucciones si desea mover solo unas pocas personas a Microsoft 365 Business. También puede [actualizar a todos automáticamente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), o trabajar con un partner para mover la suscripción y licencias de E3 a una suscripción de Microsoft 365 Business.
En las secciones siguientes se describen los cambios que debe realizar, si los hay, y qué puede hacer después de la migración.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuración y datos de suscripción de Office 365 E3
No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de la migración, lo que incluye:

- Configuración de suscripción, como los registros DNS y los nombres de dominio.
- Configuración de autenticación y cuentas de usuario y de grupo, como la autenticación multifactor o las directivas de acceso condicional.
- Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de correo de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la empresa y blocs de notas de OneNote.

### <a name="windows-10"></a>Windows 10

Si sus ventanas ya no están en la actualización del creador de Windows Pro, [actualícelas a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurar directivas para proteger archivos y dispositivos de usuario

> [!NOTE]
> Si configura las directivas y dispositivos MDM de Office 365, dichos dispositivos se enumerarán en la página **dispositivos** del centro de administración de Microsoft 365. Las directivas que configure se mostrarán en la lista de directivas clásicas en el [portal de Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).

Una vez que haya asignado las licencias a Microsoft 365 Business, puede empezar a proteger los dispositivos y archivos de los usuarios.

Si ha actualizado a todos los usuarios de su organización a Microsoft 365 Business, verá el Asistente de configuración en la Página principal y podrá seguir el procedimiento [configurar Microsoft 365 Business en el Asistente para la instalación](set-up.md) para proteger los archivos y los dispositivos móviles.

También puede completar estos pasos en la página dispositivos:
  
1. En el centro de administración, en el panel de navegación izquierdo, vaya a **directivas**de **dispositivos** \> .
    
2. En la página **directivas de dispositivos** , elija **Agregar**.
    
3. En el panel **Agregar Directiva** , asigne un nombre a la Directiva y, a continuación, elija un **tipo de directiva** en la lista desplegable. 
    
     Puede configurar directivas de aplicación para proteger los archivos en dispositivos Android y iPhone, así como en Windows 10, y puede configurar directivas de configuración de dispositivo para dispositivos Windows 10 que pertenecen a la empresa. Consulte los siguientes vínculos para obtener más información:
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Una vez que haya configurado las directivas, usted y sus empleados podrán configurar dispositivos:
    
  - Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para conocer los pasos para dispositivos Windows. 
    
  - Consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md) para conocer los pasos para Android Phones y iPhone. 

### <a name="threat-protection"></a>Protección contra amenazas

Después de realizar la migración a Microsoft 365 Business, tiene Office 365 ATP. Consulte [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) para obtener información general. Para configurar, consulte [configurar los vínculos seguros de ATP](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [configurar los datos adjuntos seguros](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)de ATP y [configurar la protección contra phishing de ATP](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para empezar a utilizar etiquetas de confidencialidad, consulte [información general sobre las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) y [crear y administrar las etiquetas de confidencialidad](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) vídeo.
