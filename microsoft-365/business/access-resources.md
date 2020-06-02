---
title: Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Obtenga información sobre cómo obtener acceso a recursos locales como líneas de aplicaciones empresariales, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 conectado a Azure Active Directory.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471259"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="19c35-103">Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 empresa Premium</span><span class="sxs-lookup"><span data-stu-id="19c35-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="19c35-104">Este artículo se aplica a Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="19c35-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="19c35-105">Cualquier dispositivo de Windows 10 que se haya unido a Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede ser protegido por Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="19c35-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="19c35-106">También puede permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras.</span><span class="sxs-lookup"><span data-stu-id="19c35-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="19c35-107">Para permitir el acceso, use [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19c35-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="19c35-108">Para obtener más información, consulte [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="19c35-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="19c35-109">Los pasos también se resumen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="19c35-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19c35-110">Este procedimiento solo es aplicable a OAuth y NTLM.</span><span class="sxs-lookup"><span data-stu-id="19c35-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="19c35-111">Kerberos no es compatible.</span><span class="sxs-lookup"><span data-stu-id="19c35-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="19c35-112">Ejecutar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="19c35-112">Run Azure AD Connect</span></span>

<span data-ttu-id="19c35-113">Complete los siguientes pasos para habilitar los dispositivos de Azure AD Unidos de su organización para que tengan acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="19c35-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="19c35-114">Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect como se describe en [configurar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="19c35-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="19c35-115">Una vez completada la sincronización de directorios, asegúrese de que los dispositivos Windows 10 de su organización están Unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19c35-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="19c35-116">Este paso se realiza de forma individual en cada dispositivo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="19c35-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="19c35-117">Para obtener más información, consulte [configurar dispositivos Windows para los usuarios de Microsoft 365 empresa Premium](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="19c35-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="19c35-118">Una vez que se unen los dispositivos de Windows 10, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="19c35-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="19c35-119">Todos los dispositivos ahora también tienen acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="19c35-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="19c35-120">No se necesitan pasos adicionales para obtener acceso a los recursos locales de los dispositivos Unidos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19c35-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="19c35-121">Esta funcionalidad está integrada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="19c35-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="19c35-122">Si tiene previsto iniciar sesión en el dispositivo AADJ que no sea el método de contraseña como PIN/bio-Metric mediante credenciales WHFB y, a continuación, obtener acceso a recursos locales (recursos compartidos, impresoras.. etc.), sigahttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="19c35-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="19c35-123">Si su organización no está lista para implementarla en la configuración de dispositivos Unidos a Azure AD descrita anteriormente, considere la posibilidad de configurar una [configuración de dispositivo de Unión híbrida de Azure ad](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="19c35-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="19c35-124">Consideraciones a la hora de unir dispositivos Windows a Azure AD</span><span class="sxs-lookup"><span data-stu-id="19c35-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="19c35-125">Si el dispositivo de Windows al que se unió Azure-AD se unió anteriormente a un dominio o en un grupo de trabajo, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="19c35-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="19c35-126">Cuando se une un dispositivo de Azure AD, se crea un nuevo usuario sin hacer referencia a un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="19c35-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="19c35-127">Los perfiles deben migrarse de forma manual.</span><span class="sxs-lookup"><span data-stu-id="19c35-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="19c35-128">Un perfil de usuario contiene información como los favoritos, los archivos locales, la configuración del explorador y la configuración del menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="19c35-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="19c35-129">Un mejor enfoque es encontrar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="19c35-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="19c35-130">Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor de servicios de configuración](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) comparable en Intune.</span><span class="sxs-lookup"><span data-stu-id="19c35-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="19c35-131">Ejecute la [herramienta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para buscar CSP comparables para los GPO existentes.</span><span class="sxs-lookup"><span data-stu-id="19c35-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="19c35-132">Los usuarios no podrán autenticarse en las aplicaciones que dependen de la autenticación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="19c35-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="19c35-133">Evalúe la aplicación heredada y considere la posibilidad de actualizarla a una aplicación que use la autenticación moderna, si es posible.</span><span class="sxs-lookup"><span data-stu-id="19c35-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="19c35-134">La detección de impresoras de Active Directory no funcionará.</span><span class="sxs-lookup"><span data-stu-id="19c35-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="19c35-135">Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión de nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="19c35-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
