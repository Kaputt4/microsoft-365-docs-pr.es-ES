---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con la entidad de servicio de Azure Active Directory y la tabla de eventos de inicio de sesión de identidad administrada del esquema de búsqueda avanzada
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
ms.openlocfilehash: 984e945107b6e0b41459659a7f2e9f649981e4b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932600"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="ce3af-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ce3af-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="ce3af-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ce3af-105">**Applies to:**</span></span>

- <span data-ttu-id="ce3af-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce3af-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ce3af-107">La tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de la entidad de seguridad de servicio de Azure Active Directory (AAD) y los eventos de inicio de sesión de identidad `AADSpnSignInEventsBeta` administrada.</span><span class="sxs-lookup"><span data-stu-id="ce3af-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="ce3af-108">Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="ce3af-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="ce3af-109">Los clientes que pueden acceder a Microsoft 365 Defender a través de la solución integrada de Microsoft Defender para endpoints de Azure Defender, pero que no tienen licencias para Microsoft Defender para Office, Microsoft Defender para Identidad o Microsoft Cloud App Security, no podrán ver este esquema.</span><span class="sxs-lookup"><span data-stu-id="ce3af-109">Customers who can access Microsoft 365 Defender through the Azure Defender’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="ce3af-110">La tabla del esquema de búsqueda avanzada contiene información sobre la entidad de servicio de Azure Active Directory y los inicios de sesión de identidad `AADSpnSignInEventsBeta` administrada. Puede obtener más información sobre los diferentes tipos de inicios de sesión en los informes de actividad de inicio de sesión [de Azure Active Directory - versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="ce3af-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="ce3af-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ce3af-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ce3af-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="ce3af-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="ce3af-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="ce3af-113">Column name</span></span>     | <span data-ttu-id="ce3af-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ce3af-114">Data type</span></span> | <span data-ttu-id="ce3af-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce3af-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="ce3af-116">datetime</span><span class="sxs-lookup"><span data-stu-id="ce3af-116">datetime</span></span>      | <span data-ttu-id="ce3af-117">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="ce3af-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="ce3af-118">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-118">string</span></span>        | <span data-ttu-id="ce3af-119">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="ce3af-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="ce3af-120">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-120">string</span></span>        | <span data-ttu-id="ce3af-121">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ce3af-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="ce3af-122">boolean</span><span class="sxs-lookup"><span data-stu-id="ce3af-122">boolean</span></span>       | <span data-ttu-id="ce3af-123">Indica si el inicio de sesión se inició mediante una identidad administrada</span><span class="sxs-lookup"><span data-stu-id="ce3af-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="ce3af-124">Entero</span><span class="sxs-lookup"><span data-stu-id="ce3af-124">int</span></span>        | <span data-ttu-id="ce3af-125">Contiene el código de error si se produce un error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ce3af-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="ce3af-126">Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="ce3af-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="ce3af-127">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-127">string</span></span>        | <span data-ttu-id="ce3af-128">Identificador único del evento de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ce3af-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="ce3af-129">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-129">string</span></span>        | <span data-ttu-id="ce3af-130">Nombre de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ce3af-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="ce3af-131">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-131">string</span></span>        | <span data-ttu-id="ce3af-132">Identificador único de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ce3af-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="ce3af-133">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-133">string</span></span>        | <span data-ttu-id="ce3af-134">Nombre para mostrar del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="ce3af-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="ce3af-135">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-135">string</span></span>        | <span data-ttu-id="ce3af-136">Identificador único del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="ce3af-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="ce3af-137">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-137">string</span></span>        | <span data-ttu-id="ce3af-138">Identificador único del inquilino del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="ce3af-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="ce3af-139">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-139">string</span></span>        | <span data-ttu-id="ce3af-140">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="ce3af-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="ce3af-141">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-141">string</span></span>        | <span data-ttu-id="ce3af-142">Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="ce3af-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="ce3af-143">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-143">string</span></span>        | <span data-ttu-id="ce3af-144">Estado en el que se produjo el inicio de sesión, si está disponible</span><span class="sxs-lookup"><span data-stu-id="ce3af-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="ce3af-145">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-145">string</span></span>        | <span data-ttu-id="ce3af-146">Ciudad donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="ce3af-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="ce3af-147">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-147">string</span></span>        | <span data-ttu-id="ce3af-148">Las coordenadas de norte a sur de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ce3af-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="ce3af-149">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-149">string</span></span>        | <span data-ttu-id="ce3af-150">Las coordenadas de este a oeste de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ce3af-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="ce3af-151">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-151">string</span></span>        | <span data-ttu-id="ce3af-152">Identificador único de la solicitud</span><span class="sxs-lookup"><span data-stu-id="ce3af-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="ce3af-153">cadena</span><span class="sxs-lookup"><span data-stu-id="ce3af-153">string</span></span> | <span data-ttu-id="ce3af-154">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="ce3af-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="ce3af-155">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="ce3af-155">Related articles</span></span>

-   [<span data-ttu-id="ce3af-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="ce3af-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="ce3af-157">Información general sobre la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="ce3af-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="ce3af-158">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="ce3af-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="ce3af-159">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="ce3af-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)