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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822279"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="b2ee5-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="b2ee5-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="b2ee5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2ee5-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b2ee5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="b2ee5-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2ee5-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="b2ee5-108">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="b2ee5-109">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b2ee5-109">Security intelligence updates</span></span>
- <span data-ttu-id="b2ee5-110">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2ee5-111">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="b2ee5-112">Asegúrese de actualizar la protección antivirus incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="b2ee5-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y [otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="b2ee5-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b2ee5-114">Security intelligence updates</span></span>

<span data-ttu-id="b2ee5-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="b2ee5-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="b2ee5-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="b2ee5-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="b2ee5-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="b2ee5-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="b2ee5-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="b2ee5-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="b2ee5-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="b2ee5-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="b2ee5-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="b2ee5-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-124">Product updates</span></span>

<span data-ttu-id="b2ee5-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="b2ee5-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="b2ee5-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="b2ee5-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b2ee5-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="b2ee5-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="b2ee5-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="b2ee5-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="b2ee5-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="b2ee5-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="b2ee5-133">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="b2ee5-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="b2ee5-134">All our updates contain</span></span> 
- <span data-ttu-id="b2ee5-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="b2ee5-135">performance improvements;</span></span>
- <span data-ttu-id="b2ee5-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="b2ee5-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="b2ee5-137">mejoras de integración (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="b2ee5-138">Mayo-2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="b2ee5-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="b2ee5-140">&ensp;Publicado: **4 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="b2ee5-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="b2ee5-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="b2ee5-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-144">What's new</span></span>
- <span data-ttu-id="b2ee5-145">Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="b2ee5-146">Característica [de filtrado de notificaciones de protección](network-protection.md) de red fija</span><span class="sxs-lookup"><span data-stu-id="b2ee5-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-147">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-147">Known Issues</span></span>
<span data-ttu-id="b2ee5-148">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-149">Abril-2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="b2ee5-150">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="b2ee5-151">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b2ee5-152">&ensp;Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="b2ee5-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="b2ee5-154">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-155">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-155">What's new</span></span>
- <span data-ttu-id="b2ee5-156">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="b2ee5-157">Detección de registrador de teclas de modo kernel mejorado</span><span class="sxs-lookup"><span data-stu-id="b2ee5-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="b2ee5-158">Se agregaron nuevos controles para administrar el proceso de implementación gradual de actualizaciones [de Microsoft Defender](updates.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-159">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-159">Known Issues</span></span>
<span data-ttu-id="b2ee5-160">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-161">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="b2ee5-162">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="b2ee5-163">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="b2ee5-164">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="b2ee5-165">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="b2ee5-166">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-167">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-167">What's new</span></span>

- <span data-ttu-id="b2ee5-168">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="b2ee5-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="b2ee5-169">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="b2ee5-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="b2ee5-170">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="b2ee5-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-171">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-171">Known Issues</span></span>
<span data-ttu-id="b2ee5-172">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="b2ee5-173">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="b2ee5-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="b2ee5-174">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="b2ee5-175">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="b2ee5-176">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="b2ee5-177">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="b2ee5-178">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="b2ee5-179">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="b2ee5-180">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="b2ee5-181">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-182">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-182">What's new</span></span>

- <span data-ttu-id="b2ee5-183">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="b2ee5-184">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-185">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-185">Known Issues</span></span>
<span data-ttu-id="b2ee5-186">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-187">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="b2ee5-188">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b2ee5-189">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="b2ee5-190">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="b2ee5-191">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2ee5-192">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-193">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-193">What's new</span></span>

- <span data-ttu-id="b2ee5-194">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="b2ee5-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="b2ee5-195">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="b2ee5-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="b2ee5-196">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="b2ee5-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="b2ee5-197">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="b2ee5-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="b2ee5-198">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="b2ee5-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-199">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-199">Known Issues</span></span>
<span data-ttu-id="b2ee5-200">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-201">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="b2ee5-202">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="b2ee5-203">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="b2ee5-204">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="b2ee5-205">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="b2ee5-206">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-207">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-207">What's new</span></span>

- <span data-ttu-id="b2ee5-208">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="b2ee5-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-209">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-209">Known Issues</span></span>
<span data-ttu-id="b2ee5-210">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-211">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="b2ee5-212">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="b2ee5-213">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="b2ee5-214">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="b2ee5-215">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2ee5-216">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-217">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-217">What's new</span></span>

- <span data-ttu-id="b2ee5-218">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="b2ee5-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="b2ee5-219">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="b2ee5-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="b2ee5-220">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="b2ee5-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="b2ee5-221">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="b2ee5-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-222">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-222">Known Issues</span></span>

<span data-ttu-id="b2ee5-223">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="b2ee5-224">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="b2ee5-225">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="b2ee5-226">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="b2ee5-227">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="b2ee5-228">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="b2ee5-229">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-230">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-230">What's new</span></span>

- <span data-ttu-id="b2ee5-231">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="b2ee5-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="b2ee5-232">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="b2ee5-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="b2ee5-233">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="b2ee5-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="b2ee5-234">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-234">New management interfaces for:</span></span>
   - <span data-ttu-id="b2ee5-235">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="b2ee5-235">UDP Inspection</span></span>
   - <span data-ttu-id="b2ee5-236">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="b2ee5-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="b2ee5-237">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="b2ee5-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="b2ee5-238">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="b2ee5-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="b2ee5-239">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="b2ee5-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-240">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-240">Known Issues</span></span>

<span data-ttu-id="b2ee5-241">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="b2ee5-242">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="b2ee5-243">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="b2ee5-244">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="b2ee5-245">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="b2ee5-246">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="b2ee5-247">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="b2ee5-248">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-248">What's new</span></span>

- <span data-ttu-id="b2ee5-249">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="b2ee5-249">Add more telemetry events</span></span>
- <span data-ttu-id="b2ee5-250">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="b2ee5-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="b2ee5-251">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="b2ee5-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="b2ee5-252">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="b2ee5-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="b2ee5-253">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2ee5-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="b2ee5-254">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="b2ee5-255">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="b2ee5-256">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-256">Known Issues</span></span>
<span data-ttu-id="b2ee5-257">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-258">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="b2ee5-259">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="b2ee5-260">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="b2ee5-261">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="b2ee5-262">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="b2ee5-263">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-264">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-264">What's new</span></span>

- <span data-ttu-id="b2ee5-265">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="b2ee5-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="b2ee5-266">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="b2ee5-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-267">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-267">Known Issues</span></span>
<span data-ttu-id="b2ee5-268">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-269">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="b2ee5-270">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="b2ee5-271">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="b2ee5-272">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="b2ee5-273">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="b2ee5-274">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-275">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-275">What's new</span></span>

- <span data-ttu-id="b2ee5-276">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="b2ee5-277">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="b2ee5-278">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="b2ee5-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="b2ee5-279">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="b2ee5-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="b2ee5-280">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="b2ee5-280">Fixed registry query</span></span> 
- <span data-ttu-id="b2ee5-281">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="b2ee5-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-282">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-282">Known Issues</span></span>
<span data-ttu-id="b2ee5-283">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-284">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="b2ee5-285">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="b2ee5-286">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="b2ee5-287">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="b2ee5-288">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="b2ee5-289">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-290">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-290">What's new</span></span>

- <span data-ttu-id="b2ee5-291">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="b2ee5-291">Improved logging for scan events</span></span>
- <span data-ttu-id="b2ee5-292">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="b2ee5-293">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="b2ee5-294">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="b2ee5-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="b2ee5-295">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="b2ee5-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="b2ee5-296">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="b2ee5-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-297">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-297">Known Issues</span></span>
<span data-ttu-id="b2ee5-298">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-299">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="b2ee5-300">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="b2ee5-301">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="b2ee5-302">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="b2ee5-303">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="b2ee5-304">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-305">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-305">What's new</span></span>
- <span data-ttu-id="b2ee5-306">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="b2ee5-306">WDfilter improvements</span></span>
- <span data-ttu-id="b2ee5-307">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="b2ee5-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="b2ee5-308">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="b2ee5-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="b2ee5-309">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="b2ee5-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="b2ee5-310">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="b2ee5-311">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="b2ee5-311">UEFI scan capability</span></span>
- <span data-ttu-id="b2ee5-312">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="b2ee5-313">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-313">Known Issues</span></span>
<span data-ttu-id="b2ee5-314">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-315">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="b2ee5-316">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="b2ee5-317">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="b2ee5-318">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="b2ee5-319">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="b2ee5-320">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="b2ee5-321">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-321">What's new</span></span>

- <span data-ttu-id="b2ee5-322">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="b2ee5-323">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b2ee5-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="b2ee5-324">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="b2ee5-325">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="b2ee5-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="b2ee5-326">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2ee5-327">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-327">Known Issues</span></span>
<span data-ttu-id="b2ee5-328">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="b2ee5-329">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="b2ee5-330">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="b2ee5-331">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="b2ee5-332">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="b2ee5-333">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="b2ee5-334">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b2ee5-335">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="b2ee5-336">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-336">Known Issues</span></span>
<span data-ttu-id="b2ee5-337">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-338">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="b2ee5-339">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="b2ee5-340">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="b2ee5-341">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="b2ee5-342">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="b2ee5-343">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="b2ee5-344">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-344">What's new</span></span>

- <span data-ttu-id="b2ee5-345">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="b2ee5-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="b2ee5-346">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="b2ee5-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="b2ee5-347">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="b2ee5-348">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="b2ee5-349">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="b2ee5-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2ee5-350">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-350">Known Issues</span></span>

<span data-ttu-id="b2ee5-351">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="b2ee5-352">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="b2ee5-353">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-353">This update is:</span></span>
> - <span data-ttu-id="b2ee5-354">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="b2ee5-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="b2ee5-355">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="b2ee5-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="b2ee5-356">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="b2ee5-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="b2ee5-357">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="b2ee5-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="b2ee5-358">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="b2ee5-359">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="b2ee5-360">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="b2ee5-361">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="b2ee5-362">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="b2ee5-363">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="b2ee5-364">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="b2ee5-365">Novedades</span><span class="sxs-lookup"><span data-stu-id="b2ee5-365">What's new</span></span>

- <span data-ttu-id="b2ee5-366">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="b2ee5-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="b2ee5-367">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="b2ee5-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="b2ee5-368">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="b2ee5-369">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="b2ee5-370">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-370">Known Issues</span></span>
<span data-ttu-id="b2ee5-371">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="b2ee5-372">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="b2ee5-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="b2ee5-373">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="b2ee5-374">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="b2ee5-375">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="b2ee5-376">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="b2ee5-377">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="b2ee5-378">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="b2ee5-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="b2ee5-379">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="b2ee5-380">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="b2ee5-381">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="b2ee5-382">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="b2ee5-383">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="b2ee5-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="b2ee5-384">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="b2ee5-384">Windows 10 release</span></span>  |<span data-ttu-id="b2ee5-385">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="b2ee5-385">Platform version</span></span>  |<span data-ttu-id="b2ee5-386">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="b2ee5-386">Engine version</span></span> |<span data-ttu-id="b2ee5-387">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="b2ee5-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b2ee5-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="b2ee5-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="b2ee5-389">4.18.1909.6</span></span> |<span data-ttu-id="b2ee5-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="b2ee5-390">1.1.17000.2</span></span> | <span data-ttu-id="b2ee5-391">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-392">1909  (19H2)</span></span> |<span data-ttu-id="b2ee5-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b2ee5-393">4.18.1902.5</span></span> |<span data-ttu-id="b2ee5-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="b2ee5-394">1.1.16700.3</span></span> | <span data-ttu-id="b2ee5-395">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-396">1903  (19H1)</span></span> |<span data-ttu-id="b2ee5-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="b2ee5-397">4.18.1902.5</span></span> |<span data-ttu-id="b2ee5-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="b2ee5-398">1.1.15600.4</span></span> | <span data-ttu-id="b2ee5-399">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-400">1809  (RS5)</span></span> |<span data-ttu-id="b2ee5-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="b2ee5-401">4.18.1807.18075</span></span> |<span data-ttu-id="b2ee5-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="b2ee5-402">1.1.15000.2</span></span> | <span data-ttu-id="b2ee5-403">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-404">1803  (RS4)</span></span> |<span data-ttu-id="b2ee5-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="b2ee5-405">4.13.17134.1</span></span> |<span data-ttu-id="b2ee5-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="b2ee5-406">1.1.14600.4</span></span> | <span data-ttu-id="b2ee5-407">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-408">1709  (RS3)</span></span> |<span data-ttu-id="b2ee5-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="b2ee5-409">4.12.16299.15</span></span> |<span data-ttu-id="b2ee5-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="b2ee5-410">1.1.14104.0</span></span> | <span data-ttu-id="b2ee5-411">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-412">1703  (RS2)</span></span> |<span data-ttu-id="b2ee5-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="b2ee5-413">4.11.15603.2</span></span> |<span data-ttu-id="b2ee5-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="b2ee5-414">1.1.13504.0</span></span> | <span data-ttu-id="b2ee5-415">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="b2ee5-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-416">1607 (RS1)</span></span> |<span data-ttu-id="b2ee5-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="b2ee5-417">4.10.14393.3683</span></span> |<span data-ttu-id="b2ee5-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="b2ee5-418">1.1.12805.0</span></span> | <span data-ttu-id="b2ee5-419">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="b2ee5-420">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="b2ee5-421">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="b2ee5-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="b2ee5-422">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="b2ee5-423">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="b2ee5-424">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="b2ee5-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="b2ee5-426">&ensp;Versión del paquete: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="b2ee5-427">&ensp;Versión de la **plataforma: 4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="b2ee5-428">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b2ee5-429">&ensp;Versión de firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-430">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-430">Fixes</span></span>
- <span data-ttu-id="b2ee5-431">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-432">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-432">Additional information</span></span>
- <span data-ttu-id="b2ee5-433">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="b2ee5-435">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="b2ee5-436">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="b2ee5-437">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="b2ee5-438">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-439">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-439">Fixes</span></span>
- <span data-ttu-id="b2ee5-440">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-441">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-441">Additional information</span></span>
- <span data-ttu-id="b2ee5-442">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="b2ee5-444">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="b2ee5-445">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="b2ee5-446">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="b2ee5-447">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-448">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-448">Fixes</span></span>
- <span data-ttu-id="b2ee5-449">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-450">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-450">Additional information</span></span>
- <span data-ttu-id="b2ee5-451">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="b2ee5-453">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="b2ee5-454">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="b2ee5-455">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2ee5-456">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-457">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-457">Fixes</span></span>
- <span data-ttu-id="b2ee5-458">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-459">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-459">Additional information</span></span>
- <span data-ttu-id="b2ee5-460">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="b2ee5-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="b2ee5-462">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="b2ee5-463">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b2ee5-464">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="b2ee5-465">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-466">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-466">Fixes</span></span>
- <span data-ttu-id="b2ee5-467">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-468">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-468">Additional information</span></span>
- <span data-ttu-id="b2ee5-469">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="b2ee5-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="b2ee5-471">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="b2ee5-472">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="b2ee5-473">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="b2ee5-474">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-475">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-475">Fixes</span></span>
- <span data-ttu-id="b2ee5-476">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-477">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-477">Additional information</span></span>
- <span data-ttu-id="b2ee5-478">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="b2ee5-480">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="b2ee5-481">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b2ee5-482">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2ee5-483">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-484">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-484">Fixes</span></span>
- <span data-ttu-id="b2ee5-485">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-486">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-486">Additional information</span></span>
- <span data-ttu-id="b2ee5-487">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="b2ee5-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="b2ee5-489">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="b2ee5-490">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="b2ee5-491">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2ee5-492">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-493">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-493">Fixes</span></span>
- <span data-ttu-id="b2ee5-494">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-495">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-495">Additional information</span></span>
- <span data-ttu-id="b2ee5-496">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="b2ee5-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="b2ee5-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="b2ee5-498">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b2ee5-499">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="b2ee5-500">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="b2ee5-501">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-502">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-502">Fixes</span></span>
- <span data-ttu-id="b2ee5-503">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-504">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-504">Additional information</span></span>
- <span data-ttu-id="b2ee5-505">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="b2ee5-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="b2ee5-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="b2ee5-507">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="b2ee5-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="b2ee5-508">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="b2ee5-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="b2ee5-509">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="b2ee5-510">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="b2ee5-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="b2ee5-511">Correcciones</span><span class="sxs-lookup"><span data-stu-id="b2ee5-511">Fixes</span></span>
- <span data-ttu-id="b2ee5-512">Ninguno</span><span class="sxs-lookup"><span data-stu-id="b2ee5-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="b2ee5-513">Información adicional</span><span class="sxs-lookup"><span data-stu-id="b2ee5-513">Additional information</span></span>
- <span data-ttu-id="b2ee5-514">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="b2ee5-515">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b2ee5-515">Additional resources</span></span>

| <span data-ttu-id="b2ee5-516">Artículo</span><span class="sxs-lookup"><span data-stu-id="b2ee5-516">Article</span></span> | <span data-ttu-id="b2ee5-517">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2ee5-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="b2ee5-518">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b2ee5-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="b2ee5-519">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="b2ee5-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="b2ee5-520">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="b2ee5-521">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="b2ee5-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b2ee5-522">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="b2ee5-523">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="b2ee5-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="b2ee5-524">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="b2ee5-525">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="b2ee5-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="b2ee5-526">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="b2ee5-527">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="b2ee5-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="b2ee5-528">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="b2ee5-529">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="b2ee5-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="b2ee5-530">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="b2ee5-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
