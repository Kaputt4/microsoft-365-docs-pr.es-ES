---
title: Investigar usuarios en el Centro de seguridad de Microsoft 365
description: investigar usuarios en el Centro de seguridad de Microsoft 365
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861278"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="e5b9c-104">Investigar usuarios en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5b9c-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e5b9c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e5b9c-105">**Applies to:**</span></span>

- <span data-ttu-id="e5b9c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5b9c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e5b9c-107">Parte de la investigación de incidentes puede incluir cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="e5b9c-108">Comience con la **pestaña Usuarios** para un incidente de incidentes & **alertas** >*incidentes>* **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

<span data-ttu-id="e5b9c-110">Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="e5b9c-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5b9c-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="e5b9c-113">Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="e5b9c-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5b9c-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="e5b9c-116">También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la **página** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="e5b9c-117">La página de usuario del Centro de seguridad de Microsoft 365 combina información de Microsoft Defender para endpoint, Microsoft Defender para Identidad y Microsoft Cloud App Security (en función de las licencias que tenga).</span><span class="sxs-lookup"><span data-stu-id="e5b9c-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="e5b9c-118">Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="e5b9c-119">Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos recientes y las alertas que contribuyeron al riesgo general del usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="e5b9c-120">Desde esta página, puede realizar estas acciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="e5b9c-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="e5b9c-121">Marcar la cuenta de usuario como comprometida</span><span class="sxs-lookup"><span data-stu-id="e5b9c-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="e5b9c-122">Requerir que el usuario inicie sesión de nuevo</span><span class="sxs-lookup"><span data-stu-id="e5b9c-122">Require the user to sign in again</span></span>
- <span data-ttu-id="e5b9c-123">Suspender la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e5b9c-123">Suspend the user account</span></span>
- <span data-ttu-id="e5b9c-124">Consulta la configuración de la cuenta de usuario de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e5b9c-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="e5b9c-125">Ver los archivos propiedad de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e5b9c-125">View the files owned by the user account</span></span>
- <span data-ttu-id="e5b9c-126">Ver archivos compartidos con este usuario.</span><span class="sxs-lookup"><span data-stu-id="e5b9c-126">View files shared with this user.</span></span> 

<span data-ttu-id="e5b9c-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e5b9c-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones en una cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="e5b9c-129">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e5b9c-129">Related topics</span></span>

- [<span data-ttu-id="e5b9c-130">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="e5b9c-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e5b9c-131">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="e5b9c-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e5b9c-132">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="e5b9c-132">Manage incidents</span></span>](manage-incidents.md)