---
title: Instalar Portal de empresa de Intune dispositivos
description: Información sobre cómo instalar la aplicación del portal de empresa en Escritorio administrado de Microsoft dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, Portal de empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086690"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="6250e-104">Instalar Portal de empresa de Intune dispositivos</span><span class="sxs-lookup"><span data-stu-id="6250e-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="6250e-105">Escritorio administrado de Microsoft requiere que los administradores de TI instalen Portal de empresa de Intune para sus usuarios con Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6250e-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="6250e-106">Estas son algunas ventajas para su organización:</span><span class="sxs-lookup"><span data-stu-id="6250e-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="6250e-107">Los usuarios tienen un lugar para examinar e instalar aplicaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="6250e-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="6250e-108">Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="6250e-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="6250e-109">Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren Portal de empresa implementar con Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6250e-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="6250e-110">Los administradores de TI pueden personalizar Portal de empresa para su organización.</span><span class="sxs-lookup"><span data-stu-id="6250e-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="6250e-111">Esto incluye la creación de imágenes de marca, la adición de contactos de soporte técnico local y mucho más.</span><span class="sxs-lookup"><span data-stu-id="6250e-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="6250e-112">Para obtener más información, [consulta How to Configure the Microsoft Intune Portal de empresa app](/intune/company-portal-app).</span><span class="sxs-lookup"><span data-stu-id="6250e-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="6250e-113">En este tema se documenta el proceso para implementar el Portal de empresa de Intune a los Escritorio administrado de Microsoft usuarios.</span><span class="sxs-lookup"><span data-stu-id="6250e-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="6250e-114">El proceso general tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="6250e-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="6250e-115">Comprar Portal de empresa desde Microsoft Store para Empresas y sincronizar con Intune</span><span class="sxs-lookup"><span data-stu-id="6250e-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="6250e-116">Asignar Portal de empresa a los usuarios</span><span class="sxs-lookup"><span data-stu-id="6250e-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="6250e-117">Comunicar el cambio a los usuarios</span><span class="sxs-lookup"><span data-stu-id="6250e-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="6250e-118">Paso 1: comprar Portal de empresa desde Microsoft Store para Empresas y sincronizar con Intune</span><span class="sxs-lookup"><span data-stu-id="6250e-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="6250e-119">Para obtener información sobre cómo comprar las aplicaciones y sincronizarlas con Intune, consulta Microsoft Store para Empresas [aplicaciones en](deploy-apps.md#msfb-apps) Deploy apps to *Escritorio administrado de Microsoft devices*.</span><span class="sxs-lookup"><span data-stu-id="6250e-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="6250e-120">En este tema se proporciona información sobre cómo:</span><span class="sxs-lookup"><span data-stu-id="6250e-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="6250e-121">Comprar Portal de empresa desde Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="6250e-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="6250e-122">Forzar la sincronización entre Intune y Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="6250e-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="6250e-123">Comprobar la sincronización activa entre Intune y Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="6250e-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="6250e-124">Paso 2: Asignar Portal de empresa a los usuarios</span><span class="sxs-lookup"><span data-stu-id="6250e-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="6250e-125">Después de la inscripción en Escritorio administrado de Microsoft, implementaremos automáticamente Portal de empresa tu inquilino e instalaremos la aplicación en Escritorio administrado de Microsoft dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="6250e-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="6250e-126">Paso 3: Comunicar el cambio a los usuarios</span><span class="sxs-lookup"><span data-stu-id="6250e-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="6250e-127">Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar Portal de empresa en su organización.</span><span class="sxs-lookup"><span data-stu-id="6250e-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="6250e-128">Escritorio administrado de Microsoft recomienda:</span><span class="sxs-lookup"><span data-stu-id="6250e-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="6250e-129">Pasos para instalar aplicaciones desde el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="6250e-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="6250e-130">Para obtener más información, consulta [Instalar y compartir aplicaciones en el dispositivo.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="6250e-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="6250e-131">Cómo enviar solicitudes a los administradores de TI para aplicaciones que no están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="6250e-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="6250e-132">Para obtener más información, [consulta Solicitar una aplicación para el trabajo o la escuela.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="6250e-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="6250e-133">Pasos para empezar con Escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6250e-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="6250e-134">Agregar y verificar los contactos de administración en el portal de administración </span><span class="sxs-lookup"><span data-stu-id="6250e-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="6250e-135">Ajustar el acceso condicional</span><span class="sxs-lookup"><span data-stu-id="6250e-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="6250e-136">Asignar licencias</span><span class="sxs-lookup"><span data-stu-id="6250e-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="6250e-137">Implementar Portal de empresa de Intune (este tema)</span><span class="sxs-lookup"><span data-stu-id="6250e-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="6250e-138">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="6250e-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="6250e-139">Instalar dispositivos</span><span class="sxs-lookup"><span data-stu-id="6250e-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="6250e-140">Prepare a los usuarios para que usen los dispositivos</span><span class="sxs-lookup"><span data-stu-id="6250e-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="6250e-141">Implementar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6250e-141">Deploy apps</span></span>](deploy-apps.md)
