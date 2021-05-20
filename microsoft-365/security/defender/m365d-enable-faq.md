---
title: Preguntas frecuentes al activar Microsoft 365 Defender
description: Obtenga respuestas a las preguntas más frecuentes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 Defender
keywords: preguntas frecuentes, preguntas frecuentes, GCC, introducción, habilitación Microsoft 365 Defender, Microsoft 365 Defender, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572770"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="09014-104">Preguntas frecuentes al activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09014-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="09014-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="09014-105">**Applies to:**</span></span>
- <span data-ttu-id="09014-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09014-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="09014-107">Lea las respuestas a las preguntas más frecuentes sobre cómo activar [Microsoft 365 Defender,](microsoft-365-defender.md)incluidas las licencias y permisos necesarios, la implementación de servicios de soporte técnico y la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="09014-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-365-defender.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="09014-108">Para obtener instrucciones sobre cómo activar el servicio, [lea Activar Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="09014-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="09014-109">No tengo licencia Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="09014-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="09014-110">¿Todavía puedo usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="09014-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="09014-111">Los clientes con las siguientes licencias que no son E5 pueden usar Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="09014-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="09014-112">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="09014-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="09014-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="09014-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="09014-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="09014-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="09014-115">Defender para Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="09014-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="09014-116">Para obtener una lista completa de las licencias admitidas, [lea los requisitos de licencia.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="09014-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="09014-117">¿Necesito instalar o implementar algo para empezar a usar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="09014-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="09014-118">No, Microsoft 365 Defender consolida los datos de Microsoft 365 servicios de seguridad que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="09014-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="09014-119">Una vez que lo encienda, las experiencias de incidentes, automatización y caza comenzarán a funcionar en el ámbito de los productos implementados.</span><span class="sxs-lookup"><span data-stu-id="09014-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="09014-120">Si ninguno de estos productos se implementa correctamente, Microsoft 365 Defender no mostrará ningún dato y no podrá realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="09014-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="09014-121">Para optimizar las experiencias de Microsoft 365 Defender, se recomienda implementar *todos los* [productos y servicios de seguridad Microsoft 365 compatibles.](deploy-supported-services.md)</span><span class="sxs-lookup"><span data-stu-id="09014-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="09014-122">¿Dónde procesa Microsoft 365 Defender y almacena mis datos?</span><span class="sxs-lookup"><span data-stu-id="09014-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="09014-123">Microsoft 365 Defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados.</span><span class="sxs-lookup"><span data-stu-id="09014-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="09014-124">Si tiene Microsoft Defender para endpoint, selecciona la misma ubicación utilizada por Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="09014-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="09014-125">Microsoft Defender for Endpoint aprovisiona automáticamente los centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="09014-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="09014-126">Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que hayan aprovisionado Microsoft Defender for Endpoint de esta manera.</span><span class="sxs-lookup"><span data-stu-id="09014-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="09014-127">La ubicación del centro de datos se muestra antes y después de que el servicio se aprovisione en la página de configuración de Microsoft 365 Defender (**Configuración > Microsoft 365 Defender**).</span><span class="sxs-lookup"><span data-stu-id="09014-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender (**Settings > Microsoft 365 Defender**).</span></span> <span data-ttu-id="09014-128">Si prefiere usar otra ubicación del centro de datos, seleccione **¿Necesita ayuda?** en el centro de seguridad Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="09014-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="09014-129">¿Dónde puedo acceder a Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="09014-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="09014-130">Microsoft 365 Defender está disponible en Microsoft 365 centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="09014-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="09014-131">Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="09014-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="09014-132">¿Qué permisos necesito para acceder a Microsoft 365 Defender en Microsoft 365 centro de seguridad?</span><span class="sxs-lookup"><span data-stu-id="09014-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="09014-133">Las cuentas asignadas a los siguientes roles de Azure Active Directory (Azure AD) pueden tener acceso a Microsoft 365 funcionalidad y datos de Defender:</span><span class="sxs-lookup"><span data-stu-id="09014-133">Accounts assigned the following Azure Active Directory (Azure AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="09014-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="09014-134">Global administrator</span></span>
- <span data-ttu-id="09014-135">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="09014-135">Security administrator</span></span>
- <span data-ttu-id="09014-136">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="09014-136">Security Operator</span></span>
- <span data-ttu-id="09014-137">Lector global</span><span class="sxs-lookup"><span data-stu-id="09014-137">Global Reader</span></span>
- <span data-ttu-id="09014-138">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="09014-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="09014-139">La configuración de control de acceso basada en roles en Microsoft Defender for Endpoint influye en el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="09014-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="09014-140">Para obtener más información, lea acerca [de cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="09014-140">For more information, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="09014-141">¿A qué zona horaria Microsoft 365 defender es el valor predeterminado?</span><span class="sxs-lookup"><span data-stu-id="09014-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="09014-142">De forma predeterminada, Microsoft 365 Defender muestra información de hora en la zona horaria UTC.</span><span class="sxs-lookup"><span data-stu-id="09014-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="09014-143">Puede cambiar esta configuración para usar la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="09014-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="09014-144">Obtén información sobre cómo configurar la zona horaria</span><span class="sxs-lookup"><span data-stu-id="09014-144">Learn about setting the time zone</span></span>](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="09014-145">¿Cómo puedo obtener información sobre las nuevas actualizaciones de Microsoft 365 Defender y de la interfaz de usuario?</span><span class="sxs-lookup"><span data-stu-id="09014-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="09014-146">Microsoft proporciona regularmente información a través de los distintos canales, entre ellos:</span><span class="sxs-lookup"><span data-stu-id="09014-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="09014-147">El [centro de mensajes](../../admin/manage/message-center.md) de Microsoft 365 centro de administración</span><span class="sxs-lookup"><span data-stu-id="09014-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="09014-148">Blogposts en la [Microsoft 365 la seguridad & comunidad tecnológica de cumplimiento](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="09014-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="09014-149">Obtenga las últimas experiencias disponibles públicamente activando las [funciones de vista previa.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="09014-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="09014-150">¿Microsoft 365 Defender está disponible para Government Community Cloud (GCC) o GCC High de EE. UU.?</span><span class="sxs-lookup"><span data-stu-id="09014-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="09014-151">No está disponible por el momento.</span><span class="sxs-lookup"><span data-stu-id="09014-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="09014-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="09014-152">Related topics</span></span>

- [<span data-ttu-id="09014-153">Microsoft 365 Visión general del defensor</span><span class="sxs-lookup"><span data-stu-id="09014-153">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- <span data-ttu-id="09014-154">[Activa Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="09014-154">[Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>
- [<span data-ttu-id="09014-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="09014-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="09014-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="09014-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="09014-157">Activar la versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="09014-157">Turn on preview features</span></span>](preview.md)
