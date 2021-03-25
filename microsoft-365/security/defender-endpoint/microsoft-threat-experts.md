---
title: Expertos en amenazas de Microsoft
ms.reviewer: ''
description: Los expertos en amenazas de Microsoft proporcionan una capa adicional de experiencia a Microsoft Defender para endpoint.
keywords: servicio de búsqueda de amenazas administradas, búsqueda de amenazas administradas, servicio de detección y respuesta administrada (MDR), MTE, Expertos en amenazas de Microsoft, MTE-TAN, notificación de ataque dirigido, Notificación de ataque dirigido
search.product: Windows 10
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 466e67bb4649f8cf87e4152a07122d57c5071b79
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185580"
---
# <a name="microsoft-threat-experts"></a><span data-ttu-id="0bdf4-104">Expertos en amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0bdf4-104">Microsoft Threat Experts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0bdf4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0bdf4-105">**Applies to:**</span></span>
- [<span data-ttu-id="0bdf4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0bdf4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0bdf4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bdf4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0bdf4-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0bdf4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0bdf4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="0bdf4-110">Microsoft Threat Experts es un servicio de búsqueda de amenazas administrado que proporciona a los Centros de operaciones de seguridad (SOC) supervisión y análisis de nivel de expertos para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierden.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-110">Microsoft Threat Experts is a managed threat hunting service that provides your Security Operation Centers (SOCs) with expert level monitoring and analysis to help them ensure that critical threats in your unique environments don’t get missed.</span></span>
  
<span data-ttu-id="0bdf4-111">Este servicio de búsqueda de amenazas administradas proporciona información y datos controlados por expertos a través de estas dos capacidades: notificación de ataques dirigidos y acceso a expertos a petición.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-111">This managed threat hunting service provides expert-driven insights and data through these two capabilities: targeted attack notification and access to experts on demand.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0bdf4-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0bdf4-112">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="0bdf4-113">Analice los requisitos de elegibilidad con su proveedor de servicios técnicos de Microsoft y el equipo de cuenta antes de aplicar al servicio de búsqueda de amenazas administradas.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-113">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to the managed threat hunting service.</span></span>

<span data-ttu-id="0bdf4-114">Si es cliente de Microsoft Defender para endpoints, debe solicitar microsoft **threat experts - Targeted Attack Notifications** para obtener información y análisis especiales que ayuden a identificar las amenazas más críticas de su entorno para que pueda responder a ellas rápidamente</span><span class="sxs-lookup"><span data-stu-id="0bdf4-114">If you're a Microsoft Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis that help identify the most critical threats in your environment so you can respond to them quickly</span></span>

<span data-ttu-id="0bdf4-115">Para inscribirse en Microsoft Threat Experts- Targeted Attack Notifications benefits, ve a **Configuración**  >  **General**  >  **Advanced features** Microsoft Threat Experts -  >  **Targeted Attack Notifications** to apply.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-115">To enroll to Microsoft Threat Experts - Targeted Attack Notifications benefits, go to **Settings** > **General** > **Advanced features** > **Microsoft Threat Experts - Targeted Attack Notifications** to apply.</span></span> <span data-ttu-id="0bdf4-116">Una vez aceptado, recibirás las ventajas de las notificaciones de ataque dirigido.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-116">Once accepted, you will get the benefits of Targeted Attack Notifications.</span></span>

<span data-ttu-id="0bdf4-117">Póngase en contacto con su equipo de cuenta o representante de Microsoft para suscribirse a Expertos en amenazas de **Microsoft:** expertos a petición para consultar con nuestros expertos en amenazas sobre las detecciones y los conflictos relevantes a los que se enfrenta su organización.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-117">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries that your organization is facing.</span></span>

<span data-ttu-id="0bdf4-118">Consulte [Configurar las capacidades de Microsoft Threat Experts](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-118">See [Configure Microsoft Threat Experts capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#before-you-begin) for details.</span></span> 

## <a name="microsoft-threat-experts---targeted-attack-notification"></a><span data-ttu-id="0bdf4-119">Expertos en amenazas de Microsoft: notificación de ataque dirigido</span><span class="sxs-lookup"><span data-stu-id="0bdf4-119">Microsoft Threat Experts - Targeted attack notification</span></span> 
<span data-ttu-id="0bdf4-120">Expertos en amenazas de Microsoft: la notificación de ataques dirigidos proporciona una búsqueda proactiva de las amenazas más importantes para la red, incluidas las intrusiones de adversarios humanos, los ataques con teclado o ataques avanzados como el ciberespionaje.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-120">Microsoft Threat Experts - Targeted attack notification provides proactive hunting for the most important threats to your network, including human adversary intrusions, hands-on-keyboard attacks, or advanced attacks like cyber-espionage.</span></span> <span data-ttu-id="0bdf4-121">Estas notificaciones se muestran como una nueva alerta.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-121">These notifications shows up as a new alert.</span></span> <span data-ttu-id="0bdf4-122">El servicio de búsqueda administrada incluye:</span><span class="sxs-lookup"><span data-stu-id="0bdf4-122">The managed hunting service includes:</span></span>  
- <span data-ttu-id="0bdf4-123">Supervisión y análisis de amenazas, lo que reduce el tiempo de permanencia y el riesgo para la empresa</span><span class="sxs-lookup"><span data-stu-id="0bdf4-123">Threat monitoring and analysis, reducing dwell time and risk to the business</span></span> 
- <span data-ttu-id="0bdf4-124">Inteligencia artificial entrenada por el cazador para descubrir y priorizar ataques conocidos y desconocidos</span><span class="sxs-lookup"><span data-stu-id="0bdf4-124">Hunter-trained artificial intelligence to discover and prioritize both known and unknown attacks</span></span>  
- <span data-ttu-id="0bdf4-125">Identificar los riesgos más importantes, ayudar a los SOC a maximizar el tiempo y la energía</span><span class="sxs-lookup"><span data-stu-id="0bdf4-125">Identifying the most important risks, helping SOCs maximize time and energy</span></span> 
- <span data-ttu-id="0bdf4-126">Ámbito de compromiso y tanto contexto como se pueda entregar rápidamente para habilitar una respuesta rápida de SOC.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-126">Scope of compromise and as much context as can be quickly delivered to enable fast SOC response.</span></span> 
 
## <a name="microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="0bdf4-127">Expertos en amenazas de Microsoft: expertos a petición</span><span class="sxs-lookup"><span data-stu-id="0bdf4-127">Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="0bdf4-128">Los clientes pueden contratar a nuestros expertos en seguridad directamente desde el Centro de seguridad de Microsoft Defender para obtener una respuesta rápida y precisa.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-128">Customers can engage our security experts directly from within Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="0bdf4-129">Los expertos proporcionan información necesaria para comprender mejor las amenazas complejas que afectan a su organización, desde las consultas de alertas, los dispositivos potencialmente en peligro, la causa raíz de una conexión de red sospechosa, hasta la inteligencia de amenazas adicional con respecto a las campañas de amenazas persistentes avanzadas en curso.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-129">Experts provide insights needed to better understand the complex threats affecting your organization, from alert inquiries, potentially compromised devices, root cause of a suspicious network connection, to additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="0bdf4-130">Con esta funcionalidad, puede:</span><span class="sxs-lookup"><span data-stu-id="0bdf4-130">With this capability, you can:</span></span>
- <span data-ttu-id="0bdf4-131">Obtener aclaraciones adicionales sobre alertas, incluida la causa raíz o el ámbito del incidente</span><span class="sxs-lookup"><span data-stu-id="0bdf4-131">Get additional clarification on alerts including root cause or scope of the incident</span></span> 
- <span data-ttu-id="0bdf4-132">Obtenga claridad sobre el comportamiento sospechoso del dispositivo y los siguientes pasos si se enfrenta a un atacante avanzado</span><span class="sxs-lookup"><span data-stu-id="0bdf4-132">Gain clarity into suspicious device behavior and next steps if faced with an advanced attacker</span></span>  
- <span data-ttu-id="0bdf4-133">Determinar el riesgo y la protección con respecto a actores de amenazas, campañas o técnicas de atacante emergente</span><span class="sxs-lookup"><span data-stu-id="0bdf4-133">Determine risk and protection regarding threat actors, campaigns, or emerging attacker techniques</span></span> 

<span data-ttu-id="0bdf4-134">La opción consultar **a un experto en** amenazas está disponible en varios lugares del portal para que pueda interactuar con expertos en el contexto de la investigación:</span><span class="sxs-lookup"><span data-stu-id="0bdf4-134">The option to **Consult a threat expert** is available in several places in the portal so you can engage with experts in the context of your investigation:</span></span>

- <span data-ttu-id="0bdf4-135"><i>**Menú ayuda y soporte técnico**</i></span><span class="sxs-lookup"><span data-stu-id="0bdf4-135"><i>**Help and support menu**</i></span></span><BR>
<span data-ttu-id="0bdf4-136">![Captura de pantalla de la opción de menú MTE-EOD](images/mte-eod-menu.png)</span><span class="sxs-lookup"><span data-stu-id="0bdf4-136">![Screenshot of MTE-EOD menu option](images/mte-eod-menu.png)</span></span>

- <span data-ttu-id="0bdf4-137"><i>**Menú acciones de página de dispositivo**</i></span><span class="sxs-lookup"><span data-stu-id="0bdf4-137"><i>**Device page actions menu**</i></span></span><BR>
<span data-ttu-id="0bdf4-138">![Captura de pantalla de la opción de menú de acción de página de dispositivo MTE-EOD](images/mte-eod-machines.png)</span><span class="sxs-lookup"><span data-stu-id="0bdf4-138">![Screenshot of MTE-EOD device page action menu option](images/mte-eod-machines.png)</span></span>

- <span data-ttu-id="0bdf4-139"><i>**Menú acciones de página alertas**</i></span><span class="sxs-lookup"><span data-stu-id="0bdf4-139"><i>**Alerts page actions menu**</i></span></span><BR>
<span data-ttu-id="0bdf4-140">![Captura de pantalla de la opción de menú de acción de página de alerta MTE-EOD](images/mte-eod-alerts.png)</span><span class="sxs-lookup"><span data-stu-id="0bdf4-140">![Screenshot of MTE-EOD alert page action menu option](images/mte-eod-alerts.png)</span></span>

- <span data-ttu-id="0bdf4-141"><i>**Menú Acciones de página de archivos**</i></span><span class="sxs-lookup"><span data-stu-id="0bdf4-141"><i>**File page actions menu**</i></span></span><BR>
<span data-ttu-id="0bdf4-142">![Captura de pantalla de la opción de menú de acción de página de archivo MTE-EOD](images/mte-eod-file.png)</span><span class="sxs-lookup"><span data-stu-id="0bdf4-142">![Screenshot of MTE-EOD file page action menu option](images/mte-eod-file.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0bdf4-143">Si desea realizar un seguimiento del estado de los casos de expertos a petición a través del Centro de servicios de Microsoft, comunicarse con el Administrador técnico de cuentas.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-143">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="0bdf4-144">Vea este vídeo para obtener una introducción rápida al Centro de servicios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bdf4-144">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 

   
## <a name="related-topic"></a><span data-ttu-id="0bdf4-145">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="0bdf4-145">Related topic</span></span>
- [<span data-ttu-id="0bdf4-146">Configurar las capacidades de Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="0bdf4-146">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md)
