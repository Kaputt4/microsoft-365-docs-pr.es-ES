---
title: Acceder a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa
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
description: Aprende a obtener acceso a recursos locales como aplicaciones de línea de negocio, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 unido a Azure Active Directory.
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688241"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="a56a8-103">Acceder a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="a56a8-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="a56a8-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="a56a8-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a56a8-105">Cualquier dispositivo con Windows 10 unido a Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede estar protegido por Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="a56a8-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="a56a8-106">También puede permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras.</span><span class="sxs-lookup"><span data-stu-id="a56a8-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="a56a8-107">Para permitir el acceso, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a56a8-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="a56a8-108">Para obtener más información, consulte [Introducción a la administración de dispositivos en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="a56a8-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="a56a8-109">Los pasos también se resumen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="a56a8-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="a56a8-110">Ejecutar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="a56a8-110">Run Azure AD Connect</span></span>

<span data-ttu-id="a56a8-111">Complete los siguientes pasos para permitir que los dispositivos unidos a Azure AD de su organización accedan a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="a56a8-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="a56a8-112">Para sincronizar los usuarios, grupos y contactos de Active Directory local con Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect, como se describe en Configurar la sincronización de directorios para [Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="a56a8-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="a56a8-113">Una vez completada la sincronización de directorios, asegúrate de que los dispositivos windows 10 de tu organización estén unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a56a8-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="a56a8-114">Este paso se realiza individualmente en cada dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a56a8-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="a56a8-115">Consulte [Configurar dispositivos Windows para usuarios de Microsoft 365 Empresa Premium](set-up-windows-devices.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a56a8-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="a56a8-116">Una vez que los dispositivos Windows 10 están unidos a Azure AD, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="a56a8-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="a56a8-117">Ahora, todos los dispositivos también tienen acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="a56a8-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="a56a8-118">No se requieren pasos adicionales para obtener acceso a recursos locales para dispositivos unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a56a8-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="a56a8-119">Esta funcionalidad está integrada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a56a8-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="a56a8-120">Si tienes previsto iniciar sesión en el dispositivo AADJ que no sea el método de contraseña, como PIN/Biométrica a través del inicio de sesión de credenciales WHFB y luego acceder a recursos locales (recursos compartidos, impresoras). etc.), siga https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="a56a8-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="a56a8-121">Si su organización no está lista para implementar en la configuración de dispositivo unido a Azure AD descrita anteriormente, considere la posibilidad de configurar la configuración híbrida de dispositivos unidos [a Azure AD.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="a56a8-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="a56a8-122">Consideraciones al unir dispositivos Windows a Azure AD</span><span class="sxs-lookup"><span data-stu-id="a56a8-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="a56a8-123">Si el dispositivo Windows al que te uniste a Azure-AD estaba previamente unido a un dominio o a un grupo de trabajo, ten en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="a56a8-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="a56a8-124">Cuando un dispositivo se une a Azure AD, crea un nuevo usuario sin hacer referencia a un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="a56a8-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="a56a8-125">Los perfiles deben migrarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="a56a8-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="a56a8-126">Un perfil de usuario contiene información como favoritos, archivos locales, configuración del explorador y configuración del menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="a56a8-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="a56a8-127">Un mejor enfoque es buscar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="a56a8-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="a56a8-128">Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un proveedor de servicios de configuración [(CSP)](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparable en Intune.</span><span class="sxs-lookup"><span data-stu-id="a56a8-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="a56a8-129">Ejecute la [herramienta MMAT para](https://www.microsoft.com/download/details.aspx?id=45520) buscar CSP comparables para GPO existentes.</span><span class="sxs-lookup"><span data-stu-id="a56a8-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="a56a8-130">Los usuarios no podrán autenticarse en aplicaciones que dependen de la autenticación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a56a8-130">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="a56a8-131">Evalúa la aplicación heredada y considera la posibilidad de actualizar a una aplicación que use la autenticación moderna, si es posible.</span><span class="sxs-lookup"><span data-stu-id="a56a8-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="a56a8-132">La detección de impresoras de Active Directory no funcionará.</span><span class="sxs-lookup"><span data-stu-id="a56a8-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="a56a8-133">Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión universal.](https://aka.ms/UPDocs)</span><span class="sxs-lookup"><span data-stu-id="a56a8-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
