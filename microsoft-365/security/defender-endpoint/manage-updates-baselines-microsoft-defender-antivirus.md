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
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="cb677-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="cb677-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="cb677-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cb677-105">**Applies to:**</span></span>

- [<span data-ttu-id="cb677-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cb677-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="cb677-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb677-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="cb677-108">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="cb677-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="cb677-109">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="cb677-109">Security intelligence updates</span></span>
- <span data-ttu-id="cb677-110">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="cb677-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb677-111">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="cb677-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="cb677-112">Asegúrese de actualizar la protección antivirus incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="cb677-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="cb677-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y [otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="cb677-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="cb677-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="cb677-114">Security intelligence updates</span></span>

<span data-ttu-id="cb677-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="cb677-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="cb677-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb677-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="cb677-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="cb677-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="cb677-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="cb677-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="cb677-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="cb677-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="cb677-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="cb677-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="cb677-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="cb677-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="cb677-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="cb677-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="cb677-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="cb677-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="cb677-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="cb677-124">Product updates</span></span>

<span data-ttu-id="cb677-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="cb677-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="cb677-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="cb677-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="cb677-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="cb677-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="cb677-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cb677-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="cb677-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="cb677-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="cb677-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="cb677-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="cb677-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="cb677-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="cb677-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="cb677-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="cb677-133">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="cb677-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="cb677-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="cb677-134">All our updates contain</span></span> 
- <span data-ttu-id="cb677-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="cb677-135">performance improvements;</span></span>
- <span data-ttu-id="cb677-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="cb677-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="cb677-137">mejoras de integración (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="cb677-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="cb677-138">Mayo-2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="cb677-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="cb677-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="cb677-140">&ensp;Publicado: **4 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="cb677-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="cb677-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="cb677-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="cb677-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="cb677-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-144">What's new</span></span>
- <span data-ttu-id="cb677-145">Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="cb677-146">Característica [de filtrado de notificaciones de protección](network-protection.md) de red fija</span><span class="sxs-lookup"><span data-stu-id="cb677-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-147">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-147">Known Issues</span></span>
<span data-ttu-id="cb677-148">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-149">Abril-2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="cb677-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="cb677-150">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="cb677-151">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="cb677-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="cb677-152">&ensp;Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="cb677-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="cb677-153">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="cb677-154">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="cb677-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-155">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-155">What's new</span></span>
- <span data-ttu-id="cb677-156">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="cb677-157">Detección de registrador de teclas de modo kernel mejorado</span><span class="sxs-lookup"><span data-stu-id="cb677-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="cb677-158">Se agregaron nuevos controles para administrar el proceso de implementación gradual de actualizaciones [de Microsoft Defender](updates.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-159">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-159">Known Issues</span></span>
<span data-ttu-id="cb677-160">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-161">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="cb677-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="cb677-162">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="cb677-163">&ensp;Publicado: **1 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="cb677-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="cb677-164">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="cb677-165">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="cb677-166">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="cb677-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-167">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-167">What's new</span></span>

- <span data-ttu-id="cb677-168">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="cb677-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="cb677-169">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="cb677-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="cb677-170">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="cb677-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-171">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-171">Known Issues</span></span>
<span data-ttu-id="cb677-172">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="cb677-173">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="cb677-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="cb677-174">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="cb677-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="cb677-175">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="cb677-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="cb677-176">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="cb677-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="cb677-177">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="cb677-178">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="cb677-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="cb677-179">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="cb677-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="cb677-180">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="cb677-181">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-182">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-182">What's new</span></span>

- <span data-ttu-id="cb677-183">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="cb677-184">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="cb677-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-185">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-185">Known Issues</span></span>
<span data-ttu-id="cb677-186">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-187">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="cb677-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="cb677-188">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="cb677-189">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="cb677-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="cb677-190">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="cb677-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="cb677-191">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="cb677-192">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-193">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-193">What's new</span></span>

- <span data-ttu-id="cb677-194">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="cb677-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="cb677-195">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="cb677-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="cb677-196">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="cb677-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="cb677-197">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="cb677-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="cb677-198">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="cb677-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-199">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-199">Known Issues</span></span>
<span data-ttu-id="cb677-200">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-201">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="cb677-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="cb677-202">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="cb677-203">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="cb677-204">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="cb677-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="cb677-205">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="cb677-206">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-207">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-207">What's new</span></span>

- <span data-ttu-id="cb677-208">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="cb677-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-209">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-209">Known Issues</span></span>
<span data-ttu-id="cb677-210">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-211">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="cb677-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="cb677-212">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="cb677-213">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="cb677-214">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="cb677-215">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="cb677-216">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-217">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-217">What's new</span></span>

- <span data-ttu-id="cb677-218">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="cb677-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="cb677-219">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="cb677-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="cb677-220">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="cb677-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="cb677-221">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="cb677-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-222">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-222">Known Issues</span></span>

<span data-ttu-id="cb677-223">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="cb677-224">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="cb677-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="cb677-225">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="cb677-226">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="cb677-227">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="cb677-228">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="cb677-229">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-230">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-230">What's new</span></span>

- <span data-ttu-id="cb677-231">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="cb677-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="cb677-232">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="cb677-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="cb677-233">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="cb677-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="cb677-234">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="cb677-234">New management interfaces for:</span></span>
   - <span data-ttu-id="cb677-235">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="cb677-235">UDP Inspection</span></span>
   - <span data-ttu-id="cb677-236">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="cb677-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="cb677-237">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="cb677-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="cb677-238">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="cb677-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="cb677-239">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="cb677-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-240">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-240">Known Issues</span></span>

<span data-ttu-id="cb677-241">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="cb677-242">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="cb677-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="cb677-243">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="cb677-244">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="cb677-245">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="cb677-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="cb677-246">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="cb677-247">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="cb677-248">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-248">What's new</span></span>

- <span data-ttu-id="cb677-249">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="cb677-249">Add more telemetry events</span></span>
- <span data-ttu-id="cb677-250">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="cb677-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="cb677-251">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="cb677-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="cb677-252">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="cb677-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="cb677-253">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb677-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="cb677-254">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="cb677-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="cb677-255">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="cb677-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="cb677-256">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-256">Known Issues</span></span>
<span data-ttu-id="cb677-257">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-258">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="cb677-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="cb677-259">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="cb677-260">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="cb677-261">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="cb677-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="cb677-262">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="cb677-263">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-264">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-264">What's new</span></span>

- <span data-ttu-id="cb677-265">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="cb677-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="cb677-266">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="cb677-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-267">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-267">Known Issues</span></span>
<span data-ttu-id="cb677-268">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-269">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="cb677-270">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="cb677-271">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="cb677-272">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="cb677-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="cb677-273">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="cb677-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="cb677-274">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-275">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-275">What's new</span></span>

- <span data-ttu-id="cb677-276">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="cb677-277">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="cb677-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="cb677-278">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="cb677-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="cb677-279">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="cb677-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="cb677-280">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="cb677-280">Fixed registry query</span></span> 
- <span data-ttu-id="cb677-281">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="cb677-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-282">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-282">Known Issues</span></span>
<span data-ttu-id="cb677-283">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-284">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="cb677-285">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="cb677-286">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="cb677-287">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="cb677-288">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="cb677-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="cb677-289">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-290">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-290">What's new</span></span>

- <span data-ttu-id="cb677-291">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="cb677-291">Improved logging for scan events</span></span>
- <span data-ttu-id="cb677-292">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="cb677-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="cb677-293">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="cb677-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="cb677-294">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="cb677-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="cb677-295">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="cb677-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="cb677-296">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="cb677-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-297">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-297">Known Issues</span></span>
<span data-ttu-id="cb677-298">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-299">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="cb677-300">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="cb677-301">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="cb677-302">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="cb677-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="cb677-303">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="cb677-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="cb677-304">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-305">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-305">What's new</span></span>
- <span data-ttu-id="cb677-306">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="cb677-306">WDfilter improvements</span></span>
- <span data-ttu-id="cb677-307">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="cb677-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="cb677-308">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="cb677-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="cb677-309">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="cb677-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="cb677-310">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="cb677-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="cb677-311">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="cb677-311">UEFI scan capability</span></span>
- <span data-ttu-id="cb677-312">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="cb677-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="cb677-313">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-313">Known Issues</span></span>
<span data-ttu-id="cb677-314">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-315">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="cb677-316">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="cb677-317">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="cb677-318">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="cb677-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="cb677-319">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="cb677-320">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="cb677-321">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-321">What's new</span></span>

- <span data-ttu-id="cb677-322">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="cb677-323">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="cb677-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="cb677-324">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="cb677-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="cb677-325">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="cb677-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="cb677-326">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="cb677-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="cb677-327">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-327">Known Issues</span></span>
<span data-ttu-id="cb677-328">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="cb677-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="cb677-329">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="cb677-330">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="cb677-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="cb677-331">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="cb677-332">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="cb677-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="cb677-333">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="cb677-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="cb677-334">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="cb677-335">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="cb677-336">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-336">Known Issues</span></span>
<span data-ttu-id="cb677-337">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-338">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="cb677-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="cb677-339">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="cb677-340">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="cb677-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="cb677-341">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="cb677-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="cb677-342">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="cb677-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="cb677-343">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="cb677-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="cb677-344">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-344">What's new</span></span>

- <span data-ttu-id="cb677-345">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="cb677-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="cb677-346">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="cb677-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="cb677-347">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="cb677-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="cb677-348">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="cb677-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="cb677-349">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="cb677-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="cb677-350">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-350">Known Issues</span></span>

<span data-ttu-id="cb677-351">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="cb677-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="cb677-352">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="cb677-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="cb677-353">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="cb677-353">This update is:</span></span>
> - <span data-ttu-id="cb677-354">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="cb677-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="cb677-355">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="cb677-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="cb677-356">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="cb677-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="cb677-357">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="cb677-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="cb677-358">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="cb677-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="cb677-359">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="cb677-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="cb677-360">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="cb677-361">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="cb677-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="cb677-362">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="cb677-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="cb677-363">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="cb677-364">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="cb677-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="cb677-365">Novedades</span><span class="sxs-lookup"><span data-stu-id="cb677-365">What's new</span></span>

- <span data-ttu-id="cb677-366">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="cb677-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="cb677-367">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="cb677-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="cb677-368">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="cb677-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="cb677-369">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="cb677-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="cb677-370">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="cb677-370">Known Issues</span></span>
<span data-ttu-id="cb677-371">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="cb677-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="cb677-372">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="cb677-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="cb677-373">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="cb677-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="cb677-374">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="cb677-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="cb677-375">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="cb677-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="cb677-376">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="cb677-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="cb677-377">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="cb677-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="cb677-378">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="cb677-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="cb677-379">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="cb677-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="cb677-380">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="cb677-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="cb677-381">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="cb677-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="cb677-382">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="cb677-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="cb677-383">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="cb677-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="cb677-384">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="cb677-384">Windows 10 release</span></span>  |<span data-ttu-id="cb677-385">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="cb677-385">Platform version</span></span>  |<span data-ttu-id="cb677-386">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="cb677-386">Engine version</span></span> |<span data-ttu-id="cb677-387">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="cb677-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="cb677-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="cb677-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="cb677-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="cb677-389">4.18.1909.6</span></span> |<span data-ttu-id="cb677-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="cb677-390">1.1.17000.2</span></span> | <span data-ttu-id="cb677-391">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="cb677-392">1909  (19H2)</span></span> |<span data-ttu-id="cb677-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="cb677-393">4.18.1902.5</span></span> |<span data-ttu-id="cb677-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="cb677-394">1.1.16700.3</span></span> | <span data-ttu-id="cb677-395">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="cb677-396">1903  (19H1)</span></span> |<span data-ttu-id="cb677-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="cb677-397">4.18.1902.5</span></span> |<span data-ttu-id="cb677-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="cb677-398">1.1.15600.4</span></span> | <span data-ttu-id="cb677-399">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="cb677-400">1809  (RS5)</span></span> |<span data-ttu-id="cb677-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="cb677-401">4.18.1807.18075</span></span> |<span data-ttu-id="cb677-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="cb677-402">1.1.15000.2</span></span> | <span data-ttu-id="cb677-403">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="cb677-404">1803  (RS4)</span></span> |<span data-ttu-id="cb677-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="cb677-405">4.13.17134.1</span></span> |<span data-ttu-id="cb677-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="cb677-406">1.1.14600.4</span></span> | <span data-ttu-id="cb677-407">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="cb677-408">1709  (RS3)</span></span> |<span data-ttu-id="cb677-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="cb677-409">4.12.16299.15</span></span> |<span data-ttu-id="cb677-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="cb677-410">1.1.14104.0</span></span> | <span data-ttu-id="cb677-411">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="cb677-412">1703  (RS2)</span></span> |<span data-ttu-id="cb677-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="cb677-413">4.11.15603.2</span></span> |<span data-ttu-id="cb677-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="cb677-414">1.1.13504.0</span></span> | <span data-ttu-id="cb677-415">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="cb677-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="cb677-416">1607 (RS1)</span></span> |<span data-ttu-id="cb677-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="cb677-417">4.10.14393.3683</span></span> |<span data-ttu-id="cb677-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="cb677-418">1.1.12805.0</span></span> | <span data-ttu-id="cb677-419">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="cb677-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="cb677-420">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="cb677-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="cb677-421">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="cb677-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="cb677-422">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="cb677-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="cb677-423">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="cb677-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="cb677-424">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="cb677-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="cb677-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="cb677-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="cb677-426">&ensp;Versión del paquete: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="cb677-427">&ensp;Versión de la **plataforma: 4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="cb677-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="cb677-428">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="cb677-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="cb677-429">&ensp;Versión de firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-430">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-430">Fixes</span></span>
- <span data-ttu-id="cb677-431">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-432">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-432">Additional information</span></span>
- <span data-ttu-id="cb677-433">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="cb677-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="cb677-435">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="cb677-436">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="cb677-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="cb677-437">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="cb677-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="cb677-438">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-439">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-439">Fixes</span></span>
- <span data-ttu-id="cb677-440">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-441">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-441">Additional information</span></span>
- <span data-ttu-id="cb677-442">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="cb677-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="cb677-444">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="cb677-445">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="cb677-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="cb677-446">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="cb677-447">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-448">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-448">Fixes</span></span>
- <span data-ttu-id="cb677-449">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-450">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-450">Additional information</span></span>
- <span data-ttu-id="cb677-451">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="cb677-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="cb677-453">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="cb677-454">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="cb677-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="cb677-455">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="cb677-456">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-457">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-457">Fixes</span></span>
- <span data-ttu-id="cb677-458">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-459">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-459">Additional information</span></span>
- <span data-ttu-id="cb677-460">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="cb677-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="cb677-462">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="cb677-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="cb677-463">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="cb677-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="cb677-464">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="cb677-465">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-466">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-466">Fixes</span></span>
- <span data-ttu-id="cb677-467">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-468">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-468">Additional information</span></span>
- <span data-ttu-id="cb677-469">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="cb677-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="cb677-471">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="cb677-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="cb677-472">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="cb677-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="cb677-473">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="cb677-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="cb677-474">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-475">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-475">Fixes</span></span>
- <span data-ttu-id="cb677-476">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-477">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-477">Additional information</span></span>
- <span data-ttu-id="cb677-478">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="cb677-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="cb677-480">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="cb677-481">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="cb677-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="cb677-482">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="cb677-483">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-484">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-484">Fixes</span></span>
- <span data-ttu-id="cb677-485">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-486">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-486">Additional information</span></span>
- <span data-ttu-id="cb677-487">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="cb677-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="cb677-489">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="cb677-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="cb677-490">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="cb677-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="cb677-491">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="cb677-492">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-493">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-493">Fixes</span></span>
- <span data-ttu-id="cb677-494">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-495">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-495">Additional information</span></span>
- <span data-ttu-id="cb677-496">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="cb677-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="cb677-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="cb677-498">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="cb677-499">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="cb677-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="cb677-500">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="cb677-501">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-502">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-502">Fixes</span></span>
- <span data-ttu-id="cb677-503">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-504">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-504">Additional information</span></span>
- <span data-ttu-id="cb677-505">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="cb677-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="cb677-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="cb677-507">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="cb677-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="cb677-508">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="cb677-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="cb677-509">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="cb677-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="cb677-510">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="cb677-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="cb677-511">Correcciones</span><span class="sxs-lookup"><span data-stu-id="cb677-511">Fixes</span></span>
- <span data-ttu-id="cb677-512">Ninguno</span><span class="sxs-lookup"><span data-stu-id="cb677-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="cb677-513">Información adicional</span><span class="sxs-lookup"><span data-stu-id="cb677-513">Additional information</span></span>
- <span data-ttu-id="cb677-514">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cb677-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="cb677-515">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cb677-515">Additional resources</span></span>

| <span data-ttu-id="cb677-516">Artículo</span><span class="sxs-lookup"><span data-stu-id="cb677-516">Article</span></span> | <span data-ttu-id="cb677-517">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb677-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="cb677-518">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="cb677-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="cb677-519">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="cb677-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="cb677-520">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="cb677-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="cb677-521">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="cb677-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="cb677-522">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="cb677-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="cb677-523">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="cb677-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="cb677-524">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="cb677-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="cb677-525">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="cb677-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="cb677-526">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="cb677-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="cb677-527">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="cb677-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="cb677-528">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="cb677-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="cb677-529">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="cb677-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="cb677-530">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="cb677-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
