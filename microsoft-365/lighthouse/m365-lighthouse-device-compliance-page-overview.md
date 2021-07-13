---
title: Microsoft 365 Lighthouse Introducción a la página de cumplimiento de dispositivos
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Cumplimiento de dispositivos.
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395229"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="2d2a1-103">Microsoft 365 Lighthouse Introducción a la página de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2d2a1-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="2d2a1-104">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a1-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="2d2a1-105">Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a1-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="2d2a1-106">Microsoft 365 Lighthouse permite ver información e información relacionada con el cumplimiento de dispositivos  de Intune para todos los inquilinos seleccionando Dispositivos en el panel de navegación izquierdo para abrir la página Cumplimiento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="2d2a1-107">En esta página, puede obtener información general sobre el estado de cumplimiento entre inquilinos, ver una lista de dispositivos para cada inquilino y obtener informes de estado sobre las directivas y la configuración de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="2d2a1-108">Ficha Información general</span><span class="sxs-lookup"><span data-stu-id="2d2a1-108">Overview tab</span></span>  
  
<span data-ttu-id="2d2a1-109">En la pestaña Información general, puedes ver el estado de cumplimiento del dispositivo en todos los inquilinos, ver las tendencias de cumplimiento de dispositivos mensuales y realizar un seguimiento de si los dispositivos tienen directivas de cumplimiento asignadas.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="2d2a1-110">También puedes ver información sobre las acciones y requisitos de cumplimiento del dispositivo de inquilino en función de las directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Captura de pantalla de la pestaña Información general.":::

## <a name="devices-tab"></a><span data-ttu-id="2d2a1-112">Pestaña Dispositivos</span><span class="sxs-lookup"><span data-stu-id="2d2a1-112">Devices tab</span></span>

<span data-ttu-id="2d2a1-113">En la pestaña Dispositivos, puede ver una lista de todos los dispositivos de inquilino y filtrar la lista en función de los siguientes estados de cumplimiento: Compatible, No conforme, Período de gracia y No evaluado.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="2d2a1-114">Para obtener más información acerca de los distintos estados de cumplimiento, vea [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span><span class="sxs-lookup"><span data-stu-id="2d2a1-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="2d2a1-115">Selecciona cualquier dispositivo para ver más información sobre por qué el dispositivo está en su estado de cumplimiento actual.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="2d2a1-116">Si necesitas realizar una acción en el dispositivo, hay una opción para ver el dispositivo en Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Captura de pantalla de la pestaña Dispositivos.":::

## <a name="policies-tab"></a><span data-ttu-id="2d2a1-118">Pestaña Directivas</span><span class="sxs-lookup"><span data-stu-id="2d2a1-118">Policies tab</span></span>

<span data-ttu-id="2d2a1-119">En la pestaña Directivas, puede ver directivas de cumplimiento en los inquilinos y comparar dos o tres directivas del mismo tipo de plataforma mediante la característica Comparar de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="2d2a1-120">También puede seleccionar cualquier directiva para ver más información.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Captura de pantalla de la pestaña Directivas.":::

## <a name="settings-tab"></a><span data-ttu-id="2d2a1-122">Configuración pestaña</span><span class="sxs-lookup"><span data-stu-id="2d2a1-122">Settings tab</span></span>

<span data-ttu-id="2d2a1-123">La pestaña configuración proporciona un informe agregado de la configuración no compatible en todos los dispositivos de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="2d2a1-124">Seleccione cualquiera de las filas de informe para ver más información, incluidos los inquilinos a los que pertenecen los dispositivos no compatibles.</span><span class="sxs-lookup"><span data-stu-id="2d2a1-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Captura de pantalla de la Configuración pestaña.":::

## <a name="related-content"></a><span data-ttu-id="2d2a1-126">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="2d2a1-126">Related content</span></span>

<span data-ttu-id="2d2a1-127">[Microsoft 365 Lighthouse de la página Usuarios](m365-lighthouse-users-page-overview.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="2d2a1-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="2d2a1-128">[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)</span><span class="sxs-lookup"><span data-stu-id="2d2a1-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
