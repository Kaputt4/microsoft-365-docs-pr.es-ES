---
title: Investigan usuarios en Microsoft 365 Defender
description: Investigue a los usuarios por un incidente en el centro de seguridad de Microsoft 365.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, identidades, datos, dispositivos, aplicaciones, incidentes, análisis, respuesta
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
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572806"
---
# <a name="investigate-users-in-microsoft-365-defender"></a><span data-ttu-id="04fad-104">Investigan usuarios en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04fad-104">Investigate users in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="04fad-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="04fad-105">**Applies to:**</span></span>

- <span data-ttu-id="04fad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04fad-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="04fad-107">Parte de la investigación de incidentes puede incluir cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="04fad-108">Comience con la pestaña **Usuarios** para detectar un incidente de **incidentes & alertas >** *incidente* **> usuarios.**</span><span class="sxs-lookup"><span data-stu-id="04fad-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página de usuarios para un incidente":::

<span data-ttu-id="04fad-110">Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="04fad-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04fad-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="04fad-113">La página Usuario muestra Azure Active Directory organización (Azure AD), así como grupos, lo que le ayuda a comprender los grupos y permisos asociados a un usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-113">The User page shows Azure Active Directory (Azure AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="04fad-114">En esta página desplegable, puede revisar la información de amenazas de los usuarios, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, las cuentas, los dispositivos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="04fad-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="04fad-115">Además, puede tomar medidas directamente en el centro de seguridad Microsoft 365 para dirigirse a un usuario comprometido, confirmando que el usuario está comprometido o requiriendo que vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="04fad-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="04fad-116">Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="04fad-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04fad-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de la cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::

<span data-ttu-id="04fad-119">También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la página **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="04fad-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="04fad-120">La página de usuario del centro de seguridad de Microsoft 365 combina información de Microsoft Defender para Endpoint, Microsoft Defender for Identity y Microsoft Cloud App Security (en función de las licencias que tenga).</span><span class="sxs-lookup"><span data-stu-id="04fad-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="04fad-121">Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="04fad-122">Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos y alertas recientes que contribuyeron al riesgo general del usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="04fad-123">Desde esta página, puede realizar estas acciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="04fad-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="04fad-124">Marque la cuenta de usuario como comprometida</span><span class="sxs-lookup"><span data-stu-id="04fad-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="04fad-125">Requerir que el usuario vuelva a iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="04fad-125">Require the user to sign in again</span></span>
- <span data-ttu-id="04fad-126">Suspender la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="04fad-126">Suspend the user account</span></span>
- <span data-ttu-id="04fad-127">Consulte la configuración de la cuenta de usuario de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="04fad-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="04fad-128">Ver los archivos propiedad de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="04fad-128">View the files owned by the user account</span></span>
- <span data-ttu-id="04fad-129">Ver archivos compartidos con este usuario.</span><span class="sxs-lookup"><span data-stu-id="04fad-129">View files shared with this user.</span></span> 

<span data-ttu-id="04fad-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="04fad-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones de una cuenta de usuario para un incidente en el centro de seguridad de Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="04fad-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="04fad-132">Next steps</span></span>

<span data-ttu-id="04fad-133">Según sea necesario para incidentes en proceso, continúe su [investigación.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="04fad-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04fad-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="04fad-134">See also</span></span>

- [<span data-ttu-id="04fad-135">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="04fad-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="04fad-136">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="04fad-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="04fad-137">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="04fad-137">Manage incidents</span></span>](manage-incidents.md)