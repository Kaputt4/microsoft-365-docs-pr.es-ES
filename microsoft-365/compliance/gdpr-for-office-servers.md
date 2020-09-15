---
title: RGPD para servidores de Office
description: Aprenda a cumplir con los requisitos del Reglamento general de protección de datos (GDPR) en los servidores de la oficina.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5ee42a12f65ad5eff0a33ef2b61d328ebdc7af3e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547336"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="ffaeb-103">RGPD para servidores locales de Office</span><span class="sxs-lookup"><span data-stu-id="ffaeb-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="ffaeb-p101">El Reglamento general de protección de datos (RGPD) presenta requisitos para que las organizaciones protejan los datos personales y respondan correctamente a las solicitudes de datos personales. Esta serie de artículos proporciona enfoques recomendados para cargas de trabajo locales:</span><span class="sxs-lookup"><span data-stu-id="ffaeb-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

- [<span data-ttu-id="ffaeb-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

- [<span data-ttu-id="ffaeb-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

- [<span data-ttu-id="ffaeb-108">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

- [<span data-ttu-id="ffaeb-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-109">Project Server</span></span>](gdpr-for-project-server.md)

- [<span data-ttu-id="ffaeb-110">Office Web Apps Server y Office Online Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

- [<span data-ttu-id="ffaeb-111">Uso compartido de archivos locales</span><span class="sxs-lookup"><span data-stu-id="ffaeb-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="ffaeb-112">Para obtener más información sobre el RGPD y cómo puede ayudarle Microsoft, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span><span class="sxs-lookup"><span data-stu-id="ffaeb-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="ffaeb-p102">Antes de realizar cualquier trabajo con los datos locales, consulte con sus equipos legales y de cumplimiento para buscar orientación y obtener información sobre los métodos de clasificación existentes para trabajar con datos personales y esquemas. Microsoft ofrece recomendaciones para desarrollar y ampliar esquemas de clasificación en el Kit de herramientas de detección de datos de RGPD de Microsoft en [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). Este kit de herramientas también describe métodos para mover datos locales a la nube donde puede usar funciones de gobierno de datos más complejas, si así lo desea. Los artículos de esta sección proporcionan recomendaciones para datos que se pretende que permanezcan en un entorno local.</span><span class="sxs-lookup"><span data-stu-id="ffaeb-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="ffaeb-p103">La siguiente ilustración enumera las capacidades recomendadas que se deben usar en cada una de estas cargas de trabajo para descubrir, clasificar, proteger y vigilar los datos personales. Consulte los artículos de esta sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ffaeb-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![Diagrama en el que se describen las funcionalidades para descubrir, clasificar, proteger y supervisar datos personales en distintas cargas de trabajo](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="ffaeb-120">Descripción de la ilustración</span><span class="sxs-lookup"><span data-stu-id="ffaeb-120">Illustration description</span></span>

<span data-ttu-id="ffaeb-121">Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="ffaeb-121">For accessibility, the following table provides the same examples in the illustration.</span></span>

****

|<span data-ttu-id="ffaeb-122">Acción</span><span class="sxs-lookup"><span data-stu-id="ffaeb-122">Action</span></span>|<span data-ttu-id="ffaeb-123">Recursos compartidos de archivos de Windows Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-123">Windows Server file shares</span></span>|<span data-ttu-id="ffaeb-124">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-124">SharePoint Server</span></span>|<span data-ttu-id="ffaeb-125">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-125">Exchange Server</span></span>|<span data-ttu-id="ffaeb-126">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ffaeb-126">Skype for Business</span></span>|<span data-ttu-id="ffaeb-127">Project Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-127">Project Server</span></span>|
|---|---|---|---|---|---|
|<span data-ttu-id="ffaeb-128">Detectar</span><span class="sxs-lookup"><span data-stu-id="ffaeb-128">Discover</span></span>|<span data-ttu-id="ffaeb-129">Escáner de Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffaeb-129">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="ffaeb-130">Centro de búsqueda o eDiscovery (después de clasificar los datos)</span><span class="sxs-lookup"><span data-stu-id="ffaeb-130">Search Center or eDiscovery (after data is classified)</span></span> <br/><br/> <span data-ttu-id="ffaeb-131">Escáner de Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffaeb-131">Azure Information Protection scanner<sup>\*</sup></span></span>|<span data-ttu-id="ffaeb-132">Portal de eDiscovery de Exchange</span><span class="sxs-lookup"><span data-stu-id="ffaeb-132">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="ffaeb-133">Portal de eDiscovery de Exchange</span><span class="sxs-lookup"><span data-stu-id="ffaeb-133">Exchange eDiscovery portal</span></span>|<span data-ttu-id="ffaeb-134">Scripts SQL de detección y exportación</span><span class="sxs-lookup"><span data-stu-id="ffaeb-134">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="ffaeb-135">Clasificar</span><span class="sxs-lookup"><span data-stu-id="ffaeb-135">Classify</span></span>|<span data-ttu-id="ffaeb-136">Escáner de Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffaeb-136">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="ffaeb-137">Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="ffaeb-137">Office 365 sensitive information types</span></span>|<span data-ttu-id="ffaeb-138">Escáner de Azure Information Protection<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ffaeb-138">Azure Information Protection scanner<sup>\*</sup></span></span> <br/><br/> <span data-ttu-id="ffaeb-139">Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="ffaeb-139">Office 365 sensitive information types</span></span>|<span data-ttu-id="ffaeb-140">Etiquetas de retención y directivas de retención de Exchange</span><span class="sxs-lookup"><span data-stu-id="ffaeb-140">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="ffaeb-141">Etiquetas de retención y directivas de retención de Exchange</span><span class="sxs-lookup"><span data-stu-id="ffaeb-141">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="ffaeb-142">Proteger</span><span class="sxs-lookup"><span data-stu-id="ffaeb-142">Protect</span></span>||<span data-ttu-id="ffaeb-143">Reglas de prevención de pérdida de datos de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-143">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="ffaeb-144">Permisos y protección IRM para las bibliotecas</span><span class="sxs-lookup"><span data-stu-id="ffaeb-144">Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="ffaeb-145">Reglas de prevención de pérdida de datos de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-145">Exchange Server data loss prevention rules</span></span> <br/><br/> <span data-ttu-id="ffaeb-146">Integración IRM con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ffaeb-146">IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="ffaeb-147">Monitorear</span><span class="sxs-lookup"><span data-stu-id="ffaeb-147">Monitor</span></span>|<span data-ttu-id="ffaeb-148">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="ffaeb-148">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ffaeb-149">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="ffaeb-149">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ffaeb-150">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="ffaeb-150">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ffaeb-151">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="ffaeb-151">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ffaeb-152">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="ffaeb-152">Integrate logs with SIEM tools</span></span>|
|

<span data-ttu-id="ffaeb-153"><sup>\*</sup> Tenga en cuenta que la protección cifra el archivo.</span><span class="sxs-lookup"><span data-stu-id="ffaeb-153"><sup>\*</sup> Note that protection encrypts the file.</span></span> <span data-ttu-id="ffaeb-154">Por lo tanto, SharePoint Server no puede encontrar tipos de información confidencial en los archivos protegidos.</span><span class="sxs-lookup"><span data-stu-id="ffaeb-154">Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
