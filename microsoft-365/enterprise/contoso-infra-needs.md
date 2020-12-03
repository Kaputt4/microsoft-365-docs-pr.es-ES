---
title: Infraestructura de ti y necesidades empresariales de Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la estructura básica de la infraestructura de ti local de Contoso y cómo se satisfacen las necesidades empresariales de Microsoft 365 para la empresa.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558411"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="7b369-103">Infraestructura de ti y necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="7b369-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="7b369-104">Contoso está pasando de una infraestructura de ti centralizada local a una configuración de nube inclusiva que incorpora las cargas de trabajo y aplicaciones de productividad personal basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="7b369-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="7b369-105">Infraestructura de TI existente de Contoso</span><span class="sxs-lookup"><span data-stu-id="7b369-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="7b369-106">Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="7b369-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="7b369-107">A continuación se muestra la oficina central con centros de aplicaciones, una red perimetral e Internet.</span><span class="sxs-lookup"><span data-stu-id="7b369-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infraestructura de TI existente de Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="7b369-109">En los centros de datos de aplicaciones locales se hospeda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b369-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="7b369-110">Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos de Linux.</span><span class="sxs-lookup"><span data-stu-id="7b369-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="7b369-111">Un conjunto de servidores de SharePoint heredados.</span><span class="sxs-lookup"><span data-stu-id="7b369-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="7b369-112">Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="7b369-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="7b369-113">Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares.</span><span class="sxs-lookup"><span data-stu-id="7b369-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="7b369-114">Estos servidores están bajo el control de los departamentos de TI regionales.</span><span class="sxs-lookup"><span data-stu-id="7b369-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="7b369-115">La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.</span><span class="sxs-lookup"><span data-stu-id="7b369-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="7b369-116">En la DMZ de la sede central de Contoso, los distintos conjuntos de servidores proporcionan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b369-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="7b369-117">Hospedaje para el sitio web público de Contoso, desde el que los clientes pueden solicitar productos, piezas, suministros y servicio.</span><span class="sxs-lookup"><span data-stu-id="7b369-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="7b369-118">Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.</span><span class="sxs-lookup"><span data-stu-id="7b369-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="7b369-119">Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="7b369-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="7b369-120">Necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="7b369-120">Contoso business needs</span></span>

<span data-ttu-id="7b369-121">Las necesidades empresariales de Contoso se dividen en cinco categorías principales:</span><span class="sxs-lookup"><span data-stu-id="7b369-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="7b369-122">**Productividad**</span><span class="sxs-lookup"><span data-stu-id="7b369-122">**Productivity**</span></span>

- <span data-ttu-id="7b369-123">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="7b369-123">Make collaboration easier</span></span>

  <span data-ttu-id="7b369-124">Reemplace el correo electrónico y la colaboración basada en recursos compartidos de archivos con un modelo en línea que permita cambios en tiempo real en documentos, reuniones en línea más sencillas y conversaciones de conversación capturadas.</span><span class="sxs-lookup"><span data-stu-id="7b369-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="7b369-125">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="7b369-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="7b369-126">Con muchos empleados que trabajan desde casa o en el campo, reemplace la solución VPN con cuellos de botella por el acceso de tipo de Contoso a los datos y recursos de la nube.</span><span class="sxs-lookup"><span data-stu-id="7b369-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="7b369-127">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="7b369-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="7b369-128">Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.</span><span class="sxs-lookup"><span data-stu-id="7b369-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="7b369-129">**Seguridad**</span><span class="sxs-lookup"><span data-stu-id="7b369-129">**Security**</span></span>

- <span data-ttu-id="7b369-130">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="7b369-130">Identity and access management</span></span>

  <span data-ttu-id="7b369-131">Exigir la autenticación multifactor y otras formas de autenticación y proteger las credenciales de las cuentas de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="7b369-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="7b369-132">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="7b369-132">Threat protection</span></span>

  <span data-ttu-id="7b369-133">Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7b369-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="7b369-134">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="7b369-134">Information protection</span></span>

  <span data-ttu-id="7b369-135">Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.</span><span class="sxs-lookup"><span data-stu-id="7b369-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="7b369-136">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="7b369-136">Security management</span></span>

  <span data-ttu-id="7b369-137">Supervise el postura de seguridad y detecte y responda a amenazas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="7b369-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="7b369-138">**Acceso móvil y remoto, y socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="7b369-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="7b369-139">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="7b369-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="7b369-140">Implemente su propio dispositivo (BYOD) y la administración de dispositivos de propiedad de la empresa para garantizar el acceso seguro, el comportamiento correcto de las aplicaciones y la protección de datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="7b369-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="7b369-141">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="7b369-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="7b369-142">Reducir los costos de mantenimiento y soporte técnico y mejorar el rendimiento de la solución de acceso remoto moviendo los recursos a los que se accede habitualmente a la nube.</span><span class="sxs-lookup"><span data-stu-id="7b369-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="7b369-143">Proporcionar mejor conectividad y menor overhead para las transacciones de negocio a susiness (B2B)</span><span class="sxs-lookup"><span data-stu-id="7b369-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="7b369-144">Reemplace una extranet de asociados con una detección de asociados con una solución basada en la nube que use la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="7b369-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="7b369-145">**Cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="7b369-145">**Compliance**</span></span>

- <span data-ttu-id="7b369-146">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="7b369-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="7b369-147">Garantizar el cumplimiento de las regulaciones de la industria y la regional para el almacenamiento de datos, el cifrado, la privacidad de datos y las regulaciones de datos personales, como el Reglamento General de protección de datos (RGPD) para la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="7b369-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="7b369-148">**Administración**</span><span class="sxs-lookup"><span data-stu-id="7b369-148">**Management**</span></span>

- <span data-ttu-id="7b369-149">Reducir la sobrecarga de TI para administrar el software que se ejecuta en equipos y dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="7b369-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="7b369-150">Automatizar la instalación de actualizaciones para el sistema operativo Windows y las aplicaciones de Microsoft 365 para empresas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7b369-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="7b369-151">Asignación de las necesidades empresariales de Contoso a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7b369-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="7b369-152">El Departamento de TI de Contoso determinó la siguiente asignación de necesidades empresariales a las características de Microsoft 365 E5 antes de la implementación:</span><span class="sxs-lookup"><span data-stu-id="7b369-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="7b369-153">Categoría</span><span class="sxs-lookup"><span data-stu-id="7b369-153">Category</span></span> | <span data-ttu-id="7b369-154">Necesidad empresarial</span><span class="sxs-lookup"><span data-stu-id="7b369-154">Business need</span></span> | <span data-ttu-id="7b369-155">Microsoft 365 para productos o características de empresa</span><span class="sxs-lookup"><span data-stu-id="7b369-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="7b369-156">Productividad</span><span class="sxs-lookup"><span data-stu-id="7b369-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="7b369-157">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="7b369-157">Make collaboration easier</span></span> | <span data-ttu-id="7b369-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="7b369-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="7b369-159">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="7b369-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="7b369-160">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="7b369-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="7b369-161">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="7b369-161">Increase creativity and innovation</span></span> | <span data-ttu-id="7b369-162">Windows Ink, Cortana en el trabajo, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7b369-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="7b369-163">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7b369-163">Security</span></span> |  |  |
|  | <span data-ttu-id="7b369-164">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="7b369-164">Identity & access management</span></span> | <span data-ttu-id="7b369-165">Cuentas de administrador global dedicadas con Azure AD multi-factor Authentication (MFA) y Azure AD privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="7b369-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="7b369-166">MFA para todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="7b369-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="7b369-167">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="7b369-167">Conditional Access</span></span> <BR> <span data-ttu-id="7b369-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="7b369-168">Windows Hello</span></span> <BR> <span data-ttu-id="7b369-169">Credential Guard de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="7b369-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="7b369-170">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="7b369-170">Threat protection</span></span> | <span data-ttu-id="7b369-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="7b369-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="7b369-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="7b369-172">Windows Defender</span></span> <BR> <span data-ttu-id="7b369-173">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7b369-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="7b369-174">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7b369-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="7b369-175">Respuesta y investigación de amenazas de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b369-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="7b369-176">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="7b369-176">Information protection</span></span> | <span data-ttu-id="7b369-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7b369-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="7b369-178">Prevención de pérdida de datos (DLP)</span><span class="sxs-lookup"><span data-stu-id="7b369-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="7b369-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="7b369-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="7b369-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7b369-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="7b369-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7b369-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="7b369-182">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="7b369-182">Security management</span></span> | <span data-ttu-id="7b369-183">Azure defender</span><span class="sxs-lookup"><span data-stu-id="7b369-183">Azure Defender</span></span>  <BR> <span data-ttu-id="7b369-184">Centro de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="7b369-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="7b369-185">Acceso móvil y remoto, y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="7b369-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="7b369-186">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="7b369-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="7b369-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7b369-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="7b369-188">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="7b369-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="7b369-189">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="7b369-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="7b369-190">Mejorar la conectividad y reducir la sobrecarga para las transacciones B2B</span><span class="sxs-lookup"><span data-stu-id="7b369-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="7b369-191">Autenticación federada y recursos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="7b369-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="7b369-192">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7b369-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="7b369-193">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="7b369-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="7b369-194">Características de RGPD en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b369-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="7b369-195">Administración</span><span class="sxs-lookup"><span data-stu-id="7b369-195">Management</span></span> |  |  |
|  | <span data-ttu-id="7b369-196">Reducir la sobrecarga de TI para instalar actualizaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="7b369-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="7b369-197">Actualizaciones de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b369-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="7b369-198">Actualizaciones para las aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7b369-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="7b369-199">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7b369-199">Next step</span></span>

<span data-ttu-id="7b369-200">Obtenga información sobre la [red local de](contoso-networking.md) contoso Corporation y cómo se optimizó para el acceso y la latencia de los recursos basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b369-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b369-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b369-201">See also</span></span>

[<span data-ttu-id="7b369-202">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7b369-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7b369-203">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="7b369-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
