---
title: Necesidades empresariales y de infraestructura de TI de Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo sus necesidades empresariales se pueden satisfacer mediante Microsoft 365 Enterprise.
ms.openlocfilehash: bd259f367cdf3417e32671457f248029c853b6f8
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283687"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="87fe4-103">Necesidades empresariales y de infraestructura de TI de Contoso</span><span class="sxs-lookup"><span data-stu-id="87fe4-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="87fe4-104">**Resumen:** Comprenda la estructura básica de la infraestructura de TI local de Contoso y cómo sus necesidades empresariales se pueden satisfacer mediante Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="87fe4-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="87fe4-105">Contoso ha realizado la transición de una infraestructura de TI centralizada local a una infraestructura de nube inclusiva que incorpora las cargas de trabajo de productividad del personal y las aplicaciones basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="87fe4-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="87fe4-106">Infraestructura de TI existente de Contoso</span><span class="sxs-lookup"><span data-stu-id="87fe4-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="87fe4-107">Contoso usa una infraestructura de TI local mayoritariamente centralizada, con centros de datos de aplicaciones en la sede de París.</span><span class="sxs-lookup"><span data-stu-id="87fe4-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="87fe4-108">En la Figura 1 se muestra una oficina central con centros de datos de aplicaciones, una red perimetral e Internet.</span><span class="sxs-lookup"><span data-stu-id="87fe4-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="87fe4-109">**Figura 1: Infraestructura de TI existente de Contoso**</span><span class="sxs-lookup"><span data-stu-id="87fe4-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="87fe4-110">En los centros de datos de aplicaciones locales se hospeda lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87fe4-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="87fe4-111">Aplicaciones de línea de negocio personalizadas que usan SQL Server y otras bases de datos de Linux.</span><span class="sxs-lookup"><span data-stu-id="87fe4-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="87fe4-112">Un conjunto de servidores de SharePoint heredados.</span><span class="sxs-lookup"><span data-stu-id="87fe4-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="87fe4-113">Servidores de nivel de equipo y de la organización para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="87fe4-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="87fe4-p101">Además, cada centro regional admite un conjunto de servidores con un conjunto de aplicaciones similar. Estos servidores están bajo el control de los departamentos de TI regionales.</span><span class="sxs-lookup"><span data-stu-id="87fe4-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="87fe4-116">La capacidad de búsqueda entre las aplicaciones y los datos de todos estos centros de datos separados geográficamente sigue siendo un desafío.</span><span class="sxs-lookup"><span data-stu-id="87fe4-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="87fe4-117">En la red perimetral de la sede central de Contoso, los distintos conjuntos de servidores proporcionan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87fe4-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="87fe4-118">Acceso remoto basado en VPN a la intranet de Contoso y proxy web para los trabajadores de la sede de París.</span><span class="sxs-lookup"><span data-stu-id="87fe4-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="87fe4-119">Hospedaje del sitio web público de Contoso, desde el que los clientes pueden solicitar productos, piezas, suministros o servicio.</span><span class="sxs-lookup"><span data-stu-id="87fe4-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="87fe4-120">Hospedaje de la extranet de partners de Contoso para la colaboración y comunicación de los partners.</span><span class="sxs-lookup"><span data-stu-id="87fe4-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="87fe4-121">Necesidades empresariales de Contoso</span><span class="sxs-lookup"><span data-stu-id="87fe4-121">Contoso's business needs</span></span>

<span data-ttu-id="87fe4-122">Las necesidades empresariales de Contoso se dividen en cinco categorías principales.</span><span class="sxs-lookup"><span data-stu-id="87fe4-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="87fe4-123">Productividad:</span><span class="sxs-lookup"><span data-stu-id="87fe4-123">Productivity:</span></span>

- <span data-ttu-id="87fe4-124">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="87fe4-124">Make collaboration easier</span></span>

  <span data-ttu-id="87fe4-125">Reemplace la colaboración basada en el correo electrónico y los recursos compartidos de archivos con un modelo en línea que permita modificar los documentos en tiempo real, facilite las reuniones en línea y capture las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="87fe4-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="87fe4-126">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="87fe4-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="87fe4-127">Con tantos empleados trabajando desde casa o sobre el terreno, cambie la solución VPN con cuellos de botella por el acceso eficaz a los datos y recursos de Contoso en la nube.</span><span class="sxs-lookup"><span data-stu-id="87fe4-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="87fe4-128">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="87fe4-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="87fe4-129">Aproveche las ventajas de los métodos más recientes de aprendizaje visual y desarrollo de ideas, como la entrada manuscrita y la visualización 3D.</span><span class="sxs-lookup"><span data-stu-id="87fe4-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="87fe4-130">Seguridad:</span><span class="sxs-lookup"><span data-stu-id="87fe4-130">Security:</span></span>

- <span data-ttu-id="87fe4-131">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="87fe4-131">Identity and access management</span></span>

  <span data-ttu-id="87fe4-132">Exija la autenticación multifactor y de otros tipos, y proteja las credenciales de las cuentas de usuario y administrador.</span><span class="sxs-lookup"><span data-stu-id="87fe4-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="87fe4-133">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="87fe4-133">Threat protection</span></span>

  <span data-ttu-id="87fe4-134">Proteja contra amenazas de seguridad externas, como el correo electrónico y el malware basado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="87fe4-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="87fe4-135">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="87fe4-135">Information protection</span></span>

  <span data-ttu-id="87fe4-136">Restrinja el acceso y cifre los activos digitales de gran valor, como los datos del cliente, las especificaciones de diseño y la información de los empleados.</span><span class="sxs-lookup"><span data-stu-id="87fe4-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="87fe4-137">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="87fe4-137">Security management</span></span>

  <span data-ttu-id="87fe4-138">Supervise el nivel de seguridad y sea capaz de detectar y responder a las amenazas en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="87fe4-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="87fe4-139">Acceso móvil y remoto, y socios comerciales:</span><span class="sxs-lookup"><span data-stu-id="87fe4-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="87fe4-140">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="87fe4-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="87fe4-141">Instaure la administración de dispositivos Bring Your Own Device (BYOD) y de propiedad de la empresa para garantizar el acceso seguro, el comportamiento correcto de las aplicaciones y la protección de los datos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="87fe4-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="87fe4-142">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="87fe4-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="87fe4-143">Reduzca los costos de mantenimiento y soporte técnico, y mejore el rendimiento de la solución de acceso remoto moviendo a la nube los recursos a los que se accede con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="87fe4-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="87fe4-144">Proporcionar mejor conectividad y menos sobrecarga para las transacciones de negocio a negocio (B2B)</span><span class="sxs-lookup"><span data-stu-id="87fe4-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="87fe4-145">Reemplace la extranet de partners, anticuada y costosa, por una solución basada en la nube que use la autenticación federada.</span><span class="sxs-lookup"><span data-stu-id="87fe4-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="87fe4-146">Cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="87fe4-146">Compliance:</span></span>

- <span data-ttu-id="87fe4-147">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="87fe4-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="87fe4-148">Cumpla con los reglamentos regionales y del sector sobre almacenamiento de datos, cifrado, privacidad de datos y normativas de datos personales, como el Reglamento general de protección de datos (RGPD) de la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="87fe4-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="87fe4-149">Administración:</span><span class="sxs-lookup"><span data-stu-id="87fe4-149">Management:</span></span>

- <span data-ttu-id="87fe4-150">Reducir la sobrecarga de TI de la administración de software en los equipos y dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="87fe4-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="87fe4-151">Automatice la instalación de actualizaciones para el sistema operativo Windows y Microsoft Office en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="87fe4-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="87fe4-152">Asignación de las necesidades empresariales de Contoso a Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="87fe4-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="87fe4-153">Antes de la implementación, el departamento de TI de Contoso determinó la siguiente asignación de las necesidades empresariales a las características de Microsoft 365 Enterprise E5:</span><span class="sxs-lookup"><span data-stu-id="87fe4-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="87fe4-154">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="87fe4-154">**Category**</span></span> | <span data-ttu-id="87fe4-155">**Necesidad empresarial**</span><span class="sxs-lookup"><span data-stu-id="87fe4-155">**Business need**</span></span> | <span data-ttu-id="87fe4-156">**Productos o características de Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="87fe4-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="87fe4-157">Productividad</span><span class="sxs-lookup"><span data-stu-id="87fe4-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="87fe4-158">Facilitar la colaboración</span><span class="sxs-lookup"><span data-stu-id="87fe4-158">Make collaboration easier</span></span> | <span data-ttu-id="87fe4-159">Teams, SharePoint Online, Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="87fe4-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="87fe4-160">Mejorar la productividad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="87fe4-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="87fe4-161">Cargas de trabajo de Office 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="87fe4-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="87fe4-162">Aumentar la creatividad y la innovación</span><span class="sxs-lookup"><span data-stu-id="87fe4-162">Increase creativity and innovation</span></span> | <span data-ttu-id="87fe4-163">Windows Ink, Cortana en el trabajo, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="87fe4-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="87fe4-164">Seguridad</span><span class="sxs-lookup"><span data-stu-id="87fe4-164">Security</span></span> |  |  |
|  | <span data-ttu-id="87fe4-165">Administración de identidad y acceso</span><span class="sxs-lookup"><span data-stu-id="87fe4-165">Identity & access management</span></span> | <span data-ttu-id="87fe4-166">Cuentas de administrador global dedicadas con la autenticación multifactor (MFA) y Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="87fe4-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="87fe4-167">MFA para todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="87fe4-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="87fe4-168">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="87fe4-168">Conditional access</span></span> <BR> <span data-ttu-id="87fe4-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="87fe4-169">Windows Hello</span></span> <BR> <span data-ttu-id="87fe4-170">Credential Guard de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="87fe4-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="87fe4-171">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="87fe4-171">Threat protection</span></span> | <span data-ttu-id="87fe4-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="87fe4-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="87fe4-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="87fe4-173">Windows Defender</span></span> <BR> <span data-ttu-id="87fe4-174">Protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="87fe4-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="87fe4-175">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe4-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="87fe4-176">Investigación y respuesta de amenazas de Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe4-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="87fe4-177">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="87fe4-177">Information protection</span></span> | <span data-ttu-id="87fe4-178">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="87fe4-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="87fe4-179">Prevención de pérdida de datos (DLP) de Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe4-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="87fe4-180">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="87fe4-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="87fe4-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87fe4-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="87fe4-182">Office 365 Cloud App Security (CAS)</span><span class="sxs-lookup"><span data-stu-id="87fe4-182">Office 365 Cloud App Security (CAS)</span></span> <BR> <span data-ttu-id="87fe4-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="87fe4-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="87fe4-184">Administración de seguridad</span><span class="sxs-lookup"><span data-stu-id="87fe4-184">Security management</span></span> | <span data-ttu-id="87fe4-185">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="87fe4-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="87fe4-186">Centro de seguridad de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="87fe4-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="87fe4-187">Acceso móvil y remoto, y socios comerciales</span><span class="sxs-lookup"><span data-stu-id="87fe4-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="87fe4-188">Mejorar la seguridad de los trabajadores remotos y móviles</span><span class="sxs-lookup"><span data-stu-id="87fe4-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="87fe4-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="87fe4-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="87fe4-190">Reducir la infraestructura de acceso remoto para los empleados</span><span class="sxs-lookup"><span data-stu-id="87fe4-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="87fe4-191">Cargas de trabajo de Office 365 y datos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="87fe4-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="87fe4-192">Proporcionar mejor conectividad y menos sobrecarga para las transacciones B2B</span><span class="sxs-lookup"><span data-stu-id="87fe4-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="87fe4-193">Autenticación federada y recursos basados en la nube</span><span class="sxs-lookup"><span data-stu-id="87fe4-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="87fe4-194">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="87fe4-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="87fe4-195">Cumplir los requisitos normativos regionales</span><span class="sxs-lookup"><span data-stu-id="87fe4-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="87fe4-196">Características del RGPD en Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe4-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="87fe4-197">Administración</span><span class="sxs-lookup"><span data-stu-id="87fe4-197">Management</span></span> |  |  |
|  | <span data-ttu-id="87fe4-198">Reducir la sobrecarga de TI para la instalación de actualizaciones de cliente</span><span class="sxs-lookup"><span data-stu-id="87fe4-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="87fe4-199">Anillos de implementación</span><span class="sxs-lookup"><span data-stu-id="87fe4-199">Deployment rings</span></span> <BR> <span data-ttu-id="87fe4-200">Actualización local de Windows 10 y Autopilot</span><span class="sxs-lookup"><span data-stu-id="87fe4-200">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="87fe4-201">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="87fe4-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="87fe4-202">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="87fe4-202">Next step</span></span>

<span data-ttu-id="87fe4-203">[Obtenga más información](contoso-networking.md) sobre la red local de Contoso Corporation y cómo se optimizó para el acceso y la latencia para los recursos basados en la nube de Microsoft 365 en la organización.</span><span class="sxs-lookup"><span data-stu-id="87fe4-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="87fe4-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="87fe4-204">See also</span></span>

[<span data-ttu-id="87fe4-205">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="87fe4-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="87fe4-206">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="87fe4-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
