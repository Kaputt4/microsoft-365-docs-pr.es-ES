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
ms.openlocfilehash: 54320ed60825a28147542094b19761889a70ae9f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065584"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="22b42-103">Migración de Office 365 E3 a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="22b42-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="22b42-104">Microsoft 365 Business tiene todo lo que necesita para su pequeña empresa, ya que combina las mejores aplicaciones de productividad basadas en la nube con la administración de dispositivos sencilla y la seguridad.</span><span class="sxs-lookup"><span data-stu-id="22b42-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="22b42-105">Si actualmente tiene una suscripción de Office 365 E3, pero no tiene más de 300 empleados, considere la posibilidad de cambiar a Microsoft 365 Business para obtener características de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="22b42-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="22b42-106">La migración es sencilla: primero cambia las licencias y todos los datos y la información de usuario de su suscripción actual se mantiene.</span><span class="sxs-lookup"><span data-stu-id="22b42-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="22b42-107">Después de la migración, deberá configurar las características que se agregan en Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="22b42-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="22b42-108">Diferencias entre Office 365 E3 y Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="22b42-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="22b42-109">En esta tabla se muestran las diferencias entre Microsoft 365 Business y Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="22b42-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="22b42-110">Característica</span><span class="sxs-lookup"><span data-stu-id="22b42-110">Feature</span></span>   | <span data-ttu-id="22b42-111">Soporte en Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="22b42-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="22b42-112">Soporte técnico en Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="22b42-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="22b42-113">**Local**</span><span class="sxs-lookup"><span data-stu-id="22b42-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="22b42-114">Aplicaciones de Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="22b42-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="22b42-115">Office 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="22b42-115">Office 365 Business</span></span>   | <span data-ttu-id="22b42-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="22b42-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="22b42-117">**Aplicaciones de productividad en la nube**</span><span class="sxs-lookup"><span data-stu-id="22b42-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="22b42-118">Exchange Online y Outlook</span><span class="sxs-lookup"><span data-stu-id="22b42-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="22b42-119">límite de almacenamiento de 50 GB por buzón y archivado ilimitado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="22b42-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>   | <span data-ttu-id="22b42-120">límite de almacenamiento de 100 GB por buzón y archivado ilimitado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="22b42-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="22b42-121">Teams</span><span class="sxs-lookup"><span data-stu-id="22b42-121">Teams</span></span> | ![Incluido en Microsoft 365 Business](../media/check-mark.png)  | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="22b42-124">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="22b42-124">OneDrive for Business</span></span> | <span data-ttu-id="22b42-125">límite de almacenamiento de 1 TB por usuario</span><span class="sxs-lookup"><span data-stu-id="22b42-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="22b42-126">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="22b42-126">Unlimited</span></span> | 
| <span data-ttu-id="22b42-127">Yammer, SharePoint Online, Planner, stream</span><span class="sxs-lookup"><span data-stu-id="22b42-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluido en Microsoft 365 Business](../media/check-mark.png)  | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="22b42-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="22b42-130">StaffHub</span></span>  | ![Incluido en Microsoft 365 Business](../media/check-mark.png)  | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="22b42-133">Administrador de clientes de Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="22b42-133">Outlook Customer Manager, MileIQ</span></span>  | ![Incluido en Microsoft 365 Business](../media/check-mark.png)  | | 
| <span data-ttu-id="22b42-135">**Protección contra amenazas**</span><span class="sxs-lookup"><span data-stu-id="22b42-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="22b42-136">Plan 1 de protección avanzada contra amenazas (ATP) de Office 365</span><span class="sxs-lookup"><span data-stu-id="22b42-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Incluido en Microsoft 365 Business](../media/check-mark.png) | <span data-ttu-id="22b42-138">No se incluye, pero puede agregarse en</span><span class="sxs-lookup"><span data-stu-id="22b42-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="22b42-139">**Administración de identidades**</span><span class="sxs-lookup"><span data-stu-id="22b42-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="22b42-140">Restablecimiento de contraseña de autoservicio para cuentas híbridas de Azure Active Directory (Azure AD), Azure multi-factor Authentication (MFA), acceso condicional, escritura diferida de contraseñas para identidades locales</span><span class="sxs-lookup"><span data-stu-id="22b42-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Incluido en Microsoft 365 Business](../media/check-mark.png)    |  | 
| <span data-ttu-id="22b42-142">**Administración de dispositivos y aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="22b42-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="22b42-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="22b42-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Incluido en Microsoft 365 Business](../media/check-mark.png)    |  |
| <span data-ttu-id="22b42-145">Activación en equipos compartidos</span><span class="sxs-lookup"><span data-stu-id="22b42-145">Shared computer activation</span></span>|   ![Incluido en Microsoft 365 Business](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="22b42-148">Derechos de actualización a Windows 10 Pro desde licencias Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="22b42-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluido en Microsoft 365 Business](../media/check-mark.png)    || 
| <span data-ttu-id="22b42-150">**Protección de la información**</span><span class="sxs-lookup"><span data-stu-id="22b42-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="22b42-151">Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="22b42-151">Office 365 Data Loss Prevention</span></span>|   ![Incluido en Microsoft 365 Business](../media/check-mark.png)|![Incluido con Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="22b42-154">Plan 1 de Azure Information Protection, cumplimiento de BitLocker</span><span class="sxs-lookup"><span data-stu-id="22b42-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Incluido en Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="22b42-156">Plan 1 de Azure Information Protection, etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="22b42-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluido en Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="22b42-158">**Licencia de acceso de cliente (derechos de CAL)**</span><span class="sxs-lookup"><span data-stu-id="22b42-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="22b42-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="22b42-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluido con Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="22b42-161"><sup>1</sup> la versión de Microsoft 365 Business de las aplicaciones de Office no incluye la activación por volumen a través de la Directiva de grupo, la telemetría de aplicaciones, los controles de actualización, la comparación de hojas de cálculo y las consultas o la inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="22b42-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="22b42-162">Migración</span><span class="sxs-lookup"><span data-stu-id="22b42-162">Migration</span></span>

<span data-ttu-id="22b42-163">Para migrar la suscripción, vea [cambiar a un plan diferente manualmente](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) para obtener instrucciones si desea mover solo unas pocas personas a Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="22b42-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="22b42-164">También puede [actualizar a todos automáticamente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), o trabajar con un partner para mover la suscripción y licencias de E3 a una suscripción de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="22b42-164">You can also [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="22b42-165">En las secciones siguientes se describen los cambios que debe realizar, si los hay, y qué puede hacer después de la migración.</span><span class="sxs-lookup"><span data-stu-id="22b42-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="22b42-166">Configuración y datos de suscripción de Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="22b42-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="22b42-167">No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de la migración, lo que incluye:</span><span class="sxs-lookup"><span data-stu-id="22b42-167">You don’t need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="22b42-168">Configuración de suscripción, como los registros DNS y los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="22b42-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="22b42-169">Configuración de autenticación y cuentas de usuario y de grupo, como la autenticación multifactor o las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="22b42-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="22b42-170">Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de correo de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la empresa y blocs de notas de OneNote.</span><span class="sxs-lookup"><span data-stu-id="22b42-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="22b42-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="22b42-171">Windows 10</span></span>

<span data-ttu-id="22b42-172">Si sus ventanas ya no están en la actualización del creador de Windows Pro, [actualícelas a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="22b42-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="22b42-173">Configurar directivas para proteger archivos y dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="22b42-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="22b42-174">Si configura las directivas y dispositivos MDM de Office 365, dichos dispositivos se enumerarán en la página **dispositivos** del centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22b42-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="22b42-175">Las directivas que configure se mostrarán en la lista de directivas clásicas en el [portal de Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="22b42-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="22b42-176">Una vez que haya asignado las licencias a Microsoft 365 Business, puede empezar a proteger los dispositivos y archivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="22b42-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="22b42-177">Si ha actualizado a todos los usuarios de su organización a Microsoft 365 Business, verá el Asistente de configuración en la Página principal y podrá seguir el procedimiento [configurar Microsoft 365 Business en el Asistente para la instalación](set-up.md) para proteger los archivos y los dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="22b42-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="22b42-178">También puede completar estos pasos en la página dispositivos:</span><span class="sxs-lookup"><span data-stu-id="22b42-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="22b42-179">En el centro de administración, en el panel de navegación izquierdo, vaya a **directivas**de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="22b42-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="22b42-180">En la página **directivas de dispositivos** , elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="22b42-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="22b42-181">En el panel **Agregar Directiva** , asigne un nombre a la Directiva y, a continuación, elija un **tipo de directiva** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="22b42-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="22b42-182">Puede configurar directivas de aplicación para proteger los archivos en dispositivos Android y iPhone, así como en Windows 10, y puede configurar directivas de configuración de dispositivo para dispositivos Windows 10 que pertenecen a la empresa.</span><span class="sxs-lookup"><span data-stu-id="22b42-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="22b42-183">Consulte los siguientes vínculos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="22b42-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="22b42-184">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="22b42-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="22b42-185">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="22b42-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="22b42-186">Establecer la configuración de protección de dispositivos para equipos con Windows 10</span><span class="sxs-lookup"><span data-stu-id="22b42-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="22b42-187">Una vez que haya configurado las directivas, usted y sus empleados podrán configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="22b42-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="22b42-188">Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para conocer los pasos para dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="22b42-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="22b42-189">Consulte [configurar dispositivos móviles para los usuarios de Microsoft 365 Business](set-up-mobile-devices.md) para conocer los pasos para Android Phones y iPhone.</span><span class="sxs-lookup"><span data-stu-id="22b42-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="22b42-190">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="22b42-190">Threat protection</span></span>

<span data-ttu-id="22b42-191">Después de realizar la migración a Microsoft 365 Business, tiene Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="22b42-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="22b42-192">Consulte [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) para obtener información general.</span><span class="sxs-lookup"><span data-stu-id="22b42-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="22b42-193">Para configurar, consulte [configurar los vínculos seguros de ATP](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [configurar los datos adjuntos seguros](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)de ATP y [configurar la protección contra phishing de ATP](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="22b42-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="22b42-194">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="22b42-194">Sensitivity labels</span></span>

<span data-ttu-id="22b42-195">Para empezar a utilizar etiquetas de confidencialidad, consulte [información general sobre las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) y [crear y administrar las etiquetas de confidencialidad](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) vídeo.</span><span class="sxs-lookup"><span data-stu-id="22b42-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
