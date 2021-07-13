---
title: Introducción al uso de líneas base para implementar configuraciones de inquilino estándar
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo usar líneas base para implementar configuraciones de inquilino estándar.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409188"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="ea498-103">Introducción al uso de líneas base para implementar configuraciones de inquilino estándar</span><span class="sxs-lookup"><span data-stu-id="ea498-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="ea498-104">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea498-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="ea498-105">Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="ea498-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="ea498-106">Microsoft 365 Lighthouse línea base proporcionan una forma repetible y escalable de evaluar y administrar la configuración Microsoft 365 seguridad en varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ea498-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="ea498-107">Las líneas base también ayudan a supervisar las directivas de seguridad principales y los estándares de cumplimiento de inquilinos con configuraciones que protegen usuarios, dispositivos y datos.</span><span class="sxs-lookup"><span data-stu-id="ea498-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="ea498-108">Diseñado para ayudar a los partners a permitir que los clientes adopten la seguridad a su propio ritmo, Microsoft 365 Lighthouse proporciona un conjunto estándar de parámetros de línea base y configuraciones predefinidas para Microsoft 365 servicios.</span><span class="sxs-lookup"><span data-stu-id="ea498-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="ea498-109">Estas configuraciones de seguridad ayudan a medir el progreso Microsoft 365 seguridad y cumplimiento de los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ea498-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="ea498-110">Puede ver la línea base predeterminada y sus pasos de implementación desde dentro de Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="ea498-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="ea498-111">Para aplicar líneas base a un inquilino, seleccione **Inquilinos** en el panel de navegación izquierdo y, a continuación, seleccione un espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea498-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="ea498-112">A continuación, vaya a la **pestaña Planes de** implementación e implemente la línea base deseada.</span><span class="sxs-lookup"><span data-stu-id="ea498-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="ea498-113">Plantillas de seguridad de línea base estándar</span><span class="sxs-lookup"><span data-stu-id="ea498-113">Standard baseline security templates</span></span>

<span data-ttu-id="ea498-114">Microsoft 365 Lighthouse configuraciones de línea base estándar para cargas de trabajo de seguridad están diseñadas para ayudar a todos los inquilinos administrados a alcanzar un estado aceptable de cobertura y cumplimiento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ea498-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="ea498-115">Las configuraciones de línea base de la tabla siguiente vienen estándar con la Microsoft 365 Lighthouse línea base predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ea498-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="ea498-116">Configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="ea498-116">Baseline configuration</span></span> | <span data-ttu-id="ea498-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea498-117">Description</span></span> |
|--|--|
| <span data-ttu-id="ea498-118">Requerir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="ea498-118">Require MFA for admins</span></span> | <span data-ttu-id="ea498-119">Una directiva de acceso condicional de solo informe que requiere autenticación multifactor para los administradores.</span><span class="sxs-lookup"><span data-stu-id="ea498-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="ea498-120">Es necesario para todas las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="ea498-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="ea498-121">Requerir MFA para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="ea498-121">Require MFA for end users</span></span> | <span data-ttu-id="ea498-122">Una directiva de acceso condicional de solo informe que requiere autenticación multifactor para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ea498-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="ea498-123">Es necesario para todas las aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="ea498-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="ea498-124">Bloquear la autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="ea498-124">Block legacy authentication</span></span> | <span data-ttu-id="ea498-125">Una directiva de acceso condicional de solo informe para bloquear la autenticación de cliente heredada.</span><span class="sxs-lookup"><span data-stu-id="ea498-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="ea498-126">Inscribir dispositivos en Microsoft Endpoint Manager: combinación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="ea498-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="ea498-127">Inscripción de dispositivos para permitir que los dispositivos de inquilino se inscriban en Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ea498-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="ea498-128">Para ello, configura la inscripción automática entre Azure Active Directory y Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ea498-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="ea498-129">Configuración de directiva antivirus (AV)</span><span class="sxs-lookup"><span data-stu-id="ea498-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="ea498-130">Un perfil de configuración de dispositivo para Windows dispositivos con una configuración Antivirus de Microsoft Defender configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ea498-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="ea498-131">Configuración de la directiva de cumplimiento de la ventana 10</span><span class="sxs-lookup"><span data-stu-id="ea498-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="ea498-132">Una Windows de dispositivos con configuraciones preconfiguradas para cumplir los requisitos básicos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="ea498-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="ea498-133">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ea498-133">Related content</span></span>

<span data-ttu-id="ea498-134">[Implementar Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ea498-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="ea498-135">[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ea498-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
