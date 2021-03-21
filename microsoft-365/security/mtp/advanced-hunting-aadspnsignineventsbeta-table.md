---
title: Tabla AADSpnSignInEventsBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre la información asociada con la entidad de servicio de Azure Active Directory y la tabla de eventos de inicio de sesión de identidad administrada del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, entidades, evidencia, archivo, dirección IP, dispositivo, máquina, usuario, cuenta, identidad, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924545"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="9e8ce-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9e8ce-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="9e8ce-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9e8ce-105">**Applies to:**</span></span>

- <span data-ttu-id="9e8ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e8ce-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9e8ce-107">La tabla está actualmente en versión beta y se ofrece a corto plazo para permitirle buscar a través de la entidad de seguridad de servicio de Azure Active Directory (AAD) y los eventos de inicio de sesión de identidad `AADSpnSignInEventsBeta` administrada.</span><span class="sxs-lookup"><span data-stu-id="9e8ce-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="9e8ce-108">Con el tiempo, moveremos toda la información del esquema de inicio de sesión a la `IdentityLogonEvents` tabla.</span><span class="sxs-lookup"><span data-stu-id="9e8ce-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="9e8ce-109">Los clientes que puedan acceder a Microsoft 365 Defender a través de la solución integrada de Microsoft Defender para endpoints del Centro de seguridad de Azure, pero que no tengan licencias para Microsoft Defender para Office, Microsoft Defender para Identidad o Microsoft Cloud App Security, no podrán ver este esquema.</span><span class="sxs-lookup"><span data-stu-id="9e8ce-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="9e8ce-110">La tabla del esquema de búsqueda avanzada contiene información sobre la entidad de servicio de Azure Active Directory y los inicios de sesión de identidad `AADSpnSignInEventsBeta` administrada. Puede obtener más información sobre los diferentes tipos de inicios de sesión en los informes de actividad de inicio de sesión [de Azure Active Directory - versión preliminar](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="9e8ce-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="9e8ce-111">Use esta referencia para crear consultas que devuelvan información de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9e8ce-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9e8ce-112">Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span><span class="sxs-lookup"><span data-stu-id="9e8ce-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="9e8ce-113">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="9e8ce-113">Column name</span></span>     | <span data-ttu-id="9e8ce-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9e8ce-114">Data type</span></span> | <span data-ttu-id="9e8ce-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e8ce-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="9e8ce-116">datetime</span><span class="sxs-lookup"><span data-stu-id="9e8ce-116">datetime</span></span>      | <span data-ttu-id="9e8ce-117">Fecha y hora en que se generó el registro</span><span class="sxs-lookup"><span data-stu-id="9e8ce-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="9e8ce-118">cadena</span><span class="sxs-lookup"><span data-stu-id="9e8ce-118">string</span></span>        | <span data-ttu-id="9e8ce-119">Aplicación que realizó la acción grabada</span><span class="sxs-lookup"><span data-stu-id="9e8ce-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="9e8ce-120">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-120">string</span></span>        | <span data-ttu-id="9e8ce-121">Identificador único de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9e8ce-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="9e8ce-122">boolean</span><span class="sxs-lookup"><span data-stu-id="9e8ce-122">boolean</span></span>       | <span data-ttu-id="9e8ce-123">Indica si el inicio de sesión se inició mediante una identidad administrada</span><span class="sxs-lookup"><span data-stu-id="9e8ce-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="9e8ce-124">Entero</span><span class="sxs-lookup"><span data-stu-id="9e8ce-124">int</span></span>        | <span data-ttu-id="9e8ce-125">Contiene el código de error si se produce un error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9e8ce-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="9e8ce-126">Para encontrar una descripción de un código de error específico, visite <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="9e8ce-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="9e8ce-127">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-127">string</span></span>        | <span data-ttu-id="9e8ce-128">Identificador único del evento de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9e8ce-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="9e8ce-129">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-129">string</span></span>        | <span data-ttu-id="9e8ce-130">Nombre de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9e8ce-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="9e8ce-131">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-131">string</span></span>        | <span data-ttu-id="9e8ce-132">Identificador único de la entidad de servicio que inició el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9e8ce-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="9e8ce-133">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-133">string</span></span>        | <span data-ttu-id="9e8ce-134">Nombre para mostrar del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9e8ce-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="9e8ce-135">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-135">string</span></span>        | <span data-ttu-id="9e8ce-136">Identificador único del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9e8ce-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="9e8ce-137">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-137">string</span></span>        | <span data-ttu-id="9e8ce-138">Identificador único del inquilino del recurso al que se ha accedido</span><span class="sxs-lookup"><span data-stu-id="9e8ce-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="9e8ce-139">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-139">string</span></span>        | <span data-ttu-id="9e8ce-140">Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas</span><span class="sxs-lookup"><span data-stu-id="9e8ce-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="9e8ce-141">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-141">string</span></span>        | <span data-ttu-id="9e8ce-142">Código de dos letras que indica el país donde se geolocalización de la dirección IP del cliente</span><span class="sxs-lookup"><span data-stu-id="9e8ce-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="9e8ce-143">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-143">string</span></span>        | <span data-ttu-id="9e8ce-144">Estado en el que se produjo el inicio de sesión, si está disponible</span><span class="sxs-lookup"><span data-stu-id="9e8ce-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="9e8ce-145">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-145">string</span></span>        | <span data-ttu-id="9e8ce-146">Ciudad donde se encuentra el usuario de la cuenta</span><span class="sxs-lookup"><span data-stu-id="9e8ce-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="9e8ce-147">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-147">string</span></span>        | <span data-ttu-id="9e8ce-148">Las coordenadas de norte a sur de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9e8ce-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="9e8ce-149">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-149">string</span></span>        | <span data-ttu-id="9e8ce-150">Las coordenadas de este a oeste de la ubicación de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9e8ce-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="9e8ce-151">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-151">string</span></span>        | <span data-ttu-id="9e8ce-152">Identificador único de la solicitud</span><span class="sxs-lookup"><span data-stu-id="9e8ce-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="9e8ce-153">string</span><span class="sxs-lookup"><span data-stu-id="9e8ce-153">string</span></span> | <span data-ttu-id="9e8ce-154">Identificador único del evento</span><span class="sxs-lookup"><span data-stu-id="9e8ce-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="9e8ce-155">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e8ce-155">Related articles</span></span>

-   [<span data-ttu-id="9e8ce-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="9e8ce-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="9e8ce-157">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="9e8ce-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="9e8ce-158">Aprender el lenguaje de consulta</span><span class="sxs-lookup"><span data-stu-id="9e8ce-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="9e8ce-159">Entender el esquema</span><span class="sxs-lookup"><span data-stu-id="9e8ce-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)