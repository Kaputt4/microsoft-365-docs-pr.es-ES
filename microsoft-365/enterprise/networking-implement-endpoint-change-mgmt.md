---
title: 'Paso 4: Planear los cambios de direcciones IP y URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291329"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="c4943-102">Paso 4: Planear los cambios de direcciones IP y URL</span><span class="sxs-lookup"><span data-stu-id="c4943-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="c4943-103">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c4943-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="c4943-p101">Antes de este paso, es necesario completar el [Paso 3](networking-configure-proxies-firewalls.md). Si no completó el paso 3, puede ir directamente al [Paso 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="c4943-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="c4943-p102">Las direcciones IP y URL usadas por la red global de Microsoft 365 cambian con el tiempo, por lo que es importante planear las actualizaciones de estos puntos de conexión. Por ejemplo, puede que necesite volver a configurar los dispositivos del perímetro de seguridad con:</span><span class="sxs-lookup"><span data-stu-id="c4943-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="c4943-108">Nuevas URL para nuevos servicios que necesiten un procesamiento sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="c4943-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="c4943-109">URL eliminadas de los servicios descontinuados.</span><span class="sxs-lookup"><span data-stu-id="c4943-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="c4943-110">Nuevos intervalos de direcciones IP para las nuevas ubicaciones de red y servidores de Microsoft en Internet.</span><span class="sxs-lookup"><span data-stu-id="c4943-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="c4943-111">Cambios en los intervalos de direcciones IP para los distintos servicios.</span><span class="sxs-lookup"><span data-stu-id="c4943-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="c4943-112">Para obtener más información sobre cómo establecer un plan de implementación para los cambios en los puntos de conexión, incluidas las notificaciones de cambios, vea [Administrar los puntos de conexión de Office 365: Integración](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) y [Administrar los puntos de conexión de Office 365: Servidores proxy](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="c4943-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="c4943-113">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step4) de este paso.</span><span class="sxs-lookup"><span data-stu-id="c4943-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c4943-114">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c4943-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="c4943-115">Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="c4943-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
