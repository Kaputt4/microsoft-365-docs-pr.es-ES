---
title: Integrar Microsoft Defender para endpoint con otras soluciones de Microsoft
description: Obtenga información sobre cómo Microsoft Defender para Endpoint se integra con otras soluciones de Microsoft, como Microsoft Defender para Identity y Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, acceso condicional, office, Microsoft Defender para endpoint, microsoft defender para la identidad, microsoft defender para office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878573"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="e0a91-104">Microsoft Defender para endpoint y otras soluciones de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0a91-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e0a91-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e0a91-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0a91-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e0a91-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e0a91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0a91-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e0a91-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="e0a91-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e0a91-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e0a91-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="e0a91-110">Integrar con otras soluciones de Microsoft</span><span class="sxs-lookup"><span data-stu-id="e0a91-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="e0a91-111">Microsoft Defender para endpoint se integra directamente con varias soluciones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0a91-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="e0a91-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="e0a91-112">Azure Defender</span></span>
<span data-ttu-id="e0a91-113">Microsoft Defender para endpoint proporciona una solución completa de protección de servidores, que incluye detección y respuesta de puntos de conexión (EDR) en Windows servidores.</span><span class="sxs-lookup"><span data-stu-id="e0a91-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="e0a91-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="e0a91-114">Azure Sentinel</span></span>
<span data-ttu-id="e0a91-115">El conector de Microsoft Defender para puntos de conexión te permite transmitir alertas de Microsoft Defender para endpoint en Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="e0a91-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="e0a91-116">Esto te permitirá analizar más exhaustivamente los eventos de seguridad en toda la organización y crear libros de juegos para obtener una respuesta eficaz e inmediata.</span><span class="sxs-lookup"><span data-stu-id="e0a91-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="e0a91-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="e0a91-117">Azure Information Protection</span></span>
<span data-ttu-id="e0a91-118">Recientemente hemos dejado de usar la integración de Azure Information Protection, ya que nuestras capacidades DLP de punto de conexión incorporan una solución mejorada de detección y protección para datos confidenciales almacenados en dispositivos de punto de conexión que facilita una mayor visibilidad e integración entre soluciones.</span><span class="sxs-lookup"><span data-stu-id="e0a91-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="e0a91-119">Esto se anunció en el [siguiente blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span><span class="sxs-lookup"><span data-stu-id="e0a91-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="e0a91-120">Se recomienda que los clientes pasen a usar DLP de extremo.</span><span class="sxs-lookup"><span data-stu-id="e0a91-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="e0a91-121">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="e0a91-121">Conditional Access</span></span>
<span data-ttu-id="e0a91-122">La puntuación de riesgo de dispositivo dinámico de Microsoft Defender para endpoint está integrada en la evaluación de acceso condicional, lo que garantiza que solo los dispositivos seguros tengan acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="e0a91-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="e0a91-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e0a91-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="e0a91-124">Microsoft Cloud App Security aprovecha las señales de punto de conexión de Microsoft Defender para endpoints para permitir la visibilidad directa del uso de aplicaciones en la nube, incluido el uso de servicios en la nube no compatibles (TI de instantánea) de todos los dispositivos supervisados por Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="e0a91-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="e0a91-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="e0a91-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="e0a91-126">Las actividades sospechosas son procesos que se ejecutan en un contexto de usuario.</span><span class="sxs-lookup"><span data-stu-id="e0a91-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="e0a91-127">La integración entre Microsoft Defender para Endpoint y Microsoft Defender for Identity proporciona la flexibilidad de realizar investigaciones de ciberseguridad entre actividades e identidades.</span><span class="sxs-lookup"><span data-stu-id="e0a91-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="e0a91-128">Microsoft Defender para Office</span><span class="sxs-lookup"><span data-stu-id="e0a91-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="e0a91-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) ayuda a proteger su organización contra malware en mensajes de correo electrónico o archivos a través de vínculos de Caja fuerte, datos adjuntos de Caja fuerte, capacidades avanzadas de inteligencia anti phishing y suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e0a91-129">[Defender for Office 365](/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="e0a91-130">La integración entre Microsoft Defender para Office 365 y Microsoft Defender para endpoint permite a los analistas de seguridad ir hacia arriba para investigar el punto de entrada de un ataque.</span><span class="sxs-lookup"><span data-stu-id="e0a91-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="e0a91-131">A través del uso compartido de inteligencia de amenazas, los ataques pueden contenerse y bloquearse.</span><span class="sxs-lookup"><span data-stu-id="e0a91-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="e0a91-132">Defender para Office 365 se muestra para eventos en los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="e0a91-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="e0a91-133">Para las alertas, Defender para Office 365 datos se muestra en función de la primera hora de actividad.</span><span class="sxs-lookup"><span data-stu-id="e0a91-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="e0a91-134">Después de eso, los datos ya no están disponibles en Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e0a91-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="e0a91-135">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="e0a91-135">Skype for Business</span></span>
<span data-ttu-id="e0a91-136">La Skype Empresarial permite a los analistas comunicarse con un usuario o propietario de dispositivo potencialmente comprometido a través de un botón sencillo del portal.</span><span class="sxs-lookup"><span data-stu-id="e0a91-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="e0a91-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0a91-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="e0a91-138">Con Microsoft 365 Defender, Microsoft Defender para endpoint y varias soluciones de seguridad de Microsoft forman un conjunto de aplicaciones de defensa empresarial unificado previo y posterior a la infracción que se integra de forma nativa en los puntos de conexión, identidad, correo electrónico y aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="e0a91-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint, and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="e0a91-139">Obtenga más información sobre Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0a91-139">Learn more about Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a><span data-ttu-id="e0a91-140">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e0a91-140">Related topics</span></span>
- [<span data-ttu-id="e0a91-141">Configurar la integración y otras características avanzadas</span><span class="sxs-lookup"><span data-stu-id="e0a91-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="e0a91-142">Microsoft 365 Introducción al defensor</span><span class="sxs-lookup"><span data-stu-id="e0a91-142">Microsoft 365 Defender overview</span></span>](/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="e0a91-143">Activar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0a91-143">Turn on Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="e0a91-144">Proteger usuarios, datos y dispositivos con acceso condicional</span><span class="sxs-lookup"><span data-stu-id="e0a91-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
