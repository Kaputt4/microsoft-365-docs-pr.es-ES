---
title: Información general sobre Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender Contoso Corporation como un negocio y la estructura en niveles de sus oficinas en todo el mundo.
ms.openlocfilehash: 856363881c749b06a530dc7cc4f0eb82dc155054
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068306"
---
# <a name="overview-of-the-contoso-corporation"></a><span data-ttu-id="429cf-103">Información general sobre Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="429cf-103">Overview of the Contoso Corporation</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

<span data-ttu-id="429cf-p101">Contoso Corporation es una empresa multinacional con sede en París, Francia. Es una organización conglomerada de fabricación, ventas y soporte técnico con más de 100 000 productos.</span><span class="sxs-lookup"><span data-stu-id="429cf-p101">The Contoso Corporation is a multi-national business with headquarters in Paris, France. It is a conglomerate manufacturing, sales, and support organization with over 100,000 products.</span></span>

## <a name="contoso-around-the-world"></a><span data-ttu-id="429cf-107">Contoso en todo el mundo</span><span class="sxs-lookup"><span data-stu-id="429cf-107">Contoso around the world</span></span>

<span data-ttu-id="429cf-108">En la figura 1, se muestran la sede central en París, las oficinas de los centros regionales y las oficinas satélite en varios continentes.</span><span class="sxs-lookup"><span data-stu-id="429cf-108">Figure 1 shows the headquarters office in Paris and regional hub and satellite offices in various continents.</span></span>

![Oficinas de Contoso en todo el mundo](../media/contoso-overview/contoso-overview-fig1.png)

<span data-ttu-id="429cf-110">**Figura 1: Oficinas de Contoso en todo el mundo**</span><span class="sxs-lookup"><span data-stu-id="429cf-110">**Figure 1: Contoso's offices around the world**</span></span>
 
<span data-ttu-id="429cf-111">Las oficinas de Contoso en todo el mundo siguen un diseño de tres niveles.</span><span class="sxs-lookup"><span data-stu-id="429cf-111">Contoso's offices around the world follow a three-tier design.</span></span>

- <span data-ttu-id="429cf-112">Sede</span><span class="sxs-lookup"><span data-stu-id="429cf-112">Headquarters</span></span>

  <span data-ttu-id="429cf-p102">La sede de Contoso Corporation se encuentra en unas grandes instalaciones corporativas en las afueras de París con decenas de edificios de instalaciones administrativas, de ingeniería y fabricación. Todos los centros de datos de Contoso y su presencia en Internet se albergan en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="429cf-p102">The Contoso Corporation headquarters is a large corporate campus on the outskirts of Paris with dozens of buildings for administrative, engineering, and manufacturing facilities. All of Contoso's datacenters and its Internet presence are housed in the Paris headquarters.</span></span>

  <span data-ttu-id="429cf-115">La sede cuenta con 25 000 empleados.</span><span class="sxs-lookup"><span data-stu-id="429cf-115">The headquarters has 25,000 workers.</span></span>

- <span data-ttu-id="429cf-116">Centros regionales</span><span class="sxs-lookup"><span data-stu-id="429cf-116">Regional hubs</span></span>

  <span data-ttu-id="429cf-p103">Las oficinas de centros regionales sirven a una región específica del mundo con el 60 % de ventas y personal de soporte técnico. Cada centro regional está conectado a la sede de París con un vínculo WAN de ancho de banda alto. </span><span class="sxs-lookup"><span data-stu-id="429cf-p103">Regional hub offices serve a specific region of the world with 60% sales and support staff. Each regional hub is connected to the Paris headquarters with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="429cf-119">Cada centro regional tiene un promedio de 2000 trabajadores.</span><span class="sxs-lookup"><span data-stu-id="429cf-119">Each regional hub has an average of 2,000 workers.</span></span>

- <span data-ttu-id="429cf-120">Oficinas satélite</span><span class="sxs-lookup"><span data-stu-id="429cf-120">Satellite offices</span></span>

  <span data-ttu-id="429cf-p104">Las oficinas satélite hospedan un 80 % del personal de ventas, y proporcionan presencia física e in situ para los clientes de Contoso en ciudades importantes o subregiones. Cada oficina satélite está conectada a un hub regional con un vínculo WAN de ancho de banda alto.</span><span class="sxs-lookup"><span data-stu-id="429cf-p104">Satellite offices contain 80% sales and support staff and provide an on-site presence for Contoso customers in key cities or sub-regions. Each satellite office is connected to a regional hub with a high-bandwidth WAN link.</span></span>

  <span data-ttu-id="429cf-123">Cada oficina satélite tiene un promedio de 250 trabajadores.</span><span class="sxs-lookup"><span data-stu-id="429cf-123">Each satellite office has an average of 250 workers.</span></span>

<span data-ttu-id="429cf-p105">El 25 % de la plantilla de Contoso es exclusivamente móvil, con un porcentaje más alto de trabajadores exclusivamente móviles en los centros regionales y las oficinas satélite. Proporcionar soporte técnico mejorado para los trabajadores exclusivamente móviles es un objetivo empresarial importante para Contoso.</span><span class="sxs-lookup"><span data-stu-id="429cf-p105">25% of Contoso's workforce is mobile-only, with a higher percentage of mobile-only workers in the regional hubs and satellite offices. Providing better support for mobile-only workers is an important business goal for Contoso.</span></span>

## <a name="design-considerations-for-microsoft-365-enterprise"></a><span data-ttu-id="429cf-126">Consideraciones sobre diseño para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="429cf-126">Design considerations for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="429cf-127">Los arquitectos de TI de Contoso identificaron las siguientes consideraciones y requisitos de diseño al implementar Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="429cf-127">Contoso's IT architects identified the following design requirements and considerations when deploying Microsoft 365 Enterprise:</span></span> 

- <span data-ttu-id="429cf-128">Varias ubicaciones geográficas con normativas y requisitos de cumplimiento locales</span><span class="sxs-lookup"><span data-stu-id="429cf-128">Multiple geographic locations with local regulations and compliance requirements</span></span>
- <span data-ttu-id="429cf-129">Un centro de datos de intranet en la sede central y servidores de aplicaciones regionales que hospedan aplicaciones internas de línea de negocio</span><span class="sxs-lookup"><span data-stu-id="429cf-129">A central intranet datacenter in the headquarters office and regional application servers that host internal line of business applications</span></span>
- <span data-ttu-id="429cf-130">Una infraestructura existente de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="429cf-130">An existing Microsoft Endpoint Configuration Manager infrastructure</span></span>
- <span data-ttu-id="429cf-131">Una combinación de dispositivos informáticos cliente, incluidos dispositivos Windows, Mac y Linux</span><span class="sxs-lookup"><span data-stu-id="429cf-131">A mix of client computing devices, including Windows, Mac, and Linux</span></span>
- <span data-ttu-id="429cf-132">Una combinación de dispositivos móviles personales y dispositivos propiedad de la empresa, incluidos dispositivos iOS (iPhone y iPad) y smartphones y tabletas Android</span><span class="sxs-lookup"><span data-stu-id="429cf-132">A mix of personal and company-owned mobile devices, including iOS (iPhone and iPad) and Android smart phones and tablets</span></span>
- <span data-ttu-id="429cf-133">Muchos trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="429cf-133">Many remote and mobile workers</span></span>
- <span data-ttu-id="429cf-134">Muchos asociados comerciales</span><span class="sxs-lookup"><span data-stu-id="429cf-134">Many business partners</span></span>
- <span data-ttu-id="429cf-135">Una gran cantidad de información de clientes y de identificación personal</span><span class="sxs-lookup"><span data-stu-id="429cf-135">A large amount of customer and personally identifiable information</span></span>
- <span data-ttu-id="429cf-136">Una gran cantidad de propiedad intelectual de gran valor en forma de especificaciones de diseño de productos y secretos empresariales de fabricación</span><span class="sxs-lookup"><span data-stu-id="429cf-136">A large amount of high-value intellectual property in the form of design specifications for products and manufacturing trade secrets</span></span>

## <a name="next-step"></a><span data-ttu-id="429cf-137">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="429cf-137">Next step</span></span>

<span data-ttu-id="429cf-138">[Obtenga más información](contoso-infra-needs.md) sobre la estructura básica de la infraestructura de TI local de Contoso y cómo sus necesidades empresariales se  satisficieron mediante Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="429cf-138">[Learn](contoso-infra-needs.md) about the Contoso Corporation’s on-premises IT infrastructure and how their business needs were addressed with Microsoft 365 Enterprise.</span></span>

## <a name="see-also"></a><span data-ttu-id="429cf-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="429cf-139">See also</span></span>

[<span data-ttu-id="429cf-140">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="429cf-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="429cf-141">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="429cf-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)



