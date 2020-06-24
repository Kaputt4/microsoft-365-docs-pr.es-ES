---
title: Preguntas más frecuentes acerca de la activación de la protección contra amenazas de Microsoft
description: Obtenga respuestas a las preguntas más frecuentes acerca de las licencias, los permisos, la configuración inicial y otros productos y servicios relacionados con la habilitación de la protección contra amenazas de Microsoft
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
ms.openlocfilehash: 9dcfeb5616afc8953e862d6d1a542d694582b157
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44845087"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a><span data-ttu-id="5dda7-104">Preguntas más frecuentes acerca de la activación de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5dda7-104">Frequently asked questions when turning on Microsoft Threat Protection</span></span>

<span data-ttu-id="5dda7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5dda7-105">**Applies to:**</span></span>
- <span data-ttu-id="5dda7-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5dda7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5dda7-107">Lea las respuestas a las preguntas más comunes sobre la activación de la [protección contra amenazas de Microsoft](microsoft-threat-protection.md), incluidas las licencias y los permisos necesarios, la implementación de los servicios de soporte y la configuración inicial.</span><span class="sxs-lookup"><span data-stu-id="5dda7-107">Read responses to the most commonly asked questions about turning on [Microsoft Threat Protection](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="5dda7-108">Para obtener instrucciones sobre cómo activar el servicio, [consulte activar la protección contra amenazas de Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="5dda7-108">For instructions on how to turn on the service, [read Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a><span data-ttu-id="5dda7-109">No tengo una licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5dda7-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="5dda7-110">¿Puedo seguir usando Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="5dda7-110">Can I still use Microsoft Threat Protection?</span></span>

<span data-ttu-id="5dda7-111">Los clientes con las siguientes licencias que no son E5 pueden usar la protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="5dda7-111">Customers with the following non-E5 licenses can use Microsoft Threat Protection:</span></span>

- <span data-ttu-id="5dda7-112">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5dda7-112">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="5dda7-113">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5dda7-113">Azure Advanced Threat Protection</span></span>
- <span data-ttu-id="5dda7-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5dda7-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5dda7-115">Protección contra amenazas avanzada de Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="5dda7-115">Office 365 Advanced Threat Protection (Plan 2)</span></span>
 
<span data-ttu-id="5dda7-116">Para obtener una lista completa de las licencias admitidas, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="5dda7-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a><span data-ttu-id="5dda7-117">¿Es necesario instalar o implementar algo para empezar a usar la protección contra amenazas de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="5dda7-117">Do I need to install or deploy anything to start using Microsoft Threat Protection?</span></span>

<span data-ttu-id="5dda7-118">No, la protección contra amenazas de Microsoft consolida datos de los servicios de seguridad de Microsoft 365 que ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="5dda7-118">No, Microsoft Threat Protection consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="5dda7-119">Una vez que la haya activado, los incidentes, la automatización y las experiencias de búsqueda empezarán a trabajar en el ámbito de los productos implementados.</span><span class="sxs-lookup"><span data-stu-id="5dda7-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="5dda7-120">Si ninguno de estos productos se ha implementado correctamente, la protección contra amenazas de Microsoft no mostrará ningún dato y no podrá realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5dda7-120">If none of these products are properly deployed, Microsoft Threat Protection will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="5dda7-121">Para optimizar sus experiencias de protección contra amenazas de Microsoft, le recomendamos que implemente *todos los* [servicios y productos de seguridad 365 de Microsoft](deploy-supported-services.md)compatibles.</span><span class="sxs-lookup"><span data-stu-id="5dda7-121">To optimize your Microsoft Threat Protection experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a><span data-ttu-id="5dda7-122">¿Dónde procesa y almacena mis datos los datos de protección contra amenazas de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="5dda7-122">Where does Microsoft Threat Protection process and store my data?</span></span>
<span data-ttu-id="5dda7-123">Microsoft Threat Protection selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados.</span><span class="sxs-lookup"><span data-stu-id="5dda7-123">Microsoft Threat Protection automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="5dda7-124">Si cuenta con ATP de Microsoft defender, selecciona la misma ubicación que ha usado ATP de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="5dda7-124">If you have Microsoft Defender ATP, it selects the same location used by Microsoft Defender ATP.</span></span>

>[!NOTE]
><span data-ttu-id="5dda7-125">Microsoft defender ATP se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través del centro de seguridad de Azure.</span><span class="sxs-lookup"><span data-stu-id="5dda7-125">Microsoft Defender ATP automatically provisions in European Union (EU) data centers when turned on through Azure Security Center.</span></span> <span data-ttu-id="5dda7-126">Microsoft Threat Protection aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que hayan aprovisionado ATP de Microsoft defender de este modo.</span><span class="sxs-lookup"><span data-stu-id="5dda7-126">Microsoft Threat Protection will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender ATP in this manner.</span></span> 

<span data-ttu-id="5dda7-127">La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft Threat Protection (**configuración > protección contra amenazas de Microsoft**).</span><span class="sxs-lookup"><span data-stu-id="5dda7-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft Threat Protection (**Settings > Microsoft Threat Protection**).</span></span> <span data-ttu-id="5dda7-128">Si prefiere usar otra ubicación de centro de datos, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5dda7-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-threat-protection"></a><span data-ttu-id="5dda7-129">¿Dónde se puede obtener acceso a Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="5dda7-129">Where can I access Microsoft Threat Protection?</span></span>

<span data-ttu-id="5dda7-130">La protección contra amenazas de Microsoft está disponible en el centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5dda7-130">Microsoft Threat Protection is available in Microsoft 365 security center.</span></span> <span data-ttu-id="5dda7-131">Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="5dda7-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a><span data-ttu-id="5dda7-132">¿Qué permisos necesito para tener acceso a Microsoft Threat Protection en el centro de seguridad de Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="5dda7-132">What permissions do I need to access Microsoft Threat Protection in Microsoft 365 security center?</span></span>

<span data-ttu-id="5dda7-133">Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a los datos y a la funcionalidad de protección contra amenazas de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="5dda7-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>

- <span data-ttu-id="5dda7-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5dda7-134">Global administrator</span></span>
- <span data-ttu-id="5dda7-135">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5dda7-135">Security administrator</span></span>
- <span data-ttu-id="5dda7-136">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="5dda7-136">Security Operator</span></span>
- <span data-ttu-id="5dda7-137">Lector global</span><span class="sxs-lookup"><span data-stu-id="5dda7-137">Global Reader</span></span>
- <span data-ttu-id="5dda7-138">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="5dda7-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="5dda7-139">Configuración de control de acceso basada en roles en ATP de Microsoft defender influencia en el acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="5dda7-139">Role-based access control settings in Microsoft Defender ATP influence access to data.</span></span> <span data-ttu-id="5dda7-140">Para obtener más información, consulte Acerca de la [Administración del acceso a la protección contra amenazas de Microsoft](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5dda7-140">For more information, read about [managing access to Microsoft Threat Protection](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a><span data-ttu-id="5dda7-141">¿Con qué zona horaria se ha predeterminado la protección contra amenazas de Microsoft?</span><span class="sxs-lookup"><span data-stu-id="5dda7-141">What time zone does Microsoft Threat Protection default to?</span></span>
<span data-ttu-id="5dda7-142">De forma predeterminada, Microsoft Threat Protection muestra la información de hora en la zona horaria UTC.</span><span class="sxs-lookup"><span data-stu-id="5dda7-142">By default, Microsoft Threat Protection displays time information in the UTC time zone.</span></span> <span data-ttu-id="5dda7-143">Puede cambiar esta configuración para que use la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="5dda7-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="5dda7-144">Obtener información sobre la configuración de la zona horaria</span><span class="sxs-lookup"><span data-stu-id="5dda7-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a><span data-ttu-id="5dda7-145">¿Cómo puedo obtener más información sobre las nuevas actualizaciones de la interfaz de usuario y la interfaz de Microsoft Threat Protection?</span><span class="sxs-lookup"><span data-stu-id="5dda7-145">How can I learn about new Microsoft Threat Protection feature and UI updates?</span></span>

<span data-ttu-id="5dda7-146">Microsoft proporciona información de forma regular a través de los distintos canales, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="5dda7-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="5dda7-147">[Centro de mensajes](../../admin/manage/message-center.md) en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5dda7-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="5dda7-148">Blogposts en la [comunidad tecnológica de Microsoft 365 security & cumplimiento normativo](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="5dda7-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="5dda7-149">Obtenga las últimas experiencias disponibles públicamente activando [las características de vista previa](preview.md).</span><span class="sxs-lookup"><span data-stu-id="5dda7-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="5dda7-150">¿Está disponible la protección contra amenazas de Microsoft en la nube de la comunidad del gobierno de los EE. UU. (GCC) o en GCC High?</span><span class="sxs-lookup"><span data-stu-id="5dda7-150">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="5dda7-151">No está disponible por el momento.</span><span class="sxs-lookup"><span data-stu-id="5dda7-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5dda7-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5dda7-152">Related topics</span></span>

- [<span data-ttu-id="5dda7-153">Introducción a la Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5dda7-153">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="5dda7-154">[Activar la protección contra amenazas de Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="5dda7-154">[Turn on Microsoft Threat Protection](mtp-enable.md).</span></span>
- [<span data-ttu-id="5dda7-155">Requisitos de licencia y otros requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5dda7-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="5dda7-156">Implementación de servicios compatibles</span><span class="sxs-lookup"><span data-stu-id="5dda7-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="5dda7-157">Activar las características de vista previa</span><span class="sxs-lookup"><span data-stu-id="5dda7-157">Turn on preview features</span></span>](preview.md)