---
title: Configurar la sincronización de directorios para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Obtenga información sobre cómo configurar la sincronización de directorios entre Microsoft 365 y su Active Directory local.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924909"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="48377-103">Configurar la sincronización de directorios para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="48377-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="48377-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="48377-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="48377-105">Microsoft 365 usa un inquilino Azure Active Directory (Azure AD) para almacenar y administrar identidades para autenticación y permisos para obtener acceso a recursos basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="48377-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="48377-106">Si tiene un bosque o dominio de Servicios de dominio de Active Directory (AD DS) local, puede sincronizar sus cuentas de usuario, grupos y contactos de AD DS con el inquilino de Azure AD de su suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48377-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="48377-107">Se trata de una identidad híbrida para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="48377-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="48377-108">Estos son sus componentes.</span><span class="sxs-lookup"><span data-stu-id="48377-108">Here are its components.</span></span>

![Componentes de sincronización de directorios para Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="48377-110">Azure AD Conectar se ejecuta en un servidor local y sincroniza su AD DS con el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="48377-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="48377-111">Junto con la sincronización de directorios, también puede especificar estas opciones de autenticación:</span><span class="sxs-lookup"><span data-stu-id="48377-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="48377-112">Sincronización de hash de contraseña (PHS)</span><span class="sxs-lookup"><span data-stu-id="48377-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="48377-113">Azure AD realiza la autenticación en sí.</span><span class="sxs-lookup"><span data-stu-id="48377-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="48377-114">Autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="48377-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="48377-115">Azure AD tiene AD DS para realizar la autenticación.</span><span class="sxs-lookup"><span data-stu-id="48377-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="48377-116">Autenticación federada</span><span class="sxs-lookup"><span data-stu-id="48377-116">Federated authentication</span></span>

  <span data-ttu-id="48377-117">Azure AD hace referencia al equipo cliente que solicita la autenticación a otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="48377-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="48377-118">Consulte [Identidades híbridas](plan-for-directory-synchronization.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="48377-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="48377-119">1. Revise los requisitos previos de Azure AD Conectar</span><span class="sxs-lookup"><span data-stu-id="48377-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="48377-120">Obtiene una suscripción gratuita de Azure AD con su Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="48377-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="48377-121">Al configurar la sincronización de directorios, instalará Azure AD Conectar uno de los servidores locales.</span><span class="sxs-lookup"><span data-stu-id="48377-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="48377-122">Para Microsoft 365 tendrás que:</span><span class="sxs-lookup"><span data-stu-id="48377-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="48377-123">Compruebe el dominio local.</span><span class="sxs-lookup"><span data-stu-id="48377-123">Verify your on-premises domain.</span></span> <span data-ttu-id="48377-124">El Asistente para Conectar azure AD le guiará a través de esto.</span><span class="sxs-lookup"><span data-stu-id="48377-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="48377-125">Obtenga los nombres de usuario y las contraseñas de las cuentas de administrador de Microsoft 365 inquilino y AD DS.</span><span class="sxs-lookup"><span data-stu-id="48377-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="48377-126">Para el servidor local en el que instale Azure AD Conectar, necesitará:</span><span class="sxs-lookup"><span data-stu-id="48377-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="48377-127">**Sistema operativo del servidor**</span><span class="sxs-lookup"><span data-stu-id="48377-127">**Server OS**</span></span>|<span data-ttu-id="48377-128">**Otros programas de software**</span><span class="sxs-lookup"><span data-stu-id="48377-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48377-129">Windows Server 2012 R2 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="48377-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="48377-130">- PowerShell está instalado de forma predeterminada, no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="48377-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="48377-131">- Net 4.5.1 y versiones posteriores se ofrecen a través de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="48377-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="48377-132">Asegúrese de haber instalado las actualizaciones más recientes en Windows server en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="48377-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="48377-133">Windows Server 2008 R2 con Service Pack 1 (SP1)\*\* o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="48377-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="48377-134">- La versión más reciente de PowerShell está disponible en Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="48377-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="48377-135">Busque en el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="48377-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="48377-136">- .Net 4.5.1 y versiones posteriores están disponibles en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="48377-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="48377-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="48377-137">Windows Server 2008</span></span> | <span data-ttu-id="48377-138">- La última versión compatible de PowerShell está disponible en Windows Management Framework 3.0, disponible en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="48377-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="48377-139">- .Net 4.5.1 y versiones posteriores están disponibles en [el Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="48377-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="48377-140">Consulte [Prerequisites for Azure Active Directory Conectar](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) para obtener información sobre los requisitos de hardware, software, cuenta y permisos, requisitos de certificado SSL y límites de objetos para Azure AD Conectar.</span><span class="sxs-lookup"><span data-stu-id="48377-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="48377-141">También puede revisar el historial de [](/azure/active-directory/hybrid/reference-connect-version-history) versiones Conectar versión de Azure AD para ver lo que se incluye y se ha corregido en cada versión.</span><span class="sxs-lookup"><span data-stu-id="48377-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="48377-142">2. Instalar Azure AD Conectar y configurar la sincronización de directorios</span><span class="sxs-lookup"><span data-stu-id="48377-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="48377-143">Antes de comenzar, asegúrese de que tiene:</span><span class="sxs-lookup"><span data-stu-id="48377-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="48377-144">El nombre de usuario y la contraseña de un Microsoft 365 administrador global</span><span class="sxs-lookup"><span data-stu-id="48377-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="48377-145">Nombre de usuario y contraseña de un administrador de dominio de AD DS</span><span class="sxs-lookup"><span data-stu-id="48377-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="48377-146">Qué método de autenticación (PHS, PTA, federado)</span><span class="sxs-lookup"><span data-stu-id="48377-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="48377-147">Si desea usar el inicio de sesión único sin problemas [(SSO)](/azure/active-directory/hybrid/how-to-connect-sso) de Azure AD</span><span class="sxs-lookup"><span data-stu-id="48377-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="48377-148">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="48377-148">Follow these steps:</span></span>

1. <span data-ttu-id="48377-149">Inicie sesión en el [centro Microsoft 365 de administración](https://admin.microsoft.com) ( y elija https://admin.microsoft.com) **Usuarios** \> **usuarios activos** en la navegación izquierda.</span><span class="sxs-lookup"><span data-stu-id="48377-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="48377-150">En la **página Usuarios activos,** elija **Más** (tres puntos) Sincronización \> **de directorios**.</span><span class="sxs-lookup"><span data-stu-id="48377-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="48377-151">En la **Azure Active Directory preparación,** seleccione el vínculo Ir al Centro de descarga para obtener el vínculo de la herramienta Conectar **Azure AD** para empezar.</span><span class="sxs-lookup"><span data-stu-id="48377-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="48377-152">Siga los pasos descritos en Azure AD Conectar guía de instalación de [Azure AD Conectar Health](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="48377-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="48377-153">3. Finalizar la configuración de dominios</span><span class="sxs-lookup"><span data-stu-id="48377-153">3. Finish setting up domains</span></span>

<span data-ttu-id="48377-154">Siga los pasos descritos en [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span><span class="sxs-lookup"><span data-stu-id="48377-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="48377-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="48377-155">Next step</span></span>

[<span data-ttu-id="48377-156">Asignar licencias a cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="48377-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)