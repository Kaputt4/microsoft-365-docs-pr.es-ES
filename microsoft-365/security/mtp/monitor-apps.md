---
title: Informes de supervisión & aplicaciones- Centro de seguridad
description: Obtén información sobre cómo obtener más información sobre el uso de aplicaciones en la nube en tu organización. Incluye diferentes tipos de aplicaciones, su nivel de riesgo y alertas.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, aplicaciones
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930527"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="d48d2-105">Supervisión e informes de aplicaciones en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d48d2-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d48d2-106">Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en su organización.</span><span class="sxs-lookup"><span data-stu-id="d48d2-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="d48d2-107">Incluye diferentes tipos de aplicaciones, su nivel de riesgo y alertas.</span><span class="sxs-lookup"><span data-stu-id="d48d2-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="d48d2-108">Supervisión de cuentas de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="d48d2-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="d48d2-109">**La protección de correo** electrónico muestra cuentas de correo electrónico en riesgo.</span><span class="sxs-lookup"><span data-stu-id="d48d2-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="d48d2-110">Puede seleccionar una cuenta para investigar más en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d48d2-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Tarjeta de protección de correo electrónico](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="d48d2-112">Supervisar los permisos de aplicación concedidos por los usuarios</span><span class="sxs-lookup"><span data-stu-id="d48d2-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="d48d2-113">**Cloud App Security: las aplicaciones de OAuth** enumeran las aplicaciones detectadas por Cloud App Security a las que los usuarios han concedido permisos.</span><span class="sxs-lookup"><span data-stu-id="d48d2-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="d48d2-114">El catálogo de riesgos de Cloud App Security incluye más de 16 000 aplicaciones que se evalúan con más de 70 factores de riesgo.</span><span class="sxs-lookup"><span data-stu-id="d48d2-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="d48d2-115">Los factores de riesgo empiezan por la información general, como el editor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d48d2-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="d48d2-116">A continuación, pasa a medidas de seguridad y controles, como si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="d48d2-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Tarjeta de aplicaciones OAuth de Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="d48d2-118">Supervisar cuentas de usuario de aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="d48d2-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="d48d2-119">**Las cuentas de aplicación en la nube para revisión** enumeran las cuentas que pueden requerir atención.</span><span class="sxs-lookup"><span data-stu-id="d48d2-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cuentas de aplicación en la nube para la tarjeta de revisión](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="d48d2-121">Comprender qué aplicaciones en la nube se usan</span><span class="sxs-lookup"><span data-stu-id="d48d2-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="d48d2-122">**Las aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización.</span><span class="sxs-lookup"><span data-stu-id="d48d2-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="d48d2-123">Se vincula al panel de detección de nube en Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d48d2-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="d48d2-124">Para obtener más información, consulta [Inicio rápido: Trabajar con aplicaciones detectadas.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="d48d2-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Tarjeta de categorías de aplicaciones en la nube detectadas](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="d48d2-126">Supervisar dónde acceden los usuarios a las aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="d48d2-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="d48d2-127">**Las ubicaciones de actividad de aplicaciones en la** nube muestran dónde obtienen acceso los usuarios a las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="d48d2-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Tarjeta de ubicaciones de actividad de la aplicación en la nube](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="d48d2-129">Supervisar el estado de las cargas de trabajo de infraestructura</span><span class="sxs-lookup"><span data-stu-id="d48d2-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="d48d2-130">**El estado de la** infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="d48d2-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="d48d2-131">Azure Defender proporciona administración de seguridad unificada y Defender para Office 365 en cargas de trabajo locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="d48d2-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="d48d2-132">Puede recopilar, buscar y analizar datos de seguridad de diferentes orígenes, incluidos firewalls y otras soluciones de asociados.</span><span class="sxs-lookup"><span data-stu-id="d48d2-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="d48d2-133">Para obtener más información, consulte [la documentación de Azure Defender.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="d48d2-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Tarjeta de estado de la infraestructura](../../media/infrastructure-health.png)
