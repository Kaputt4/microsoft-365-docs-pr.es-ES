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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49374000"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="e2ad5-104">Novedades de la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2ad5-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e2ad5-105">Para convertir la puntuación segura de Microsoft en un mejor representante de su postura de seguridad, hemos realizado algunos cambios.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="e2ad5-106">Para obtener información sobre los cambios planeados, consulte [¿qué viene con la puntuación segura de Microsoft?](microsoft-secure-score-whats-coming.md).</span><span class="sxs-lookup"><span data-stu-id="e2ad5-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="e2ad5-107">Se puede encontrar la puntuación segura de Microsoft en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="e2ad5-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="e2ad5-108">Noviembre de 2020</span><span class="sxs-lookup"><span data-stu-id="e2ad5-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="e2ad5-109">Se agregaron 3 acciones de mejora relacionadas con los servicios para Microsoft defender para el punto de conexión (ATP anterior de Microsoft defender):</span><span class="sxs-lookup"><span data-stu-id="e2ad5-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="e2ad5-110">Corregir la ruta del servicio sin comillas para los servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="e2ad5-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="e2ad5-111">Cambiar la ruta de acceso del ejecutable del servicio a una ubicación común protegida</span><span class="sxs-lookup"><span data-stu-id="e2ad5-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="e2ad5-112">Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el registro de Windows</span><span class="sxs-lookup"><span data-stu-id="e2ad5-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="e2ad5-113">Octubre de 2020</span><span class="sxs-lookup"><span data-stu-id="e2ad5-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e2ad5-114">Quitar la acción de mejora relacionada con Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e2ad5-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="e2ad5-115">Establecer la comprobación de contenido Web de aplicación de la tienda Windows de Microsoft defender para advertir</span><span class="sxs-lookup"><span data-stu-id="e2ad5-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="e2ad5-116">Agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="e2ad5-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="e2ad5-117">Se actualizó la acción de mejora para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e2ad5-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="e2ad5-118">Habilitar la Directiva para bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="e2ad5-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="e2ad5-119">Incompatibilidad con la puntuación segura de la identidad y la API de Graph</span><span class="sxs-lookup"><span data-stu-id="e2ad5-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="e2ad5-120">En la versión más reciente de la puntuación segura de Microsoft, se ha lanzado un modelo de resultados mejorado.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="e2ad5-121">Estos cambios permiten una vista más flexible y precisa de la postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="e2ad5-122">Sin embargo, estas actualizaciones han hecho que la puntuación segura de Microsoft sea incompatible temporalmente con la puntuación segura de identidad y la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="e2ad5-123">En el tiempo, la calificación de identidad segura y la API de Graph adoptarán el nuevo modelo de calificación.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="e2ad5-124">Hasta entonces, los clientes verán las diferencias en los resultados indicados por la puntuación segura de Microsoft, la puntuación segura de identidad y la API de Graph.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="e2ad5-125">Lamentamos las molestias y los motivos para garantizar que estas experiencias sean más compatibles en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="e2ad5-126">Acciones de mejora actualizadas</span><span class="sxs-lookup"><span data-stu-id="e2ad5-126">Updated improvement actions</span></span>

- <span data-ttu-id="e2ad5-127">Se agregaron acciones de mejora de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e2ad5-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="e2ad5-128">Se agregaron las acciones de Microsoft defender para mejorar la identidad</span><span class="sxs-lookup"><span data-stu-id="e2ad5-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="e2ad5-129">Soporte para la amenaza de Microsoft defender para la amenaza de extremo & recomendaciones de seguridad para la [Administración de vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="e2ad5-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="e2ad5-130">Todas las recomendaciones de seguridad emitidas suministradas por TVM ya están disponibles</span><span class="sxs-lookup"><span data-stu-id="e2ad5-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="e2ad5-131">Interfaz y funciones actualizadas</span><span class="sxs-lookup"><span data-stu-id="e2ad5-131">Updated interface and functionality</span></span>

* <span data-ttu-id="e2ad5-132">Todas las nuevas métricas y vistas de tendencias para CISO y discusiones de nivel de liderazgo</span><span class="sxs-lookup"><span data-stu-id="e2ad5-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="e2ad5-133">Nuevas formas de realizar un seguimiento y evaluar su puntuación</span><span class="sxs-lookup"><span data-stu-id="e2ad5-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="e2ad5-134">Mejor seguimiento y comprensión de las regresiones de puntuación</span><span class="sxs-lookup"><span data-stu-id="e2ad5-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="e2ad5-135">Filtrar, etiquetar, buscar y agrupar las acciones de mejora</span><span class="sxs-lookup"><span data-stu-id="e2ad5-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="e2ad5-136">Administrar hacia sus metas futuras mediante proyecciones de puntuación y acciones planeadas</span><span class="sxs-lookup"><span data-stu-id="e2ad5-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="e2ad5-137">Y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e2ad5-138">Queremos conocer su opinión</span><span class="sxs-lookup"><span data-stu-id="e2ad5-138">We want to hear from you</span></span>

<span data-ttu-id="e2ad5-139">Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="e2ad5-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e2ad5-140">Estamos supervisando la comunidad y le proporcionaremos ayuda.</span><span class="sxs-lookup"><span data-stu-id="e2ad5-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e2ad5-141">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2ad5-141">Related resources</span></span>

- [<span data-ttu-id="e2ad5-142">Evaluar su postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2ad5-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e2ad5-143">Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos</span><span class="sxs-lookup"><span data-stu-id="e2ad5-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e2ad5-144">Próximas novedades</span><span class="sxs-lookup"><span data-stu-id="e2ad5-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
