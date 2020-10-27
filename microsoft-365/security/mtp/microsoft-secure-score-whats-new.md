---
title: Novedades de la puntuación segura de Microsoft
description: Describe los cambios que han sucedido a la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365
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
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 71316d6c53862b80178d06726f7c249a2491d659
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769035"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="5fd83-104">Novedades de la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5fd83-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5fd83-105">Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="5fd83-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="5fd83-106">Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="5fd83-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

## <a name="august-2020"></a><span data-ttu-id="5fd83-107">Agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="5fd83-107">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="5fd83-108">Se actualizó la acción de mejora para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5fd83-108">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="5fd83-109">Habilitar la Directiva para bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="5fd83-109">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="5fd83-110">Incompatibilidad con la puntuación segura de la identidad y la API de Graph</span><span class="sxs-lookup"><span data-stu-id="5fd83-110">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="5fd83-111">En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado.</span><span class="sxs-lookup"><span data-stu-id="5fd83-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="5fd83-112">Estos cambios permiten una vista más flexible y precisa de la postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5fd83-112">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="5fd83-113">Sin embargo, estas actualizaciones han hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de identidad y la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="5fd83-113">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="5fd83-114">En el tiempo, la calificación de identidad segura y la API de Graph adoptarán el nuevo modelo de calificación.</span><span class="sxs-lookup"><span data-stu-id="5fd83-114">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="5fd83-115">Hasta entonces, los clientes verán las diferencias en los resultados indicados por la puntuación segura de Microsoft, la puntuación segura de identidad y la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="5fd83-115">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="5fd83-116">Lamentamos las molestias y los motivos para garantizar que estas experiencias sean más compatibles en el futuro.</span><span class="sxs-lookup"><span data-stu-id="5fd83-116">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="5fd83-117">Acciones de mejora actualizadas</span><span class="sxs-lookup"><span data-stu-id="5fd83-117">Updated improvement actions</span></span>

- <span data-ttu-id="5fd83-118">Se agregaron acciones de mejora de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5fd83-118">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="5fd83-119">Se agregaron acciones de mejora de protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="5fd83-119">Added Azure Advanced Threat Protection improvement actions</span></span>
- <span data-ttu-id="5fd83-120">Compatibilidad con las recomendaciones de seguridad de la [vulnerabilidad ATP & vulnerabilidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="5fd83-120">Support for Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="5fd83-121">Todas las recomendaciones de seguridad emitidas suministradas por TVM ya están disponibles</span><span class="sxs-lookup"><span data-stu-id="5fd83-121">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="5fd83-122">Interfaz y funciones actualizadas</span><span class="sxs-lookup"><span data-stu-id="5fd83-122">Updated interface and functionality</span></span>

* <span data-ttu-id="5fd83-123">Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo</span><span class="sxs-lookup"><span data-stu-id="5fd83-123">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="5fd83-124">Nuevas formas de realizar un seguimiento y evaluar su puntuación</span><span class="sxs-lookup"><span data-stu-id="5fd83-124">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="5fd83-125">Mejor seguimiento y comprensión de las regresiones de puntuación</span><span class="sxs-lookup"><span data-stu-id="5fd83-125">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="5fd83-126">Filtrar, etiquetar, buscar y agrupar las acciones de mejora</span><span class="sxs-lookup"><span data-stu-id="5fd83-126">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="5fd83-127">Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas</span><span class="sxs-lookup"><span data-stu-id="5fd83-127">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="5fd83-128">Y mucho más.</span><span class="sxs-lookup"><span data-stu-id="5fd83-128">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5fd83-129">Queremos conocer su opinión</span><span class="sxs-lookup"><span data-stu-id="5fd83-129">We want to hear from you</span></span>

<span data-ttu-id="5fd83-130">Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="5fd83-130">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5fd83-131">Estamos supervisando la comunidad y le proporcionaremos ayuda.</span><span class="sxs-lookup"><span data-stu-id="5fd83-131">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5fd83-132">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="5fd83-132">Related resources</span></span>

- [<span data-ttu-id="5fd83-133">Evaluar su postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="5fd83-133">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="5fd83-134">Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos</span><span class="sxs-lookup"><span data-stu-id="5fd83-134">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5fd83-135">Próximas novedades</span><span class="sxs-lookup"><span data-stu-id="5fd83-135">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
