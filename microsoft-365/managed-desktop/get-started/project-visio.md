---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado por Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126832"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a><span data-ttu-id="d6983-104">Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6983-104">Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices</span></span>

<span data-ttu-id="d6983-105">Microsoft Project y Microsoft Visio requieren que se instalen pasos específicos en dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6983-105">Microsoft Project and Microsoft Visio require specific steps to be installed on Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d6983-106">En este tema se documentan los requisitos previos y el proceso de instalación de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d6983-106">This topic documents the prerequisites and installation process for these applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6983-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d6983-107">Prerequisites</span></span>

<span data-ttu-id="d6983-108">Los administradores deben comprobar que cumplen estos requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="d6983-108">Admins should verify that they meet these prerequisites:</span></span>
- <span data-ttu-id="d6983-109">**Cantidades de licencias** : la cantidad correcta de licencias de Microsoft Project y Microsoft Visio debe estar disponible para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d6983-109">**License quantities** - The correct amount of Microsoft Project and Microsoft Visio licenses must be available for your users.</span></span> <span data-ttu-id="d6983-110">Actualmente, Microsoft Managed Desktop solo admite versiones de 64 bits de estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d6983-110">Microsoft Managed Desktop currently only supports 64-bit versions of these applications.</span></span> 
- <span data-ttu-id="d6983-111">**Nombres de licencia** : los nombres de licencia apropiados para estas aplicaciones son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6983-111">**License names** - The appropriate license names for these applications are:</span></span>
    - <span data-ttu-id="d6983-112">**Microsoft Project** -Project Online Professional o Project online Premium</span><span class="sxs-lookup"><span data-stu-id="d6983-112">**Microsoft Project** - Project Online Professional or Project Online Premium</span></span>
    - <span data-ttu-id="d6983-113">**Microsoft Visio** -Visio online plan 2</span><span class="sxs-lookup"><span data-stu-id="d6983-113">**Microsoft Visio** - Visio Online Plan 2</span></span>
- <span data-ttu-id="d6983-114">**Portal de empresa** : el portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d6983-114">**Company Portal** -  The Company Portal must be available in your tenant for your users to install these applications.</span></span> <span data-ttu-id="d6983-115">Si el portal de la empresa no está implementado en el espacio empresarial, consulte [Company Portal](company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="d6983-115">If the Company Portal isn’t deployed in your tenant, see [Company Portal](company-portal.md).</span></span>

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a><span data-ttu-id="d6983-116">Implementación de Project y Visio para dispositivos de escritorio administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6983-116">Deploy Project and Visio for Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d6983-117">Microsoft Managed Desktop agregará Microsoft Project y Microsoft Visio como dos aplicaciones Win32 en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d6983-117">Microsoft Managed Desktop will add Microsoft Project and Microsoft Visio as two Win32 Applications in Microsoft Intune.</span></span> <span data-ttu-id="d6983-118">También se crean dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con el propósito "disponible".</span><span class="sxs-lookup"><span data-stu-id="d6983-118">We will also create two groups in Azure Active Directory which will be assigned to the corresponding application with the "Available" intent.</span></span> 

<span data-ttu-id="d6983-119">**Para implementar Project y Visio** Agregue el usuario al grupo adecuado y la aplicación estará disponible en el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d6983-119">**To deploy Project and Visio** Add the user to the appropriate group and the application will become available in the Company Portal.</span></span> <span data-ttu-id="d6983-120">La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d6983-120">It may take a few minutes to sync, but then your users can install the apps from Company Portal.</span></span> 

<span data-ttu-id="d6983-121">Nombre de grupo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="d6983-121">Azure AD Group name</span></span> | <span data-ttu-id="d6983-122">¿Qué usuarios va a asignar?</span><span class="sxs-lookup"><span data-stu-id="d6983-122">Which users to assign?</span></span>   
 --- | ---
<span data-ttu-id="d6983-123">Espacio de trabajo moderno: Project_Install de Office</span><span class="sxs-lookup"><span data-stu-id="d6983-123">Modern Workplace-Office-Project_Install</span></span> | <span data-ttu-id="d6983-124">Usuarios que necesitan Project</span><span class="sxs-lookup"><span data-stu-id="d6983-124">Users needing Project</span></span>
<span data-ttu-id="d6983-125">Espacio de trabajo moderno: Visio_Install de Office</span><span class="sxs-lookup"><span data-stu-id="d6983-125">Modern Workplace-Office-Visio_Install</span></span> | <span data-ttu-id="d6983-126">Usuarios que necesitan Visio</span><span class="sxs-lookup"><span data-stu-id="d6983-126">Users needing Visio</span></span>

## <a name="communicate-changes"></a><span data-ttu-id="d6983-127">Comunicar los cambios</span><span class="sxs-lookup"><span data-stu-id="d6983-127">Communicate changes</span></span>
<span data-ttu-id="d6983-128">Es importante que los administradores de ti permitan a sus usuarios saber cómo instalar Project y Visio.</span><span class="sxs-lookup"><span data-stu-id="d6983-128">It’s important for IT administrators to let their users know how to install Project and Visio.</span></span> <span data-ttu-id="d6983-129">Incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6983-129">This includes:</span></span> 
- <span data-ttu-id="d6983-130">Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos.</span><span class="sxs-lookup"><span data-stu-id="d6983-130">Notifying users when these applications are available to them.</span></span> 
- <span data-ttu-id="d6983-131">Instrucciones sobre cómo instalar estas aplicaciones desde el portal de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d6983-131">Instructions on how to install these applications from the Company Portal.</span></span>
