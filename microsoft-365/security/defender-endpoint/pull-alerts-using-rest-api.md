---
title: Extraer Microsoft Defender para detecciones de puntos de conexión mediante la API de REST
description: Obtenga información sobre cómo llamar a un punto de conexión de la API de Microsoft Defender para endpoints para extraer detecciones en formato JSON mediante la API de REST de SIEM.
keywords: detecciones, detecciones de extracción, api de reposo, solicitud, respuesta
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771674"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="4a9ae-104">Extraer Microsoft Defender para detecciones de puntos de conexión con la API de REST de SIEM</span><span class="sxs-lookup"><span data-stu-id="4a9ae-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4a9ae-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4a9ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a9ae-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4a9ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a9ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a9ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4a9ae-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4a9ae-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a9ae-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="4a9ae-110">[Microsoft Defender para alerta de](alerts.md) extremo se compone de una o más detecciones.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="4a9ae-111">[Microsoft Defender para la detección de](api-portal-mapping.md) puntos de conexión se compone del evento sospechoso que se produjo en el dispositivo y sus detalles de alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="4a9ae-112">-La API de alertas de punto de conexión de Microsoft Defender es la API más reciente para el consumo de alertas y contiene una lista detallada de pruebas relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="4a9ae-113">Para obtener más información, vea [Alert methods and properties y](alerts.md) List [alerts](get-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ae-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="4a9ae-114">Microsoft Defender para endpoint admite el protocolo OAuth 2.0 para extraer detecciones de la API.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="4a9ae-115">En general, el protocolo OAuth 2.0 admite cuatro tipos de flujos:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="4a9ae-116">Flujo de concesión de autorización</span><span class="sxs-lookup"><span data-stu-id="4a9ae-116">Authorization grant flow</span></span>
- <span data-ttu-id="4a9ae-117">Flujo implícito</span><span class="sxs-lookup"><span data-stu-id="4a9ae-117">Implicit flow</span></span>
- <span data-ttu-id="4a9ae-118">Flujo de credenciales de cliente</span><span class="sxs-lookup"><span data-stu-id="4a9ae-118">Client credentials flow</span></span>
- <span data-ttu-id="4a9ae-119">Flujo de propietario de recursos</span><span class="sxs-lookup"><span data-stu-id="4a9ae-119">Resource owner flow</span></span>

<span data-ttu-id="4a9ae-120">Para obtener más información acerca de las especificaciones de OAuth, vea el sitio [web de OAuth](http://www.oauth.net).</span><span class="sxs-lookup"><span data-stu-id="4a9ae-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="4a9ae-121">Microsoft Defender para  endpoint admite  el flujo de concesión de autorización y el flujo de credenciales de cliente para obtener acceso a las detecciones de extracción, con Azure Active Directory (AAD) como servidor de autorización.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="4a9ae-122">El _flujo de concesión de_ autorización usa credenciales de usuario para obtener un código de autorización, que luego se usa para obtener un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="4a9ae-123">El _flujo de credenciales de cliente_ usa credenciales de cliente para autenticarse en la dirección URL del punto de conexión de Microsoft Defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="4a9ae-124">Este flujo es adecuado para escenarios en los que un cliente de OAuth crea solicitudes a una API que no requiere credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="4a9ae-125">Use el siguiente método en la API de Microsoft Defender para Endpoint para extraer detecciones en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="4a9ae-126">Centro de seguridad de Microsoft Defender combina detecciones de alertas similares en una sola alerta.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="4a9ae-127">Esta API extrae detecciones de alertas en su forma sin procesar en función de los parámetros de consulta que establezca, lo que le permite aplicar su propia agrupación y filtrado.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="4a9ae-128">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4a9ae-128">Before you begin</span></span>
- <span data-ttu-id="4a9ae-129">Antes de llamar al extremo de Microsoft Defender para endpoint para extraer detecciones, deberá habilitar la aplicación de integración siem en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="4a9ae-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="4a9ae-130">Para obtener más información, vea [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ae-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="4a9ae-p106">Anote los siguientes valores en su registro de aplicaciones de Azure ya que los necesitará para configurar el flujo de OAuth en su aplicación de servicio o demonio:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="4a9ae-133">Identificador de la aplicación (exclusivo de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="4a9ae-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="4a9ae-134">Clave de aplicación o secreto (exclusivo de la aplicación)</span><span class="sxs-lookup"><span data-stu-id="4a9ae-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="4a9ae-135">El punto de conexión del token de OAuth 2.0 de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4a9ae-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="4a9ae-p107">Para ver este valor, haga clic en **Ver puntos de conexión** en la parte inferior del Portal de administración de Azure, en la página de su aplicación. El punto de conexión será algo similar a `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="4a9ae-138">Obtener un token de acceso</span><span class="sxs-lookup"><span data-stu-id="4a9ae-138">Get an access token</span></span>
<span data-ttu-id="4a9ae-139">Antes de crear llamadas al punto de conexión, deberá obtener un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="4a9ae-140">Usarás el token de acceso para obtener acceso al recurso protegido, que es detecciones en Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4a9ae-141">Para obtener un token de acceso, deberá realizar una solicitud POST al punto de conexión de emisión de tokens.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="4a9ae-142">Esta es una solicitud de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="4a9ae-143">La respuesta incluirá un acceso token e información de expiración.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="4a9ae-144">Ahora puede usar el valor en el campo *access_token* en una solicitud a la API de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="4a9ae-145">Solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-145">Request</span></span>
<span data-ttu-id="4a9ae-146">Con un token de acceso, la aplicación puede realizar solicitudes autenticadas a la API de Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="4a9ae-147">Su aplicación debe anexar el token de acceso al encabezado de autorización de cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="4a9ae-148">Sintaxis de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-148">Request syntax</span></span>
<span data-ttu-id="4a9ae-149">Método</span><span class="sxs-lookup"><span data-stu-id="4a9ae-149">Method</span></span> | <span data-ttu-id="4a9ae-150">URI de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="4a9ae-151">GET</span><span class="sxs-lookup"><span data-stu-id="4a9ae-151">GET</span></span>| <span data-ttu-id="4a9ae-152">Use el URI aplicable para su región.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="4a9ae-153">**Para la UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4a9ae-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="4a9ae-154">**Para EE. UU.**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4a9ae-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="4a9ae-155">**Para Reino Unido**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4a9ae-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="4a9ae-156">Encabezado de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-156">Request header</span></span>
<span data-ttu-id="4a9ae-157">Encabezado</span><span class="sxs-lookup"><span data-stu-id="4a9ae-157">Header</span></span> | <span data-ttu-id="4a9ae-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="4a9ae-158">Type</span></span> | <span data-ttu-id="4a9ae-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a9ae-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="4a9ae-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="4a9ae-160">Authorization</span></span> | <span data-ttu-id="4a9ae-161">string</span><span class="sxs-lookup"><span data-stu-id="4a9ae-161">string</span></span> | <span data-ttu-id="4a9ae-162">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-162">Required.</span></span> <span data-ttu-id="4a9ae-163">El token de acceso de Azure AD con el formato **Bearer** &lt; *token* &gt; .</span><span class="sxs-lookup"><span data-stu-id="4a9ae-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="4a9ae-164">Parámetros de la solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-164">Request parameters</span></span>

<span data-ttu-id="4a9ae-165">Use parámetros de consulta opcionales para especificar y controlar la cantidad de datos devueltos en una respuesta.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="4a9ae-166">Si llama a este método sin parámetros, la respuesta contiene todas las alertas de la organización en las últimas 2 horas.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="4a9ae-167">Nombre</span><span class="sxs-lookup"><span data-stu-id="4a9ae-167">Name</span></span> | <span data-ttu-id="4a9ae-168">Valor</span><span class="sxs-lookup"><span data-stu-id="4a9ae-168">Value</span></span>| <span data-ttu-id="4a9ae-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a9ae-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="4a9ae-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="4a9ae-170">sinceTimeUtc</span></span> | <span data-ttu-id="4a9ae-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="4a9ae-171">DateTime</span></span> | <span data-ttu-id="4a9ae-172">Define las alertas de límite de tiempo inferior de las que se recuperan, según el campo:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="4a9ae-173">El intervalo de tiempo será: de la hora sinceTimeUtc a la hora actual.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="4a9ae-174">**NOTA:** Cuando no se especifica, se recuperan todas las alertas generadas en las últimas dos horas.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="4a9ae-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="4a9ae-175">untilTimeUtc</span></span> | <span data-ttu-id="4a9ae-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="4a9ae-176">DateTime</span></span> | <span data-ttu-id="4a9ae-177">Define las alertas enlazadas de tiempo superior que se recuperan.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="4a9ae-178">El intervalo de tiempo será: de `sinceTimeUtc` vez en `untilTimeUtc` cuando.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="4a9ae-179">**NOTA**: Cuando no se especifica, el valor predeterminado será la hora actual.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="4a9ae-180">ago</span><span class="sxs-lookup"><span data-stu-id="4a9ae-180">ago</span></span> | <span data-ttu-id="4a9ae-181">cadena</span><span class="sxs-lookup"><span data-stu-id="4a9ae-181">string</span></span> | <span data-ttu-id="4a9ae-182">Extrae alertas en el siguiente intervalo de tiempo: `(current_time - ago)` de vez en `current_time` cuando.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="4a9ae-183">El valor debe establecerse según **el formato de duración ISO 8601**</span><span class="sxs-lookup"><span data-stu-id="4a9ae-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="4a9ae-184">Ejemplo: `ago=PT10M` extraerá las alertas recibidas en los últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="4a9ae-185">límite</span><span class="sxs-lookup"><span data-stu-id="4a9ae-185">limit</span></span> | <span data-ttu-id="4a9ae-186">Entero</span><span class="sxs-lookup"><span data-stu-id="4a9ae-186">int</span></span> | <span data-ttu-id="4a9ae-187">Define el número de alertas que se recuperarán.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="4a9ae-188">Las alertas más recientes se recuperarán en función del número definido.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="4a9ae-189">**NOTA**: Cuando no se especifique, se recuperarán todas las alertas disponibles en el intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="4a9ae-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="4a9ae-190">machinegroups</span></span> | <span data-ttu-id="4a9ae-191">cadena</span><span class="sxs-lookup"><span data-stu-id="4a9ae-191">string</span></span> | <span data-ttu-id="4a9ae-192">Especifica los grupos de dispositivos de los que extraer alertas.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="4a9ae-193">**NOTA:** Cuando no se especifica, se recuperarán las alertas de todos los grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="4a9ae-194">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="4a9ae-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="4a9ae-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="4a9ae-196">cadena</span><span class="sxs-lookup"><span data-stu-id="4a9ae-196">string</span></span> | <span data-ttu-id="4a9ae-197">Etiqueta de dispositivo única del Registro.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-197">Single device tag from the registry.</span></span>
<span data-ttu-id="4a9ae-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="4a9ae-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="4a9ae-199">cadena</span><span class="sxs-lookup"><span data-stu-id="4a9ae-199">string</span></span> | <span data-ttu-id="4a9ae-200">Etiquetas de dispositivo que se crearon en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="4a9ae-201">Ejemplo de solicitud</span><span class="sxs-lookup"><span data-stu-id="4a9ae-201">Request example</span></span>
<span data-ttu-id="4a9ae-202">En el ejemplo siguiente se muestra cómo recuperar todas las detecciones de la organización.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="4a9ae-203">En el siguiente ejemplo se muestra una solicitud para obtener las últimas 20 detecciones desde 2016-09-12 a las 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="4a9ae-204">Respuesta</span><span class="sxs-lookup"><span data-stu-id="4a9ae-204">Response</span></span>
<span data-ttu-id="4a9ae-205">El valor devuelto es una matriz de objetos de alerta en formato JSON.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="4a9ae-206">Este es un valor devuelto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a9ae-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="4a9ae-207">Ejemplos de código</span><span class="sxs-lookup"><span data-stu-id="4a9ae-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="4a9ae-208">Obtener token de acceso</span><span class="sxs-lookup"><span data-stu-id="4a9ae-208">Get access token</span></span>
<span data-ttu-id="4a9ae-209">En los ejemplos de código siguientes se muestra cómo obtener un token de acceso para llamar a la API SIEM de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="4a9ae-210">Usar token para conectarse al extremo de detecciones</span><span class="sxs-lookup"><span data-stu-id="4a9ae-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="4a9ae-211">Los ejemplos de código siguientes muestran cómo usar un token de acceso para llamar a la API SIEM de Defender for Endpoint para obtener alertas.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="4a9ae-212">Códigos de error</span><span class="sxs-lookup"><span data-stu-id="4a9ae-212">Error codes</span></span>
<span data-ttu-id="4a9ae-213">La API de REST de Microsoft Defender para endpoint devuelve los siguientes códigos de error causados por una solicitud no válida.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="4a9ae-214">Código de error HTTP</span><span class="sxs-lookup"><span data-stu-id="4a9ae-214">HTTP error code</span></span> | <span data-ttu-id="4a9ae-215">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a9ae-215">Description</span></span>
:---|:---
<span data-ttu-id="4a9ae-216">401</span><span class="sxs-lookup"><span data-stu-id="4a9ae-216">401</span></span> | <span data-ttu-id="4a9ae-217">Solicitud malformada o token no válido.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="4a9ae-218">403</span><span class="sxs-lookup"><span data-stu-id="4a9ae-218">403</span></span> | <span data-ttu-id="4a9ae-219">Excepción no autorizada: el administrador de inquilinos no administra ninguno de los dominios o se elimina el estado del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="4a9ae-220">500</span><span class="sxs-lookup"><span data-stu-id="4a9ae-220">500</span></span> | <span data-ttu-id="4a9ae-221">Error en el servicio.</span><span class="sxs-lookup"><span data-stu-id="4a9ae-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a9ae-222">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4a9ae-222">Related topics</span></span>
- [<span data-ttu-id="4a9ae-223">Habilitar la integración de SIEM en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4a9ae-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="4a9ae-224">Configurar ArcSight para extraer Microsoft Defender para detecciones de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="4a9ae-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="4a9ae-225">Extraer detecciones a las herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="4a9ae-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="4a9ae-226">Campos de Microsoft Defender para detección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="4a9ae-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="4a9ae-227">Solucionar problemas de integración de la herramienta SIEM</span><span class="sxs-lookup"><span data-stu-id="4a9ae-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
