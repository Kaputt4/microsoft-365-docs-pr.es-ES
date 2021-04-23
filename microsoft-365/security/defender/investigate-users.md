---
title: Analizar usuarios en el Centro de seguridad de Microsoft 365
description: Analizar usuarios en el Centro de seguridad de Microsoft 365
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
ms.openlocfilehash: 2fd9b958cdbdaf22346f8171c789f2ca9a8336d1
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957612"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="168d0-104">Analizar usuarios en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="168d0-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="168d0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="168d0-105">**Applies to:**</span></span>

- <span data-ttu-id="168d0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="168d0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="168d0-107">Parte del análisis de incidentes puede incluir cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="168d0-108">Comience con la **pestaña Usuarios** para un incidente de incidentes & **alertas** >*incidentes>* **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="168d0-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Ejemplo de una página Usuarios para un incidente":::

<span data-ttu-id="168d0-110">Para obtener un resumen rápido de una cuenta de usuario para el incidente, seleccione la marca de verificación junto al nombre de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="168d0-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="168d0-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Ejemplo del panel de resumen de la cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::

> [!NOTE]
> <span data-ttu-id="168d0-113">La página Usuario muestra la organización de Azure Active Directory (AD), así como los grupos, lo que le ayuda a comprender los grupos y permisos asociados con un usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="168d0-114">En esta página desplegable, puede revisar la información de amenazas del usuario, incluidos los incidentes actuales, las alertas activas y el nivel de riesgo, así como la exposición del usuario, cuentas, dispositivos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="168d0-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="168d0-115">Además, puede realizar acciones directamente en el Centro de seguridad de Microsoft 365 para abordar un usuario en peligro, confirmando que el usuario está en peligro o requiriendo que inicie sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="168d0-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="168d0-116">Desde aquí, puede seleccionar **Ir a la página de usuario** para ver los detalles de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="168d0-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="168d0-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Ejemplo de la página de cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="168d0-119">También puede ver esta página seleccionando el nombre de la cuenta de usuario de la lista de la **página** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="168d0-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="168d0-120">La página de usuario del Centro de seguridad de Microsoft 365 combina información de Microsoft Defender para endpoint, Microsoft Defender para Identidad y Microsoft Cloud App Security (en función de las licencias que tenga).</span><span class="sxs-lookup"><span data-stu-id="168d0-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="168d0-121">Esta página muestra información específica del riesgo de seguridad de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="168d0-122">Esto incluye una puntuación que ayuda a evaluar el riesgo y los eventos recientes y las alertas que contribuyeron al riesgo general del usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="168d0-123">Desde esta página, puede realizar estas acciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="168d0-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="168d0-124">Marcar la cuenta de usuario como comprometida</span><span class="sxs-lookup"><span data-stu-id="168d0-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="168d0-125">Requerir que el usuario inicie sesión de nuevo</span><span class="sxs-lookup"><span data-stu-id="168d0-125">Require the user to sign in again</span></span>
- <span data-ttu-id="168d0-126">Suspender la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="168d0-126">Suspend the user account</span></span>
- <span data-ttu-id="168d0-127">Consulta la configuración de la cuenta de usuario de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="168d0-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="168d0-128">Ver los archivos propiedad de la cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="168d0-128">View the files owned by the user account</span></span>
- <span data-ttu-id="168d0-129">Ver archivos compartidos con este usuario.</span><span class="sxs-lookup"><span data-stu-id="168d0-129">View files shared with this user.</span></span> 

<span data-ttu-id="168d0-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="168d0-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Ejemplo de las acciones en una cuenta de usuario para un incidente en el Centro de seguridad de Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="168d0-132">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="168d0-132">Related topics</span></span>

- [<span data-ttu-id="168d0-133">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="168d0-133">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="168d0-134">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="168d0-134">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="168d0-135">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="168d0-135">Manage incidents</span></span>](manage-incidents.md)