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
ms.openlocfilehash: efdf4030a2a638a3fd56d1c415fcc6e6ac261c1a
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772731"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-enterprise-e3"></a><span data-ttu-id="a9bcf-103">Migrar de Microsoft 365 empresa a Microsoft 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a9bcf-103">Migrate from Microsoft 365 Business to Microsoft 365 Enterprise E3</span></span>

<span data-ttu-id="a9bcf-104">Microsoft 365 Business tiene todo lo que necesita para su pequeña empresa, ya que combina las mejores aplicaciones de productividad basadas en la nube con la administración de dispositivos sencilla y la seguridad que les permite a sus empleados realizar el mejor trabajo posible.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="a9bcf-105">Sin embargo, en algunos casos, es posible que tenga que migrar su suscripción de Microsoft 365 empresa a Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="a9bcf-106">Por ejemplo, su empresa ha crecido y necesita más de 300 licencias (Enhorabuena, por cierto).</span><span class="sxs-lookup"><span data-stu-id="a9bcf-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="a9bcf-107">O bien, su empresa necesita características empresariales, como Office 365 ProPlus, Windows 10 Enterprise E3 o licencias de acceso de cliente (cal) de empresa.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="a9bcf-108">La migración es sencilla: solo cambiar licencias.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-108">Migrating is easy: Just switch licenses.</span></span> <span data-ttu-id="a9bcf-109">Se mantienen todos los datos y la configuración de la suscripción actual.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="a9bcf-110">No hay nada que hacer para prepararse para la migración ni para nada después, a menos que aproveche las ventajas de las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-110">There is nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="a9bcf-111">También puede usar una suscripción de Microsoft 365 empresa para un máximo de 300 puestos y obtener una suscripción a Microsoft 365 Enterprise E3 para más de 300 plazas.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 Enterprise E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="a9bcf-112">Sin embargo, Office 365 ATP no se incluye con Microsoft 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-112">However, Office 365 ATP is not included with Microsoft 365 Enterprise E3.</span></span> <span data-ttu-id="a9bcf-113">Debe agregar licencias de ATP de Office 365 adicionales para los usuarios de su suscripción a Microsoft 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-113">You should add additional Office 365 ATP licenses for the users in your Microsoft 365 Enterprise E3 subscription.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="a9bcf-114">Diferencias entre Microsoft 365 Business y Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9bcf-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="a9bcf-115">En esta tabla se muestran las diferencias entre Microsoft 365 Business y Microsoft 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 Enterprise E3.</span></span>

| <span data-ttu-id="a9bcf-116">Característica</span><span class="sxs-lookup"><span data-stu-id="a9bcf-116">Feature</span></span>   | <span data-ttu-id="a9bcf-117">Soporte en Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a9bcf-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="a9bcf-118">Soporte técnico de Microsoft 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a9bcf-118">Support in Microsoft 365 Enterprise E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="a9bcf-119">**Local**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="a9bcf-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9bcf-120">Windows 10</span></span>    | <span data-ttu-id="a9bcf-121">Windows 10 Empresa</span><span class="sxs-lookup"><span data-stu-id="a9bcf-121">Windows 10 Business</span></span>  |    <span data-ttu-id="a9bcf-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a9bcf-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="a9bcf-123">Aplicaciones de Office \*</span><span class="sxs-lookup"><span data-stu-id="a9bcf-123">Office apps\*</span></span>  | [<span data-ttu-id="a9bcf-124">Office 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="a9bcf-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="a9bcf-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="a9bcf-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="a9bcf-126">**Aplicaciones de productividad en la nube**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="a9bcf-127">Exchange Online y Outlook</span><span class="sxs-lookup"><span data-stu-id="a9bcf-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="a9bcf-128">límite de almacenamiento de 50 GB por buzón y archivado ilimitado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a9bcf-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="a9bcf-129">límite de almacenamiento de 100 GB por buzón y archivado ilimitado de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a9bcf-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="a9bcf-130">Teams</span><span class="sxs-lookup"><span data-stu-id="a9bcf-130">Teams</span></span> | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-133">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="a9bcf-133">OneDrive for Business</span></span> | <span data-ttu-id="a9bcf-134">límite de almacenamiento de 1 TB por usuario</span><span class="sxs-lookup"><span data-stu-id="a9bcf-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="a9bcf-135">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="a9bcf-135">Unlimited</span></span> | 
| <span data-ttu-id="a9bcf-136">Yammer, SharePoint Online, Planner, stream</span><span class="sxs-lookup"><span data-stu-id="a9bcf-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-139">StaffHub</span><span class="sxs-lookup"><span data-stu-id="a9bcf-139">StaffHub</span></span>  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-142">Administrador de clientes de Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="a9bcf-142">Outlook Customer Manager, MileIQ</span></span>  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | | 
| <span data-ttu-id="a9bcf-144">**Protección contra amenazas**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-144">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="a9bcf-145">Capacidades de reducción de superficie de ataques</span><span class="sxs-lookup"><span data-stu-id="a9bcf-145">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="a9bcf-146">Vea esta lista</span><span class="sxs-lookup"><span data-stu-id="a9bcf-146">See this list</span></span>](#threat-protection) | <span data-ttu-id="a9bcf-147">Administración empresarial del aislamiento basado en hardware para Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a9bcf-147">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="a9bcf-148">Plan 1 de protección avanzada contra amenazas (ATP) de Office 365</span><span class="sxs-lookup"><span data-stu-id="a9bcf-148">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Incluido en Microsoft 365 Business](./media/check-mark.png)  | <span data-ttu-id="a9bcf-150">No se incluye, pero puede agregarse en</span><span class="sxs-lookup"><span data-stu-id="a9bcf-150">Not included, but can be added on</span></span> | 
| <span data-ttu-id="a9bcf-151">**Administración de identidades**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-151">**Identity management**</span></span>       | | | 
| <span data-ttu-id="a9bcf-152">Restablecimiento de contraseña de autoservicio para cuentas híbridas de Azure Active Directory (Azure AD), Azure multi-factor Authentication (MFA), acceso condicional, escritura diferida de contraseñas para identidades locales</span><span class="sxs-lookup"><span data-stu-id="a9bcf-152">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-155">Detección de aplicaciones en la nube, Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="a9bcf-155">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-157">El inicio de sesión único (SSO) de las aplicaciones Office 365 de Azure AD: 10 aplicaciones por usuario (Galería de aplicaciones SaaS como Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="a9bcf-157">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-160">Azure AD Premium 1 SSO: sin límite (aplicaciones locales a través de proxy de aplicación de Azure AD y aplicaciones que no son de galería con plantillas de integración de aplicaciones de autoservicio)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-160">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-162">**Administración de dispositivos y aplicaciones**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-162">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="a9bcf-163">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="a9bcf-163">Microsoft Intune, Windows Autopilot</span></span>|  ![Incluido en Microsoft 365 Business](./media/check-mark.png) | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|<span data-ttu-id="a9bcf-166">Acceso de escritorio virtual (VDA)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-166">Virtual Desktop Access (VDA)</span></span>   |  |    ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|<span data-ttu-id="a9bcf-168">Escritorio virtual de Windows (WVD)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-168">Windows Virtual Desktop (WVD)</span></span>  | ![Incluido en Microsoft 365 Business](./media/check-mark.png) |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
|<span data-ttu-id="a9bcf-171">Activación en equipos compartidos (SCA)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-171">Shared Computer Activation (SCA)</span></span>   | ![Incluido en Microsoft 365 Business](./media/check-mark.png) |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-174">Paquete de optimización del escritorio de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9bcf-174">Microsoft Desktop Optimization Package</span></span>    | |     ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-176">**Protección de la información**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-176">**Information protection**</span></span>        | | | 
| <span data-ttu-id="a9bcf-177">Prevención de pérdida de datos de Office 365, plan 1 de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="a9bcf-177">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-180">Protección de la información de ventanas para DLP de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a9bcf-180">Window Information Protection for endpoint DLP</span></span>    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-183">**Licencia de acceso de cliente (derechos de CAL)**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-183">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="a9bcf-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-184">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, System Center Configuration Manager, Windows Rights Management)</span></span>| |        ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-186">**Cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="a9bcf-186">**Compliance**</span></span>        | | | 
| <span data-ttu-id="a9bcf-187">Archivado de correo electrónico ilimitado</span><span class="sxs-lookup"><span data-stu-id="a9bcf-187">Unlimited email archiving</span></span> | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-190">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a9bcf-190">Compliance Manager</span></span>    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-193">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a9bcf-193">eDiscovery</span></span>    | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-196">Conservación local y retención por juicio</span><span class="sxs-lookup"><span data-stu-id="a9bcf-196">In-place hold and litigation hold</span></span> | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
| <span data-ttu-id="a9bcf-199">Etiquetas de retención y directivas de retención de administración de registros de mensajería (MRM)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-199">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Incluido en Microsoft 365 Business](./media/check-mark.png)   | ![Incluido en Microsoft 365 Enterprise E3](./media/check-mark.png) | 
||||

<span data-ttu-id="a9bcf-202">\*Los usuarios a los que se les asignó acceso a las aplicaciones de SaaS pueden obtener acceso SSO a un máximo de 10 aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-202">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="a9bcf-203">Los administradores pueden configurar el SSO y cambiar el acceso del usuario a distintas aplicaciones de SaaS, pero el acceso SSO solo se permite para 10 aplicaciones por usuario a la vez.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-203">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="a9bcf-204">Todas las aplicaciones de Office 365 se cuentan como una aplicación única.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-204">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="a9bcf-205">Migración</span><span class="sxs-lookup"><span data-stu-id="a9bcf-205">Migration</span></span>

<span data-ttu-id="a9bcf-206">Para migrar, trabaje con su partner para transferir su suscripción y licencias de Microsoft 365 Business a una suscripción a Microsoft 365 Enterprise E3 adecuada con sus licencias.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-206">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to suitable a Microsoft 365 Enterprise E3 subscription with its licenses.</span></span>

<span data-ttu-id="a9bcf-207">En las secciones siguientes se describen los cambios que debe realizar, si los hay, y qué puede hacer después de la migración.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-207">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="a9bcf-208">Datos y configuración de suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9bcf-208">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="a9bcf-209">No es necesario realizar ningún cambio en la suscripción o los datos actuales antes de la migración, lo que incluye:</span><span class="sxs-lookup"><span data-stu-id="a9bcf-209">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="a9bcf-210">Configuración de la suscripción, como los nombres de dominio DNS.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-210">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="a9bcf-211">Configuración de autenticación y cuentas de usuario y de grupo, como la autenticación multifactor o las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-211">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="a9bcf-212">Las configuraciones del servicio de productividad y sus datos, como Teams, buzones de correo de Exchange Online, sitios de SharePoint Online, carpetas de OneDrive para la empresa y blocs de notas de OneNote.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-212">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="a9bcf-213">Los usuarios ahora pueden disfrutar de un almacenamiento ilimitado en las carpetas de buzones de Exchange Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-213">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="a9bcf-214">Puede empezar a usar Cloud App Discovery, Azure AD Connect Health y SSO para más de 10 aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-214">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="a9bcf-215">Después de migrar a Microsoft 365 Enterprise E3, ya no es administrador de clientes de Outlook y MileIQ.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-215">After migrating to Microsoft 365 Enterprise E3, you no longer Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="a9bcf-216">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="a9bcf-216">Threat protection</span></span>

<span data-ttu-id="a9bcf-217">Windows 10 Business incluye estas protecciones:</span><span class="sxs-lookup"><span data-stu-id="a9bcf-217">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="a9bcf-218">Aplicación de integridad del proceso de inicio del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a9bcf-218">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="a9bcf-219">Aplicación de integridad de componentes operativos confidenciales</span><span class="sxs-lookup"><span data-stu-id="a9bcf-219">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="a9bcf-220">Vulnerabilidades avanzadas y mitigaciones de ataques de día cero</span><span class="sxs-lookup"><span data-stu-id="a9bcf-220">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="a9bcf-221">Protección de red basada en la reputación para Microsoft Edge, Internet Explorer y Chrome</span><span class="sxs-lookup"><span data-stu-id="a9bcf-221">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="a9bcf-222">Firewall basado en host</span><span class="sxs-lookup"><span data-stu-id="a9bcf-222">Host-based firewall</span></span>
- <span data-ttu-id="a9bcf-223">Mitigaciones de ransomware</span><span class="sxs-lookup"><span data-stu-id="a9bcf-223">Ransomware mitigations</span></span>
- <span data-ttu-id="a9bcf-224">Aislamiento basado en hardware para Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a9bcf-224">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="a9bcf-225">Control de aplicaciones basado en el gráfico de seguridad inteligente</span><span class="sxs-lookup"><span data-stu-id="a9bcf-225">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="a9bcf-226">Control de dispositivo (USB)</span><span class="sxs-lookup"><span data-stu-id="a9bcf-226">Device control (USB)</span></span>
- <span data-ttu-id="a9bcf-227">Protección de red para amenazas basadas en la web</span><span class="sxs-lookup"><span data-stu-id="a9bcf-227">Network protection for web-based threats</span></span>
- <span data-ttu-id="a9bcf-228">Reglas de Host Intrusion Prevention</span><span class="sxs-lookup"><span data-stu-id="a9bcf-228">Host intrusion prevention rules</span></span>

<span data-ttu-id="a9bcf-229">Windows 10 Enterprise E3 también incluye administración empresarial del aislamiento basado en hardware para Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-229">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="a9bcf-230">Después de realizar la migración a Microsoft 365 Enterprise E3, ya no tiene Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-230">After migrating to Microsoft 365 Enterprise E3, you no longer have Office 365 ATP.</span></span> <span data-ttu-id="a9bcf-231">Puede comprar licencias de ATP de Office 365 adicionales para su suscripción a Microsoft 365 Enterprise E3 y asignarlas a sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-231">You can purchase additional Office 365 ATP licenses for your Microsoft 365 Enterprise E3 subscription and assign them to your user accounts.</span></span>
>

### <a name="device-management-with-intune"></a><span data-ttu-id="a9bcf-232">Administración de dispositivos con Intune</span><span class="sxs-lookup"><span data-stu-id="a9bcf-232">Device management with Intune</span></span>

<span data-ttu-id="a9bcf-233">No es necesario realizar ningún cambio en la configuración actual de Intune antes de la migración, lo que incluye los dispositivos inscritos y la configuración de dispositivos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-233">You don’t need to do any changes to your current Intune configuration prior to migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="a9bcf-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9bcf-234">Windows 10</span></span>

<span data-ttu-id="a9bcf-235">Microsoft 365 Business incluye Windows 10 Business, que puede instalar con Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-235">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows Autopilot.</span></span> <span data-ttu-id="a9bcf-236">Al migrar a Microsoft 365 Enterprise E3, cada licencia de usuario incluye Windows 10 Enterprise E3, que también puede instalar con Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-236">When you migrate to Microsoft 365 Enterprise E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="a9bcf-237">Office 365 Empresa</span><span class="sxs-lookup"><span data-stu-id="a9bcf-237">Office 365 Business</span></span>

<span data-ttu-id="a9bcf-238">El cliente de Office 365 empresa instalado en los dispositivos comenzará a usar automáticamente las características de Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="a9bcf-238">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="a9bcf-239">Después de la migración, ahora puede usar:</span><span class="sxs-lookup"><span data-stu-id="a9bcf-239">After migration, you can now use:</span></span>

 - <span data-ttu-id="a9bcf-240">Activación por volumen mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="a9bcf-240">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="a9bcf-241">Telemetría de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a9bcf-241">App telemetry</span></span>
 - <span data-ttu-id="a9bcf-242">Controles de actualización</span><span class="sxs-lookup"><span data-stu-id="a9bcf-242">Update controls</span></span>
 - <span data-ttu-id="a9bcf-243">Comparación de hojas de cálculo y consulta</span><span class="sxs-lookup"><span data-stu-id="a9bcf-243">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="a9bcf-244">Inteligencia empresarial</span><span class="sxs-lookup"><span data-stu-id="a9bcf-244">Business intelligence</span></span>

