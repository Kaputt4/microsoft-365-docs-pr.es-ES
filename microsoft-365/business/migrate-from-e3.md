---
title: Migrar a Microsoft 365 Empresa desde Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Si tiene una suscripción Office 365 E3 pero no tiene más de 300 empleados, considere la posibilidad de cambiar a Microsoft 365 Empresa Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623613"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="f614b-103">Migración de Office 365 E3 a Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="f614b-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="f614b-104">Microsoft 365 Empresa Premium todo lo que necesitas para tu pequeña empresa, combinando las mejores aplicaciones de productividad basadas en la nube con una administración y seguridad de dispositivos sencillas.</span><span class="sxs-lookup"><span data-stu-id="f614b-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="f614b-105">Si actualmente tiene una suscripción Office 365 E3, pero no tiene más de 300 empleados, considere la posibilidad de cambiar a Microsoft 365 Empresa Premium para características de seguridad agregadas.</span><span class="sxs-lookup"><span data-stu-id="f614b-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="f614b-106">La migración es fácil: primero se cambian las licencias y se mantienen todos los datos y la información de usuario de la suscripción actual.</span><span class="sxs-lookup"><span data-stu-id="f614b-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="f614b-107">Después de la migración, deberá configurar las características que se agregan en Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="f614b-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="f614b-108">Diferencias entre Office 365 E3 y Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="f614b-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="f614b-109">En esta tabla se muestran las diferencias entre Microsoft 365 Empresa Premium y Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="f614b-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="f614b-110">Característica</span><span class="sxs-lookup"><span data-stu-id="f614b-110">Feature</span></span>    | <span data-ttu-id="f614b-111">Compatibilidad con Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="f614b-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="f614b-112">Compatibilidad con Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="f614b-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="f614b-113">**Local**</span><span class="sxs-lookup"><span data-stu-id="f614b-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="f614b-114">Office aplicaciones<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f614b-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="f614b-115">Aplicaciones de Microsoft 365 para negocios</span><span class="sxs-lookup"><span data-stu-id="f614b-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="f614b-116">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f614b-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="f614b-117">**Aplicaciones de productividad en la nube**</span><span class="sxs-lookup"><span data-stu-id="f614b-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="f614b-118">Exchange Online y Outlook</span><span class="sxs-lookup"><span data-stu-id="f614b-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="f614b-119">Límite de almacenamiento de 50 GB por buzón y límite Archivado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f614b-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="f614b-120">Límite de almacenamiento de 100 GB por buzón y límite Archivado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f614b-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="f614b-121">Teams</span><span class="sxs-lookup"><span data-stu-id="f614b-121">Teams</span></span>    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="f614b-124">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="f614b-124">OneDrive for Business</span></span>    | <span data-ttu-id="f614b-125">Límite de almacenamiento de 1 TB por usuario</span><span class="sxs-lookup"><span data-stu-id="f614b-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="f614b-126">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="f614b-126">Unlimited</span></span> | 
| <span data-ttu-id="f614b-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="f614b-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="f614b-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="f614b-130">StaffHub</span></span>    | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="f614b-133">**Protección contra amenazas**</span><span class="sxs-lookup"><span data-stu-id="f614b-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="f614b-134">Defender para Office 365 Plan 1</span><span class="sxs-lookup"><span data-stu-id="f614b-134">Defender for Office 365 Plan 1</span></span> | ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | <span data-ttu-id="f614b-136">No se incluye, pero se puede agregar en</span><span class="sxs-lookup"><span data-stu-id="f614b-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="f614b-137">**Administración de identidades**</span><span class="sxs-lookup"><span data-stu-id="f614b-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="f614b-138">Restablecimiento de contraseñas de autoservicio para cuentas Azure Active Directory híbridas (Azure AD), autenticación multifactor (MFA) de Azure AD, acceso condicional, escritura de contraseña para identidades locales</span><span class="sxs-lookup"><span data-stu-id="f614b-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="f614b-140">**Administración de aplicaciones y dispositivos**</span><span class="sxs-lookup"><span data-stu-id="f614b-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="f614b-141">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f614b-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="f614b-143">Activación en equipos compartidos</span><span class="sxs-lookup"><span data-stu-id="f614b-143">Shared computer activation</span></span>|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    | ![Incluido con Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="f614b-146">Derechos de actualización Windows 10 Pro de licencias de Win 7/8.1 Pro licencias</span><span class="sxs-lookup"><span data-stu-id="f614b-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)    ||
| <span data-ttu-id="f614b-148">**Protección de la información**</span><span class="sxs-lookup"><span data-stu-id="f614b-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="f614b-149">Prevención de pérdida de datos de Office 365</span><span class="sxs-lookup"><span data-stu-id="f614b-149">Office 365 Data Loss Prevention</span></span>|    ![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)|![Incluido con Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="f614b-152">Azure Information Protection Plan 1, BitLocker cumplimiento</span><span class="sxs-lookup"><span data-stu-id="f614b-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)||
|<span data-ttu-id="f614b-154">Plan 1 de Azure Information Protection, etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f614b-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Se incluye con Microsoft 365 Empresa Premium](../media/check-mark.png)||
|<span data-ttu-id="f614b-156">**Licencia de acceso de cliente (derechos CAL)**</span><span class="sxs-lookup"><span data-stu-id="f614b-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="f614b-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="f614b-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluido con Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="f614b-159"><sup>1</sup> La versión Microsoft 365 Empresa Premium de las aplicaciones de Office no incluye la activación por volumen a través de la directiva de grupo, telemetría de aplicaciones, controles de actualización, comparación e consulta de hojas de cálculo o inteligencia empresarial.</span><span class="sxs-lookup"><span data-stu-id="f614b-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="f614b-160">Migración</span><span class="sxs-lookup"><span data-stu-id="f614b-160">Migration</span></span>

<span data-ttu-id="f614b-161">Para migrar la suscripción, consulta [Cambiar planes manualmente](../commerce/subscriptions/change-plans-manually.md) para obtener instrucciones si quieres mover solo unas cuantas personas a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="f614b-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="f614b-162">También puede actualizar [todos automáticamente](../commerce/subscriptions/upgrade-to-different-plan.md)o trabajar con un partner para mover la suscripción y las licencias de E3 a una Microsoft 365 Empresa Premium suscripción.</span><span class="sxs-lookup"><span data-stu-id="f614b-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="f614b-163">En las secciones siguientes se describen los cambios que debe realizar, si los hay, y lo que puede hacer después de la migración.</span><span class="sxs-lookup"><span data-stu-id="f614b-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="f614b-164">Office 365 Configuración y datos de suscripción de E3</span><span class="sxs-lookup"><span data-stu-id="f614b-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="f614b-165">No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de migrar, lo que incluye:</span><span class="sxs-lookup"><span data-stu-id="f614b-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="f614b-166">Configuración de suscripción, como registros DNS y nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="f614b-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="f614b-167">Cuentas de usuario y grupo y configuración de autenticación, como la autenticación multifactor o las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="f614b-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="f614b-168">Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de Exchange Online, sitios de SharePoint online, OneDrive para la Empresa carpetas y blocs de notas OneNote usuario.</span><span class="sxs-lookup"><span data-stu-id="f614b-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="f614b-169">Office las aplicaciones se escalarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f614b-169">Office applications will scale automatically.</span></span> <span data-ttu-id="f614b-170">Office 365 licencias modernas comprobarán la asignación de licencia del usuario cada 72 horas y convertirán las aplicaciones Office a la versión que coincida con la suscripción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f614b-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="f614b-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f614b-171">Windows 10</span></span>

<span data-ttu-id="f614b-172">Si el Windows aún no está en la actualización Windows Pro Creator, actualíctelos [a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="f614b-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="f614b-173">Configurar directivas para proteger los archivos y dispositivos de usuario</span><span class="sxs-lookup"><span data-stu-id="f614b-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="f614b-174">Si configuras Office 365 y dispositivos MDM, estos dispositivos  aparecerán en la página Dispositivos del centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="f614b-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f614b-175">Las directivas que configures aparecerán en la lista de directivas clásicas en el [portal de Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="f614b-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="f614b-176">Después de asignar licencias a Microsoft 365 Empresa Premium, puede empezar a proteger los dispositivos y archivos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f614b-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="f614b-177">Si ha actualizado a todos los usuarios de la organización a Microsoft 365 Empresa Premium, verá el asistente para la instalación en la página Principal y puede seguir el procedimiento Configurar [Microsoft 365 Empresa Premium](set-up.md) en los pasos del Asistente para la instalación para proteger archivos y dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="f614b-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="f614b-178">También puedes completar estos pasos en la página Dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f614b-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="f614b-179">En el Centro de administración, en la navegación izquierda, vaya a **Directivas de** \> **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f614b-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="f614b-180">En la **página Directivas de dispositivo,** elija **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f614b-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="f614b-181">En el **panel Agregar directiva,** asigne un nombre a la directiva y, a continuación, elija un **tipo de directiva** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f614b-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="f614b-182">Puedes configurar directivas de aplicación para proteger archivos en dispositivos Android y iPhone, así como Windows 10, y puedes configurar directivas de configuración de dispositivos para dispositivos de Windows 10 empresa.</span><span class="sxs-lookup"><span data-stu-id="f614b-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="f614b-183">Vea los siguientes vínculos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="f614b-183">See the following links for details:</span></span>

  - [<span data-ttu-id="f614b-184">Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS</span><span class="sxs-lookup"><span data-stu-id="f614b-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="f614b-185">Establecer la configuración de protección de aplicaciones para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="f614b-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="f614b-186">Establecer la configuración de protección de dispositivos Windows 10 equipos</span><span class="sxs-lookup"><span data-stu-id="f614b-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="f614b-187">Una vez configuradas las directivas, tú y tus empleados pueden configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f614b-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="f614b-188">Consulta [Configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios para](set-up-windows-devices.md) ver los pasos para Windows dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f614b-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="f614b-189">Consulta [Configurar dispositivos móviles para Microsoft 365 Empresa Premium usuarios para](set-up-mobile-devices.md) ver los pasos para teléfonos Android y iPhones.</span><span class="sxs-lookup"><span data-stu-id="f614b-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="f614b-190">Tamaño del buzón</span><span class="sxs-lookup"><span data-stu-id="f614b-190">Mailbox Size</span></span>

<span data-ttu-id="f614b-191">Microsoft 365 Empresa Premium tiene un límite de almacenamiento de 50 GB, ya que usa Exchange Online plan 1.</span><span class="sxs-lookup"><span data-stu-id="f614b-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="f614b-192">Al migrar a Microsoft 365 Empresa Premium, si alguno de los usuarios supera los 50 GB de almacenamiento de buzones, se recomienda asignar a este usuario un plan Exchange Online 2 y quitar el plan 1 de Exchange Online, ya que no es factible asignar ambos.</span><span class="sxs-lookup"><span data-stu-id="f614b-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="f614b-193">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="f614b-193">Threat protection</span></span>

<span data-ttu-id="f614b-194">Después de migrar a Microsoft 365 Empresa Premium, tiene Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f614b-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="f614b-195">Consulta [Microsoft Defender para obtener Office 365](../security/office-365-security/defender-for-office-365.md) información general.</span><span class="sxs-lookup"><span data-stu-id="f614b-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="f614b-196">Para configurar, vea Configurar vínculos [Caja fuerte,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)configurar Caja fuerte [adjuntos](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)y configurar [anti phishing en Defender para Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="f614b-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="f614b-197">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f614b-197">Sensitivity labels</span></span>

<span data-ttu-id="f614b-198">Para empezar a usar etiquetas de confidencialidad, vea [Overview of sensitivity labels](../compliance/sensitivity-labels.md) y create and manage sensitivity [labels](../business-video/create-sensitivity-labels.md) video.</span><span class="sxs-lookup"><span data-stu-id="f614b-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="f614b-199">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="f614b-199">Related content</span></span>

<span data-ttu-id="f614b-200">[Cambiar planes manualmente](../commerce/subscriptions/change-plans-manually.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f614b-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="f614b-201">[Actualizar Windows dispositivos a Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="f614b-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="f614b-202">[Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](app-protection-settings-for-android-and-ios.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f614b-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="f614b-203">[Establecer o editar la configuración de protección de aplicaciones Windows 10 dispositivos](protection-settings-for-windows-10-devices.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="f614b-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="f614b-204">[]</span><span class="sxs-lookup"><span data-stu-id="f614b-204">[]</span></span>

