---
title: Optimizar el rendimiento de Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Este artículo contiene sugerencias generales y vínculos a otros recursos que le dicen cómo mejorar el rendimiento de Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694065"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="dd0c5-103">Optimizar el rendimiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd0c5-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="dd0c5-104">Este artículo contiene sugerencias generales y vínculos a otros recursos que le dicen cómo mejorar el rendimiento de Exchange Online, especialmente antes de una migración.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="dd0c5-105">Este artículo forma parte del plan de red y el ajuste [del rendimiento para el proyecto de Office 365.](https://aka.ms/tune)</span><span class="sxs-lookup"><span data-stu-id="dd0c5-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="dd0c5-106">Aspectos que se deben tener en cuenta para mejorar el rendimiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd0c5-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="dd0c5-107">Para mejorar la velocidad de migración y reducir las restricciones de ancho de banda de su organización para Exchange Online, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd0c5-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="dd0c5-108">**Reduzca los tamaños de los buzones.**</span><span class="sxs-lookup"><span data-stu-id="dd0c5-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="dd0c5-109">Un tamaño de buzón más pequeño mejora la velocidad de migración.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="dd0c5-110">**Use las capacidades de movimiento de buzones con una implementación híbrida de Exchange.**</span><span class="sxs-lookup"><span data-stu-id="dd0c5-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="dd0c5-111">Con una implementación híbrida de Exchange, correo sin conexión (en forma de . Archivos OST) no requiere volver a descargar al migrar a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="dd0c5-112">Esto reduce significativamente los requisitos de ancho de banda de descarga.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="dd0c5-113">**Programar movimientos de buzones para que se produzcan durante períodos de poco tráfico de Internet y bajo uso de Exchange local.**</span><span class="sxs-lookup"><span data-stu-id="dd0c5-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="dd0c5-114">Al programar movimientos, las solicitudes de migración se envían al proxy de replicación de buzones de correo y es posible que no se lleve a cabo inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="dd0c5-115">**Use ventanas emergentes inclinadas para Outlook en la Web.**</span><span class="sxs-lookup"><span data-stu-id="dd0c5-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="dd0c5-116">Los elementos emergentes lean proporcionan versiones más pequeñas y con menos memoria de determinados mensajes de correo electrónico en Microsoft Edge o Internet Explorer mediante la representación de algunos componentes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="dd0c5-117">Para obtener más información, [vea Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="dd0c5-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="dd0c5-118">Consejos generales</span><span class="sxs-lookup"><span data-stu-id="dd0c5-118">General advice</span></span>

- <span data-ttu-id="dd0c5-119">Asegúrese de que la búsqueda de DNS outlook.office.com en el centro de datos MS en una ubicación de entrada lógica para su ubicación.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="dd0c5-120">Investigue el almacenamiento en caché del buzón y elija las opciones adecuadas (re.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="dd0c5-121">período de almacenamiento en caché, almacenamiento en caché de buzones compartidos, etc.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="dd0c5-122">Evitar que los datos de Outlook pasen por conexiones VPN (a una oficina central) antes de pasar por Internet.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="dd0c5-123">Asegúrese de que los datos del buzón cumplen las limitaciones de las cantidades de carpetas y elementos.</span><span class="sxs-lookup"><span data-stu-id="dd0c5-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="dd0c5-124">Para obtener más información sobre el rendimiento de la migración de Exchange, vea el rendimiento de la migración de [Office 365 y los procedimientos recomendados.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="dd0c5-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  

