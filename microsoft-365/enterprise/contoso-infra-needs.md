---
title: Infraestructura de ti y necesidades empresariales de Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la estructura básica de la infraestructura de ti local de Contoso y cómo se satisfacen las necesidades empresariales de Microsoft 365 para la empresa.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637180"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="41d36-103">Infraestructura de ti y necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="41d36-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="41d36-104">Contoso está pasando de una infraestructura de ti centralizada local a una configuración de nube inclusiva que incorpora las cargas de trabajo y aplicaciones de productividad personal basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="41d36-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="41d36-105">Infraestructura de TI existente de Contoso</span><span class="sxs-lookup"><span data-stu-id="41d36-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="41d36-106">Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="41d36-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="41d36-107">La figura 1 muestra la oficina central con centros de aplicaciones, una red perimetral e Internet.</span><span class="sxs-lookup"><span data-stu-id="41d36-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infraestructura de TI existente de Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="41d36-109">**Figura 1: infraestructura de TI existente de Contoso**</span><span class="sxs-lookup"><span data-stu-id="41d36-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="41d36-110">En los centros de datos de aplicaciones locales se hospeda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41d36-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="41d36-111">Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos de Linux.</span><span class="sxs-lookup"><span data-stu-id="41d36-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="41d36-112">Un conjunto de servidores de SharePoint heredados.</span><span class="sxs-lookup"><span data-stu-id="41d36-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="41d36-113">Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="41d36-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="41d36-114">Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares.</span><span class="sxs-lookup"><span data-stu-id="41d36-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="41d36-115">Estos servidores están bajo el control de los departamentos de TI regionales.</span><span class="sxs-lookup"><span data-stu-id="41d36-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="41d36-116">La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.</span><span class="sxs-lookup"><span data-stu-id="41d36-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="41d36-117">En la DMZ de la sede central de Contoso, los distintos conjuntos de servidores proporcionan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41d36-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="41d36-118">Hospedaje para el sitio web público de Contoso, desde el que los clientes pueden solicitar productos, piezas, suministros y servicio.</span><span class="sxs-lookup"><span data-stu-id="41d36-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="41d36-119">Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.</span><span class="sxs-lookup"><span data-stu-id="41d36-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="41d36-120">Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="41d36-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="41d36-121">Necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="41d36-121">Contoso business needs</span></span>

<span data-ttu-id="41d36-122">Las necesidades empresariales de Contoso se dividen en cinco categorías principales:</span><span class="sxs-lookup"><span data-stu-id="41d36-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="41d36-123">**Productividad**</span><span class="sxs-lookup"><span data-stu-id="41d36-123">**Productivity**</span></span>

- <span data-ttu-id="41d36-124">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="41d36-124">Make collaboration easier</span></span>

  <span data-ttu-id="41d36-125">Reemplace el correo electrónico y la colaboración basada en recursos compartidos de archivos con un modelo en línea que permita cambios en tiempo real en documentos, reuniones en línea más sencillas y conversaciones de conversación capturadas.</span><span class="sxs-lookup"><span data-stu-id="41d36-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="41d36-126">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="41d36-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="41d36-127">Con muchos empleados que trabajan desde casa o en el campo, reemplace la solución VPN con cuellos de botella por el acceso de tipo de Contoso a los datos y recursos de la nube.</span><span class="sxs-lookup"><span data-stu-id="41d36-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="41d36-128">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="41d36-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="41d36-129">Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.</span><span class="sxs-lookup"><span data-stu-id="41d36-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="41d36-130">**Seguridad**</span><span class="sxs-lookup"><span data-stu-id="41d36-130">**Security**</span></span>

- <span data-ttu-id="41d36-131">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="41d36-131">Identity and access management</span></span>

  <span data-ttu-id="41d36-132">Exigir la autenticación multifactor y otras formas de autenticación y proteger las credenciales de las cuentas de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="41d36-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="41d36-133">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="41d36-133">Threat protection</span></span>

  <span data-ttu-id="41d36-134">Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="41d36-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="41d36-135">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="41d36-135">Information protection</span></span>

  <span data-ttu-id="41d36-136">Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.</span><span class="sxs-lookup"><span data-stu-id="41d36-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="41d36-137">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="41d36-137">Security management</span></span>

  <span data-ttu-id="41d36-138">Supervise el postura de seguridad y detecte y responda a amenazas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="41d36-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="41d36-139">**Acceso móvil y remoto, y socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="41d36-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="41d36-140">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="41d36-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="41d36-141">Implemente su propio dispositivo (BYOD) y la administración de dispositivos de propiedad de la empresa para garantizar el acceso seguro, el comportamiento correcto de las aplicaciones y la protección de datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="41d36-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="41d36-142">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="41d36-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="41d36-143">Reducir los costos de mantenimiento y soporte técnico y mejorar el rendimiento de la solución de acceso remoto moviendo los recursos a los que se accede habitualmente a la nube.</span><span class="sxs-lookup"><span data-stu-id="41d36-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="41d36-144">Proporcionar mejor conectividad y menor overhead para las transacciones de negocio a susiness (B2B)</span><span class="sxs-lookup"><span data-stu-id="41d36-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="41d36-145">Reemplace una extranet de asociados con una detección de asociados con una solución basada en la nube que use la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="41d36-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="41d36-146">**Cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="41d36-146">**Compliance**</span></span>

- <span data-ttu-id="41d36-147">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="41d36-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="41d36-148">Garantizar el cumplimiento de las regulaciones de la industria y la regional para el almacenamiento de datos, el cifrado, la privacidad de datos y las regulaciones de datos personales, como el Reglamento General de protección de datos (RGPD) para la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="41d36-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="41d36-149">**Administración**</span><span class="sxs-lookup"><span data-stu-id="41d36-149">**Management**</span></span>

- <span data-ttu-id="41d36-150">Reducir la sobrecarga de TI para administrar el software que se ejecuta en equipos y dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="41d36-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="41d36-151">Automatizar la instalación de actualizaciones para el sistema operativo Windows y las aplicaciones de Microsoft 365 para empresas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="41d36-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="41d36-152">Asignación de las necesidades empresariales de Contoso a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="41d36-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="41d36-153">El Departamento de TI de Contoso determinó la siguiente asignación de necesidades empresariales a las características de Microsoft 365 E5 antes de la implementación:</span><span class="sxs-lookup"><span data-stu-id="41d36-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="41d36-154">Categoría</span><span class="sxs-lookup"><span data-stu-id="41d36-154">Category</span></span> | <span data-ttu-id="41d36-155">Necesidad empresarial</span><span class="sxs-lookup"><span data-stu-id="41d36-155">Business need</span></span> | <span data-ttu-id="41d36-156">Microsoft 365 para productos o características de empresa</span><span class="sxs-lookup"><span data-stu-id="41d36-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="41d36-157">Productividad</span><span class="sxs-lookup"><span data-stu-id="41d36-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="41d36-158">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="41d36-158">Make collaboration easier</span></span> | <span data-ttu-id="41d36-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="41d36-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="41d36-160">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="41d36-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="41d36-161">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="41d36-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="41d36-162">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="41d36-162">Increase creativity and innovation</span></span> | <span data-ttu-id="41d36-163">Windows Ink, Cortana en el trabajo, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="41d36-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="41d36-164">Seguridad</span><span class="sxs-lookup"><span data-stu-id="41d36-164">Security</span></span> |  |  |
|  | <span data-ttu-id="41d36-165">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="41d36-165">Identity & access management</span></span> | <span data-ttu-id="41d36-166">Cuentas de administrador global dedicadas con Azure multi-factor Authentication (MFA) y Azure Active Directory privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="41d36-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="41d36-167">MFA para todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="41d36-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="41d36-168">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="41d36-168">Conditional Access</span></span> <BR> <span data-ttu-id="41d36-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="41d36-169">Windows Hello</span></span> <BR> <span data-ttu-id="41d36-170">Credential Guard de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="41d36-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="41d36-171">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="41d36-171">Threat protection</span></span> | <span data-ttu-id="41d36-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="41d36-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="41d36-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="41d36-173">Windows Defender</span></span> <BR> <span data-ttu-id="41d36-174">Protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="41d36-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="41d36-175">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="41d36-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="41d36-176">Respuesta y investigación de amenazas de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41d36-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="41d36-177">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="41d36-177">Information protection</span></span> | <span data-ttu-id="41d36-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="41d36-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="41d36-179">Prevención de pérdida de datos (DLP)</span><span class="sxs-lookup"><span data-stu-id="41d36-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="41d36-180">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="41d36-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="41d36-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41d36-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="41d36-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="41d36-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="41d36-183">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="41d36-183">Security management</span></span> | <span data-ttu-id="41d36-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="41d36-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="41d36-185">Centro de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="41d36-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="41d36-186">Acceso móvil y remoto, y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="41d36-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="41d36-187">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="41d36-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="41d36-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="41d36-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="41d36-189">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="41d36-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="41d36-190">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="41d36-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="41d36-191">Mejorar la conectividad y reducir la sobrecarga para las transacciones B2B</span><span class="sxs-lookup"><span data-stu-id="41d36-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="41d36-192">Autenticación federada y recursos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="41d36-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="41d36-193">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="41d36-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="41d36-194">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="41d36-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="41d36-195">Características de RGPD en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41d36-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="41d36-196">Administración</span><span class="sxs-lookup"><span data-stu-id="41d36-196">Management</span></span> |  |  |
|  | <span data-ttu-id="41d36-197">Reducir la sobrecarga de TI para instalar actualizaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="41d36-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="41d36-198">Anillos de implementación</span><span class="sxs-lookup"><span data-stu-id="41d36-198">Deployment rings</span></span> <BR> <span data-ttu-id="41d36-199">Actualizaciones de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="41d36-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="41d36-200">Actualizaciones para las aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="41d36-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="41d36-201">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="41d36-201">Next step</span></span>

<span data-ttu-id="41d36-202">[Obtenga información](contoso-networking.md) sobre la red local de Contoso Corporation y cómo se optimizó para el acceso y la latencia de los recursos basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41d36-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="41d36-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="41d36-203">See also</span></span>

[<span data-ttu-id="41d36-204">Información general de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="41d36-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="41d36-205">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="41d36-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
