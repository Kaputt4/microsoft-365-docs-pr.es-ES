---
title: Infraestructura de TI de Contoso y necesidades empresariales
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
description: Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo Microsoft 365 para empresas cumple las necesidades empresariales de la empresa.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558411"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="192f0-103">Infraestructura de TI de Contoso y necesidades empresariales</span><span class="sxs-lookup"><span data-stu-id="192f0-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="192f0-104">Contoso está pasando de una infraestructura de TI centralizada local a una configuración de nube inclusiva que incorpora aplicaciones y cargas de trabajo de productividad personal basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="192f0-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="192f0-105">Infraestructura de TI de Contoso existente</span><span class="sxs-lookup"><span data-stu-id="192f0-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="192f0-106">Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="192f0-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="192f0-107">Esta es la oficina central con centros de datos de aplicaciones, una red perimetral e Internet.</span><span class="sxs-lookup"><span data-stu-id="192f0-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infraestructura de TI de Contoso existente](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="192f0-109">En los centros de datos de aplicaciones locales se hospeda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="192f0-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="192f0-110">Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos linux.</span><span class="sxs-lookup"><span data-stu-id="192f0-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="192f0-111">Un conjunto de servidores de SharePoint heredados.</span><span class="sxs-lookup"><span data-stu-id="192f0-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="192f0-112">Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="192f0-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="192f0-113">Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares.</span><span class="sxs-lookup"><span data-stu-id="192f0-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="192f0-114">Estos servidores están bajo el control de los departamentos de TI regionales.</span><span class="sxs-lookup"><span data-stu-id="192f0-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="192f0-115">La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.</span><span class="sxs-lookup"><span data-stu-id="192f0-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="192f0-116">En la red perimetral de la sede de Contoso, distintos conjuntos de servidores proporcionan:</span><span class="sxs-lookup"><span data-stu-id="192f0-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="192f0-117">Hospedaje para el sitio web público de Contoso, desde el que los clientes pueden pedir productos, elementos, suministros y servicio.</span><span class="sxs-lookup"><span data-stu-id="192f0-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="192f0-118">Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.</span><span class="sxs-lookup"><span data-stu-id="192f0-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="192f0-119">Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="192f0-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="192f0-120">Necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="192f0-120">Contoso business needs</span></span>

<span data-ttu-id="192f0-121">Las necesidades empresariales de Contoso se divide en cinco categorías principales:</span><span class="sxs-lookup"><span data-stu-id="192f0-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="192f0-122">**Productividad**</span><span class="sxs-lookup"><span data-stu-id="192f0-122">**Productivity**</span></span>

- <span data-ttu-id="192f0-123">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="192f0-123">Make collaboration easier</span></span>

  <span data-ttu-id="192f0-124">Reemplace la colaboración basada en el uso compartido de archivos y el correo electrónico con un modelo en línea que permita cambios en tiempo real en documentos, reuniones en línea más fáciles y conversaciones capturadas.</span><span class="sxs-lookup"><span data-stu-id="192f0-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="192f0-125">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="192f0-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="192f0-126">Con muchos empleados trabajando desde casa o en el campo, reemplace la solución VPN con cuellos de botella por un acceso eficaz a los datos y recursos de Contoso en la nube.</span><span class="sxs-lookup"><span data-stu-id="192f0-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="192f0-127">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="192f0-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="192f0-128">Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.</span><span class="sxs-lookup"><span data-stu-id="192f0-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="192f0-129">**Seguridad**</span><span class="sxs-lookup"><span data-stu-id="192f0-129">**Security**</span></span>

- <span data-ttu-id="192f0-130">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="192f0-130">Identity and access management</span></span>

  <span data-ttu-id="192f0-131">Exigir multifactor y otras formas de autenticación y proteger las credenciales de cuenta de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="192f0-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="192f0-132">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="192f0-132">Threat protection</span></span>

  <span data-ttu-id="192f0-133">Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="192f0-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="192f0-134">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="192f0-134">Information protection</span></span>

  <span data-ttu-id="192f0-135">Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.</span><span class="sxs-lookup"><span data-stu-id="192f0-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="192f0-136">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="192f0-136">Security management</span></span>

  <span data-ttu-id="192f0-137">Supervise la posición de seguridad y detecte y responda a las amenazas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="192f0-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="192f0-138">**Acceso móvil y remoto, y socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="192f0-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="192f0-139">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="192f0-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="192f0-140">Implementa bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span><span class="sxs-lookup"><span data-stu-id="192f0-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="192f0-141">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="192f0-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="192f0-142">Reduzca los costos de mantenimiento y soporte técnico y mejore el rendimiento de la solución de acceso remoto moviendo los recursos de acceso frecuente a la nube.</span><span class="sxs-lookup"><span data-stu-id="192f0-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="192f0-143">Proporcionar una mejor conectividad y una menor sobrecarga para las transacciones de negocio a suspenso (B2B)</span><span class="sxs-lookup"><span data-stu-id="192f0-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="192f0-144">Reemplace una extranet de asociados costosa y con vencimiento por una solución basada en la nube que use la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="192f0-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="192f0-145">**Cumplimiento**</span><span class="sxs-lookup"><span data-stu-id="192f0-145">**Compliance**</span></span>

- <span data-ttu-id="192f0-146">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="192f0-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="192f0-147">Garantizar el cumplimiento de las normativas regionales y del sector para el almacenamiento de datos, el cifrado, la privacidad de los datos y las normativas de datos personales, como el Reglamento general de protección de datos (RGPD) para la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="192f0-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="192f0-148">**Administración**</span><span class="sxs-lookup"><span data-stu-id="192f0-148">**Management**</span></span>

- <span data-ttu-id="192f0-149">Reducir la sobrecarga de TI para administrar el software que se ejecuta en equipos y dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="192f0-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="192f0-150">Automatice la instalación de actualizaciones en el sistema operativo Windows y aplicaciones de Microsoft 365 para empresas en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="192f0-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="192f0-151">Asignación de las necesidades empresariales de Contoso a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="192f0-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="192f0-152">El departamento de TI de Contoso determinó la siguiente asignación de las necesidades empresariales a las características de Microsoft 365 E5 antes de la implementación:</span><span class="sxs-lookup"><span data-stu-id="192f0-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="192f0-153">Categoría</span><span class="sxs-lookup"><span data-stu-id="192f0-153">Category</span></span> | <span data-ttu-id="192f0-154">Necesidad empresarial</span><span class="sxs-lookup"><span data-stu-id="192f0-154">Business need</span></span> | <span data-ttu-id="192f0-155">Características o productos de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="192f0-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="192f0-156">Productividad</span><span class="sxs-lookup"><span data-stu-id="192f0-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="192f0-157">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="192f0-157">Make collaboration easier</span></span> | <span data-ttu-id="192f0-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="192f0-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="192f0-159">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="192f0-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="192f0-160">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="192f0-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="192f0-161">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="192f0-161">Increase creativity and innovation</span></span> | <span data-ttu-id="192f0-162">Windows Ink, Cortana en el trabajo, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="192f0-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="192f0-163">Seguridad</span><span class="sxs-lookup"><span data-stu-id="192f0-163">Security</span></span> |  |  |
|  | <span data-ttu-id="192f0-164">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="192f0-164">Identity & access management</span></span> | <span data-ttu-id="192f0-165">Cuentas de administrador global dedicadas con Azure AD Multi-Factor Authentication (MFA) y Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="192f0-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="192f0-166">MFA para todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="192f0-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="192f0-167">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="192f0-167">Conditional Access</span></span> <BR> <span data-ttu-id="192f0-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="192f0-168">Windows Hello</span></span> <BR> <span data-ttu-id="192f0-169">Credential Guard de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="192f0-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="192f0-170">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="192f0-170">Threat protection</span></span> | <span data-ttu-id="192f0-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="192f0-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="192f0-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="192f0-172">Windows Defender</span></span> <BR> <span data-ttu-id="192f0-173">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="192f0-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="192f0-174">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="192f0-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="192f0-175">Investigación y respuesta de amenazas de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="192f0-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="192f0-176">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="192f0-176">Information protection</span></span> | <span data-ttu-id="192f0-177">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="192f0-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="192f0-178">Prevención de pérdida de datos (DLP)</span><span class="sxs-lookup"><span data-stu-id="192f0-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="192f0-179">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="192f0-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="192f0-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="192f0-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="192f0-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="192f0-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="192f0-182">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="192f0-182">Security management</span></span> | <span data-ttu-id="192f0-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="192f0-183">Azure Defender</span></span>  <BR> <span data-ttu-id="192f0-184">Centro de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="192f0-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="192f0-185">Acceso móvil y remoto, y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="192f0-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="192f0-186">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="192f0-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="192f0-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="192f0-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="192f0-188">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="192f0-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="192f0-189">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="192f0-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="192f0-190">Mejorar la conectividad y reducir la sobrecarga para las transacciones B2B</span><span class="sxs-lookup"><span data-stu-id="192f0-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="192f0-191">Autenticación federada y recursos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="192f0-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="192f0-192">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="192f0-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="192f0-193">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="192f0-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="192f0-194">Características del RGPD en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="192f0-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="192f0-195">Administración</span><span class="sxs-lookup"><span data-stu-id="192f0-195">Management</span></span> |  |  |
|  | <span data-ttu-id="192f0-196">Reducir la sobrecarga de TI para instalar actualizaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="192f0-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="192f0-197">Actualizaciones de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="192f0-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="192f0-198">Actualizaciones para las aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="192f0-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="192f0-199">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="192f0-199">Next step</span></span>

<span data-ttu-id="192f0-200">Obtenga información sobre la red local de Contoso [Corporation](contoso-networking.md) y cómo se optimizó para el acceso y la latencia a los recursos basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="192f0-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="192f0-201">Vea también</span><span class="sxs-lookup"><span data-stu-id="192f0-201">See also</span></span>

[<span data-ttu-id="192f0-202">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="192f0-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="192f0-203">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="192f0-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
