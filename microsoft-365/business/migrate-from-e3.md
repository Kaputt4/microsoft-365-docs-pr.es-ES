---
title: Migrar a Microsoft 365 Empresa desde Office 365 E3
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo mover su empresa a Microsoft 365 Empresa Premium desde Office 365 E3.
ms.openlocfilehash: 3f9fd70b2d31b32027981e638de249d92e98ea08
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164541"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Migración de Office 365 E3 a Microsoft 365 Empresa Premium

Microsoft 365 Empresa Premium tiene todo lo que necesita para su pequeña empresa, combinando las mejores aplicaciones de productividad basadas en la nube con una administración y seguridad de dispositivos sencillas. Si actualmente tiene una suscripción a Office 365 E3, pero no tiene más de 300 empleados, considere la posibilidad de cambiar a Microsoft 365 Empresa Premium para características de seguridad adicionales.

La migración es fácil: primero se cambian las licencias y se mantienen todos los datos y la información de usuario de la suscripción actual. Después de la migración, tendrás que configurar las características que se agregan en Microsoft 365 Empresa Premium.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Diferencias entre Office 365 E3 y Microsoft 365 Empresa Premium

En esta tabla se muestran las diferencias entre Microsoft 365 Empresa Premium y Office 365 E3.

| Característica    | Compatibilidad con Microsoft 365 Empresa Premium    | Compatibilidad con Office 365 E3 | 
|:-------|:-----|:-----|
| **Local**        | | | 
| Aplicaciones de Office<sup>1</sup>    | Aplicaciones de Microsoft 365 para negocios    | Aplicaciones de Microsoft 365 para empresas | 
| **Aplicaciones de productividad en la nube**        | | | 
| Exchange Online y Outlook    | Límite de almacenamiento de 50 GB por buzón y límite Archivado de Exchange Online    | Límite de almacenamiento de 100 GB por buzón y límite Archivado de Exchange Online | 
| Teams    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| OneDrive para la Empresa    | Límite de almacenamiento de 1 TB por usuario    | Ilimitado | 
| Yammer, SharePoint Online, Planner, Stream    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| StaffHub    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| Outlook Customer Manager    | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | | 
| **Protección contra amenazas**        | | | 
| Defender para Office 365 Plan 1 | ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | No se incluye, pero se puede agregar en | 
| **Administración de identidades**        | | | 
| Restablecimiento de contraseñas de autoservicio para cuentas híbridas de Azure Active Directory (Azure AD), autenticación multifactor (MFA) de Azure AD, acceso condicional, escritura de contraseña para identidades locales|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    |  | 
| **Administración de aplicaciones y dispositivos**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    |  |
| Activación en equipos compartidos|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png)| 
| Derechos de actualización a Windows 10 Pro desde licencias de Win 7/8.1 Pro|     ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)    || 
| **Protección de la información**        | | |
|Prevención de pérdida de datos de Office 365|    ![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)|![Incluido con Office 365 E3](../media/check-mark.png)|
|Plan 1 de Azure Information Protection, aplicación de Bitlocker|![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)||
|Plan 1 de Azure Information Protection, etiquetas de confidencialidad|![Incluido con Microsoft 365 Empresa Premium](../media/check-mark.png)||
|**Licencia de acceso de cliente (derechos CAL)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Incluido con Office 365 E3](../media/check-mark.png)|

<sup>1</sup> La versión de Microsoft 365 Empresa Premium de las aplicaciones de Office no incluye la activación por volumen a través de la directiva de grupo, telemetría de aplicaciones, controles de actualización, comparación e investigación de hojas de cálculo o inteligencia empresarial.

## <a name="migration"></a>Migración

Para migrar la suscripción, consulta [Cambiar planes manualmente](../commerce/subscriptions/change-plans-manually.md) para obtener instrucciones si quieres mover solo unas cuantas personas a Microsoft 365 Empresa Premium. También puedes actualizar [a todos automáticamente](../commerce/subscriptions/upgrade-to-different-plan.md)o trabajar con un partner para mover tu suscripción y licencias de E3 a una suscripción de Microsoft 365 Empresa Premium.
En las secciones siguientes se describen los cambios que debe realizar, si los hay, y lo que puede hacer después de la migración.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Configuración y datos de suscripción de Office 365 E3
No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de migrar, lo que incluye:

- Configuración de suscripción, como registros DNS y nombres de dominio.
- Cuentas de usuario y grupo y configuración de autenticación, como la autenticación multifactor o las directivas de acceso condicional.
- Configuraciones de servicio de productividad y sus datos, como Teams, buzones de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la Empresa y blocs de notas de OneNote.
- Las aplicaciones de Office se escalarán automáticamente. Las licencias modernas de Office 365 comprobarán la asignación de licencia del usuario cada 72 horas y convertirán las aplicaciones de Office en la versión que coincida con la suscripción del usuario.

### <a name="windows-10"></a>Windows 10

Si Windows aún no está en la actualización de Windows Pro Creator, [actualíceslos a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>Configurar directivas para proteger los archivos y dispositivos de usuario

> [!NOTE]
> Si configura dispositivos y directivas mdm de Office 365, estos dispositivos aparecerán en la página Dispositivos del Centro de administración de Microsoft 365.  Las directivas que configures aparecerán en la lista de directivas clásicas en el [portal de Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)

Después de asignar licencias a Microsoft 365 Empresa Premium, puede empezar a proteger los dispositivos y archivos de los usuarios.

Si ha actualizado todos los usuarios de su organización a Microsoft 365 Empresa Premium, verá el asistente de configuración en la página principal y puede seguir los pasos del Asistente para configurar [Microsoft 365 Empresa Premium](set-up.md) para proteger archivos y dispositivos móviles.

También puedes completar estos pasos en la página Dispositivos:
  
1. En el Centro de administración, en la navegación izquierda, vaya a **Directivas de** \> **dispositivos**.
    
2. En la **página Directivas de dispositivo,** elija **Agregar**.
    
3. En el **panel Agregar directiva,** asigne un nombre a la directiva y, a continuación, elija un **tipo de directiva** en la lista desplegable. 
    
     Puedes configurar directivas de aplicación para proteger archivos en dispositivos Android y iPhone, así como Windows 10, y puedes configurar directivas de configuración de dispositivos para dispositivos windows 10 propiedad de la empresa. Vea los siguientes vínculos para obtener más información:
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Establecer la configuración de protección de aplicaciones para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Establecer la configuración de protección de dispositivos para equipos con Windows 10](protection-settings-for-windows-10-pcs.md)
  
4. Una vez configuradas las directivas, tú y tus empleados pueden configurar dispositivos:
    
  - Consulta [Configurar dispositivos Windows para usuarios de Microsoft 365 Empresa Premium](set-up-windows-devices.md) para ver los pasos para dispositivos Windows. 
    
  - Consulta [Configurar dispositivos móviles para usuarios de Microsoft 365 Empresa Premium](set-up-mobile-devices.md) para ver los pasos para teléfonos Android y iPhones. 
  
### <a name="mailbox-size"></a>Tamaño del buzón

Microsoft 365 Empresa Premium tiene un límite de almacenamiento de 50 GB, ya que usa Exchange Online Plan 1. Al migrar a Microsoft 365 Empresa Premium, si alguno de los usuarios supera los 50 GB de almacenamiento de buzones, se recomienda asignar a este usuario un Plan 2 de Exchange Online y quitar el Plan 1 de Exchange Online, ya que no es factible asignar ambos.


### <a name="threat-protection"></a>Protección contra amenazas

Después de migrar a Microsoft 365 Empresa Premium, tiene Defender para Office 365. Vea [Microsoft Defender para Office 365](../security/defender-365-security/defender-for-office-365.md) para obtener información general. Para configurar, vea [Configurar](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)vínculos [seguros,](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)configurar datos adjuntos seguros y configurar la protección contra suplantación de identidad en Defender para [Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para empezar a usar etiquetas de confidencialidad, vea [Overview of sensitivity labels](../compliance/sensitivity-labels.md) y create and manage sensitivity [labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.
