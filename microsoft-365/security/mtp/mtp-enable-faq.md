---
title: Preguntas más frecuentes al activar Microsoft 365 defender
description: Obtenga respuestas a las preguntas más comunes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 defender
keywords: Preguntas más frecuentes, preguntas más frecuentes, GCC, introducción, habilitar MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de los datos, permisos necesarios, requisitos de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920495"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="00f97-104">Preguntas más frecuentes al activar Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="00f97-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="00f97-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="00f97-105">**Applies to:**</span></span>
- <span data-ttu-id="00f97-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00f97-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="00f97-107">Lea las respuestas a las preguntas más comunes sobre cómo activar [Microsoft 365 defender](microsoft-threat-protection.md), incluidas las licencias y los permisos necesarios, la implementación de los servicios de soporte y la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="00f97-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="00f97-108">Para obtener instrucciones sobre cómo activar el servicio, [consulte activar Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="00f97-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="00f97-109">No tengo una licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="00f97-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="00f97-110">¿Puedo seguir usando Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="00f97-111">Los clientes con las siguientes licencias que no son E5 pueden usar Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="00f97-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="00f97-112">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="00f97-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="00f97-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="00f97-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="00f97-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="00f97-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="00f97-115">Defender para Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="00f97-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="00f97-116">Para obtener una lista completa de las licencias admitidas, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="00f97-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="00f97-117">¿Es necesario instalar o implementar algo para empezar a usar Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="00f97-118">No, Microsoft 365 defender consolida datos de los servicios de seguridad de Microsoft 365 que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="00f97-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="00f97-119">Una vez que la haya activado, los incidentes, la automatización y las experiencias de búsqueda empezarán a trabajar en el ámbito de los productos implementados.</span><span class="sxs-lookup"><span data-stu-id="00f97-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="00f97-120">Si ninguno de estos productos se ha implementado correctamente, Microsoft 365 defender no mostrará ningún dato y no podrá realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="00f97-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="00f97-121">Para optimizar la experiencia de Microsoft 365 defender, recomendamos implementar *todos los* [servicios y productos de seguridad de Microsoft 365](deploy-supported-services.md)compatibles.</span><span class="sxs-lookup"><span data-stu-id="00f97-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="00f97-122">¿Dónde procesa y almacena mis datos los datos Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="00f97-123">Microsoft 365 defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados.</span><span class="sxs-lookup"><span data-stu-id="00f97-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="00f97-124">Si tiene Microsoft defender para el punto de conexión, selecciona la misma ubicación que usa defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="00f97-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="00f97-125">Microsoft defender for Endpoint se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través de Azure defender.</span><span class="sxs-lookup"><span data-stu-id="00f97-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="00f97-126">Microsoft 365 defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que han aprovisionado Microsoft defender para el punto de conexión de esta manera.</span><span class="sxs-lookup"><span data-stu-id="00f97-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="00f97-127">La ubicación del centro de datos se muestra antes y después de que se aprovisione el servicio en la página de configuración de Microsoft 365 defender ( **settings > Microsoft 365 defender** ).</span><span class="sxs-lookup"><span data-stu-id="00f97-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="00f97-128">Si prefiere usar otra ubicación de centro de datos, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="00f97-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="00f97-129">¿Dónde puedo obtener acceso a Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="00f97-130">Microsoft 365 defender está disponible en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00f97-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="00f97-131">Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="00f97-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="00f97-132">¿Qué permisos necesito para tener acceso a Microsoft 365 defender en el centro de seguridad de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="00f97-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="00f97-133">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden tener acceso a los datos y la funcionalidad de Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="00f97-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="00f97-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="00f97-134">Global administrator</span></span>
- <span data-ttu-id="00f97-135">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="00f97-135">Security administrator</span></span>
- <span data-ttu-id="00f97-136">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="00f97-136">Security Operator</span></span>
- <span data-ttu-id="00f97-137">Lector global</span><span class="sxs-lookup"><span data-stu-id="00f97-137">Global Reader</span></span>
- <span data-ttu-id="00f97-138">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="00f97-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="00f97-139">Configuración de control de acceso basada en roles en Microsoft defender para el acceso a datos de la influencia del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="00f97-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="00f97-140">Para obtener más información, consulte Acerca de la [Administración del acceso a Microsoft 365 defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="00f97-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="00f97-141">¿Cuál es la zona horaria predeterminada de Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="00f97-142">De forma predeterminada, Microsoft 365 defender muestra la información de hora en la zona horaria UTC.</span><span class="sxs-lookup"><span data-stu-id="00f97-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="00f97-143">Puede cambiar esta configuración para que use la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="00f97-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="00f97-144">Obtener información sobre la configuración de la zona horaria</span><span class="sxs-lookup"><span data-stu-id="00f97-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="00f97-145">¿Cómo puedo obtener más información sobre las nuevas actualizaciones de la interfaz de usuario y la característica de Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="00f97-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="00f97-146">Microsoft proporciona información de forma regular a través de los distintos canales, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="00f97-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="00f97-147">[Centro de mensajes](../../admin/manage/message-center.md) en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00f97-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="00f97-148">Blogposts en la [comunidad tecnológica de Microsoft 365 security & cumplimiento normativo](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="00f97-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="00f97-149">Obtenga las últimas experiencias disponibles públicamente activando [las características de vista previa](preview.md).</span><span class="sxs-lookup"><span data-stu-id="00f97-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="00f97-150">¿Está disponible Microsoft 365 defender para la nube de la comunidad de administración de Estados Unidos (GCC) o GCC High?</span><span class="sxs-lookup"><span data-stu-id="00f97-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="00f97-151">No está disponible por el momento.</span><span class="sxs-lookup"><span data-stu-id="00f97-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00f97-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="00f97-152">Related topics</span></span>

- [<span data-ttu-id="00f97-153">Información general de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="00f97-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="00f97-154">[Active Microsoft 365 defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="00f97-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="00f97-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="00f97-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="00f97-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="00f97-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="00f97-157">Activar la versión preliminar de las características</span><span class="sxs-lookup"><span data-stu-id="00f97-157">Turn on preview features</span></span>](preview.md)
