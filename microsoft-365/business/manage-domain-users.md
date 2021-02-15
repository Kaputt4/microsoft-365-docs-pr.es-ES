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
description: Sincronizar usuarios controlados por dominio con Microsoft 365 para empresas.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841367"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="204c5-103">Sincronizar usuarios del dominio con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="204c5-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="204c5-104">1. Preparar la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="204c5-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="204c5-105">Antes de sincronizar los usuarios y equipos desde el dominio local de Active Directory, revise Preparar la sincronización de directorios [con Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="204c5-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="204c5-106">En particular:</span><span class="sxs-lookup"><span data-stu-id="204c5-106">In particular:</span></span>

   - <span data-ttu-id="204c5-107">Asegúrese de que no existen duplicados en el directorio para los atributos siguientes: **mail**, **proxyAddresses** y **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="204c5-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="204c5-108">Estos valores deben ser únicos y se deben quitar los duplicados.</span><span class="sxs-lookup"><span data-stu-id="204c5-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="204c5-109">Se recomienda configurar el atributo **userPrincipalName** (UPN) para cada cuenta de usuario local para que coincida con la dirección de correo electrónico principal que corresponde al usuario de Microsoft 365 con licencia.</span><span class="sxs-lookup"><span data-stu-id="204c5-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="204c5-110">Por ejemplo: *mary.shelley@contoso.com* en lugar *de mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="204c5-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="204c5-111">Si el dominio de Active Directory termina en un sufijo no enrutable como *.local* o *.lan*, en lugar de un sufijo enrutable de Internet como *.com* o *.org,* ajuste primero el sufijo UPN de las cuentas de usuario local tal como se describe en Preparar un dominio no enrutable para la sincronización de directorios. [](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="204c5-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="204c5-112">La **ejecución de IdFix en** el paso cuatro (4) siguiente, también se asegura de que su Active Directory local está listo para la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="204c5-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="204c5-113">2. Instalar y configurar Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="204c5-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="204c5-114">Para sincronizar los usuarios, grupos y contactos del Active Directory local con Azure Active Directory, instale Azure Active Directory Connect y configure la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="204c5-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="204c5-115">En el [Centro de administración,](https://go.microsoft.com/fwlink/p/?linkid=2024339)seleccione **Configurar** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="204c5-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="204c5-116">En **Inicio de sesión y seguridad,** elija **Ver** en Sincronizar usuarios del directorio de **su organización.**</span><span class="sxs-lookup"><span data-stu-id="204c5-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="204c5-117">En la **página Sincronizar usuarios de la página del directorio** de su organización, elija **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="204c5-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="204c5-118">En el primer paso, ejecute la herramienta IdFix para preparar la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="204c5-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="204c5-119">Siga los pasos del asistente para descargar Azure AD Connect y usarlo para sincronizar los usuarios controlados por el dominio con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="204c5-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="204c5-120">Consulte [Configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="204c5-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="204c5-121">A medida que configure las opciones de Azure AD Connect, le recomendamos  que habilite la sincronización de contraseñas, el inicio de sesión único sin problemas y la característica de escritura escritura por contraseña, que también es compatible con Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="204c5-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="204c5-122">Hay algunos pasos adicionales para la reescribición de contraseñas más allá de la casilla en Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="204c5-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="204c5-123">Para obtener más información, vea [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="204c5-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="204c5-124">Si también quieres administrar dispositivos Windows 10 unidos a un dominio, consulta Habilitar dispositivos Windows 10 unidos a un dominio para que Microsoft [365 Empresa Premium](manage-windows-devices.md) administre para configurar una unión híbrida de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="204c5-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 