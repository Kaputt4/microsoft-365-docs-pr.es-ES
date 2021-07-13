---
title: Implementar Microsoft 365 Lighthouse base
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo implementar Microsoft 365 Lighthouse líneas base.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395364"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="88782-103">Implementar Microsoft 365 Lighthouse base</span><span class="sxs-lookup"><span data-stu-id="88782-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="88782-104">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88782-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="88782-105">Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="88782-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="88782-106">Microsoft 365 Lighthouse línea base le permiten implementar configuraciones de inquilino administrado estándar para proteger los usuarios, dispositivos y datos del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="88782-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="88782-107">Hay seis configuraciones de línea base predeterminadas que vienen estándar con Microsoft 365 Lighthouse:</span><span class="sxs-lookup"><span data-stu-id="88782-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="88782-108">Requerir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="88782-108">Require MFA for admins</span></span>
- <span data-ttu-id="88782-109">Requerir MFA para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="88782-109">Require MFA for end users</span></span>
- <span data-ttu-id="88782-110">Bloquear autenticación heredada</span><span class="sxs-lookup"><span data-stu-id="88782-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="88782-111">Configurar la inscripción de dispositivos en Microsoft Endpoint Manager: unión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="88782-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="88782-112">Configurar la directiva antivirus de Defender para Windows dispositivos</span><span class="sxs-lookup"><span data-stu-id="88782-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="88782-113">Configurar la directiva de cumplimiento para Windows dispositivos</span><span class="sxs-lookup"><span data-stu-id="88782-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="88782-114">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="88782-114">Before you begin</span></span>

<span data-ttu-id="88782-115">Asegúrese de que usted y sus inquilinos de clientes cumplan los requisitos enumerados en [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88782-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="88782-116">Más información sobre la línea base predeterminada</span><span class="sxs-lookup"><span data-stu-id="88782-116">Learn more about the default baseline</span></span>

<span data-ttu-id="88782-117">Seleccione **Líneas base en** el panel de navegación izquierdo para abrir la página Líneas base.</span><span class="sxs-lookup"><span data-stu-id="88782-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="88782-118">Verá que la línea base predeterminada ya se ha agregado al grupo de inquilinos predeterminado (todos los inquilinos).</span><span class="sxs-lookup"><span data-stu-id="88782-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="88782-119">Para ver las configuraciones de línea base predeterminadas, seleccione **Ver línea base** para abrir la página Línea base predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88782-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="88782-120">Las configuraciones se enumeran como pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="88782-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="88782-121">Seleccione cualquiera de los pasos de implementación para ver los detalles de implementación y el impacto del usuario.</span><span class="sxs-lookup"><span data-stu-id="88782-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Captura de pantalla de la página de línea base predeterminada.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="88782-123">Implementar una configuración de línea base</span><span class="sxs-lookup"><span data-stu-id="88782-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="88782-124">En la página de navegación izquierda, seleccione **Inquilinos** para ver una lista de los inquilinos incorporados.</span><span class="sxs-lookup"><span data-stu-id="88782-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="88782-125">Seleccione el espacio empresarial en el que desea implementar la configuración de línea base.</span><span class="sxs-lookup"><span data-stu-id="88782-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="88782-126">Seleccione la **pestaña Plan de** implementación para ver todos los pasos de implementación de la línea base que se han agregado al plan de implementación del inquilino.</span><span class="sxs-lookup"><span data-stu-id="88782-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="88782-127">Seleccione un paso de implementación para abrir la página de pasos de implementación.</span><span class="sxs-lookup"><span data-stu-id="88782-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="88782-128">Seleccione **Aplicar** para aplicar el paso de implementación seleccionado al espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="88782-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="88782-129">Si el paso de implementación indica "Esta acción requiere un paso manual", asegúrese de completar el paso manual para que el paso de implementación se aplique correctamente.</span><span class="sxs-lookup"><span data-stu-id="88782-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="88782-130">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="88782-130">Related content</span></span>

<span data-ttu-id="88782-131">[Introducción al uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="88782-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="88782-132">[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="88782-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>