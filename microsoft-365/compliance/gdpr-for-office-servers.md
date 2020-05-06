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
ms.openlocfilehash: 4efb3803df2baa1ca37aeda05ae81947c3b65010
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036265"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="af12e-103">RGPD para servidores locales de Office</span><span class="sxs-lookup"><span data-stu-id="af12e-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="af12e-p101">El Reglamento general de protección de datos (RGPD) presenta requisitos para que las organizaciones protejan los datos personales y respondan correctamente a las solicitudes de datos personales. Esta serie de artículos proporciona enfoques recomendados para cargas de trabajo locales:</span><span class="sxs-lookup"><span data-stu-id="af12e-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="af12e-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="af12e-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="af12e-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="af12e-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="af12e-108">Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="af12e-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="af12e-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="af12e-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="af12e-110">Office Web Apps Server y Office Online Server</span><span class="sxs-lookup"><span data-stu-id="af12e-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="af12e-111">Uso compartido de archivos locales</span><span class="sxs-lookup"><span data-stu-id="af12e-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="af12e-112">Para obtener más información sobre el RGPD y cómo puede ayudarle Microsoft, consulte el [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span><span class="sxs-lookup"><span data-stu-id="af12e-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).</span></span>

<span data-ttu-id="af12e-p102">Antes de realizar cualquier trabajo con los datos locales, consulte con sus equipos legales y de cumplimiento para buscar orientación y obtener información sobre los métodos de clasificación existentes para trabajar con datos personales y esquemas. Microsoft ofrece recomendaciones para desarrollar y ampliar esquemas de clasificación en el Kit de herramientas de detección de datos de RGPD de Microsoft en [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). Este kit de herramientas también describe métodos para mover datos locales a la nube donde puede usar funciones de gobierno de datos más complejas, si así lo desea. Los artículos de esta sección proporcionan recomendaciones para datos que se pretende que permanezcan en un entorno local.</span><span class="sxs-lookup"><span data-stu-id="af12e-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="af12e-p103">La siguiente ilustración enumera las capacidades recomendadas que se deben usar en cada una de estas cargas de trabajo para descubrir, clasificar, proteger y vigilar los datos personales. Consulte los artículos de esta sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="af12e-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="af12e-119">Descripción de la ilustración</span><span class="sxs-lookup"><span data-stu-id="af12e-119">Illustration description</span></span>

<span data-ttu-id="af12e-120">Por motivos de accesibilidad, en la tabla siguiente se incluyen los mismos ejemplos que en la ilustración.</span><span class="sxs-lookup"><span data-stu-id="af12e-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="af12e-121">Recursos compartidos de archivos de Windows Server</span><span class="sxs-lookup"><span data-stu-id="af12e-121">Windows Server file shares</span></span>|<span data-ttu-id="af12e-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="af12e-122">SharePoint Server</span></span>|<span data-ttu-id="af12e-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="af12e-123">Exchange Server</span></span>|<span data-ttu-id="af12e-124">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="af12e-124">Skype for Business</span></span>|<span data-ttu-id="af12e-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="af12e-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="af12e-126">Descubrir</span><span class="sxs-lookup"><span data-stu-id="af12e-126">Discover</span></span>|<span data-ttu-id="af12e-127">Escáner de Azure Information Protection\*</span><span class="sxs-lookup"><span data-stu-id="af12e-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="af12e-128">Centro de búsqueda o eDiscovery (cuando los datos estén clasificados); escáner de Azure Information Protection\*</span><span class="sxs-lookup"><span data-stu-id="af12e-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="af12e-129">Portal de eDiscovery de Exchange</span><span class="sxs-lookup"><span data-stu-id="af12e-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="af12e-130">Portal de eDiscovery de Exchange</span><span class="sxs-lookup"><span data-stu-id="af12e-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="af12e-131">Scripts SQL de detección y exportación</span><span class="sxs-lookup"><span data-stu-id="af12e-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="af12e-132">Clasificar</span><span class="sxs-lookup"><span data-stu-id="af12e-132">Classify</span></span>|<span data-ttu-id="af12e-133">Escáner de Azure Information Protection\*; Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="af12e-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="af12e-134">Escáner de Azure Information Protection\*; Tipos de información confidencial de Office 365</span><span class="sxs-lookup"><span data-stu-id="af12e-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="af12e-135">Etiquetas de retención y directivas de retención de Exchange</span><span class="sxs-lookup"><span data-stu-id="af12e-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="af12e-136">Etiquetas de retención y directivas de retención de Exchange</span><span class="sxs-lookup"><span data-stu-id="af12e-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="af12e-137">Proteger</span><span class="sxs-lookup"><span data-stu-id="af12e-137">Protect</span></span>||<span data-ttu-id="af12e-138">Reglas de prevención de pérdida de datos de Exchange Server; protección IRM para las bibliotecas</span><span class="sxs-lookup"><span data-stu-id="af12e-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="af12e-139">Reglas de prevención de pérdida de datos de Exchange Server; integración IRM con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="af12e-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="af12e-140">Supervisar</span><span class="sxs-lookup"><span data-stu-id="af12e-140">Monitor</span></span>|<span data-ttu-id="af12e-141">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="af12e-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="af12e-142">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="af12e-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="af12e-143">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="af12e-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="af12e-144">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="af12e-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="af12e-145">Integrar registros con herramientas SIEM</span><span class="sxs-lookup"><span data-stu-id="af12e-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="af12e-p104">\*Nota que la protección cifra el archivo. Por consiguiente, SharePoint Server no puede encontrar los tipos de información sensible en los archivos protegidos.</span><span class="sxs-lookup"><span data-stu-id="af12e-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can't find the sensitive information types in protected files.</span></span>
