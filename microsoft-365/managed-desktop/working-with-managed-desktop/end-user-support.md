---
title: Obtener soporte técnico de usuario para Escritorio administrado de Microsoft
description: Cómo los usuarios pueden obtener ayuda con el servicio y los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362611"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="dbbfb-104">Obtener ayuda para los usuarios</span><span class="sxs-lookup"><span data-stu-id="dbbfb-104">Getting help for users</span></span>

<span data-ttu-id="dbbfb-105">Si has llegado al punto [](../service-description/user-support.md) del flujo de trabajo en el que necesitas solicitar acceso o escalación de dispositivos elevados a Microsoft, sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="dbbfb-106">Estas opciones de soporte técnico no están disponibles para los dispositivos del grupo De prueba.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="dbbfb-107">Solicitudes de elevación</span><span class="sxs-lookup"><span data-stu-id="dbbfb-107">Elevation requests</span></span>

<span data-ttu-id="dbbfb-108">Antes de solicitar acceso elevado a un dispositivo, es mejor revisar qué acciones son más adecuadas.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="dbbfb-109">**Las acciones típicas** son para lo que está diseñado este proceso y se realizarían de forma rutinaria al solucionar problemas con Escritorio administrado de Microsoft dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbbfb-110">Algunos ejemplos son:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-110">Examples include:</span></span>
    - <span data-ttu-id="dbbfb-111">Elevar los solucionadores de problemas del sistema integrados, el símbolo del sistema o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbbfb-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="dbbfb-112">Solución de problemas de aplicaciones de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="dbbfb-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="dbbfb-113">Usar una solución alternativa para corregir algo que debe funcionar por diseño (como la activación de BitLocker o la hora del sistema no se actualiza)</span><span class="sxs-lookup"><span data-stu-id="dbbfb-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="dbbfb-114">Elevar el Administrador de dispositivos para hacer cosas como actualizar controladores, desinstalar un dispositivo o buscar nuevos cambios</span><span class="sxs-lookup"><span data-stu-id="dbbfb-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="dbbfb-115">**Entre las acciones que no se recomiendan** se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="dbbfb-116">Instalación de software o exploradores</span><span class="sxs-lookup"><span data-stu-id="dbbfb-116">Installing software or browsers</span></span>
    - <span data-ttu-id="dbbfb-117">Instalación de controladores fuera de Windows, incluidos los de periféricos</span><span class="sxs-lookup"><span data-stu-id="dbbfb-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="dbbfb-118">Instalación .msi o .exe archivos</span><span class="sxs-lookup"><span data-stu-id="dbbfb-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="dbbfb-119">Instalación Windows características</span><span class="sxs-lookup"><span data-stu-id="dbbfb-119">Installing Windows features</span></span>

- <span data-ttu-id="dbbfb-120">**Entre las acciones que no se admiten** se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="dbbfb-121">Instalación de software o características que entren en conflicto con Escritorio administrado de Microsoft de seguridad o administración o operaciones</span><span class="sxs-lookup"><span data-stu-id="dbbfb-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="dbbfb-122">Deshabilitar una característica Windows necesaria para Escritorio administrado de Microsoft, como BitLocker</span><span class="sxs-lookup"><span data-stu-id="dbbfb-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="dbbfb-123">Modificar la configuración administrada por la organización</span><span class="sxs-lookup"><span data-stu-id="dbbfb-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="dbbfb-124">Para solicitar elevación</span><span class="sxs-lookup"><span data-stu-id="dbbfb-124">To request elevation</span></span>

1. <span data-ttu-id="dbbfb-125">Vaya al portal en [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e inicie sesión con sus Azure Active Directory credenciales.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="dbbfb-126">Seleccione **Nueva solicitud de elevación**.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="dbbfb-127">Proporcione estos detalles:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-127">Provide these details:</span></span>
    - <span data-ttu-id="dbbfb-128">**Id. de vale de** soporte técnico de su propio sistema de vales de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="dbbfb-129">**Nombre del dispositivo:** escriba el número de serie del dispositivo y, a continuación, seleccione el dispositivo en el menú.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="dbbfb-130">**Categoría:** seleccione la categoría que mejor se adapte a su problema.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="dbbfb-131">Si ninguna opción parece estar cerca, selecciona **Otros** y proporciona más información en los campos **Título** y **Plan de** acción.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="dbbfb-132">Es mejor seleccionar una categoría si es posible.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="dbbfb-133">**Subcategoría:** seleccione la que mejor se adapte al problema.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="dbbfb-134">Si ninguna opción parece estar cerca, seleccione **Otro** y proporcione una breve descripción en **Título**.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="dbbfb-135">En **Plan of action**, proporcione los pasos de solución de problemas que tiene previsto realizar una vez que se conceda la elevación.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="dbbfb-136">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="dbbfb-137">Solicitudes de escalación</span><span class="sxs-lookup"><span data-stu-id="dbbfb-137">Escalation requests</span></span>


<span data-ttu-id="dbbfb-138">Si necesita escalar [un problema](../service-description/user-support.md#escalation-portal) a Microsoft, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="dbbfb-139">Vaya al portal en [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e inicie sesión con sus Azure Active Directory credenciales.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="dbbfb-140">Seleccione **Solicitudes de escalación** y, a continuación, **nueva solicitud de escalación**.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="dbbfb-141">Proporcione estos detalles:</span><span class="sxs-lookup"><span data-stu-id="dbbfb-141">Provide these details:</span></span>
    - <span data-ttu-id="dbbfb-142">**Categoría:** seleccione la categoría que mejor se adapte a su problema.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="dbbfb-143">**Título:** proporcione una descripción muy breve.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="dbbfb-144">**Descripción:** agregue cualquier información adicional que pueda ayudar a nuestro equipo a comprender el problema.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="dbbfb-145">Si necesita adjuntar archivos, puede hacerlo volviendo a la solicitud después de enviarlo.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="dbbfb-146">**Información de contacto principal:** proporcione información sobre cómo ponerse en contacto con la persona principal responsable de trabajar con nuestro equipo.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="dbbfb-147">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-147">Select **Submit**.</span></span>
5. <span data-ttu-id="dbbfb-148">Vuelva a visitar el vale en el mismo portal para interactuar con nuestro equipo.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbfb-149">Solo los problemas de gravedad C se pueden escalar a través de esta ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="dbbfb-150">Para otros problemas, póngase en contacto con el administrador de TI para presentar la solicitud a través del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="dbbfb-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>