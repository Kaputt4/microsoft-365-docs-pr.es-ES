---
title: Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base
description: Administrar cómo Antivirus de Microsoft Defender recibe actualizaciones de productos y protección.
keywords: actualizaciones, líneas base de seguridad, protección, actualizaciones de programación, actualizaciones de fuerza, actualizaciones móviles, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ae17aa6e2cb0cefd460ef0db0730570af8c84bb8
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995038"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="01d12-104">Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="01d12-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="01d12-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="01d12-105">**Applies to:**</span></span>

- [<span data-ttu-id="01d12-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="01d12-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="01d12-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01d12-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="01d12-108">Hay dos tipos de actualizaciones relacionadas con la actualización del Antivirus de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="01d12-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="01d12-109">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="01d12-109">Security intelligence updates</span></span>
- <span data-ttu-id="01d12-110">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="01d12-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01d12-111">Mantener el Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de malware y ataques.</span><span class="sxs-lookup"><span data-stu-id="01d12-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="01d12-112">Asegúrese de actualizar la protección antivirus incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="01d12-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="01d12-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de [Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="01d12-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="01d12-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="01d12-114">Security intelligence updates</span></span>

<span data-ttu-id="01d12-115">Antivirus de Microsoft Defender usa [protección](cloud-protection-microsoft-defender-antivirus.md) entregada en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="01d12-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="01d12-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="01d12-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="01d12-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="01d12-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="01d12-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="01d12-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="01d12-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="01d12-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="01d12-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="01d12-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="01d12-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="01d12-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="01d12-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad para Antivirus de [Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="01d12-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="01d12-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="01d12-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="01d12-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="01d12-124">Product updates</span></span>

<span data-ttu-id="01d12-125">Microsoft Defender Antivirus requiere actualizaciones [mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con las versiones de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="01d12-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="01d12-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="01d12-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="01d12-127">Servicio de actualización de Windows Server (WSUS)</span><span class="sxs-lookup"><span data-stu-id="01d12-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="01d12-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="01d12-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="01d12-129">El método habitual que usas para implementar las actualizaciones de Microsoft y Windows en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="01d12-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="01d12-130">Para obtener más información, vea [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="01d12-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="01d12-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="01d12-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="01d12-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="01d12-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="01d12-133">Para obtener información sobre cómo actualizar o instalar la actualización de plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="01d12-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="01d12-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="01d12-134">All our updates contain</span></span> 
- <span data-ttu-id="01d12-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="01d12-135">performance improvements;</span></span>
- <span data-ttu-id="01d12-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="01d12-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="01d12-137">mejoras de integración (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="01d12-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="01d12-138">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="01d12-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="01d12-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="01d12-140">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="01d12-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="01d12-141">&ensp;Plataforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="01d12-142">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="01d12-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="01d12-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-144">What's new</span></span>

- <span data-ttu-id="01d12-145">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="01d12-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="01d12-146">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="01d12-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="01d12-147">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="01d12-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-148">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-148">Known Issues</span></span>
<span data-ttu-id="01d12-149">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="01d12-150">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="01d12-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="01d12-151">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="01d12-152">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="01d12-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="01d12-153">&ensp;Plataforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="01d12-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="01d12-154">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="01d12-155">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="01d12-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-156">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-156">What's new</span></span>

- <span data-ttu-id="01d12-157">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="01d12-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="01d12-158">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="01d12-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-159">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-159">Known Issues</span></span>
<span data-ttu-id="01d12-160">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="01d12-161">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="01d12-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="01d12-162">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="01d12-163">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="01d12-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="01d12-164">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="01d12-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="01d12-165">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="01d12-166">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="01d12-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-167">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-167">What's new</span></span>

- <span data-ttu-id="01d12-168">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="01d12-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="01d12-169">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="01d12-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="01d12-170">Mejoras en las características de protección contra el entorpecimiento en los servicios antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01d12-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="01d12-171">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="01d12-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="01d12-172">Corrección: La notificación de bloqueo de EDR permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="01d12-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-173">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-173">Known Issues</span></span>
<span data-ttu-id="01d12-174">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="01d12-175">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="01d12-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="01d12-176">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="01d12-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="01d12-177">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="01d12-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="01d12-178">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="01d12-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="01d12-179">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="01d12-180">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="01d12-181">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="01d12-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="01d12-182">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="01d12-183">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-183">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-184">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-184">What's new</span></span>

- <span data-ttu-id="01d12-185">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="01d12-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-186">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-186">Known Issues</span></span>
<span data-ttu-id="01d12-187">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="01d12-188">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="01d12-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="01d12-189">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="01d12-190">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="01d12-191">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="01d12-192">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="01d12-193">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-193">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-194">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-194">What's new</span></span>

- <span data-ttu-id="01d12-195">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="01d12-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="01d12-196">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="01d12-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="01d12-197">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="01d12-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="01d12-198">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="01d12-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-199">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-199">Known Issues</span></span>

<span data-ttu-id="01d12-200">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="01d12-201">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="01d12-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="01d12-202">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="01d12-203">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="01d12-204">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="01d12-205">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="01d12-206">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-207">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-207">What's new</span></span>

- <span data-ttu-id="01d12-208">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="01d12-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="01d12-209">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="01d12-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="01d12-210">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="01d12-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="01d12-211">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="01d12-211">New management interfaces for:</span></span>
   - <span data-ttu-id="01d12-212">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="01d12-212">UDP Inspection</span></span>
   - <span data-ttu-id="01d12-213">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="01d12-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="01d12-214">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="01d12-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="01d12-215">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="01d12-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="01d12-216">Examen mejorado del módulo VBA de Office</span><span class="sxs-lookup"><span data-stu-id="01d12-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-217">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-217">Known Issues</span></span>

<span data-ttu-id="01d12-218">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="01d12-219">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="01d12-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="01d12-220">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="01d12-221">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="01d12-222">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="01d12-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="01d12-223">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="01d12-224">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="01d12-225">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-225">What's new</span></span>

- <span data-ttu-id="01d12-226">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="01d12-226">Add more telemetry events</span></span>
- <span data-ttu-id="01d12-227">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="01d12-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="01d12-228">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="01d12-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="01d12-229">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="01d12-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="01d12-230">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="01d12-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="01d12-231">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="01d12-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="01d12-232">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="01d12-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="01d12-233">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-233">Known Issues</span></span>
<span data-ttu-id="01d12-234">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-235">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="01d12-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="01d12-236">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="01d12-237">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="01d12-238">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="01d12-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="01d12-239">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="01d12-240">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-241">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-241">What's new</span></span>

- <span data-ttu-id="01d12-242">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="01d12-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="01d12-243">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="01d12-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-244">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-244">Known Issues</span></span>
<span data-ttu-id="01d12-245">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-246">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="01d12-247">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="01d12-248">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="01d12-249">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="01d12-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="01d12-250">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="01d12-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="01d12-251">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-252">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-252">What's new</span></span>

- <span data-ttu-id="01d12-253">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="01d12-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="01d12-254">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="01d12-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="01d12-255">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="01d12-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="01d12-256">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="01d12-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="01d12-257">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="01d12-257">Fixed registry query</span></span> 
- <span data-ttu-id="01d12-258">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="01d12-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-259">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-259">Known Issues</span></span>
<span data-ttu-id="01d12-260">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-261">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="01d12-262">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="01d12-263">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="01d12-264">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="01d12-265">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="01d12-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="01d12-266">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-267">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-267">What's new</span></span>

- <span data-ttu-id="01d12-268">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="01d12-268">Improved logging for scan events</span></span>
- <span data-ttu-id="01d12-269">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="01d12-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="01d12-270">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="01d12-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="01d12-271">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="01d12-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="01d12-272">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="01d12-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="01d12-273">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="01d12-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-274">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-274">Known Issues</span></span>
<span data-ttu-id="01d12-275">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-276">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="01d12-277">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="01d12-278">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="01d12-279">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="01d12-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="01d12-280">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="01d12-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="01d12-281">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-282">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-282">What's new</span></span>
- <span data-ttu-id="01d12-283">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="01d12-283">WDfilter improvements</span></span>
- <span data-ttu-id="01d12-284">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="01d12-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="01d12-285">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="01d12-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="01d12-286">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="01d12-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="01d12-287">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="01d12-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="01d12-288">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="01d12-288">UEFI scan capability</span></span>
- <span data-ttu-id="01d12-289">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="01d12-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="01d12-290">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-290">Known Issues</span></span>
<span data-ttu-id="01d12-291">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-292">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="01d12-293">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="01d12-294">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="01d12-295">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="01d12-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="01d12-296">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="01d12-297">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="01d12-298">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-298">What's new</span></span>

- <span data-ttu-id="01d12-299">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="01d12-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="01d12-300">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="01d12-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="01d12-301">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="01d12-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="01d12-302">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="01d12-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="01d12-303">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="01d12-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="01d12-304">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-304">Known Issues</span></span>
<span data-ttu-id="01d12-305">[**Fijo**] Antivirus de Microsoft Defender omite archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="01d12-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="01d12-306">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="01d12-307">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="01d12-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="01d12-308">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="01d12-309">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="01d12-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="01d12-310">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="01d12-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="01d12-311">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="01d12-312">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="01d12-313">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-313">Known Issues</span></span>
<span data-ttu-id="01d12-314">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-315">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="01d12-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="01d12-316">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="01d12-317">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="01d12-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="01d12-318">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="01d12-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="01d12-319">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="01d12-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="01d12-320">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="01d12-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="01d12-321">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-321">What's new</span></span>

- <span data-ttu-id="01d12-322">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="01d12-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="01d12-323">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="01d12-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="01d12-324">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="01d12-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="01d12-325">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="01d12-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="01d12-326">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="01d12-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="01d12-327">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-327">Known Issues</span></span>

<span data-ttu-id="01d12-328">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="01d12-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="01d12-329">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="01d12-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="01d12-330">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="01d12-330">This update is:</span></span>
> - <span data-ttu-id="01d12-331">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="01d12-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="01d12-332">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="01d12-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="01d12-333">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="01d12-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="01d12-334">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="01d12-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="01d12-335">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="01d12-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="01d12-336">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="01d12-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="01d12-337">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="01d12-338">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="01d12-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="01d12-339">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="01d12-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="01d12-340">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="01d12-341">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="01d12-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="01d12-342">Novedades</span><span class="sxs-lookup"><span data-stu-id="01d12-342">What's new</span></span>

- <span data-ttu-id="01d12-343">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="01d12-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="01d12-344">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="01d12-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="01d12-345">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="01d12-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="01d12-346">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="01d12-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="01d12-347">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="01d12-347">Known Issues</span></span>
<span data-ttu-id="01d12-348">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.10.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="01d12-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="01d12-349">Compatibilidad con la plataforma antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01d12-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="01d12-350">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="01d12-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="01d12-351">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="01d12-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="01d12-352">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="01d12-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="01d12-353">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="01d12-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="01d12-354">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="01d12-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="01d12-355">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="01d12-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="01d12-356">\* Se seguirá brindando soporte técnico para las actualizaciones de la versión de versión de Windows 10 (consulta Versión de plataforma incluida con versiones de [Windows 10)](#platform-version-included-with-windows-10-releases)a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="01d12-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="01d12-357">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="01d12-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="01d12-358">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="01d12-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="01d12-359">Versión de plataforma incluida con versiones de Windows 10</span><span class="sxs-lookup"><span data-stu-id="01d12-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="01d12-360">En la tabla siguiente se proporcionan las versiones del motor y la plataforma antivirus de Microsoft Defender que se suministran con las versiones más recientes de Windows 10:</span><span class="sxs-lookup"><span data-stu-id="01d12-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="01d12-361">Versión de Windows 10</span><span class="sxs-lookup"><span data-stu-id="01d12-361">Windows 10 release</span></span>  |<span data-ttu-id="01d12-362">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="01d12-362">Platform version</span></span>  |<span data-ttu-id="01d12-363">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="01d12-363">Engine version</span></span> |<span data-ttu-id="01d12-364">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="01d12-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="01d12-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="01d12-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="01d12-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="01d12-366">4.18.1909.6</span></span> |<span data-ttu-id="01d12-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="01d12-367">1.1.17000.2</span></span> | <span data-ttu-id="01d12-368">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="01d12-369">1909  (19H2)</span></span> |<span data-ttu-id="01d12-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="01d12-370">4.18.1902.5</span></span> |<span data-ttu-id="01d12-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="01d12-371">1.1.16700.3</span></span> | <span data-ttu-id="01d12-372">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="01d12-373">1903  (19H1)</span></span> |<span data-ttu-id="01d12-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="01d12-374">4.18.1902.5</span></span> |<span data-ttu-id="01d12-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="01d12-375">1.1.15600.4</span></span> | <span data-ttu-id="01d12-376">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="01d12-377">1809  (RS5)</span></span> |<span data-ttu-id="01d12-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="01d12-378">4.18.1807.18075</span></span> |<span data-ttu-id="01d12-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="01d12-379">1.1.15000.2</span></span> | <span data-ttu-id="01d12-380">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="01d12-381">1803  (RS4)</span></span> |<span data-ttu-id="01d12-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="01d12-382">4.13.17134.1</span></span> |<span data-ttu-id="01d12-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="01d12-383">1.1.14600.4</span></span> | <span data-ttu-id="01d12-384">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="01d12-385">1709  (RS3)</span></span> |<span data-ttu-id="01d12-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="01d12-386">4.12.16299.15</span></span> |<span data-ttu-id="01d12-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="01d12-387">1.1.14104.0</span></span> | <span data-ttu-id="01d12-388">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="01d12-389">1703  (RS2)</span></span> |<span data-ttu-id="01d12-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="01d12-390">4.11.15603.2</span></span> |<span data-ttu-id="01d12-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="01d12-391">1.1.13504.0</span></span> | <span data-ttu-id="01d12-392">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="01d12-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="01d12-393">1607 (RS1)</span></span> |<span data-ttu-id="01d12-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="01d12-394">4.10.14393.3683</span></span> |<span data-ttu-id="01d12-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="01d12-395">1.1.12805.0</span></span> | <span data-ttu-id="01d12-396">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="01d12-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="01d12-397">Para obtener información sobre la versión de Windows 10, consulta la hoja de hechos del ciclo [de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="01d12-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="01d12-398">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="01d12-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="01d12-399">Se recomienda actualizar las imágenes de instalación del sistema operativo Windows 10 (Enterprise, Pro y Home editions), Windows Server 2019 y Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="01d12-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="01d12-400">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="01d12-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="01d12-401">Para obtener más información, consulta [Actualización de Microsoft Defender para imágenes de instalación del sistema operativo Windows](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="01d12-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="01d12-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="01d12-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="01d12-403">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="01d12-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="01d12-404">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="01d12-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="01d12-405">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="01d12-406">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-407">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-407">Fixes</span></span>
- <span data-ttu-id="01d12-408">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-409">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-409">Additional information</span></span>
- <span data-ttu-id="01d12-410">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="01d12-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="01d12-412">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="01d12-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="01d12-413">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="01d12-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="01d12-414">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="01d12-415">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-416">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-416">Fixes</span></span>
- <span data-ttu-id="01d12-417">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-418">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-418">Additional information</span></span>
- <span data-ttu-id="01d12-419">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="01d12-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="01d12-421">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="01d12-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="01d12-422">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="01d12-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="01d12-423">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="01d12-424">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-425">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-425">Fixes</span></span>
- <span data-ttu-id="01d12-426">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-427">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-427">Additional information</span></span>
- <span data-ttu-id="01d12-428">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="01d12-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="01d12-430">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="01d12-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="01d12-431">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="01d12-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="01d12-432">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="01d12-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="01d12-433">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-434">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-434">Fixes</span></span>
- <span data-ttu-id="01d12-435">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-436">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-436">Additional information</span></span>
- <span data-ttu-id="01d12-437">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="01d12-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="01d12-439">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="01d12-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="01d12-440">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="01d12-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="01d12-441">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="01d12-442">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-443">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-443">Fixes</span></span>
- <span data-ttu-id="01d12-444">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-445">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-445">Additional information</span></span>
- <span data-ttu-id="01d12-446">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="01d12-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="01d12-448">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="01d12-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="01d12-449">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="01d12-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="01d12-450">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="01d12-451">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-452">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-452">Fixes</span></span>
- <span data-ttu-id="01d12-453">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-454">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-454">Additional information</span></span>
- <span data-ttu-id="01d12-455">Firmas de Antivirus de Microsoft Defender actualizados</span><span class="sxs-lookup"><span data-stu-id="01d12-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="01d12-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="01d12-457">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="01d12-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="01d12-458">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="01d12-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="01d12-459">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="01d12-460">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-461">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-461">Fixes</span></span>
- <span data-ttu-id="01d12-462">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-463">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-463">Additional information</span></span>
- <span data-ttu-id="01d12-464">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="01d12-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="01d12-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="01d12-466">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="01d12-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="01d12-467">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="01d12-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="01d12-468">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="01d12-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="01d12-469">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="01d12-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="01d12-470">Correcciones</span><span class="sxs-lookup"><span data-stu-id="01d12-470">Fixes</span></span>
- <span data-ttu-id="01d12-471">Ninguno</span><span class="sxs-lookup"><span data-stu-id="01d12-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="01d12-472">Información adicional</span><span class="sxs-lookup"><span data-stu-id="01d12-472">Additional information</span></span>
- <span data-ttu-id="01d12-473">Se agregó compatibilidad con imágenes de instalación del sistema operativo Windows 10 RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="01d12-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="01d12-474">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="01d12-474">Additional resources</span></span>

| <span data-ttu-id="01d12-475">Artículo</span><span class="sxs-lookup"><span data-stu-id="01d12-475">Article</span></span> | <span data-ttu-id="01d12-476">Descripción</span><span class="sxs-lookup"><span data-stu-id="01d12-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="01d12-477">Actualización de Microsoft Defender para imágenes de instalación del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="01d12-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="01d12-478">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="01d12-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="01d12-479">Obtén actualizaciones de Antivirus de Microsoft Defender para Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Imágenes de instalación de Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="01d12-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="01d12-480">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="01d12-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="01d12-481">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="01d12-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="01d12-482">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="01d12-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="01d12-483">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="01d12-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="01d12-484">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="01d12-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="01d12-485">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="01d12-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="01d12-486">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="01d12-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="01d12-487">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="01d12-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="01d12-488">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="01d12-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="01d12-489">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="01d12-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
