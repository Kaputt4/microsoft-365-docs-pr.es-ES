---
title: Solucionar problemas de integración de herramientas SIEM en Microsoft Defender para endpoint
description: Solucionar problemas que pueden surgir al usar herramientas SIEM con Microsoft Defender para endpoint.
keywords: troubleshoot, siem, client secret, secret
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689454"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="c8f36-104">Solucionar problemas de integración de la herramienta SIEM</span><span class="sxs-lookup"><span data-stu-id="c8f36-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c8f36-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c8f36-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8f36-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c8f36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8f36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8f36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c8f36-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c8f36-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c8f36-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c8f36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="c8f36-110">Es posible que deba solucionar problemas al extraer detecciones en las herramientas SIEM.</span><span class="sxs-lookup"><span data-stu-id="c8f36-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="c8f36-111">En esta página se proporcionan pasos detallados para solucionar problemas que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="c8f36-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="c8f36-112">Obtenga información sobre cómo obtener un nuevo secreto de cliente</span><span class="sxs-lookup"><span data-stu-id="c8f36-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="c8f36-113">Si el secreto de cliente expira o si ha perdido la copia proporcionada al habilitar la aplicación de herramienta SIEM, tendrá que obtener un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="c8f36-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="c8f36-114">Inicie sesión en [el Portal de administración de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c8f36-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="c8f36-115">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="c8f36-116">Seleccione el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c8f36-116">Select your tenant.</span></span>

4. <span data-ttu-id="c8f36-117">Haga **clic en Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-117">Click **App registrations**.</span></span> <span data-ttu-id="c8f36-118">A continuación, en la lista aplicaciones, seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c8f36-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="c8f36-119">Seleccione **la sección** Claves, proporcione una descripción de clave y especifique la duración de validez de la clave.</span><span class="sxs-lookup"><span data-stu-id="c8f36-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="c8f36-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-120">Click **Save**.</span></span> <span data-ttu-id="c8f36-121">Se muestra el valor de la clave.</span><span class="sxs-lookup"><span data-stu-id="c8f36-121">The key value is displayed.</span></span>

7. <span data-ttu-id="c8f36-122">Copie el valor y guárdelo en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="c8f36-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="c8f36-123">Error al obtener un token de acceso de actualización</span><span class="sxs-lookup"><span data-stu-id="c8f36-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="c8f36-124">Si se produce un error al intentar obtener un token de actualización al usar la API de inteligencia de amenazas o las herramientas SIEM, deberá agregar la dirección URL de respuesta para la aplicación relevante en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8f36-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="c8f36-125">Inicie sesión en [el Portal de administración de Azure](https://ms.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c8f36-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="c8f36-126">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="c8f36-127">Seleccione el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c8f36-127">Select your tenant.</span></span>

4. <span data-ttu-id="c8f36-128">Haga **clic en Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-128">Click **App Registrations**.</span></span> <span data-ttu-id="c8f36-129">A continuación, en la lista aplicaciones, seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c8f36-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="c8f36-130">Agregue la siguiente dirección URL:</span><span class="sxs-lookup"><span data-stu-id="c8f36-130">Add the following URL:</span></span>
   - <span data-ttu-id="c8f36-131">Para la Unión Europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="c8f36-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="c8f36-132">Para el Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="c8f36-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="c8f36-133">Para Estados Unidos:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="c8f36-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="c8f36-134">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c8f36-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="c8f36-135">Error al habilitar la aplicación de conector SIEM</span><span class="sxs-lookup"><span data-stu-id="c8f36-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="c8f36-136">Si se produce un error al intentar habilitar la aplicación de conector SIEM, compruebe la configuración del bloqueador de elementos emergentes del explorador.</span><span class="sxs-lookup"><span data-stu-id="c8f36-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="c8f36-137">Puede que esté bloqueando la nueva ventana que se abre al habilitar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c8f36-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="c8f36-138">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c8f36-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8f36-139">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c8f36-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="c8f36-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c8f36-140">Related topics</span></span>
- [<span data-ttu-id="c8f36-141">Habilitar la integración de SIEM en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="c8f36-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="c8f36-142">Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="c8f36-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="c8f36-143">Extraer detecciones a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="c8f36-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="c8f36-144">Campos de Microsoft Defender para detección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="c8f36-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="c8f36-145">Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST</span><span class="sxs-lookup"><span data-stu-id="c8f36-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
