---
title: Evaluar Antivirus de Microsoft Defender
description: Las empresas de todos los tamaños pueden usar esta guía para evaluar y probar la protección que ofrece Antivirus de Microsoft Defender en Windows 10.
keywords: Antivirus de Microsoft Defender, protección en la nube, nube, antimalware, seguridad, defender, evaluar, probar, proteger, comparar, protección en tiempo real
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274741"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="a63fd-104">Evaluar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a63fd-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a63fd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a63fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="a63fd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a63fd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a63fd-107">Use esta guía para determinar qué tan bien Antivirus de Microsoft Defender protege contra virus, malware y aplicaciones potencialmente no deseadas.</span><span class="sxs-lookup"><span data-stu-id="a63fd-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="a63fd-108">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las siguientes características funcionan y ver cómo funcionan:</span><span class="sxs-lookup"><span data-stu-id="a63fd-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="a63fd-109">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="a63fd-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="a63fd-110">Aprendizaje rápido (incluido Bloquear a primera vista)</span><span class="sxs-lookup"><span data-stu-id="a63fd-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="a63fd-111">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="a63fd-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="a63fd-112">Explica las características importantes de protección de próxima generación de Antivirus de Microsoft Defender disponibles para pequeñas y grandes empresas, y cómo aumentan la detección y protección de malware en toda la red.</span><span class="sxs-lookup"><span data-stu-id="a63fd-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="a63fd-113">Puede elegir configurar y evaluar cada configuración de forma independiente o todo a la vez.</span><span class="sxs-lookup"><span data-stu-id="a63fd-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="a63fd-114">Hemos agrupado configuraciones similares en función de escenarios de evaluación típicos e incluye instrucciones para usar PowerShell para habilitar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a63fd-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="a63fd-115">La guía está disponible en formato PDF para la visualización sin conexión:</span><span class="sxs-lookup"><span data-stu-id="a63fd-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="a63fd-116">Descargar la guía en formato PDF</span><span class="sxs-lookup"><span data-stu-id="a63fd-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="a63fd-117">También puede descargar un PowerShell que habilitará automáticamente todas las opciones descritas en la guía.</span><span class="sxs-lookup"><span data-stu-id="a63fd-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="a63fd-118">Puede obtener el script junto con la descarga de PDF anterior o individualmente desde la Galería de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a63fd-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="a63fd-119">Descargar el script de PowerShell para configurar automáticamente la configuración</span><span class="sxs-lookup"><span data-stu-id="a63fd-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="a63fd-120">La guía está diseñada actualmente para la evaluación de una sola máquina de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a63fd-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="a63fd-121">Es posible que la habilitación de toda la configuración de esta guía no sea adecuada para la implementación en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="a63fd-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="a63fd-122">Para obtener las recomendaciones más recientes para la implementación real y la supervisión de Antivirus de Microsoft Defender en una red, vea [Deploy Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a63fd-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a63fd-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a63fd-123">Related topics</span></span>

- [<span data-ttu-id="a63fd-124">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="a63fd-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a63fd-125">Implementar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a63fd-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)