---
title: Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base
description: Administrar cómo Antivirus de Microsoft Defender la protección y las actualizaciones de productos.
keywords: actualizaciones, líneas base de seguridad, protección, actualizaciones de programación, actualizaciones de fuerza, actualizaciones móviles, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: 4f2b931018d49affa2d94ddf1a147c4fd2e02085
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302081"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="e4597-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="e4597-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="e4597-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e4597-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4597-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e4597-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="e4597-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e4597-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e4597-108">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="e4597-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="e4597-109">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e4597-109">Security intelligence updates</span></span>
- <span data-ttu-id="e4597-110">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="e4597-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4597-111">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="e4597-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="e4597-112">Asegúrese de actualizar la protección antivirus incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="e4597-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="e4597-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y [otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="e4597-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="e4597-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e4597-114">Security intelligence updates</span></span>

<span data-ttu-id="e4597-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="e4597-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="e4597-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4597-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="e4597-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="e4597-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="e4597-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="e4597-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="e4597-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="e4597-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="e4597-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="e4597-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="e4597-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="e4597-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e4597-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="e4597-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="e4597-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="e4597-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="e4597-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="e4597-124">Product updates</span></span>

<span data-ttu-id="e4597-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="e4597-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="e4597-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="e4597-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="e4597-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="e4597-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="e4597-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e4597-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="e4597-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="e4597-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="e4597-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="e4597-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="e4597-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="e4597-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="e4597-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="e4597-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="e4597-133">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="e4597-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="e4597-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="e4597-134">All our updates contain</span></span> 
- <span data-ttu-id="e4597-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="e4597-135">performance improvements;</span></span>
- <span data-ttu-id="e4597-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="e4597-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="e4597-137">mejoras de integración (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="e4597-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="e4597-138">Abril-2021 (plataforma: 4.18.2104.9| Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="e4597-138">April-2021 (Platform: 4.18.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="e4597-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="e4597-140">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="e4597-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="e4597-141">&ensp;Plataforma: **4.18.2104.9**</span><span class="sxs-lookup"><span data-stu-id="e4597-141">&ensp;Platform: **4.18.2104.9**</span></span>  
<span data-ttu-id="e4597-142">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="e4597-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e4597-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-144">What's new</span></span>
- <span data-ttu-id="e4597-145">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="e4597-146">Detección de registrador de teclas de modo kernel mejorado</span><span class="sxs-lookup"><span data-stu-id="e4597-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-147">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-147">Known Issues</span></span>
<span data-ttu-id="e4597-148">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-149">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="e4597-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="e4597-150">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="e4597-151">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="e4597-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="e4597-152">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="e4597-153">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4597-154">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e4597-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-155">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-155">What's new</span></span>

- <span data-ttu-id="e4597-156">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="e4597-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="e4597-157">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="e4597-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="e4597-158">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="e4597-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-159">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-159">Known Issues</span></span>
<span data-ttu-id="e4597-160">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4597-161">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="e4597-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="e4597-162">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="e4597-163">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="e4597-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="e4597-164">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="e4597-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="e4597-165">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="e4597-166">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e4597-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-167">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-167">What's new</span></span>

- <span data-ttu-id="e4597-168">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e4597-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="e4597-169">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="e4597-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-170">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-170">Known Issues</span></span>
<span data-ttu-id="e4597-171">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="e4597-172">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="e4597-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="e4597-173">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e4597-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="e4597-174">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="e4597-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="e4597-175">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="e4597-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="e4597-176">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4597-177">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="e4597-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="e4597-178">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="e4597-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="e4597-179">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4597-180">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-181">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-181">What's new</span></span>

- <span data-ttu-id="e4597-182">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="e4597-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="e4597-183">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="e4597-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="e4597-184">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="e4597-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="e4597-185">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="e4597-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="e4597-186">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="e4597-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-187">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-187">Known Issues</span></span>
<span data-ttu-id="e4597-188">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4597-189">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="e4597-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="e4597-190">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e4597-191">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="e4597-192">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="e4597-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="e4597-193">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4597-194">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-195">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-195">What's new</span></span>

- <span data-ttu-id="e4597-196">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="e4597-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-197">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-197">Known Issues</span></span>
<span data-ttu-id="e4597-198">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4597-199">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="e4597-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="e4597-200">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="e4597-201">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="e4597-202">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="e4597-203">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4597-204">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-205">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-205">What's new</span></span>

- <span data-ttu-id="e4597-206">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="e4597-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="e4597-207">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="e4597-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="e4597-208">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="e4597-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="e4597-209">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="e4597-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-210">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-210">Known Issues</span></span>

<span data-ttu-id="e4597-211">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e4597-212">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="e4597-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="e4597-213">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="e4597-214">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="e4597-215">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4597-216">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="e4597-217">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-218">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-218">What's new</span></span>

- <span data-ttu-id="e4597-219">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e4597-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="e4597-220">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="e4597-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="e4597-221">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="e4597-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="e4597-222">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="e4597-222">New management interfaces for:</span></span>
   - <span data-ttu-id="e4597-223">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="e4597-223">UDP Inspection</span></span>
   - <span data-ttu-id="e4597-224">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="e4597-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="e4597-225">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="e4597-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="e4597-226">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="e4597-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="e4597-227">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="e4597-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-228">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-228">Known Issues</span></span>

<span data-ttu-id="e4597-229">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="e4597-230">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="e4597-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="e4597-231">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="e4597-232">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="e4597-233">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="e4597-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="e4597-234">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4597-235">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="e4597-236">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-236">What's new</span></span>

- <span data-ttu-id="e4597-237">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="e4597-237">Add more telemetry events</span></span>
- <span data-ttu-id="e4597-238">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="e4597-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="e4597-239">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="e4597-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="e4597-240">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="e4597-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="e4597-241">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4597-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="e4597-242">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="e4597-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="e4597-243">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="e4597-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="e4597-244">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-244">Known Issues</span></span>
<span data-ttu-id="e4597-245">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-246">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="e4597-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="e4597-247">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="e4597-248">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="e4597-249">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="e4597-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="e4597-250">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="e4597-251">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-252">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-252">What's new</span></span>

- <span data-ttu-id="e4597-253">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="e4597-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="e4597-254">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="e4597-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-255">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-255">Known Issues</span></span>
<span data-ttu-id="e4597-256">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-257">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="e4597-258">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="e4597-259">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="e4597-260">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="e4597-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="e4597-261">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="e4597-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="e4597-262">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-263">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-263">What's new</span></span>

- <span data-ttu-id="e4597-264">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="e4597-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="e4597-265">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="e4597-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="e4597-266">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="e4597-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="e4597-267">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="e4597-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="e4597-268">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="e4597-268">Fixed registry query</span></span> 
- <span data-ttu-id="e4597-269">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="e4597-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-270">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-270">Known Issues</span></span>
<span data-ttu-id="e4597-271">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-272">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="e4597-273">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="e4597-274">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="e4597-275">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="e4597-276">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="e4597-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="e4597-277">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-278">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-278">What's new</span></span>

- <span data-ttu-id="e4597-279">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="e4597-279">Improved logging for scan events</span></span>
- <span data-ttu-id="e4597-280">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="e4597-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="e4597-281">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="e4597-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="e4597-282">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="e4597-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="e4597-283">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="e4597-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="e4597-284">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="e4597-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-285">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-285">Known Issues</span></span>
<span data-ttu-id="e4597-286">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-287">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="e4597-288">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="e4597-289">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="e4597-290">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="e4597-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="e4597-291">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="e4597-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="e4597-292">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-293">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-293">What's new</span></span>
- <span data-ttu-id="e4597-294">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="e4597-294">WDfilter improvements</span></span>
- <span data-ttu-id="e4597-295">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="e4597-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="e4597-296">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="e4597-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="e4597-297">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="e4597-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="e4597-298">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="e4597-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="e4597-299">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="e4597-299">UEFI scan capability</span></span>
- <span data-ttu-id="e4597-300">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e4597-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="e4597-301">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-301">Known Issues</span></span>
<span data-ttu-id="e4597-302">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-303">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="e4597-304">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="e4597-305">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="e4597-306">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="e4597-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="e4597-307">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="e4597-308">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e4597-309">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-309">What's new</span></span>

- <span data-ttu-id="e4597-310">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e4597-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="e4597-311">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e4597-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="e4597-312">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="e4597-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="e4597-313">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="e4597-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="e4597-314">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="e4597-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4597-315">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-315">Known Issues</span></span>
<span data-ttu-id="e4597-316">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="e4597-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="e4597-317">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="e4597-318">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="e4597-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="e4597-319">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="e4597-320">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="e4597-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="e4597-321">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="e4597-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="e4597-322">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4597-323">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="e4597-324">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-324">Known Issues</span></span>
<span data-ttu-id="e4597-325">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-326">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="e4597-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="e4597-327">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="e4597-328">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="e4597-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="e4597-329">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="e4597-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="e4597-330">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="e4597-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="e4597-331">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e4597-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e4597-332">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-332">What's new</span></span>

- <span data-ttu-id="e4597-333">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="e4597-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="e4597-334">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="e4597-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="e4597-335">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e4597-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="e4597-336">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e4597-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="e4597-337">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="e4597-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4597-338">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-338">Known Issues</span></span>

<span data-ttu-id="e4597-339">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="e4597-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="e4597-340">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="e4597-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="e4597-341">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="e4597-341">This update is:</span></span>
> - <span data-ttu-id="e4597-342">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="e4597-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="e4597-343">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="e4597-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="e4597-344">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="e4597-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="e4597-345">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="e4597-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="e4597-346">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="e4597-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e4597-347">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="e4597-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="e4597-348">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="e4597-349">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="e4597-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="e4597-350">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="e4597-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="e4597-351">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="e4597-352">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="e4597-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="e4597-353">Novedades</span><span class="sxs-lookup"><span data-stu-id="e4597-353">What's new</span></span>

- <span data-ttu-id="e4597-354">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="e4597-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="e4597-355">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="e4597-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="e4597-356">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="e4597-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="e4597-357">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="e4597-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e4597-358">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e4597-358">Known Issues</span></span>
<span data-ttu-id="e4597-359">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.10.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e4597-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="e4597-360">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="e4597-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="e4597-361">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="e4597-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="e4597-362">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e4597-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="e4597-363">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="e4597-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="e4597-364">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="e4597-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="e4597-365">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e4597-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="e4597-366">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="e4597-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="e4597-367">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e4597-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="e4597-368">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="e4597-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="e4597-369">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="e4597-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="e4597-370">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="e4597-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="e4597-371">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="e4597-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="e4597-372">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="e4597-372">Windows 10 release</span></span>  |<span data-ttu-id="e4597-373">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="e4597-373">Platform version</span></span>  |<span data-ttu-id="e4597-374">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="e4597-374">Engine version</span></span> |<span data-ttu-id="e4597-375">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e4597-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4597-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="e4597-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="e4597-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="e4597-377">4.18.1909.6</span></span> |<span data-ttu-id="e4597-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="e4597-378">1.1.17000.2</span></span> | <span data-ttu-id="e4597-379">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="e4597-380">1909  (19H2)</span></span> |<span data-ttu-id="e4597-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4597-381">4.18.1902.5</span></span> |<span data-ttu-id="e4597-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="e4597-382">1.1.16700.3</span></span> | <span data-ttu-id="e4597-383">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="e4597-384">1903  (19H1)</span></span> |<span data-ttu-id="e4597-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e4597-385">4.18.1902.5</span></span> |<span data-ttu-id="e4597-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="e4597-386">1.1.15600.4</span></span> | <span data-ttu-id="e4597-387">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="e4597-388">1809  (RS5)</span></span> |<span data-ttu-id="e4597-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="e4597-389">4.18.1807.18075</span></span> |<span data-ttu-id="e4597-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="e4597-390">1.1.15000.2</span></span> | <span data-ttu-id="e4597-391">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="e4597-392">1803  (RS4)</span></span> |<span data-ttu-id="e4597-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="e4597-393">4.13.17134.1</span></span> |<span data-ttu-id="e4597-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="e4597-394">1.1.14600.4</span></span> | <span data-ttu-id="e4597-395">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="e4597-396">1709  (RS3)</span></span> |<span data-ttu-id="e4597-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="e4597-397">4.12.16299.15</span></span> |<span data-ttu-id="e4597-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="e4597-398">1.1.14104.0</span></span> | <span data-ttu-id="e4597-399">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="e4597-400">1703  (RS2)</span></span> |<span data-ttu-id="e4597-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="e4597-401">4.11.15603.2</span></span> |<span data-ttu-id="e4597-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="e4597-402">1.1.13504.0</span></span> | <span data-ttu-id="e4597-403">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e4597-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="e4597-404">1607 (RS1)</span></span> |<span data-ttu-id="e4597-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="e4597-405">4.10.14393.3683</span></span> |<span data-ttu-id="e4597-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="e4597-406">1.1.12805.0</span></span> | <span data-ttu-id="e4597-407">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e4597-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="e4597-408">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="e4597-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="e4597-409">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="e4597-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="e4597-410">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="e4597-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="e4597-411">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="e4597-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="e4597-412">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="e4597-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="e4597-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="e4597-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="e4597-414">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="e4597-415">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="e4597-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="e4597-416">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e4597-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e4597-417">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-418">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-418">Fixes</span></span>
- <span data-ttu-id="e4597-419">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-420">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-420">Additional information</span></span>
- <span data-ttu-id="e4597-421">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="e4597-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="e4597-423">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="e4597-424">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="e4597-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="e4597-425">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="e4597-426">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-427">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-427">Fixes</span></span>
- <span data-ttu-id="e4597-428">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-429">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-429">Additional information</span></span>
- <span data-ttu-id="e4597-430">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="e4597-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="e4597-432">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="e4597-433">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="e4597-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="e4597-434">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4597-435">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-436">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-436">Fixes</span></span>
- <span data-ttu-id="e4597-437">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-438">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-438">Additional information</span></span>
- <span data-ttu-id="e4597-439">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="e4597-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="e4597-441">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="e4597-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="e4597-442">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4597-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4597-443">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e4597-444">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-445">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-445">Fixes</span></span>
- <span data-ttu-id="e4597-446">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-447">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-447">Additional information</span></span>
- <span data-ttu-id="e4597-448">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="e4597-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="e4597-450">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="e4597-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="e4597-451">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e4597-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e4597-452">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e4597-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="e4597-453">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-454">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-454">Fixes</span></span>
- <span data-ttu-id="e4597-455">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-456">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-456">Additional information</span></span>
- <span data-ttu-id="e4597-457">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="e4597-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="e4597-459">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="e4597-460">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4597-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4597-461">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4597-462">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-463">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-463">Fixes</span></span>
- <span data-ttu-id="e4597-464">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-465">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-465">Additional information</span></span>
- <span data-ttu-id="e4597-466">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="e4597-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="e4597-468">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="e4597-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="e4597-469">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e4597-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e4597-470">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4597-471">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-472">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-472">Fixes</span></span>
- <span data-ttu-id="e4597-473">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-474">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-474">Additional information</span></span>
- <span data-ttu-id="e4597-475">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="e4597-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="e4597-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="e4597-477">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4597-478">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e4597-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="e4597-479">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e4597-480">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-481">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-481">Fixes</span></span>
- <span data-ttu-id="e4597-482">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-483">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-483">Additional information</span></span>
- <span data-ttu-id="e4597-484">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e4597-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="e4597-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="e4597-486">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e4597-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e4597-487">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="e4597-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="e4597-488">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e4597-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="e4597-489">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="e4597-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e4597-490">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e4597-490">Fixes</span></span>
- <span data-ttu-id="e4597-491">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e4597-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e4597-492">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e4597-492">Additional information</span></span>
- <span data-ttu-id="e4597-493">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e4597-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="e4597-494">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e4597-494">Additional resources</span></span>

| <span data-ttu-id="e4597-495">Artículo</span><span class="sxs-lookup"><span data-stu-id="e4597-495">Article</span></span> | <span data-ttu-id="e4597-496">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4597-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="e4597-497">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="e4597-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="e4597-498">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="e4597-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="e4597-499">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="e4597-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="e4597-500">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="e4597-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4597-501">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="e4597-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="e4597-502">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="e4597-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="e4597-503">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="e4597-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="e4597-504">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="e4597-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="e4597-505">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="e4597-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="e4597-506">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="e4597-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e4597-507">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="e4597-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="e4597-508">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="e4597-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="e4597-509">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="e4597-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
