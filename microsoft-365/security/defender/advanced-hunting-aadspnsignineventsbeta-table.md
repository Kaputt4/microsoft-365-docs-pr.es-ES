---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada Azure Active Directory principal de servicio y la tabla de eventos de inicio de sesión de identidad administrada del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6aa709fe4534bf049c6f8c097bc4bd85a9d6793b
ms.sourcegitcommit: 93eeaefc0d509c75e4c2210029155298ecca7583
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53347912"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="9ace4-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9ace4-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="9ace4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9ace4-105">**Applies to:**</span></span>

- <span data-ttu-id="9ace4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ace4-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9ace4-107">La tabla se encuentra actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de la entidad de seguridad de servicio de Azure Active Directory (AAD) y los eventos de inicio de sesión de identidad `AADSpnSignInEventsBeta` administrada.</span><span class="sxs-lookup"><span data-stu-id="9ace4-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="9ace4-108">Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="9ace4-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="9ace4-109">La tabla del esquema de búsqueda avanzada contiene información sobre Azure Active Directory principal de servicio y los `AADSpnSignInEventsBeta` inicios de sesión de identidad administrada. Puede obtener más información sobre los diferentes tipos de inicios de sesión en Azure Active Directory de actividad de inicio de sesión [- versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="9ace4-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="9ace4-110">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ace4-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9ace4-111">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="9ace4-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="9ace4-112">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="9ace4-112">Column name</span></span> | <span data-ttu-id="9ace4-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9ace4-113">Data type</span></span> | <span data-ttu-id="9ace4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ace4-114">Description</span></span> |
|-----|-----|-----|
| `Timestamp` | <span data-ttu-id="9ace4-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9ace4-115">datetime</span></span> | <span data-ttu-id="9ace4-116">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="9ace4-116">Date and time when the record was generated</span></span> |
| `Application` | <span data-ttu-id="9ace4-117">cadena</span><span class="sxs-lookup"><span data-stu-id="9ace4-117">string</span></span> | <span data-ttu-id="9ace4-118">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9ace4-118">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="9ace4-119">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-119">string</span></span> | <span data-ttu-id="9ace4-120">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9ace4-120">Unique identifier for the application</span></span> |
| `IsManagedIdentity`    | <span data-ttu-id="9ace4-121">boolean</span><span class="sxs-lookup"><span data-stu-id="9ace4-121">boolean</span></span>       | <span data-ttu-id="9ace4-122">Indica si el inicio de sesión se inició mediante una identidad administrada</span><span class="sxs-lookup"><span data-stu-id="9ace4-122">Indicates whether the sign-in was initiated by a managed identity</span></span> |
| `ErrorCode`    | <span data-ttu-id="9ace4-123">int</span><span class="sxs-lookup"><span data-stu-id="9ace4-123">int</span></span> | <span data-ttu-id="9ace4-124">Contiene el código de error si se produce un error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9ace4-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="9ace4-125">Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="9ace4-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="9ace4-126">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-126">string</span></span>        | <span data-ttu-id="9ace4-127">Identificador único del evento de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9ace4-127">Unique identifier of the sign-in event</span></span> |
| `ServicePrincipalName` | <span data-ttu-id="9ace4-128">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-128">string</span></span>        | <span data-ttu-id="9ace4-129">Nombre de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9ace4-129">Name of the service principal that initiated the sign-in</span></span>  |
| `ServicePrincipalId`   | <span data-ttu-id="9ace4-130">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-130">string</span></span>        | <span data-ttu-id="9ace4-131">Identificador único de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9ace4-131">Unique identifier of the service principal that initiated the sign-in</span></span>  |
| `ResourceDisplayName`  | <span data-ttu-id="9ace4-132">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-132">string</span></span>        | <span data-ttu-id="9ace4-133">Nombre para mostrar del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9ace4-133">Display name of the resource accessed</span></span>  |
| `ResourceId`           | <span data-ttu-id="9ace4-134">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-134">string</span></span>        | <span data-ttu-id="9ace4-135">Identificador único del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9ace4-135">Unique identifier of the resource accessed</span></span>  |
| `ResourceTenantId`     | <span data-ttu-id="9ace4-136">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-136">string</span></span>        | <span data-ttu-id="9ace4-137">Identificador único del inquilino del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9ace4-137">Unique identifier of the tenant of the resource accessed</span></span> |
| `IPAddress`            | <span data-ttu-id="9ace4-138">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-138">string</span></span>        | <span data-ttu-id="9ace4-139">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="9ace4-139">IP address assigned to the endpoint and used during related network communications</span></span>  |
| `Country`          | <span data-ttu-id="9ace4-140">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-140">string</span></span>        | <span data-ttu-id="9ace4-141">Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="9ace4-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `State`                | <span data-ttu-id="9ace4-142">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-142">string</span></span>        | <span data-ttu-id="9ace4-143">Estado en el que se produjo el inicio de sesión, si está disponible</span><span class="sxs-lookup"><span data-stu-id="9ace4-143">State where the sign-in occurred, if available</span></span> |
| `City`                 | <span data-ttu-id="9ace4-144">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-144">string</span></span>        | <span data-ttu-id="9ace4-145">Ciudad donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9ace4-145">City where the account user is located</span></span>  |
| `Latitude`             | <span data-ttu-id="9ace4-146">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-146">string</span></span>        | <span data-ttu-id="9ace4-147">Las coordenadas de norte a sur de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9ace4-147">The north to south coordinates of the sign-in location</span></span> |
| `Longitude`            | <span data-ttu-id="9ace4-148">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-148">string</span></span>        | <span data-ttu-id="9ace4-149">Las coordenadas de este a oeste de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9ace4-149">The east to west coordinates of the sign-in location</span></span> |
| `RequestId`            | <span data-ttu-id="9ace4-150">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-150">string</span></span>        | <span data-ttu-id="9ace4-151">Identificador único de la solicitud</span><span class="sxs-lookup"><span data-stu-id="9ace4-151">Unique identifier of the request</span></span> |
|`ReportId` | <span data-ttu-id="9ace4-152">string</span><span class="sxs-lookup"><span data-stu-id="9ace4-152">string</span></span> | <span data-ttu-id="9ace4-153">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="9ace4-153">Unique identifier for the event</span></span> |

 

## <a name="related-articles"></a><span data-ttu-id="9ace4-154">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ace4-154">Related articles</span></span>

-   [<span data-ttu-id="9ace4-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9ace4-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="9ace4-156">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="9ace4-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="9ace4-157">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="9ace4-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="9ace4-158">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="9ace4-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
