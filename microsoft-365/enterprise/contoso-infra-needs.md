---
title: Necesidades empresariales y de infraestructura de TI de Contoso
author: JoeDavies-MSFT
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
description: Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo sus necesidades empresariales fueron satisfechas mediante Microsoft 365 Enterprise.
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369591"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="b169b-103">Necesidades empresariales y de infraestructura de TI de Contoso</span><span class="sxs-lookup"><span data-stu-id="b169b-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="b169b-104">**Resumen:** Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo sus necesidades empresariales fueron satisfechas mediante Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b169b-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b169b-105">Contoso ha realizado la transición de una infraestructura de TI centralizada local a una infraestructura de nube inclusiva que incorpora las cargas de trabajo de productividad del personal y las aplicaciones basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="b169b-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="b169b-106">Infraestructura de TI existente de Contoso</span><span class="sxs-lookup"><span data-stu-id="b169b-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="b169b-107">Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="b169b-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="b169b-108">En la Figura 1 se muestra una oficina central con centros de datos de aplicaciones, una red perimetral e Internet.</span><span class="sxs-lookup"><span data-stu-id="b169b-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Infraestructura de TI existente de Contoso](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="b169b-110">**Figura 1: Infraestructura de TI existente de Contoso**</span><span class="sxs-lookup"><span data-stu-id="b169b-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="b169b-111">En los centros de datos de aplicaciones locales se hospeda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b169b-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="b169b-112">Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos de Linux.</span><span class="sxs-lookup"><span data-stu-id="b169b-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="b169b-113">Un conjunto de servidores de SharePoint heredados.</span><span class="sxs-lookup"><span data-stu-id="b169b-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="b169b-114">Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="b169b-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="b169b-115">Además, cada una de las oficinas centrales regionales es compatible con un conjunto de servidores que tiene un conjunto de aplicaciones similares.</span><span class="sxs-lookup"><span data-stu-id="b169b-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="b169b-116">Estos servidores están bajo el control de los departamentos de TI regionales.</span><span class="sxs-lookup"><span data-stu-id="b169b-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="b169b-117">La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.</span><span class="sxs-lookup"><span data-stu-id="b169b-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="b169b-118">En la red perimetral de la sede central de Contoso, los distintos conjuntos de servidores proporcionan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b169b-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="b169b-119">Hospedaje del sitio web público de Contoso, desde el que los clientes pueden solicitar productos, piezas, suministros o servicio.</span><span class="sxs-lookup"><span data-stu-id="b169b-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="b169b-120">Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.</span><span class="sxs-lookup"><span data-stu-id="b169b-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="b169b-121">Acceso remoto a la intranet de Contoso basado en VPN (Red privada virtual) y proxy web para los trabajadores de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="b169b-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="b169b-122">Necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="b169b-122">Contoso's business needs</span></span>

<span data-ttu-id="b169b-123">Las necesidades empresariales de Contoso se dividen en cinco categorías principales.</span><span class="sxs-lookup"><span data-stu-id="b169b-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="b169b-124">Productividad:</span><span class="sxs-lookup"><span data-stu-id="b169b-124">Productivity:</span></span>

- <span data-ttu-id="b169b-125">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="b169b-125">Make collaboration easier</span></span>

  <span data-ttu-id="b169b-126">Reemplace la colaboración basada en el correo electrónico y los recursos compartidos de archivos con un modelo en línea que permita modificar los documentos en tiempo real, facilite las reuniones en línea y capture las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b169b-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="b169b-127">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="b169b-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="b169b-128">Con tantos empleados trabajando desde casa o sobre el terreno, cambie la solución VPN con cuellos de botella por el acceso eficaz a los datos y recursos de Contoso en la nube.</span><span class="sxs-lookup"><span data-stu-id="b169b-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="b169b-129">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="b169b-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="b169b-130">Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.</span><span class="sxs-lookup"><span data-stu-id="b169b-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="b169b-131">Seguridad:</span><span class="sxs-lookup"><span data-stu-id="b169b-131">Security:</span></span>

- <span data-ttu-id="b169b-132">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="b169b-132">Identity and access management</span></span>

  <span data-ttu-id="b169b-133">Exija la autenticación multifactor y de otros tipos, y proteja las credenciales de las cuentas de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="b169b-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="b169b-134">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="b169b-134">Threat protection</span></span>

  <span data-ttu-id="b169b-135">Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b169b-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="b169b-136">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="b169b-136">Information protection</span></span>

  <span data-ttu-id="b169b-137">Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y manufactura y la información de los empleados.</span><span class="sxs-lookup"><span data-stu-id="b169b-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="b169b-138">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="b169b-138">Security management</span></span>

  <span data-ttu-id="b169b-139">Supervise el nivel de seguridad y sea capaz de detectar y responder a las amenazas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b169b-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="b169b-140">Acceso móvil y remoto, y socios comerciales:</span><span class="sxs-lookup"><span data-stu-id="b169b-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="b169b-141">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="b169b-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="b169b-142">Instaure la administración de dispositivos Bring Your Own Device (BYOD) y de propiedad de la empresa para garantizar el acceso seguro, el comportamiento correcto de las aplicaciones y la protección de los datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="b169b-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="b169b-143">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="b169b-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="b169b-144">Reduzca los costos de mantenimiento y soporte técnico, y mejore el rendimiento de la solución de acceso remoto moviendo a la nube los recursos de uso más frecuente.</span><span class="sxs-lookup"><span data-stu-id="b169b-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="b169b-145">Proporcionar mejor conectividad y menos sobrecarga para las transacciones de negocio a negocio (B2B)</span><span class="sxs-lookup"><span data-stu-id="b169b-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="b169b-146">Reemplace la extranet de partners, anticuada y costosa, por una solución basada en la nube que use la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="b169b-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="b169b-147">Cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="b169b-147">Compliance:</span></span>

- <span data-ttu-id="b169b-148">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="b169b-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="b169b-149">Cumpla con los reglamentos regionales y del sector sobre almacenamiento de datos, cifrado, privacidad de datos y normativas de datos personales, como el Reglamento general de protección de datos (RGPD) de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="b169b-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="b169b-150">Administración:</span><span class="sxs-lookup"><span data-stu-id="b169b-150">Management:</span></span>

- <span data-ttu-id="b169b-151">Reducir la sobrecarga de TI de la administración de software en los equipos y dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="b169b-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="b169b-152">Automatice la instalación de actualizaciones para el sistema operativo Windows y Microsoft Office ProPlus en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="b169b-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="b169b-153">Asignación de las necesidades empresariales de Contoso a Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b169b-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b169b-154">Antes de la implementación, el departamento de TI de Contoso determinó la siguiente asignación de las necesidades empresariales a las características de Microsoft 365 Enterprise E5:</span><span class="sxs-lookup"><span data-stu-id="b169b-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="b169b-155">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="b169b-155">**Category**</span></span> | <span data-ttu-id="b169b-156">**Necesidad empresarial**</span><span class="sxs-lookup"><span data-stu-id="b169b-156">**Business need**</span></span> | <span data-ttu-id="b169b-157">**Productos o características de Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="b169b-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="b169b-158">Productividad</span><span class="sxs-lookup"><span data-stu-id="b169b-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="b169b-159">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="b169b-159">Make collaboration easier</span></span> | <span data-ttu-id="b169b-160">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="b169b-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="b169b-161">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="b169b-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="b169b-162">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="b169b-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b169b-163">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="b169b-163">Increase creativity and innovation</span></span> | <span data-ttu-id="b169b-164">Windows Ink, Cortana en el trabajo, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b169b-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="b169b-165">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b169b-165">Security</span></span> |  |  |
|  | <span data-ttu-id="b169b-166">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="b169b-166">Identity & access management</span></span> | <span data-ttu-id="b169b-167">Cuentas de administrador global dedicadas con la autenticación multifactor (MFA) Azure y Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="b169b-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="b169b-168">MFA para todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="b169b-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="b169b-169">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="b169b-169">Conditional access</span></span> <BR> <span data-ttu-id="b169b-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b169b-170">Windows Hello</span></span> <BR> <span data-ttu-id="b169b-171">Credential Guard de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b169b-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="b169b-172">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="b169b-172">Threat protection</span></span> | <span data-ttu-id="b169b-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="b169b-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="b169b-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b169b-174">Windows Defender</span></span> <BR> <span data-ttu-id="b169b-175">Protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="b169b-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b169b-176">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="b169b-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b169b-177">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="b169b-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="b169b-178">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="b169b-178">Information protection</span></span> | <span data-ttu-id="b169b-179">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="b169b-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="b169b-180">Prevención de pérdida de datos (DLP) de Office 365</span><span class="sxs-lookup"><span data-stu-id="b169b-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="b169b-181">Windows Information Protection (WIP)</span><span class="sxs-lookup"><span data-stu-id="b169b-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="b169b-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b169b-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="b169b-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b169b-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b169b-184">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="b169b-184">Security management</span></span> | <span data-ttu-id="b169b-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="b169b-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="b169b-186">Centro de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b169b-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="b169b-187">Acceso móvil y remoto, y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="b169b-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="b169b-188">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="b169b-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="b169b-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b169b-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b169b-190">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="b169b-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="b169b-191">Cargas de trabajo de Microsoft 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="b169b-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b169b-192">Proporcionar mejor conectividad y menos sobrecarga para las transacciones B2B</span><span class="sxs-lookup"><span data-stu-id="b169b-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="b169b-193">Autenticación federada y recursos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="b169b-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="b169b-194">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b169b-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="b169b-195">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="b169b-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="b169b-196">Características del RGPD en Office 365</span><span class="sxs-lookup"><span data-stu-id="b169b-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="b169b-197">Administración</span><span class="sxs-lookup"><span data-stu-id="b169b-197">Management</span></span> |  |  |
|  | <span data-ttu-id="b169b-198">Reducir la sobrecarga de TI para la instalación de actualizaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="b169b-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="b169b-199">Anillos de implementación</span><span class="sxs-lookup"><span data-stu-id="b169b-199">Deployment rings</span></span> <BR> <span data-ttu-id="b169b-200">Actualizaciones de Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b169b-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="b169b-201">Actualizaciones de Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="b169b-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="b169b-202">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="b169b-202">Next step</span></span>

<span data-ttu-id="b169b-203">[Obtenga más información](contoso-networking.md) sobre la red local de Contoso Corporation y cómo se optimizó para el acceso y la latencia para los recursos basados en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b169b-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b169b-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="b169b-204">See also</span></span>

[<span data-ttu-id="b169b-205">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="b169b-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b169b-206">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="b169b-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
