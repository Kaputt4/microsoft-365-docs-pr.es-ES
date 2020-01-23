---
title: Usuarios de administración de riesgos de Insider (versión preliminar)
description: Obtenga información sobre los usuarios de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5688d1554bc48632c3dca40dd33c65b4ea41ee20
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256743"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="05346-104">Usuarios de administración de riesgos de Insider (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="05346-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="05346-105">Los usuarios de administración de riesgos de Insider son empleados de su organización que están incluidos en una o varias directivas de administración de riesgos de Insider.</span><span class="sxs-lookup"><span data-stu-id="05346-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="05346-106">Use el **Panel usuarios** para revisar rápidamente la información de riesgos de los empleados y agregar un empleado a una directiva de administración de riesgos de Insider existente.</span><span class="sxs-lookup"><span data-stu-id="05346-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="05346-107">Cada usuario incluido en una directiva de administración de riesgos de Insider tiene la siguiente información que se muestra en el **Panel de usuarios**:</span><span class="sxs-lookup"><span data-stu-id="05346-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="05346-108">**Users**: el nombre de usuario de un usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="05346-109">**Nivel de riesgo**:</span><span class="sxs-lookup"><span data-stu-id="05346-109">**Risk level**:</span></span> 
- <span data-ttu-id="05346-110">**Alertas activas**: el número de alertas activas para todas las directivas.</span><span class="sxs-lookup"><span data-stu-id="05346-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="05346-111">**Infracciones confirmadas**: el número de casos resueltos como *infracción de la Directiva confirmada* para el usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="05346-112">**Caso**: el caso activo actual para el usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-112">**Case**: The current active case for the user.</span></span>

![Panel de usuarios de administración de riesgos de Insider](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="05346-114">Ver detalles del usuario</span><span class="sxs-lookup"><span data-stu-id="05346-114">View user details</span></span>

<span data-ttu-id="05346-115">Para ver más detalles sobre la actividad de riesgos para un usuario, abra el panel de detalles del usuario haciendo doble clic en un usuario en el **Panel de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="05346-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="05346-116">En el panel de detalles, puede ver la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="05346-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="05346-117">Ficha **Perfil de usuario**</span><span class="sxs-lookup"><span data-stu-id="05346-117">**User profile** tab</span></span>
    - <span data-ttu-id="05346-118">**Nombre y título**: el nombre y el título de la posición del usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="05346-119">**Correo electrónico del usuario**: la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="05346-120">**Alias**: el alias de red del usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="05346-121">**Organización o departamento**: la organización o el Departamento del usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="05346-122">Ficha **actividad del usuario**</span><span class="sxs-lookup"><span data-stu-id="05346-122">**User activity** tab</span></span>
    - <span data-ttu-id="05346-123">**Historial de la actividad reciente de los usuarios**: enumera los eventos de desencadenamiento de directivas y los indicadores de riesgos para las actividades de usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="05346-124">Un evento desencadenante puede ser la aceptación de una fecha de retirada o la fecha del último trabajo programado para el empleado.</span><span class="sxs-lookup"><span data-stu-id="05346-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="05346-125">Los indicadores de riesgo son actividades que se determinan para tener un elemento de riesgo y que coinciden con las directivas en las que el usuario está incluido.</span><span class="sxs-lookup"><span data-stu-id="05346-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="05346-126">Los eventos y las actividades de riesgo se muestran con el elemento más reciente enumerado primero.</span><span class="sxs-lookup"><span data-stu-id="05346-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="05346-127">Agregar un usuario a una directiva</span><span class="sxs-lookup"><span data-stu-id="05346-127">Add a user to a policy</span></span>

<span data-ttu-id="05346-128">Para agregar un usuario a una directiva de administración de riesgos de Insider, use el Asistente para nueva Directiva o la pestaña **usuarios** de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="05346-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="05346-129">Complete los siguientes pasos para agregar un usuario a una directiva de riesgos de Insider existente:</span><span class="sxs-lookup"><span data-stu-id="05346-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="05346-130">En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="05346-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="05346-131">Seleccione **Agregar un usuario a una directiva** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="05346-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="05346-132">En el cuadro de diálogo **Agregar un nuevo usuario** , empiece a escribir un nombre de usuario en el campo **usuario** .</span><span class="sxs-lookup"><span data-stu-id="05346-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="05346-133">Seleccione el usuario que desea agregar a una directiva.</span><span class="sxs-lookup"><span data-stu-id="05346-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="05346-134">Seleccione la flecha desplegable del campo de **Directiva** para mostrar las directivas de administración de riesgos de Insider configuradas.</span><span class="sxs-lookup"><span data-stu-id="05346-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="05346-135">Seleccione la Directiva a la que desea agregar el usuario.</span><span class="sxs-lookup"><span data-stu-id="05346-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="05346-136">Use el control deslizante de la **ventana de supervisión** para definir la...... El intervalo para la ventana de supervisión es de 5 a 30 días.</span><span class="sxs-lookup"><span data-stu-id="05346-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="05346-137">Seleccione **Agregar** y **confirme** para agregar el usuario a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="05346-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
