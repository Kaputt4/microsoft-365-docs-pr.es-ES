---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business
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
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos Windows 10 locales Unidos a directorio activo en tan solo unos pocos pasos.
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550255"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="99964-103">Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="99964-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="99964-104">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business para proteger sus dispositivos con Windows 10 y mantener al mismo tiempo el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="99964-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="99964-105">Para configurar esta protección, puede implementar dispositivos de **Azure ad Unidos híbridos**.</span><span class="sxs-lookup"><span data-stu-id="99964-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="99964-106">Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99964-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="99964-107">Este vídeo describe los pasos para configurar esta configuración para el escenario más común, que también se detalla en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="99964-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="99964-108">1. preparar la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="99964-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="99964-109">Antes de sincronizar los usuarios y los equipos desde el dominio local de Active Directory, revise [preparar la sincronización de directorios en Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="99964-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="99964-110">En particular:</span><span class="sxs-lookup"><span data-stu-id="99964-110">In particular:</span></span>

   - <span data-ttu-id="99964-111">Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses**y **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="99964-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="99964-112">Estos valores deben ser únicos y se deben quitar todos los duplicados.</span><span class="sxs-lookup"><span data-stu-id="99964-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="99964-113">Le recomendamos que configure el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local de manera que coincida con la dirección de correo electrónico principal que corresponda al usuario con licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99964-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="99964-114">Por ejemplo: *Mary.Shelley@contoso.com* en lugar de *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="99964-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="99964-115">Si el dominio de Active Directory termina en un sufijo no enrutable como *. local* o *. LAN*, en lugar de un sufijo enrutable de Internet como *. com* o *. org*, ajuste primero el sufijo UPN de las cuentas de usuario locales como se describe en [preparar un dominio no enrutable para la sincronización de directorios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="99964-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="99964-116">2. instalar y configurar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="99964-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="99964-117">Para sincronizar los usuarios, los grupos y los contactos de Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="99964-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="99964-118">Consulte [configurar la sincronización de directorios para Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="99964-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="99964-119">Los pasos son exactamente iguales para Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="99964-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="99964-120">A medida que configure las opciones de Azure AD Connect, le recomendamos que habilite la **sincronización de contraseña**, el **Inicio de sesión único sin problemas**y la característica de **escritura diferida de contraseñas** , que también se admite en Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="99964-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="99964-121">Hay algunos pasos adicionales para la escritura diferida de contraseñas más allá de la casilla en Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="99964-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="99964-122">Para obtener más información, consulte [How-to: configure password reescritura](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="99964-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="99964-123">3. configurar una Unión híbrida de Azure AD</span><span class="sxs-lookup"><span data-stu-id="99964-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="99964-124">Antes de habilitar los dispositivos Windows 10 para que sean Unidos a Azure AD híbrido, asegúrese de que cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="99964-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="99964-125">Está ejecutando la última versión de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="99964-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="99964-126">Azure AD Connect ha sincronizado todos los objetos de equipo de los dispositivos que desea que sean Unidos a Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="99964-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="99964-127">Si los objetos de equipo pertenecen a unidades organizativas específicas (OU), asegúrese de que estas ou estén configuradas para la sincronización en Azure AD Connect también.</span><span class="sxs-lookup"><span data-stu-id="99964-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="99964-128">Para registrar los dispositivos existentes de Windows 10 Unidos a un dominio como Unidos de híbrido de Azure AD, siga los pasos descritos en el [Tutorial: configure Hybrid Azure Active Directory join for Managed Domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="99964-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="99964-129">Este entorno híbrido: habilita sus equipos locales de Active Directory Unidos a los equipos con Windows 10 y los pone a disposición en la nube.</span><span class="sxs-lookup"><span data-stu-id="99964-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="99964-130">4. habilitar la inscripción automática para Windows 10</span><span class="sxs-lookup"><span data-stu-id="99964-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="99964-131">Para inscribir automáticamente dispositivos Windows 10 para la administración de dispositivos móviles en Intune, consulte [inscribir automáticamente un dispositivo con Windows 10 mediante la Directiva de grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span><span class="sxs-lookup"><span data-stu-id="99964-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="99964-132">Puede establecer la Directiva de grupo en el nivel de un equipo local o en operaciones masivas, puede usar la consola de administración de directivas de grupo y las plantillas ADMX para crear esta opción de directiva de grupo en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="99964-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="99964-133">5. configurar el inicio de sesión único sin interrupciones</span><span class="sxs-lookup"><span data-stu-id="99964-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="99964-134">El SSO sin problemas firma automáticamente a los usuarios en los recursos de nube de Microsoft 365 cuando usan equipos corporativos.</span><span class="sxs-lookup"><span data-stu-id="99964-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="99964-135">Simplemente, implemente una de las dos opciones de directiva de grupo descritas en [Azure Active Directory de inicio de sesión único: Inicio rápido](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span><span class="sxs-lookup"><span data-stu-id="99964-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="99964-136">La opción de **Directiva de grupo** no permite a los usuarios cambiar su configuración, mientras que la opción de preferencia de la **Directiva de grupo** establece los valores, pero también les permite configurar el usuario.</span><span class="sxs-lookup"><span data-stu-id="99964-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="99964-137">6. configurar Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="99964-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="99964-138">Windows Hello para empresas reemplaza contraseñas con la autenticación segura en dos fases (2FA) para iniciar sesión en un equipo local.</span><span class="sxs-lookup"><span data-stu-id="99964-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="99964-139">Un factor es un par de claves asimétricas y el otro es un PIN u otro movimiento local, como el reconocimiento facial o de la huella digital, si el dispositivo lo admite.</span><span class="sxs-lookup"><span data-stu-id="99964-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="99964-140">Le recomendamos que reemplace las contraseñas con 2FA y Windows Hello para empresas siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="99964-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="99964-141">Para configurar la implementación híbrida de Windows Hello para empresas, revise los [requisitos previos de confianza de clave híbrida de Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span><span class="sxs-lookup"><span data-stu-id="99964-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="99964-142">A continuación, siga las instrucciones que se indican en [Configure Hybrid Windows Hello for Business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span><span class="sxs-lookup"><span data-stu-id="99964-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
