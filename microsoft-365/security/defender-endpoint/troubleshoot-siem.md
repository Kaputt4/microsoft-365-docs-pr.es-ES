---
title: Solucionar problemas de integración de herramientas SIEM en ATP de Microsoft Defender
description: Solucionar problemas que pueden surgir al usar herramientas SIEM con ATP de Microsoft Defender.
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
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072875"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="47be7-104">Solucionar problemas de integración de herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="47be7-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47be7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="47be7-105">**Applies to:**</span></span>
- [<span data-ttu-id="47be7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="47be7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="47be7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="47be7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="47be7-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="47be7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47be7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="47be7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="47be7-110">Es posible que deba solucionar problemas al extraer detecciones en las herramientas SIEM.</span><span class="sxs-lookup"><span data-stu-id="47be7-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="47be7-111">En esta página se proporcionan pasos detallados para solucionar problemas que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="47be7-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="47be7-112">Obtenga información sobre cómo obtener un nuevo secreto de cliente</span><span class="sxs-lookup"><span data-stu-id="47be7-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="47be7-113">Si el secreto de cliente expira o si ha perdido la copia proporcionada al habilitar la aplicación de herramienta SIEM, tendrá que obtener un nuevo secreto.</span><span class="sxs-lookup"><span data-stu-id="47be7-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="47be7-114">Inicie sesión en [el Portal de administración de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="47be7-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="47be7-115">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="47be7-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="47be7-116">Seleccione el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="47be7-116">Select your tenant.</span></span>

4. <span data-ttu-id="47be7-117">Haga **clic en Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="47be7-117">Click **App registrations**.</span></span> <span data-ttu-id="47be7-118">A continuación, en la lista aplicaciones, seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47be7-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="47be7-119">Seleccione **la sección** Claves, proporcione una descripción de clave y especifique la duración de validez de la clave.</span><span class="sxs-lookup"><span data-stu-id="47be7-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="47be7-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47be7-120">Click **Save**.</span></span> <span data-ttu-id="47be7-121">Se muestra el valor de la clave.</span><span class="sxs-lookup"><span data-stu-id="47be7-121">The key value is displayed.</span></span>

7. <span data-ttu-id="47be7-122">Copie el valor y guárdelo en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="47be7-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="47be7-123">Error al obtener un token de acceso de actualización</span><span class="sxs-lookup"><span data-stu-id="47be7-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="47be7-124">Si se produce un error al intentar obtener un token de actualización al usar la API de inteligencia de amenazas o las herramientas SIEM, deberá agregar la dirección URL de respuesta para la aplicación relevante en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47be7-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="47be7-125">Inicie sesión en [el Portal de administración de Azure](https://ms.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="47be7-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="47be7-126">Seleccione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="47be7-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="47be7-127">Seleccione el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="47be7-127">Select your tenant.</span></span>

4. <span data-ttu-id="47be7-128">Haga **clic en Registros de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="47be7-128">Click **App Registrations**.</span></span> <span data-ttu-id="47be7-129">A continuación, en la lista aplicaciones, seleccione la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47be7-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="47be7-130">Agregue la siguiente dirección URL:</span><span class="sxs-lookup"><span data-stu-id="47be7-130">Add the following URL:</span></span>
   - <span data-ttu-id="47be7-131">Para la Unión Europea: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="47be7-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="47be7-132">Para el Reino Unido: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="47be7-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="47be7-133">Para Estados Unidos:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="47be7-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="47be7-134">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47be7-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="47be7-135">Error al habilitar la aplicación de conector SIEM</span><span class="sxs-lookup"><span data-stu-id="47be7-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="47be7-136">Si se produce un error al intentar habilitar la aplicación de conector SIEM, compruebe la configuración del bloqueador de elementos emergentes del explorador.</span><span class="sxs-lookup"><span data-stu-id="47be7-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="47be7-137">Puede que esté bloqueando la nueva ventana que se abre al habilitar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="47be7-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="47be7-138">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="47be7-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="47be7-139">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="47be7-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="47be7-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47be7-140">Related topics</span></span>
- [<span data-ttu-id="47be7-141">Habilitar la integración de SIEM en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="47be7-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="47be7-142">Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="47be7-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="47be7-143">Extraer detecciones a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="47be7-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="47be7-144">Campos de Microsoft Defender para detección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="47be7-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="47be7-145">Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST</span><span class="sxs-lookup"><span data-stu-id="47be7-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
