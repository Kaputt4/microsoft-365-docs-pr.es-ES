---
title: Sincronizar usuarios del dominio con Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronice los usuarios controlados por dominio con Microsoft 365 para empresas.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306457"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="94da2-103">Sincronizar usuarios del dominio con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94da2-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="94da2-104">1. preparar la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="94da2-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="94da2-105">Antes de sincronizar los usuarios y los equipos desde el dominio local de Active Directory, consulte [preparar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="94da2-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="94da2-106">En particular:</span><span class="sxs-lookup"><span data-stu-id="94da2-106">In particular:</span></span>

   - <span data-ttu-id="94da2-107">Asegúrese de que no existen duplicados en el directorio para los siguientes atributos: **mail**, **proxyAddresses**y **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="94da2-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="94da2-108">Estos valores deben ser únicos y se deben quitar todos los duplicados.</span><span class="sxs-lookup"><span data-stu-id="94da2-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="94da2-109">Le recomendamos que configure el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local de manera que coincida con la dirección de correo electrónico principal que corresponda al usuario con licencia de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94da2-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="94da2-110">Por ejemplo: *Mary.Shelley@contoso.com* en lugar de *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="94da2-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="94da2-111">Si el dominio de Active Directory termina en un sufijo no enrutable como *. local* o *. LAN*, en lugar de un sufijo enrutable de Internet como *. com* o *. org*, ajuste primero el sufijo UPN de las cuentas de usuario locales como se describe en [preparar un dominio no enrutable para la sincronización de directorios](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="94da2-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="94da2-112">La **ejecución de IdFix** en el paso cuatro (4) que se muestra a continuación, también asegurará que su Active Directory local esté preparado para la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="94da2-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="94da2-113">2. instalar y configurar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="94da2-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="94da2-114">Para sincronizar los usuarios, los grupos y los contactos de Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="94da2-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="94da2-115">En el centro de administración de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Seleccione **configuración** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="94da2-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="94da2-116">En **Inicio de sesión y seguridad**, elija **Ver**  en **sincronizar usuarios en el directorio de su organización**.</span><span class="sxs-lookup"><span data-stu-id="94da2-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="94da2-117">En la página **sincronizar usuarios desde el directorio de su organización** **, elija introducción**.</span><span class="sxs-lookup"><span data-stu-id="94da2-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="94da2-118">En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="94da2-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="94da2-119">Siga los pasos del Asistente para descargar Azure AD Connect y usarlo para sincronizar los usuarios controlados por dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94da2-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="94da2-120">Consulte [configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="94da2-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="94da2-121">A medida que configure las opciones de Azure AD Connect, le recomendamos que habilite la **sincronización de contraseña**, el **Inicio de sesión único sin problemas**y la característica de **escritura diferida de contraseñas** , que también se admite en Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="94da2-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="94da2-122">Hay algunos pasos adicionales para la escritura diferida de contraseñas más allá de la casilla en Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="94da2-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="94da2-123">Para obtener más información, consulte [How-to: configure password reescritura](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="94da2-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="94da2-124">Si desea administrar también dispositivos Windows 10 Unidos a un dominio, consulte [enable Domain-unirme a Domain Windows 10 Devices to Manage by Microsoft 365 Business Premium](manage-windows-devices.md) para configurar una Unión híbrida de Azure ad.</span><span class="sxs-lookup"><span data-stu-id="94da2-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 