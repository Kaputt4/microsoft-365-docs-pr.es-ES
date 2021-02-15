---
title: Preguntas más frecuentes al activar Microsoft 365 Defender
description: Obtenga respuestas a las preguntas más frecuentes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 Defender
keywords: preguntas más frecuentes, preguntas más frecuentes, GCC, introducción, habilitar MTP, Protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930191"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="dbee8-104">Preguntas más frecuentes al activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbee8-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dbee8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dbee8-105">**Applies to:**</span></span>
- <span data-ttu-id="dbee8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbee8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="dbee8-107">Lea las respuestas a las preguntas más frecuentes sobre cómo activar [Microsoft 365 Defender,](microsoft-threat-protection.md)incluidas las licencias y permisos necesarios, la implementación de servicios de soporte técnico y la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="dbee8-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="dbee8-108">Para obtener instrucciones sobre cómo activar el servicio, [lea Activar Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="dbee8-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="dbee8-109">No tengo una licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dbee8-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="dbee8-110">¿Puedo seguir utilizando Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="dbee8-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="dbee8-111">Los clientes con las siguientes licencias que no son E5 pueden usar Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="dbee8-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="dbee8-112">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dbee8-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="dbee8-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="dbee8-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="dbee8-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dbee8-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="dbee8-115">Defender para Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="dbee8-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="dbee8-116">Para obtener una lista completa de las licencias admitidas, [lea los requisitos de licencia.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="dbee8-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="dbee8-117">¿Necesito instalar o implementar algo para empezar a usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="dbee8-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="dbee8-118">No, Microsoft 365 Defender consolida los datos de los servicios de seguridad de Microsoft 365 que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="dbee8-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="dbee8-119">Una vez que lo active, las experiencias de incidentes, automatización y búsqueda empezarán a funcionar dentro del ámbito de los productos implementados.</span><span class="sxs-lookup"><span data-stu-id="dbee8-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="dbee8-120">Si ninguno de estos productos se implementa correctamente, Microsoft 365 Defender no mostrará ningún dato y no podrá realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="dbee8-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="dbee8-121">Para optimizar las experiencias de Microsoft 365 Defender, se recomienda implementar todos los productos y servicios de seguridad de [Microsoft 365 compatibles.](deploy-supported-services.md) </span><span class="sxs-lookup"><span data-stu-id="dbee8-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="dbee8-122">¿Dónde procesa y almacena Microsoft 365 Defender mis datos?</span><span class="sxs-lookup"><span data-stu-id="dbee8-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="dbee8-123">Microsoft 365 Defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados.</span><span class="sxs-lookup"><span data-stu-id="dbee8-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="dbee8-124">Si tienes Microsoft Defender para Endpoint, selecciona la misma ubicación usada por Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dbee8-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="dbee8-125">Microsoft Defender para puntos de conexión aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="dbee8-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="dbee8-126">Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Microsoft Defender para Endpoint de esta manera.</span><span class="sxs-lookup"><span data-stu-id="dbee8-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="dbee8-127">La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft 365 Defender ( Configuración **> Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="dbee8-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="dbee8-128">Si prefiere usar otra ubicación del centro de datos, seleccione ¿Necesita **ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dbee8-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="dbee8-129">¿Dónde puedo acceder a Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="dbee8-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="dbee8-130">Microsoft 365 Defender está disponible en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbee8-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="dbee8-131">Para ir al centro de seguridad, vaya a la dirección [https://security.microsoft.com](https://security.microsoft.com) URL.</span><span class="sxs-lookup"><span data-stu-id="dbee8-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="dbee8-132">¿Qué permisos necesito para acceder a Microsoft 365 Defender en el Centro de seguridad de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="dbee8-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="dbee8-133">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a la funcionalidad y los datos de Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="dbee8-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="dbee8-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="dbee8-134">Global administrator</span></span>
- <span data-ttu-id="dbee8-135">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="dbee8-135">Security administrator</span></span>
- <span data-ttu-id="dbee8-136">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="dbee8-136">Security Operator</span></span>
- <span data-ttu-id="dbee8-137">Lector global</span><span class="sxs-lookup"><span data-stu-id="dbee8-137">Global Reader</span></span>
- <span data-ttu-id="dbee8-138">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="dbee8-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="dbee8-139">La configuración del control de acceso basado en roles en Microsoft Defender para puntos de conexión influye en el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="dbee8-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="dbee8-140">Para obtener más información, lea acerca [de cómo administrar el acceso a Microsoft 365 Defender.](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="dbee8-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="dbee8-141">¿En qué zona horaria se usa Microsoft 365 Defender de forma predeterminada?</span><span class="sxs-lookup"><span data-stu-id="dbee8-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="dbee8-142">De forma predeterminada, Microsoft 365 Defender muestra información de hora en la zona horaria UTC.</span><span class="sxs-lookup"><span data-stu-id="dbee8-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="dbee8-143">Puedes cambiar esta configuración para usar la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="dbee8-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="dbee8-144">Más información sobre cómo establecer la zona horaria</span><span class="sxs-lookup"><span data-stu-id="dbee8-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="dbee8-145">¿Cómo puedo obtener información sobre las nuevas actualizaciones de la interfaz de usuario y la característica de Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="dbee8-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="dbee8-146">Microsoft proporciona información periódicamente a través de los distintos canales, incluidos:</span><span class="sxs-lookup"><span data-stu-id="dbee8-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="dbee8-147">Centro [de mensajes en](../../admin/manage/message-center.md) el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dbee8-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="dbee8-148">Blogs en la comunidad técnica de [seguridad y cumplimiento & Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="dbee8-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="dbee8-149">Obtenga las últimas experiencias disponibles públicamente al activar las características [de vista previa.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="dbee8-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="dbee8-150">¿Microsoft 365 Defender está disponible para US Government Community Cloud (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="dbee8-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="dbee8-151">No está disponible por el momento.</span><span class="sxs-lookup"><span data-stu-id="dbee8-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbee8-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dbee8-152">Related topics</span></span>

- [<span data-ttu-id="dbee8-153">Introducción a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbee8-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="dbee8-154">[Active Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="dbee8-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="dbee8-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dbee8-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="dbee8-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="dbee8-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="dbee8-157">Activar la versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="dbee8-157">Turn on preview features</span></span>](preview.md)
