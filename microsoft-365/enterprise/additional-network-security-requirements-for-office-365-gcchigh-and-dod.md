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
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693915"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="7416d-103">Requisitos de seguridad de conexión de red adicionales para Office 365 GCC High y DOD</span><span class="sxs-lookup"><span data-stu-id="7416d-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="7416d-104">*Este artículo se aplica a Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High y Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="7416d-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="7416d-105">Office 365 GCC High y DOD son entornos de nube seguros para satisfacer las necesidades del Gobierno de los Estados Unidos y sus proveedores y contratistas.</span><span class="sxs-lookup"><span data-stu-id="7416d-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="7416d-106">Estos entornos de nube tienen restricciones de red adicionales a los puntos de conexión externos a los que los servicios tienen permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="7416d-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="7416d-107">Los clientes de GCC High y DOD que planean usar identidades federadas o coexistencia híbrida pueden requerir que Microsoft permita el acceso entrante y/o saliente a las implementaciones locales existentes.</span><span class="sxs-lookup"><span data-stu-id="7416d-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="7416d-108">Algunos ejemplos de estas actividades son:</span><span class="sxs-lookup"><span data-stu-id="7416d-108">Examples of these activities include:</span></span>

* <span data-ttu-id="7416d-109">Uso de identidades federadas (con servicios de federación de Active Directory o STS admitidos similares)</span><span class="sxs-lookup"><span data-stu-id="7416d-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="7416d-110">Coexistencia híbrida con una implementación local Exchange Server o Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="7416d-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="7416d-111">Migración de contenido de usuario existente desde un sistema local</span><span class="sxs-lookup"><span data-stu-id="7416d-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="7416d-112">Para permitir que el servicio se comunique con  los puntos de conexión locales, debe enviar un correo electrónico a los ingenieros de Office 365 para realizar cambios en la red.</span><span class="sxs-lookup"><span data-stu-id="7416d-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="7416d-113">Todas las solicitudes tienen **un** SLA de tres semanas y no se pueden acelerar debido a los controles de seguridad y cumplimiento necesarios y a las canalizaciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="7416d-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="7416d-114">Esto incluye las solicitudes de red de incorporación iniciales, así como cualquier cambio después de migrar al servicio.</span><span class="sxs-lookup"><span data-stu-id="7416d-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="7416d-115">Asegúrese de que los equipos de red son conscientes de esta escala de tiempo e inscluyéndola en sus ciclos de planeación.</span><span class="sxs-lookup"><span data-stu-id="7416d-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="7416d-116">Envíe un correo electrónico a la lista [blanca de Office 365 Government Network](mailto:o365gwlt@microsoft.com) con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7416d-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="7416d-117">**Para:** Lista blanca de red de Office [365 Administración Pública](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="7416d-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="7416d-118">**Desde**: Un administrador de inquilinos: el correo electrónico de **envío debe coincidir** con un contacto de administrador global en su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="7416d-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="7416d-119">**Asunto del correo** electrónico: Solicitud de red alta GCC de Office 365: contoso.onmicrosoft.us (reemplace esto por el nombre de su espacio empresarial)</span><span class="sxs-lookup"><span data-stu-id="7416d-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="7416d-120">El cuerpo del mensaje debe incluir los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="7416d-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="7416d-121">Su Microsoft Online Services inquilino (es decir, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="7416d-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="7416d-122">Una lista de distribución de correo electrónico con la que Microsoft se comunicará para comunicaciones en marcha relacionadas con cambios en la red o seguimiento de subredes no válidas</span><span class="sxs-lookup"><span data-stu-id="7416d-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="7416d-123">Indicar si tiene previsto usar la coexistencia híbrida de Microsoft Teams con las implementaciones locales</span><span class="sxs-lookup"><span data-stu-id="7416d-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="7416d-124">Dirección URL de acceso externo del sistema de identidad federada (por ejemplo, sts.contoso.com) e intervalo de direcciones IP en notación CIDR (por ejemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="7416d-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="7416d-125">Dirección URL de lista de revocación de certificados PKI locales e intervalo de direcciones IP en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="7416d-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="7416d-126">Dirección URL de acceso externo e intervalo de direcciones IP para Exchange Server implementación local en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="7416d-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="7416d-127">Url de acceso externo e intervalo de direcciones IP para la implementación local de Skype Empresarial en notación CIDR</span><span class="sxs-lookup"><span data-stu-id="7416d-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="7416d-128">Por motivos de seguridad y cumplimiento, tenga en cuenta las siguientes restricciones en su solicitud:</span><span class="sxs-lookup"><span data-stu-id="7416d-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="7416d-129">Hay una limitación de cuatro subredes por inquilino</span><span class="sxs-lookup"><span data-stu-id="7416d-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="7416d-130">Las subredes deben estar en notación CIDR (por ejemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="7416d-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="7416d-131">Los intervalos de subredes no pueden ser superiores a /24</span><span class="sxs-lookup"><span data-stu-id="7416d-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="7416d-132">No **podemos dar** cabida a solicitudes para permitir el acceso a los servicios en la nube comerciales (comercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="7416d-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="7416d-133">Una vez que Microsoft ha recibido y aprobado la solicitud, hay un SLA de tres semanas para la implementación y no se puede acelerar.</span><span class="sxs-lookup"><span data-stu-id="7416d-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="7416d-134">Recibirá un acuse de recibo inicial cuando hayamos recibido su solicitud y una confirmación final una vez que se haya completado.</span><span class="sxs-lookup"><span data-stu-id="7416d-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
