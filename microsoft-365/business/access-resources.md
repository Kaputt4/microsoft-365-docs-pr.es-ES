---
title: Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Obtenga información sobre cómo obtener acceso a recursos locales como líneas de aplicaciones empresariales, recursos compartidos de archivos e impresoras desde un dispositivo Windows 10 conectado a Azure Active Directory.
ms.openlocfilehash: 92e8ccb99dfece7687c25db84b81fc7bc7158d71
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574686"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="65a94-103">Acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="65a94-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="65a94-104">Cualquier dispositivo de Windows 10 que se haya unido a Azure Active Directory tendrá acceso a todos los recursos basados en la nube, como las aplicaciones de Office 365 y puede ser protegido por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="65a94-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="65a94-105">Para permitir también el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras, debe sincronizar su Active Directory local con Azure Active Directory mediante [Azure ad Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="65a94-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> 

<span data-ttu-id="65a94-106">Consulte [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="65a94-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="65a94-107">Los pasos también se resumen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="65a94-107">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="65a94-108">Ejecutar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="65a94-108">Run Azure AD Connect</span></span>

<span data-ttu-id="65a94-109">Complete los siguientes pasos para habilitar los dispositivos de Azure AD Unidos de su organización para que tengan acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="65a94-109">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="65a94-110">Para sincronizar los usuarios, los grupos y los contactos de Active Directory local a Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Connect como se describe en [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="65a94-110">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="65a94-111">Una vez completada la sincronización de directorios, asegúrese de que los dispositivos Windows 10 de su organización están Unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65a94-111">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="65a94-112">Este paso se realiza de forma individual en cada dispositivo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="65a94-112">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="65a94-113">Consulte [configurar dispositivos Windows para usuarios de Microsoft 365 Business](set-up-windows-devices.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="65a94-113">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="65a94-114">Una vez que se unen los dispositivos Windows 10, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus credenciales de Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="65a94-114">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="65a94-115">Todos los dispositivos ahora tendrán acceso también a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="65a94-115">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="65a94-116">No se necesitan pasos adicionales para obtener acceso a los recursos locales de los dispositivos Unidos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="65a94-116">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="65a94-117">Esta es la funcionalidad integrada disponible en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="65a94-117">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="65a94-118">Si su organización no está lista para implementarse en la configuración de dispositivos Unidos a Azure AD descrita anteriormente, considere la posibilidad de configurar una [configuración de dispositivo de Unión híbrida de Azure ad](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="65a94-118">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="65a94-119">Consideraciones al unir los dispositivos Windows a Azure AD</span><span class="sxs-lookup"><span data-stu-id="65a94-119">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="65a94-120">Si Azure AD se une a un dispositivo de Windows que anteriormente se unió a un dominio o está en un grupo de trabajo, debe tener en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="65a94-120">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="65a94-121">Cuando se une un dispositivo de Azure AD, se crea un nuevo usuario sin hacer referencia a un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="65a94-121">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="65a94-122">Para solucionarlo, los perfiles deben migrarse de forma manual.</span><span class="sxs-lookup"><span data-stu-id="65a94-122">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="65a94-123">Un perfil de usuario contiene información como los favoritos, los archivos locales, la configuración del explorador, la configuración del menú Inicio, etc. Un enfoque mejor es encontrar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil</span><span class="sxs-lookup"><span data-stu-id="65a94-123">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="65a94-124">Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor de servicios de configuración](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) comparable en Intune.</span><span class="sxs-lookup"><span data-stu-id="65a94-124">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="65a94-125">Ejecute la [herramienta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para buscar CSP comparables para los GPO existentes.</span><span class="sxs-lookup"><span data-stu-id="65a94-125">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="65a94-126">Los usuarios no podrán autenticarse en las aplicaciones que dependen de la autenticación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="65a94-126">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="65a94-127">Para solucionar este error, evalúe usando una aplicación heredada y considere la posibilidad de actualizar a una aplicación que use la autenticación moderna, si es posible.</span><span class="sxs-lookup"><span data-stu-id="65a94-127">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="65a94-128">La detección de impresoras de Active Directory no funcionará.</span><span class="sxs-lookup"><span data-stu-id="65a94-128">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="65a94-129">Para solucionarlo, proporcione rutas de impresora directas para todos los usuarios o aproveche [la impresión de nube híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="65a94-129">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
