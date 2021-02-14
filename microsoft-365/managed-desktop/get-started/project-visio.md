---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950537"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="8471e-104">Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8471e-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="8471e-105">Microsoft Project y Microsoft Visio requieren pasos específicos para instalarse en dispositivos de Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8471e-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8471e-106">En este tema se documenta los requisitos previos y el proceso de instalación de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8471e-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8471e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8471e-107">Prerequisites</span></span>

<span data-ttu-id="8471e-108">Los administradores deben comprobar que cumplen estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="8471e-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="8471e-109">**Cantidades de licencias:** la cantidad correcta de licencias de Microsoft Project y Microsoft Visio debe estar disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8471e-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="8471e-110">Actualmente, escritorio administrado de Microsoft solo admite versiones de 64 bits de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8471e-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="8471e-111">**Nombres de licencia:** los nombres de licencia adecuados para estas aplicaciones son:</span><span class="sxs-lookup"><span data-stu-id="8471e-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="8471e-112">**Microsoft Project:** Project Online Professional o Project Online Premium</span><span class="sxs-lookup"><span data-stu-id="8471e-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="8471e-113">**Microsoft Visio-** Visio Online Plan 2</span><span class="sxs-lookup"><span data-stu-id="8471e-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="8471e-114">**Portal de** empresa: el Portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8471e-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="8471e-115">Si el Portal de empresa no está implementado en su espacio empresarial, consulte [Portal de empresa.](company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="8471e-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="8471e-116">Implementar Project y Visio para dispositivos de escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8471e-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="8471e-117">Escritorio administrado de Microsoft agregará Microsoft Project y Microsoft Visio como dos aplicaciones win32 en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8471e-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="8471e-118">También crearemos dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con la intención "Disponible".</span><span class="sxs-lookup"><span data-stu-id="8471e-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="8471e-119">**Para implementar Project y Visio** Agregue el usuario al grupo adecuado y la aplicación estará disponible en el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="8471e-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="8471e-120">La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="8471e-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="8471e-121">Nombre del grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="8471e-121">Azure AD Group name</span></span> | <span data-ttu-id="8471e-122">¿Qué usuarios asignar?</span><span class="sxs-lookup"><span data-stu-id="8471e-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="8471e-123">Modern Workplace-Office-Project_Install</span><span class="sxs-lookup"><span data-stu-id="8471e-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="8471e-124">Usuarios que necesitan Project</span><span class="sxs-lookup"><span data-stu-id="8471e-124">Users needing Project</span></span>
<span data-ttu-id="8471e-125">Modern Workplace-Office-Visio_Install</span><span class="sxs-lookup"><span data-stu-id="8471e-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="8471e-126">Usuarios que necesitan Visio</span><span class="sxs-lookup"><span data-stu-id="8471e-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="8471e-127">Comunicar cambios</span><span class="sxs-lookup"><span data-stu-id="8471e-127">Communicate changes</span></span>
<span data-ttu-id="8471e-128">Es importante que los administradores de TI sepan a los usuarios cómo instalar Project y Visio.</span><span class="sxs-lookup"><span data-stu-id="8471e-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="8471e-129">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8471e-129">This includes:</span></span> 
- <span data-ttu-id="8471e-130">Notificar a los usuarios cuándo están disponibles estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8471e-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="8471e-131">Instrucciones sobre cómo instalar estas aplicaciones desde el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="8471e-131">Instructions on how to install these applications from the Company Portal.</span></span>
