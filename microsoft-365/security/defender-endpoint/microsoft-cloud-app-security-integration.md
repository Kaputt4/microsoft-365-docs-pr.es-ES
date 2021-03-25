---
title: Introducción a la integración de Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender para endpoint se integra con Cloud App Security mediante el reenvío de todas las actividades de red de aplicaciones en la nube.
keywords: nube, aplicación, redes, visibilidad, uso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185604"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="9344d-104">Introducción a Microsoft Cloud App Security en Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9344d-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="9344d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9344d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9344d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9344d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9344d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9344d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="9344d-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="9344d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9344d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="9344d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9344d-110">Microsoft Cloud App Security (Cloud App Security) es una solución completa que da visibilidad a los servicios y aplicaciones en la nube, ya que permite controlar y limitar el acceso a las aplicaciones en la nube, al tiempo que se cumplen los requisitos de cumplimiento en los datos almacenados en la nube.</span><span class="sxs-lookup"><span data-stu-id="9344d-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="9344d-111">Para obtener más información, vea [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="9344d-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="9344d-112">Esta característica está disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10 versión 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9344d-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="9344d-113">Integración de Microsoft Defender para Endpoint y Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9344d-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="9344d-114">La detección de Cloud App Security se basa en los registros de tráfico en la nube que se le reenvían desde servidores proxy y firewall de empresa.</span><span class="sxs-lookup"><span data-stu-id="9344d-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="9344d-115">Microsoft Defender para endpoint se integra con Cloud App Security recopilando y reenviando todas las actividades de red de aplicaciones en la nube, lo que proporciona una visibilidad sin igual del uso de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="9344d-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="9344d-116">La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.</span><span class="sxs-lookup"><span data-stu-id="9344d-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="9344d-117">La integración proporciona las siguientes mejoras importantes en la detección existente de Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="9344d-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="9344d-118">Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, dentro o fuera de la red corporativa, ya que ya no depende del tráfico enrutado a través del firewall de empresa o los servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="9344d-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="9344d-119">Funciona sin necesidad de configuración: el reenvío de registros de tráfico en la nube a Cloud App Security requiere una configuración de servidor proxy y firewall.</span><span class="sxs-lookup"><span data-stu-id="9344d-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="9344d-120">Con la integración de Defender para Endpoint y Cloud App Security, no se requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="9344d-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="9344d-121">Solo tienes que activarla en la configuración del Centro de seguridad de Microsoft Defender y puedes ir.</span><span class="sxs-lookup"><span data-stu-id="9344d-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="9344d-122">Contexto del dispositivo: los registros de tráfico en la nube carecen de contexto del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9344d-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="9344d-123">La actividad de la red defender para puntos de conexión se notifica con el contexto del dispositivo (a qué dispositivo se ha accedido a la aplicación en la nube), por lo que puedes comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó.</span><span class="sxs-lookup"><span data-stu-id="9344d-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="9344d-124">Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="9344d-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="9344d-125">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="9344d-125">Related topic</span></span>

- [<span data-ttu-id="9344d-126">Configurar la integración de Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9344d-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
