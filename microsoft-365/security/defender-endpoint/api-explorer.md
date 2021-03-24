---
title: Explorador de API en ATP de Microsoft Defender
ms.reviewer: ''
description: Usar el Explorador de API para crear y realizar consultas api, probar y enviar solicitudes para cualquier API disponible
keywords: api, explorer, send, request, get, post,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0cfe5227d5d1cdb1f1f4eaea2c859937d7e75264
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073099"
---
# <a name="api-explorer"></a><span data-ttu-id="7ffb4-104">Explorador de API</span><span class="sxs-lookup"><span data-stu-id="7ffb4-104">API Explorer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ffb4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7ffb4-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ffb4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7ffb4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


<span data-ttu-id="7ffb4-107">El Explorador de API de Microsoft Defender para Endpoint es una herramienta que le ayuda a explorar varias API de Defender for Endpoint de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-107">The Microsoft Defender for Endpoint API Explorer is a tool that helps you explore various Defender for Endpoint APIs interactively.</span></span> 

<span data-ttu-id="7ffb4-108">El Explorador de API facilita la construcción y la realización de consultas api, pruebas y envío de solicitudes para cualquier punto de conexión disponible de Defender para endpoint API.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-108">The API Explorer makes it easy to construct and do API queries, test, and send requests for any available Defender for Endpoint API endpoint.</span></span> <span data-ttu-id="7ffb4-109">Use el Explorador de API para realizar acciones o buscar datos que aún no estén disponibles a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-109">Use the API Explorer to take actions or find data that might not yet be available through the user interface.</span></span>

<span data-ttu-id="7ffb4-110">La herramienta es útil durante el desarrollo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-110">The tool is useful during app development.</span></span> <span data-ttu-id="7ffb4-111">Le permite realizar consultas api que respetan la configuración de acceso de usuario, lo que reduce la necesidad de generar tokens de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-111">It allows you to perform API queries that respect your user access settings, reducing the need to generate access tokens.</span></span>

<span data-ttu-id="7ffb4-112">También puede usar la herramienta para explorar la galería de consultas de ejemplo, copiar ejemplos de código de resultado y generar información de depuración.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-112">You can also use the tool to explore the gallery of sample queries, copy result code samples, and generate debug information.</span></span>

<span data-ttu-id="7ffb4-113">Con el Explorador de API, puede:</span><span class="sxs-lookup"><span data-stu-id="7ffb4-113">With the API Explorer, you can:</span></span>

- <span data-ttu-id="7ffb4-114">Ejecutar solicitudes para cualquier método y ver respuestas en tiempo real</span><span class="sxs-lookup"><span data-stu-id="7ffb4-114">Run requests for any method and see responses in real-time</span></span>
- <span data-ttu-id="7ffb4-115">Examinar rápidamente los ejemplos de API y obtener información sobre los parámetros que admiten</span><span class="sxs-lookup"><span data-stu-id="7ffb4-115">Quickly browse through the API samples and learn what parameters they support</span></span>
- <span data-ttu-id="7ffb4-116">Realizar llamadas API con facilidad; no es necesario autenticar más allá del inicio de sesión del portal de administración</span><span class="sxs-lookup"><span data-stu-id="7ffb4-116">Make API calls with ease; no need to authenticate beyond the management portal sign in</span></span>

## <a name="access-api-explorer"></a><span data-ttu-id="7ffb4-117">Explorador de API de Access</span><span class="sxs-lookup"><span data-stu-id="7ffb4-117">Access API Explorer</span></span>

<span data-ttu-id="7ffb4-118">En el menú de navegación izquierdo, seleccione **Partners & API**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-118">From the left navigation menu, select **Partners & APIs** > **API Explorer**.</span></span>

## <a name="supported-apis"></a><span data-ttu-id="7ffb4-119">API compatibles</span><span class="sxs-lookup"><span data-stu-id="7ffb4-119">Supported APIs</span></span>

<span data-ttu-id="7ffb4-120">El Explorador de API admite todas las API que ofrece Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-120">API Explorer supports all the APIs offered by Defender for Endpoint.</span></span>
  
<span data-ttu-id="7ffb4-121">La lista de API admitidas está disponible en la [documentación de las API.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7ffb4-121">The list of supported APIs is available in the [APIs documentation](apis-intro.md).</span></span> 

## <a name="get-started-with-the-api-explorer"></a><span data-ttu-id="7ffb4-122">Introducción al Explorador de API</span><span class="sxs-lookup"><span data-stu-id="7ffb4-122">Get started with the API Explorer</span></span>

1. <span data-ttu-id="7ffb4-123">En el panel izquierdo, hay una lista de solicitudes de ejemplo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-123">In the left pane, there is a list of sample requests that you can use.</span></span> 
2. <span data-ttu-id="7ffb4-124">Siga los vínculos y haga clic **en Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-124">Follow the links and click **Run query**.</span></span> 

<span data-ttu-id="7ffb4-125">Algunos de los ejemplos pueden requerir la especificación de un parámetro en la dirección URL, por ejemplo, {machine- ID}.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-125">Some of the samples may require specifying a parameter in the URL, for example, {machine- ID}.</span></span>

## <a name="faq"></a><span data-ttu-id="7ffb4-126">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="7ffb4-126">FAQ</span></span>

<span data-ttu-id="7ffb4-127">**¿Necesito tener un token de API para usar el Explorador de API?**</span><span class="sxs-lookup"><span data-stu-id="7ffb4-127">**Do I need to have an API token to use the API Explorer?**</span></span> <br>
<span data-ttu-id="7ffb4-128">Las credenciales para obtener acceso a una API no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-128">Credentials to access an API aren't needed.</span></span> <span data-ttu-id="7ffb4-129">El Explorador de API usa el token del portal de administración de Defender para puntos de conexión siempre que realiza una solicitud.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-129">The API Explorer uses the Defender for Endpoint management portal token whenever it makes a request.</span></span>

<span data-ttu-id="7ffb4-130">La credencial de autenticación de usuario iniciada se usa para comprobar que el Explorador de API está autorizado para tener acceso a los datos en su nombre.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-130">The logged-in user authentication credential is used to verify that the API Explorer is authorized to access data on your behalf.</span></span>

<span data-ttu-id="7ffb4-131">Las solicitudes de API específicas son limitadas en función de los privilegios rbac.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-131">Specific API requests are limited based on your RBAC privileges.</span></span> <span data-ttu-id="7ffb4-132">Por ejemplo, una solicitud a "Enviar indicador" está limitada al rol de administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ffb4-132">For example, a request to "Submit indicator" is limited to the security admin role.</span></span> 
