---
title: 'Paso 5: Optimizar el rendimiento del servicio de Microsoft 365 y el cliente'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Configure las opciones de TCP y los servicios de Microsoft 365 para obtener un mejor rendimiento.
ms.openlocfilehash: 2db35f67ff19998b8a70742ec8fa24cb8d517c5d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631470"
---
# <a name="step-5-optimize-client-and-microsoft-365-service-performance"></a><span data-ttu-id="93270-103">Paso 5: Optimizar el rendimiento del servicio de Microsoft 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="93270-103">Step 5: Optimize client and Microsoft 365 service performance</span></span>

<span data-ttu-id="93270-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="93270-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Red](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="93270-106">Puede aumentar el rendimiento si ajusta la forma en que el Protocolo de control de transmisión (TCP) funciona entre los dispositivos cliente y los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93270-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Microsoft 365 services.</span></span>

<span data-ttu-id="93270-107">Puede cambiar las siguientes opciones de configuración de TCP en los dispositivos cliente para optimizar el rendimiento de TCP:</span><span class="sxs-lookup"><span data-stu-id="93270-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="93270-108">[Escalado de ventana de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que el dispositivo cliente pueda enviar más datos antes de exigir una confirmación.</span><span class="sxs-lookup"><span data-stu-id="93270-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="93270-109">[Tiempo de inactividad de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que el dispositivo cliente pueda administrar las conexiones abiertas de forma más eficiente.</span><span class="sxs-lookup"><span data-stu-id="93270-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="93270-110">[Tamaño máximo del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que el dispositivo cliente pueda enviar los bloques de datos de mayor tamaño en un paquete.</span><span class="sxs-lookup"><span data-stu-id="93270-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="93270-111">[Confirmaciones selectivas de TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que el dispositivo cliente pueda confirmar los datos recibidos de forma más eficiente.</span><span class="sxs-lookup"><span data-stu-id="93270-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="93270-112">Para los servicios de Microsoft 365, vea estos recursos adicionales para optimizar el rendimiento:</span><span class="sxs-lookup"><span data-stu-id="93270-112">For Microsoft 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="93270-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="93270-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="93270-114">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="93270-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="93270-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="93270-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="93270-116">Project Web App en Project Online</span><span class="sxs-lookup"><span data-stu-id="93270-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="93270-117">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step5) de este paso.</span><span class="sxs-lookup"><span data-stu-id="93270-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="93270-118">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="93270-118">Next step</span></span>

[<span data-ttu-id="93270-119">Criterios de salida de infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="93270-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
