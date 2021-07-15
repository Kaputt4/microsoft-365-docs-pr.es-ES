---
title: Administrar directivas de aplicación
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Administre las directivas de gobernanza de aplicaciones.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420403"
---
# <a name="manage-app-policies"></a><span data-ttu-id="db100-103">Administrar directivas de aplicación</span><span class="sxs-lookup"><span data-stu-id="db100-103">Manage app policies</span></span>

><span data-ttu-id="db100-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="db100-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="db100-105">Para mantenerse al día con las aplicaciones más recientes que usa su organización, responder a nuevos ataques basados en aplicaciones y gestionar los cambios continuos en las necesidades de cumplimiento de las aplicaciones, es posible que deba administrar las directivas de aplicación mediante estas acciones:</span><span class="sxs-lookup"><span data-stu-id="db100-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="db100-106">Crear nuevas directivas destinadas a nuevas aplicaciones</span><span class="sxs-lookup"><span data-stu-id="db100-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="db100-107">Cambiar el estado de una directiva existente (activo, inactivo, modo de auditoría)</span><span class="sxs-lookup"><span data-stu-id="db100-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="db100-108">Cambiar las condiciones de una directiva existente</span><span class="sxs-lookup"><span data-stu-id="db100-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="db100-109">Cambiar las acciones de una directiva existente para la corrección automática de alertas</span><span class="sxs-lookup"><span data-stu-id="db100-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="db100-110">Este es un ejemplo de un proceso para administrar una directiva existente:</span><span class="sxs-lookup"><span data-stu-id="db100-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="db100-111">Edite la directiva:</span><span class="sxs-lookup"><span data-stu-id="db100-111">Edit the policy:</span></span>

  - <span data-ttu-id="db100-112">Cambie la configuración de la directiva.</span><span class="sxs-lookup"><span data-stu-id="db100-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="db100-113">Si es necesario, cambie el estado a **modo de auditoría** para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="db100-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="db100-114">Compruebe el comportamiento esperado, como las alertas generadas.</span><span class="sxs-lookup"><span data-stu-id="db100-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="db100-115">Si el comportamiento no es el esperado, vuelva al paso 1.</span><span class="sxs-lookup"><span data-stu-id="db100-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="db100-116">Si el comportamiento es el esperado, edite la directiva y cambie su estado a activo (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="db100-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![Flujo de trabajo de administración de directivas de aplicaciones](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="db100-118">Editar la configuración de una directiva de aplicación</span><span class="sxs-lookup"><span data-stu-id="db100-118">Editing an app policy configuration</span></span>

<span data-ttu-id="db100-119">Para cambiar la configuración de una directiva de aplicación existente:</span><span class="sxs-lookup"><span data-stu-id="db100-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="db100-120">Seleccione la directiva en la lista de directivas y, a continuación, seleccione **Editar** en el panel de directivas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="db100-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="db100-121">Seleccione los puntos suspensivos verticales de la directiva en la lista y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db100-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="db100-122">Para la página **Editar directiva**, recorra las páginas y realice los cambios adecuados:</span><span class="sxs-lookup"><span data-stu-id="db100-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="db100-123">**Descripción**: cambie la descripción para que sea más fácil comprender el propósito de la directiva.</span><span class="sxs-lookup"><span data-stu-id="db100-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="db100-124">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="db100-124">**Severity**</span></span>
- <span data-ttu-id="db100-125">**Configuración de directiva**: cambie el conjunto de aplicaciones a las que se aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="db100-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="db100-126">También puede optar por usar las condiciones existentes o modificarlas.</span><span class="sxs-lookup"><span data-stu-id="db100-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="db100-127">**Acciones**: cambie la acción de corrección automática para las alertas generadas por la directiva.</span><span class="sxs-lookup"><span data-stu-id="db100-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="db100-128">**Estado**: cambie el estado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="db100-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="db100-129">Eliminación de una directiva de aplicación</span><span class="sxs-lookup"><span data-stu-id="db100-129">Deleting an app policy</span></span>

<span data-ttu-id="db100-130">Para eliminar una directiva de aplicación:</span><span class="sxs-lookup"><span data-stu-id="db100-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="db100-131">Seleccione la directiva en la lista de directivas y, a continuación, seleccione **Eliminar** en el panel de directivas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="db100-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="db100-132">Seleccione los puntos suspensivos verticales de la directiva en la lista y, a continuación, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="db100-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="db100-133">Una alternativa a la eliminación de una directiva de aplicación es cambiar su estado a inactivo.</span><span class="sxs-lookup"><span data-stu-id="db100-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="db100-134">Una vez inactiva, no generará alertas.</span><span class="sxs-lookup"><span data-stu-id="db100-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="db100-135">Por ejemplo, en lugar de eliminar una directiva de aplicación para una aplicación con un conjunto específico de condiciones que pueden ser útiles para una directiva futura, cambie el nombre de la directiva de aplicación para indicar su utilidad y establezca su estado en inactivo.</span><span class="sxs-lookup"><span data-stu-id="db100-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="db100-136">Más adelante, podrá volver a la directiva, modificarla para una aplicación similar y establecer su estado en modo de auditoría o inactivo.</span><span class="sxs-lookup"><span data-stu-id="db100-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
