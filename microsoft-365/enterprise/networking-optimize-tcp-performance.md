---
title: 'Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Configure las opciones de TCP y los servicios de Office 365 para obtener un mejor rendimiento.
ms.openlocfilehash: 40f99f1b50a324af0650382de165dcfd3df97b0c
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871365"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="2ce69-103">Paso 5: Optimizar el rendimiento del servicio de Office 365 y el cliente</span><span class="sxs-lookup"><span data-stu-id="2ce69-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="2ce69-104">*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2ce69-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="2ce69-105">Puede aumentar el rendimiento si ajusta la forma en que el Protocolo de control de transmisión (TCP) funciona entre los dispositivos cliente y los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ce69-105">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="2ce69-106">Puede cambiar las siguientes opciones de configuración de TCP en los dispositivos cliente para optimizar el rendimiento de TCP:</span><span class="sxs-lookup"><span data-stu-id="2ce69-106">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="2ce69-107">[Escalado de ventana de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), para que el dispositivo cliente pueda enviar más datos antes de exigir una confirmación.</span><span class="sxs-lookup"><span data-stu-id="2ce69-107">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="2ce69-108">[Tiempo de inactividad de TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), para que el dispositivo cliente pueda administrar las conexiones abiertas de forma más eficiente.</span><span class="sxs-lookup"><span data-stu-id="2ce69-108">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="2ce69-109">[Tamaño máximo del segmento TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), para que el dispositivo cliente pueda enviar los bloques de datos de mayor tamaño en un paquete.</span><span class="sxs-lookup"><span data-stu-id="2ce69-109">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="2ce69-110">[Confirmaciones selectivas de TCP](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), para que el dispositivo cliente pueda confirmar los datos recibidos de forma más eficiente.</span><span class="sxs-lookup"><span data-stu-id="2ce69-110">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="2ce69-111">Para los servicios de Office 365, vea estos recursos adicionales para optimizar el rendimiento:</span><span class="sxs-lookup"><span data-stu-id="2ce69-111">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="2ce69-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2ce69-112">Exchange Online</span></span>](https://support.office.com/article/Tune-Exchange-Online-performance-026e83cb-a945-4543-97b0-a8af6e80ac61)
- [<span data-ttu-id="2ce69-113">Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="2ce69-113">Skype for Business Online</span></span>](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802)
- [<span data-ttu-id="2ce69-114">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2ce69-114">SharePoint Online</span></span>](https://support.office.com/article/Tune-SharePoint-Online-performance-f0522d4a-fbf4-41f9-854e-c9b59555091d)
- [<span data-ttu-id="2ce69-115">Project Online</span><span class="sxs-lookup"><span data-stu-id="2ce69-115">Project Online</span></span>](https://support.office.com/article/Tune-Project-Online-performance-12ba0ebd-c616-42e5-b9b6-cad570e8409c)

<span data-ttu-id="2ce69-116">Como punto de control provisional, puede ver los [criterios de salida](networking-exit-criteria.md#crit-networking-step5) de este paso.</span><span class="sxs-lookup"><span data-stu-id="2ce69-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2ce69-117">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2ce69-117">Next step</span></span>

[<span data-ttu-id="2ce69-118">Criterios de salida de infraestructura de red</span><span class="sxs-lookup"><span data-stu-id="2ce69-118">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
