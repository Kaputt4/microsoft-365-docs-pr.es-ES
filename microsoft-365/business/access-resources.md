---
title: Obtener acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Obtén información sobre cómo obtener acceso a recursos locales como aplicaciones de línea de negocio, recursos compartidos de archivos e impresoras desde Azure Active Directory dispositivo Windows 10 usuario.
ms.openlocfilehash: 71d60e0187c917dffb7390afcedf22dc73f44008
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393467"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="0846d-103">Obtenga acceso a recursos locales desde un dispositivo unido a Azure AD en Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="0846d-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="0846d-104">Este artículo se aplica a Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="0846d-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0846d-105">Cualquier Windows 10 que esté unido Azure Active Directory tiene acceso a todos los recursos basados en la nube, como las aplicaciones de Microsoft 365, y puede protegerse mediante Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="0846d-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="0846d-106">También puedes permitir el acceso a recursos locales como aplicaciones de línea de negocio (LOB), recursos compartidos de archivos e impresoras.</span><span class="sxs-lookup"><span data-stu-id="0846d-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="0846d-107">Para permitir el acceso, use [Azure AD Conectar](/azure/active-directory/connect/active-directory-aadconnect) para sincronizar su Active Directory local con Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0846d-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span>

<span data-ttu-id="0846d-108">Para obtener más información, consulta [Introducción a la administración de dispositivos en Azure Active Directory](/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="0846d-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="0846d-109">Los pasos también se resumen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0846d-109">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="0846d-110">Ejecutar Azure AD Conectar</span><span class="sxs-lookup"><span data-stu-id="0846d-110">Run Azure AD Connect</span></span>

<span data-ttu-id="0846d-111">Siga estos pasos para permitir que los dispositivos unidos a Azure AD de la organización puedan tener acceso a los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="0846d-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>

1. <span data-ttu-id="0846d-112">Para sincronizar los usuarios, grupos y contactos de Active Directory local en Azure Active Directory, ejecute el Asistente para sincronización de directorios y Azure AD Conectar como se describe en Configurar la sincronización de directorios [para Office 365](../enterprise/set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="0846d-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>

2. <span data-ttu-id="0846d-113">Una vez completada la sincronización de directorios, asegúrese de que los dispositivos Windows 10 de la organización estén unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0846d-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="0846d-114">Este paso se realiza individualmente en cada Windows 10 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0846d-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="0846d-115">Consulta [Configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios para obtener](set-up-windows-devices.md) más información.</span><span class="sxs-lookup"><span data-stu-id="0846d-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span>

3. <span data-ttu-id="0846d-116">Una vez que los Windows 10 están unidos a Azure AD, cada usuario debe reiniciar sus dispositivos e iniciar sesión con sus Microsoft 365 Empresa Premium usuario.</span><span class="sxs-lookup"><span data-stu-id="0846d-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="0846d-117">Todos los dispositivos ahora también tienen acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="0846d-117">All devices now have access to on-premises resources as well.</span></span>

<span data-ttu-id="0846d-118">No se requieren pasos adicionales para obtener acceso a recursos locales para dispositivos unidos a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0846d-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="0846d-119">Esta funcionalidad está integrada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0846d-119">This functionality is built into Windows 10.</span></span>

<span data-ttu-id="0846d-120">Si tiene planes de iniciar sesión en el dispositivo AADJ que no sea el método de contraseña Like PIN/Bio-metric a través del inicio de sesión de credenciales WHFB y, a continuación, acceder a recursos locales (recursos compartidos, impresoras, etc.), siga este artículo [.](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)</span><span class="sxs-lookup"><span data-stu-id="0846d-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares, printers, etc.), please follow [this article](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base).</span></span>

<span data-ttu-id="0846d-121">Si su organización no está lista para implementar en la configuración de dispositivo unido a Azure AD descrita anteriormente, considere la posibilidad de configurar la configuración de dispositivo unido a [Azure AD híbrido.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="0846d-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>

### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="0846d-122">Consideraciones al unirse Windows dispositivos a Azure AD</span><span class="sxs-lookup"><span data-stu-id="0846d-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="0846d-123">Si el Windows al que se unió Azure-AD estaba previamente unido a un dominio o en un grupo de trabajo, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="0846d-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>

- <span data-ttu-id="0846d-124">Cuando un dispositivo se une a Azure AD, crea un nuevo usuario sin hacer referencia a un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="0846d-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="0846d-125">Los perfiles deben migrarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="0846d-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="0846d-126">Un perfil de usuario contiene información como favoritos, archivos locales, configuración del explorador y menú Inicio configuración.</span><span class="sxs-lookup"><span data-stu-id="0846d-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="0846d-127">El mejor enfoque es buscar una herramienta de terceros para asignar los archivos y la configuración existentes al nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="0846d-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="0846d-128">Si el dispositivo usa objetos de directiva de grupo (GPO), es posible que algunos GPO no tengan un [proveedor](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) de servicios de configuración (CSP) comparable en Intune.</span><span class="sxs-lookup"><span data-stu-id="0846d-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="0846d-129">Ejecute la [herramienta MMAT para](https://www.microsoft.com/download/details.aspx?id=45520) buscar LOSP comparables para los GPO existentes.</span><span class="sxs-lookup"><span data-stu-id="0846d-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="0846d-130">Es posible que los usuarios no puedan autenticarse en aplicaciones que dependen de la autenticación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0846d-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="0846d-131">Evalúa la aplicación heredada y considera la posibilidad de actualizar a una aplicación que usa Auth moderno, si es posible.</span><span class="sxs-lookup"><span data-stu-id="0846d-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="0846d-132">La detección de impresoras de Active Directory no funcionará.</span><span class="sxs-lookup"><span data-stu-id="0846d-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="0846d-133">Puede proporcionar rutas de impresora directas para todos los usuarios o usar [impresión universal](/universal-print/).</span><span class="sxs-lookup"><span data-stu-id="0846d-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>

### <a name="related-articles"></a><span data-ttu-id="0846d-134">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="0846d-134">Related Articles</span></span>

[<span data-ttu-id="0846d-135">Requisitos previos para Azure AD Conectar</span><span class="sxs-lookup"><span data-stu-id="0846d-135">Prerequisites for Azure AD Connect</span></span>](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
