---
title: 'Supervisión de aplicaciones & de informes: Centro de seguridad'
description: Obtenga información sobre cómo obtener más información sobre el uso de aplicaciones en la nube en la organización. Incluye distintos tipos de aplicaciones, su nivel de riesgo y alertas.
keywords: seguridad, malware, Microsoft 365, M365, Security Center, monitor, Report, apps
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f73c6b010677cdc481655d1d5310872fd1a99126
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920519"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="fc6fe-105">Supervisión y generación de informes de aplicaciones en el centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc6fe-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc6fe-106">Estos informes proporcionan más información sobre cómo se usan las aplicaciones en la nube en la organización.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="fc6fe-107">Incluye distintos tipos de aplicaciones, su nivel de riesgo y alertas.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="fc6fe-108">Supervisión de cuentas de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="fc6fe-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="fc6fe-109">La **protección de correo electrónico** muestra las cuentas de correo electrónico en riesgo.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="fc6fe-110">Puede seleccionar una cuenta para investigar con más detalle en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Tarjeta de protección de correo electrónico](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="fc6fe-112">Supervisar los permisos de aplicación concedidos por los usuarios</span><span class="sxs-lookup"><span data-stu-id="fc6fe-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="fc6fe-113">**Cloud App Security: aplicaciones de OAuth** enumera las aplicaciones descubiertas por Cloud App Security a las que los usuarios han concedido permisos.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="fc6fe-114">El catálogo de riesgos de Cloud App Security incluye más de 16.000 aplicaciones que se evalúan con más de 70 factores de riesgo.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="fc6fe-115">Los factores de riesgo comienzan a partir de información general, como el editor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="fc6fe-116">A continuación, se desplaza a medidas y controles de seguridad, por ejemplo, si la aplicación admite el cifrado en reposo o proporciona un registro de auditoría de la actividad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Tarjeta de aplicaciones de OAuth para Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="fc6fe-118">Supervisar las cuentas de usuario de aplicación de nube</span><span class="sxs-lookup"><span data-stu-id="fc6fe-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="fc6fe-119">**Cuentas de aplicación de nube para revisión** enumera las cuentas que pueden requerir atención.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Cuentas de aplicación de nube para la tarjeta de revisión](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="fc6fe-121">Comprender qué aplicaciones en la nube se usan</span><span class="sxs-lookup"><span data-stu-id="fc6fe-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="fc6fe-122">Las **aplicaciones en la nube detectadas (categorías)** muestran qué tipos de aplicaciones se usan en la organización.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="fc6fe-123">Se vincula al panel de detección en la nube de Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="fc6fe-124">Para obtener más información, consulte [Inicio rápido: trabajar con aplicaciones detectadas](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="fc6fe-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Tarjeta de categorías de aplicaciones en la nube detectadas](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="fc6fe-126">Supervisar dónde acceden los usuarios a las aplicaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="fc6fe-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="fc6fe-127">Las **ubicaciones de actividad de aplicación de nube** muestran dónde los usuarios están accediendo a las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Tarjeta de ubicaciones de actividad de aplicación en la nube](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="fc6fe-129">Supervisión del estado de las cargas de trabajo de la infraestructura</span><span class="sxs-lookup"><span data-stu-id="fc6fe-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="fc6fe-130">**Estado** de la infraestructura muestra alertas de estado de mantenimiento para cargas de trabajo de infraestructura en Azure defender.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="fc6fe-131">Azure defender ofrece administración de seguridad unificada y defender para Office 365 en cargas de trabajo locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="fc6fe-132">Puede recopilar, buscar y analizar datos de seguridad de diferentes orígenes, incluidos firewalls y otras soluciones de asociados.</span><span class="sxs-lookup"><span data-stu-id="fc6fe-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="fc6fe-133">Para obtener más información, vea la [documentación de Azure defender](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="fc6fe-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Tarjeta de mantenimiento de la infraestructura](../../media/infrastructure-health.png)
