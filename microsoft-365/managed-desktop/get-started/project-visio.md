---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado por Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: aba6d1b81e4c579e82e6fad90daec65d775b450a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30573424"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="a1f9f-104">Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="a1f9f-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="a1f9f-105">Microsoft Project y Microsoft Visio requieren que se instalen pasos específicos en dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a1f9f-106">En este tema se documentan los requisitos previos y el proceso de instalación de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1f9f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a1f9f-107">Prerequisites</span></span>

<span data-ttu-id="a1f9f-108">Los administradores deben comprobar que cumplen estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="a1f9f-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="a1f9f-109">**Cantidades de licencias** : la cantidad correcta de licencias de Microsoft Project y Microsoft Visio debe estar disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="a1f9f-110">Actualmente, Microsoft manAged Desktop solo admite versiones de 64 bits de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="a1f9f-111">**Nombres de licencia** : los nombres de licencia apropiados para estas aplicaciones son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1f9f-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="a1f9f-112">**Microsoft Project** -Project Online Professional o Project online Premium</span><span class="sxs-lookup"><span data-stu-id="a1f9f-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="a1f9f-113">**Microsoft Visio** -Visio online plan 2</span><span class="sxs-lookup"><span data-stu-id="a1f9f-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="a1f9f-114">**Portal de empresa** : el portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="a1f9f-115">Si el portal de la empresa no está implementado en el espacio empresarial, consulte [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="a1f9f-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="a1f9f-116">Implementación de Project y Visio para dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="a1f9f-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="a1f9f-117">Después de enviar su solicitud de soporte técnico, el escritorio administrado de Microsoft creará tres grupos de Azure AD y tres implementaciones de aplicaciones a través de Microsoft Intune para implementar las aplicaciones en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-117">After you submit your support request, Microsoft Managed Desktop will create three Azure AD groups and three application deployments through Microsoft Intune to deploy the apps to your tenant.</span></span>  

<span data-ttu-id="a1f9f-118">**Para implementar Project y Visio**</span><span class="sxs-lookup"><span data-stu-id="a1f9f-118">**To deploy Project and Visio**</span></span>
1. <span data-ttu-id="a1f9f-119">**Archivar una solicitud de soporte técnico** Los administradores de TI deben presentar una solicitud de soporte técnico para que estas aplicaciones estén disponibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-119">**File a support request** IT administrators need to file a support request to make these applications available their users.</span></span> <span data-ttu-id="a1f9f-120">Para obtener información sobre cómo ponerse en contacto con el escritorio administrado de Microsoft, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="a1f9f-120">For information on contacting Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>
2. <span data-ttu-id="a1f9f-121">**Asignar usuarios a los nuevos grupos de Azure ad** Microsoft manAged Desktop creará 3 grupos de Azure AD en el espacio empresarial y tres implementaciones de aplicaciones correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-121">**Assign users to new Azure AD groups** Microsoft Managed Desktop will create 3 Azure AD groups in your tenant and 3 corresponding application deployments.</span></span> <span data-ttu-id="a1f9f-122">Los administradores de TI deben asignar los usuarios a los grupos adecuados.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-122">IT admins need to assign the users to the appropriate groups.</span></span>

>[!NOTE]
><span data-ttu-id="a1f9f-123">Asigne usuarios a solo uno de estos grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-123">Assign users to only one of these Azure AD groups.</span></span> 

<span data-ttu-id="a1f9f-124">Nombre de grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="a1f9f-124">Azure AD Group name</span></span> | <span data-ttu-id="a1f9f-125">¿Qué usuarios va a asignar?</span><span class="sxs-lookup"><span data-stu-id="a1f9f-125">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="a1f9f-126">Microsoft-Office-Project-install</span><span class="sxs-lookup"><span data-stu-id="a1f9f-126">Microsoft-Office-Project-Install</span></span> | <span data-ttu-id="a1f9f-127">Los usuarios solo necesitan un proyecto</span><span class="sxs-lookup"><span data-stu-id="a1f9f-127">Users needing only Project</span></span>
<span data-ttu-id="a1f9f-128">Microsoft-Office-Visio-install</span><span class="sxs-lookup"><span data-stu-id="a1f9f-128">Microsoft-Office-Visio-Install</span></span> | <span data-ttu-id="a1f9f-129">Usuarios que solo necesitan Visio</span><span class="sxs-lookup"><span data-stu-id="a1f9f-129">Users needing only Visio</span></span>
<span data-ttu-id="a1f9f-130">Microsoft-Office-Project y Visio-install</span><span class="sxs-lookup"><span data-stu-id="a1f9f-130">Microsoft-Office-Project and Visio-Install</span></span> | <span data-ttu-id="a1f9f-131">Usuarios que necesiten tanto Project como Visio</span><span class="sxs-lookup"><span data-stu-id="a1f9f-131">Users needing both Project and Visio</span></span>

<span data-ttu-id="a1f9f-132">Una vez asignada a estos grupos, las aplicaciones estarán disponibles en el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-132">Once assigned to these groups, applications will be available in the Company Portal.</span></span> <span data-ttu-id="a1f9f-133">La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-133">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

## <a name="communicate-changes"></a><span data-ttu-id="a1f9f-134">Comunicar los cambios</span><span class="sxs-lookup"><span data-stu-id="a1f9f-134">Communicate changes</span></span>
<span data-ttu-id="a1f9f-135">Es importante que los administradores de ti permitan a sus usuarios saber cómo instalar Project y Visio.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-135">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="a1f9f-136">Incluye:</span><span class="sxs-lookup"><span data-stu-id="a1f9f-136">This includes:</span></span> 
- <span data-ttu-id="a1f9f-137">Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-137">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="a1f9f-138">Instrucciones sobre cómo instalar estas aplicaciones desde el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-138">Instructions on how to install these applications from the Company Portal.</span></span>

>[!NOTE]
><span data-ttu-id="a1f9f-139">Los usuarios deben cerrar todas las aplicaciones de Office antes de instalar Microsoft Project o Microsoft Visio desde el portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="a1f9f-139">Users must close all Office applications before installing Microsoft Project or Microsoft Visio from Company Portal.</span></span> 
