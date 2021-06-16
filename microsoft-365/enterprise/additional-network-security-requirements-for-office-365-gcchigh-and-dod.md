---
title: Requisitos de seguridad de red adicionales para Office 365 GCC High y DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumen: Office 365 GCC High y DoD tienen requisitos de seguridad de red adicionales'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926564"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="00b7f-103">Requisitos de seguridad de conexión de red adicionales para Office 365 GCC High y DOD</span><span class="sxs-lookup"><span data-stu-id="00b7f-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="00b7f-104">*Este artículo se aplica a Office 365 GCC, Office 365 DOD, Microsoft 365 GCC High y Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="00b7f-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="00b7f-105">Office 365 GCC High y DOD son entornos de nube seguros para satisfacer las necesidades del Gobierno de Los Estados Unidos y sus proveedores y contratistas.</span><span class="sxs-lookup"><span data-stu-id="00b7f-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="00b7f-106">Estos entornos en la nube tienen restricciones de red adicionales a las que los puntos de conexión externos a los servicios pueden tener acceso.</span><span class="sxs-lookup"><span data-stu-id="00b7f-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="00b7f-107">GCC Los clientes altos y dod que planean usar identidades federadas o coexistencia híbrida pueden requerir que Microsoft permita el acceso entrante y/o saliente a las implementaciones locales existentes.</span><span class="sxs-lookup"><span data-stu-id="00b7f-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="00b7f-108">Algunos ejemplos de estas actividades son:</span><span class="sxs-lookup"><span data-stu-id="00b7f-108">Examples of these activities include:</span></span>

* <span data-ttu-id="00b7f-109">Uso de identidades federadas (con servicios de federación de Active Directory o STS compatibles similares)</span><span class="sxs-lookup"><span data-stu-id="00b7f-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="00b7f-110">Coexistencia híbrida con una implementación Exchange Server o Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="00b7f-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="00b7f-111">Migración de contenido de usuario existente desde un sistema local</span><span class="sxs-lookup"><span data-stu-id="00b7f-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="00b7f-112">Para permitir que el servicio se comunique con  los puntos de conexión locales, debe enviar un correo electrónico a Office 365 ingeniería para los cambios de red.</span><span class="sxs-lookup"><span data-stu-id="00b7f-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="00b7f-113">Todas las solicitudes tienen **un** SLA de tres semanas y no se pueden acelerar debido a los controles de seguridad y cumplimiento requeridos y las canalizaciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="00b7f-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="00b7f-114">Esto incluye solicitudes de red de incorporación iniciales, así como cualquier cambio después de migrar al servicio.</span><span class="sxs-lookup"><span data-stu-id="00b7f-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="00b7f-115">Asegúrese de que los equipos de red son conscientes de esta escala de tiempo e incluirla en sus ciclos de planeación.</span><span class="sxs-lookup"><span data-stu-id="00b7f-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="00b7f-116">Envíe un correo electrónico [a Office 365 Administración Pública Allow-List solicitudes](mailto:o365gwlt@microsoft.com) con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="00b7f-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="00b7f-117">**To**: [Office 365 Administración Pública Allow-List Requests](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="00b7f-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="00b7f-118">**From**: A tenant administrator: the send email **must** match a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="00b7f-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="00b7f-119">**Asunto de correo** electrónico: Office 365 GCC solicitud de red alta : contoso.onmicrosoft.us (reemplace por el nombre del inquilino)</span><span class="sxs-lookup"><span data-stu-id="00b7f-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="00b7f-120">El cuerpo del mensaje debe incluir los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="00b7f-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="00b7f-121">Nombre Microsoft Online Services inquilino (por ejemplo, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="00b7f-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="00b7f-122">Una lista de distribución de correo electrónico con la que Microsoft se comunicará para las comunicaciones en marcha relacionadas con los cambios de red o el seguimiento de subredes no válidas</span><span class="sxs-lookup"><span data-stu-id="00b7f-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="00b7f-123">Indica si planeas usar la Microsoft Teams híbrida con las implementaciones locales</span><span class="sxs-lookup"><span data-stu-id="00b7f-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="00b7f-124">Dirección URL accesible externamente del sistema de identidad federada (por ejemplo, sts.contoso.com) e intervalo de direcciones IP en la notación CIDR (por ejemplo, .</span><span class="sxs-lookup"><span data-stu-id="00b7f-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="00b7f-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="00b7f-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="00b7f-126">Dirección URL de lista de revocación de certificados PKI local e intervalo de direcciones IP en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="00b7f-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="00b7f-127">Dirección URL y intervalo de direcciones IP accesibles externamente para Exchange Server implementación local en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="00b7f-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="00b7f-128">Dirección URL y intervalo de direcciones IP accesibles externamente para Skype Empresarial implementación local en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="00b7f-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="00b7f-129">Por motivos de seguridad y cumplimiento, tenga en cuenta las siguientes restricciones en su solicitud:</span><span class="sxs-lookup"><span data-stu-id="00b7f-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="00b7f-130">Hay una limitación de cuatro subredes por inquilino</span><span class="sxs-lookup"><span data-stu-id="00b7f-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="00b7f-131">Las subredes deben estar en notación CIDR (por ejemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="00b7f-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="00b7f-132">Los intervalos de subred no pueden ser mayores que /24</span><span class="sxs-lookup"><span data-stu-id="00b7f-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="00b7f-133">No **podemos dar** cabida a solicitudes para permitir el acceso a servicios comerciales en la nube (Office 365 comerciales, Google G-Suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="00b7f-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="00b7f-134">Una vez que Microsoft ha recibido y aprobado la solicitud, hay un SLA de tres semanas para la implementación y no se puede acelerar.</span><span class="sxs-lookup"><span data-stu-id="00b7f-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="00b7f-135">Recibirá un acuse de recibo inicial cuando hayamos recibido su solicitud y un acuse de recibo final una vez que se haya completado.</span><span class="sxs-lookup"><span data-stu-id="00b7f-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
