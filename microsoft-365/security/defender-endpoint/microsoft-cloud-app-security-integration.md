---
title: Introducción a integración de Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender para endpoint se integra con Cloud App Security reenviando todas las actividades de red de aplicaciones en la nube.
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
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844747"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="ebe38-104">Microsoft Cloud App Security información general de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ebe38-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ebe38-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="ebe38-105">**Applies to:**</span></span>
- [<span data-ttu-id="ebe38-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="ebe38-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ebe38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebe38-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ebe38-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="ebe38-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ebe38-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="ebe38-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ebe38-110">Microsoft Cloud App Security (Cloud App Security) es una solución completa que da visibilidad a los servicios y aplicaciones en la nube, ya que permite controlar y limitar el acceso a las aplicaciones en la nube, al tiempo que se cumplen los requisitos de cumplimiento en los datos almacenados en la nube.</span><span class="sxs-lookup"><span data-stu-id="ebe38-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="ebe38-111">Para obtener más información, [vea Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="ebe38-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="ebe38-112">Esta característica está disponible con una licencia E5 [para](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) Enterprise Mobility + Security dispositivos que Windows 10 versión 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ebe38-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="ebe38-113">Microsoft Defender para la integración de puntos Cloud App Security de conexión</span><span class="sxs-lookup"><span data-stu-id="ebe38-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="ebe38-114">Cloud App Security de detección se basa en los registros de tráfico en la nube que se reenvían desde servidores proxy y firewall de empresa.</span><span class="sxs-lookup"><span data-stu-id="ebe38-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="ebe38-115">Microsoft Defender para endpoint se integra con Cloud App Security recopilando y reenviando todas las actividades de red de aplicaciones en la nube, lo que proporciona una visibilidad sin precedentes del uso de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="ebe38-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="ebe38-116">La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.</span><span class="sxs-lookup"><span data-stu-id="ebe38-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="ebe38-117">La integración proporciona las siguientes mejoras importantes en la detección de Cloud App Security existente:</span><span class="sxs-lookup"><span data-stu-id="ebe38-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="ebe38-118">Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, dentro o fuera de la red corporativa, ya que ya no depende del tráfico enrutado a través del firewall de empresa o los servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="ebe38-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="ebe38-119">Funciona sin necesidad de configuración: reenviar registros de tráfico en la nube a Cloud App Security configuración del servidor proxy y firewall.</span><span class="sxs-lookup"><span data-stu-id="ebe38-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="ebe38-120">Con Defender for Endpoint y Cloud App Security integración, no se requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="ebe38-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="ebe38-121">Solo tienes que activarlo en Centro de seguridad de Microsoft Defender configuración y puedes ir.</span><span class="sxs-lookup"><span data-stu-id="ebe38-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="ebe38-122">Contexto del dispositivo: los registros de tráfico en la nube carecen de contexto del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ebe38-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="ebe38-123">La actividad de la red defender para puntos de conexión se notifica con el contexto del dispositivo (a qué dispositivo se ha accedido a la aplicación en la nube), por lo que puedes comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó.</span><span class="sxs-lookup"><span data-stu-id="ebe38-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="ebe38-124">Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="ebe38-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="ebe38-125">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="ebe38-125">Related topic</span></span>

- [<span data-ttu-id="ebe38-126">Configurar la integración con Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ebe38-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
