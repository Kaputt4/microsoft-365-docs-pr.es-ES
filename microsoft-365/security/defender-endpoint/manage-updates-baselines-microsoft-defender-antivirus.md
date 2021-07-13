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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/12/2021
ms.openlocfilehash: 0179c620c8ba00c987395a800ed335644048283f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394970"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="e2f5e-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="e2f5e-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="e2f5e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2f5e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e2f5e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="e2f5e-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e2f5e-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="e2f5e-108">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="e2f5e-109">Asegúrese de actualizar la protección antivirus, incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="e2f5e-110">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="e2f5e-111">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2f5e-111">Security intelligence updates</span></span>
- <span data-ttu-id="e2f5e-112">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="e2f5e-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender [y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="e2f5e-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e2f5e-114">Security intelligence updates</span></span>

<span data-ttu-id="e2f5e-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="e2f5e-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="e2f5e-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="e2f5e-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="e2f5e-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="e2f5e-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="e2f5e-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="e2f5e-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="e2f5e-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="e2f5e-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="e2f5e-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="e2f5e-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-124">Product updates</span></span>

<span data-ttu-id="e2f5e-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) conocidas como *actualizaciones de plataforma.*</span><span class="sxs-lookup"><span data-stu-id="e2f5e-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="e2f5e-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="e2f5e-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="e2f5e-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e2f5e-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="e2f5e-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="e2f5e-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="e2f5e-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="e2f5e-132">En este artículo se enumeran los cambios que se incluyen en el canal de versión general.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="e2f5e-133">[Vea la versión de canal general más reciente aquí.](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="e2f5e-134">Para obtener más información sobre el proceso de implementación gradual y para obtener más información acerca de la próxima versión, consulte [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="e2f5e-135">Para obtener más información acerca de las actualizaciones de inteligencia de seguridad, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="e2f5e-136">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="e2f5e-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="e2f5e-137">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="e2f5e-138">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="e2f5e-138">All our updates contain</span></span> 
- <span data-ttu-id="e2f5e-139">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="e2f5e-139">performance improvements;</span></span>
- <span data-ttu-id="e2f5e-140">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="e2f5e-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="e2f5e-141">mejoras de integración (cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="e2f5e-142">Junio-2021 (Plataforma: 4.18.2106.5 | Motor: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="e2f5e-143">&ensp;Versión de actualización de inteligencia de seguridad: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="e2f5e-144">&ensp;Publicado: **28 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="e2f5e-145">&ensp;Plataforma: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="e2f5e-146">&ensp;Motor: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="e2f5e-147">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-148">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-148">What's new</span></span>
- <span data-ttu-id="e2f5e-149">Nuevos controles para administrar el proceso de implementación gradual de las actualizaciones de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="e2f5e-150">Consulte [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="e2f5e-151">Mejora del motor de supervisión de comportamiento</span><span class="sxs-lookup"><span data-stu-id="e2f5e-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="e2f5e-152">Mejoras en la implementación de definiciones de antimalware</span><span class="sxs-lookup"><span data-stu-id="e2f5e-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="e2f5e-153">Inspecciones de eventos de red perimetral extendida</span><span class="sxs-lookup"><span data-stu-id="e2f5e-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-154">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-154">Known Issues</span></span>
<span data-ttu-id="e2f5e-155">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-156">Mayo-2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="e2f5e-157">&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="e2f5e-158">&ensp;Publicado: **3 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="e2f5e-159">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="e2f5e-160">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="e2f5e-161">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-162">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-162">What's new</span></span>
- <span data-ttu-id="e2f5e-163">Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="e2f5e-164">Característica [de filtrado de notificaciones de protección](network-protection.md) de red fija</span><span class="sxs-lookup"><span data-stu-id="e2f5e-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-165">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-165">Known Issues</span></span>
<span data-ttu-id="e2f5e-166">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-167">Abril-2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="e2f5e-168">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="e2f5e-169">&ensp;Publicado: 26 de abril de **2021**  (Motor: 1.1.18100.6 publicado el 5 de mayo de 2021) &ensp; Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="e2f5e-170">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="e2f5e-171">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-172">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-172">What's new</span></span>
- <span data-ttu-id="e2f5e-173">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="e2f5e-174">Detección mejorada del registrador de claves del modo kernel</span><span class="sxs-lookup"><span data-stu-id="e2f5e-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="e2f5e-175">Se agregaron nuevos controles para administrar el proceso de implementación gradual de actualizaciones [de Microsoft Defender](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="e2f5e-176">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-176">Known Issues</span></span>
<span data-ttu-id="e2f5e-177">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="e2f5e-178">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="e2f5e-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="e2f5e-179">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="e2f5e-180">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="e2f5e-181">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="e2f5e-182">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="e2f5e-183">&ensp;Publicado: **2 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="e2f5e-184">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="e2f5e-185">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="e2f5e-186">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-187">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-187">What's new</span></span>

- <span data-ttu-id="e2f5e-188">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="e2f5e-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="e2f5e-189">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="e2f5e-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="e2f5e-190">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="e2f5e-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-191">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-191">Known Issues</span></span>
<span data-ttu-id="e2f5e-192">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-193">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="e2f5e-194">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="e2f5e-195">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="e2f5e-196">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="e2f5e-197">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="e2f5e-198">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-199">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-199">What's new</span></span>

- <span data-ttu-id="e2f5e-200">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="e2f5e-201">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-202">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-202">Known Issues</span></span>
<span data-ttu-id="e2f5e-203">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-204">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="e2f5e-205">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e2f5e-206">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="e2f5e-207">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="e2f5e-208">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="e2f5e-209">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-210">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-210">What's new</span></span>

- <span data-ttu-id="e2f5e-211">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="e2f5e-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="e2f5e-212">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="e2f5e-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="e2f5e-213">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="e2f5e-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="e2f5e-214">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="e2f5e-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="e2f5e-215">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="e2f5e-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-216">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-216">Known Issues</span></span>
<span data-ttu-id="e2f5e-217">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-218">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="e2f5e-219">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="e2f5e-220">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="e2f5e-221">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="e2f5e-222">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="e2f5e-223">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-224">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-224">What's new</span></span>

- <span data-ttu-id="e2f5e-225">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="e2f5e-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-226">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-226">Known Issues</span></span>
<span data-ttu-id="e2f5e-227">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-228">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="e2f5e-229">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="e2f5e-230">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="e2f5e-231">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="e2f5e-232">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="e2f5e-233">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-234">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-234">What's new</span></span>

- <span data-ttu-id="e2f5e-235">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="e2f5e-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="e2f5e-236">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="e2f5e-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="e2f5e-237">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="e2f5e-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="e2f5e-238">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="e2f5e-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-239">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-239">Known Issues</span></span>

<span data-ttu-id="e2f5e-240">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="e2f5e-241">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="e2f5e-242">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="e2f5e-243">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="e2f5e-244">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="e2f5e-245">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="e2f5e-246">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-247">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-247">What's new</span></span>

- <span data-ttu-id="e2f5e-248">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="e2f5e-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="e2f5e-249">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="e2f5e-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="e2f5e-250">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="e2f5e-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="e2f5e-251">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-251">New management interfaces for:</span></span>
   - <span data-ttu-id="e2f5e-252">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="e2f5e-252">UDP Inspection</span></span>
   - <span data-ttu-id="e2f5e-253">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="e2f5e-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="e2f5e-254">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="e2f5e-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="e2f5e-255">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="e2f5e-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="e2f5e-256">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="e2f5e-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-257">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-257">Known Issues</span></span>

<span data-ttu-id="e2f5e-258">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="e2f5e-259">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="e2f5e-260">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="e2f5e-261">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="e2f5e-262">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="e2f5e-263">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="e2f5e-264">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="e2f5e-265">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-265">What's new</span></span>

- <span data-ttu-id="e2f5e-266">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="e2f5e-266">Add more telemetry events</span></span>
- <span data-ttu-id="e2f5e-267">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="e2f5e-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="e2f5e-268">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="e2f5e-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="e2f5e-269">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="e2f5e-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="e2f5e-270">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2f5e-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="e2f5e-271">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="e2f5e-272">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="e2f5e-273">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-273">Known Issues</span></span>
<span data-ttu-id="e2f5e-274">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-275">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="e2f5e-276">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="e2f5e-277">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="e2f5e-278">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="e2f5e-279">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="e2f5e-280">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-281">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-281">What's new</span></span>

- <span data-ttu-id="e2f5e-282">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="e2f5e-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="e2f5e-283">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="e2f5e-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-284">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-284">Known Issues</span></span>
<span data-ttu-id="e2f5e-285">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-286">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="e2f5e-287">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="e2f5e-288">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="e2f5e-289">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="e2f5e-290">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="e2f5e-291">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-292">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-292">What's new</span></span>

- <span data-ttu-id="e2f5e-293">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="e2f5e-294">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="e2f5e-295">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="e2f5e-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="e2f5e-296">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="e2f5e-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="e2f5e-297">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="e2f5e-297">Fixed registry query</span></span> 
- <span data-ttu-id="e2f5e-298">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="e2f5e-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-299">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-299">Known Issues</span></span>
<span data-ttu-id="e2f5e-300">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-301">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="e2f5e-302">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="e2f5e-303">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="e2f5e-304">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="e2f5e-305">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="e2f5e-306">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-307">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-307">What's new</span></span>

- <span data-ttu-id="e2f5e-308">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="e2f5e-308">Improved logging for scan events</span></span>
- <span data-ttu-id="e2f5e-309">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="e2f5e-310">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="e2f5e-311">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="e2f5e-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="e2f5e-312">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="e2f5e-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="e2f5e-313">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="e2f5e-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-314">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-314">Known Issues</span></span>
<span data-ttu-id="e2f5e-315">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-316">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="e2f5e-317">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="e2f5e-318">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="e2f5e-319">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="e2f5e-320">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="e2f5e-321">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-322">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-322">What's new</span></span>
- <span data-ttu-id="e2f5e-323">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="e2f5e-323">WDfilter improvements</span></span>
- <span data-ttu-id="e2f5e-324">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="e2f5e-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="e2f5e-325">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="e2f5e-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="e2f5e-326">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="e2f5e-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="e2f5e-327">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="e2f5e-328">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="e2f5e-328">UEFI scan capability</span></span>
- <span data-ttu-id="e2f5e-329">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="e2f5e-330">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-330">Known Issues</span></span>
<span data-ttu-id="e2f5e-331">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-332">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="e2f5e-333">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="e2f5e-334">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="e2f5e-335">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="e2f5e-336">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="e2f5e-337">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="e2f5e-338">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-338">What's new</span></span>

- <span data-ttu-id="e2f5e-339">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="e2f5e-340">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e2f5e-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="e2f5e-341">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="e2f5e-342">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="e2f5e-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="e2f5e-343">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e2f5e-344">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-344">Known Issues</span></span>
<span data-ttu-id="e2f5e-345">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="e2f5e-346">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="e2f5e-347">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="e2f5e-348">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="e2f5e-349">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="e2f5e-350">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="e2f5e-351">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e2f5e-352">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="e2f5e-353">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-353">Known Issues</span></span>
<span data-ttu-id="e2f5e-354">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-355">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="e2f5e-356">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="e2f5e-357">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="e2f5e-358">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="e2f5e-359">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="e2f5e-360">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="e2f5e-361">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-361">What's new</span></span>

- <span data-ttu-id="e2f5e-362">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="e2f5e-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="e2f5e-363">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="e2f5e-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="e2f5e-364">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="e2f5e-365">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="e2f5e-366">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="e2f5e-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e2f5e-367">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-367">Known Issues</span></span>

<span data-ttu-id="e2f5e-368">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="e2f5e-369">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="e2f5e-370">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-370">This update is:</span></span>
> - <span data-ttu-id="e2f5e-371">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="e2f5e-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="e2f5e-372">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="e2f5e-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="e2f5e-373">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="e2f5e-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="e2f5e-374">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="e2f5e-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="e2f5e-375">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="e2f5e-376">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="e2f5e-377">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="e2f5e-378">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="e2f5e-379">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="e2f5e-380">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="e2f5e-381">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="e2f5e-382">Novedades</span><span class="sxs-lookup"><span data-stu-id="e2f5e-382">What's new</span></span>

- <span data-ttu-id="e2f5e-383">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="e2f5e-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="e2f5e-384">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="e2f5e-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="e2f5e-385">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="e2f5e-386">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="e2f5e-387">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-387">Known Issues</span></span>
<span data-ttu-id="e2f5e-388">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="e2f5e-389">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="e2f5e-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="e2f5e-390">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="e2f5e-391">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="e2f5e-392">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="e2f5e-393">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="e2f5e-394">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="e2f5e-395">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="e2f5e-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="e2f5e-396">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="e2f5e-397">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="e2f5e-398">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="e2f5e-399">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="e2f5e-400">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="e2f5e-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="e2f5e-401">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="e2f5e-401">Windows 10 release</span></span>  |<span data-ttu-id="e2f5e-402">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="e2f5e-402">Platform version</span></span>  |<span data-ttu-id="e2f5e-403">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="e2f5e-403">Engine version</span></span> |<span data-ttu-id="e2f5e-404">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="e2f5e-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e2f5e-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="e2f5e-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="e2f5e-406">4.18.1909.6</span></span> |<span data-ttu-id="e2f5e-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="e2f5e-407">1.1.17000.2</span></span> | <span data-ttu-id="e2f5e-408">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-409">1909  (19H2)</span></span> |<span data-ttu-id="e2f5e-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e2f5e-410">4.18.1902.5</span></span> |<span data-ttu-id="e2f5e-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="e2f5e-411">1.1.16700.3</span></span> | <span data-ttu-id="e2f5e-412">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-413">1903  (19H1)</span></span> |<span data-ttu-id="e2f5e-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="e2f5e-414">4.18.1902.5</span></span> |<span data-ttu-id="e2f5e-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="e2f5e-415">1.1.15600.4</span></span> | <span data-ttu-id="e2f5e-416">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-417">1809  (RS5)</span></span> |<span data-ttu-id="e2f5e-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="e2f5e-418">4.18.1807.18075</span></span> |<span data-ttu-id="e2f5e-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="e2f5e-419">1.1.15000.2</span></span> | <span data-ttu-id="e2f5e-420">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-421">1803  (RS4)</span></span> |<span data-ttu-id="e2f5e-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="e2f5e-422">4.13.17134.1</span></span> |<span data-ttu-id="e2f5e-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="e2f5e-423">1.1.14600.4</span></span> | <span data-ttu-id="e2f5e-424">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-425">1709  (RS3)</span></span> |<span data-ttu-id="e2f5e-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="e2f5e-426">4.12.16299.15</span></span> |<span data-ttu-id="e2f5e-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="e2f5e-427">1.1.14104.0</span></span> | <span data-ttu-id="e2f5e-428">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-429">1703  (RS2)</span></span> |<span data-ttu-id="e2f5e-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="e2f5e-430">4.11.15603.2</span></span> |<span data-ttu-id="e2f5e-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="e2f5e-431">1.1.13504.0</span></span> | <span data-ttu-id="e2f5e-432">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="e2f5e-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-433">1607 (RS1)</span></span> |<span data-ttu-id="e2f5e-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="e2f5e-434">4.10.14393.3683</span></span> |<span data-ttu-id="e2f5e-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="e2f5e-435">1.1.12805.0</span></span> | <span data-ttu-id="e2f5e-436">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="e2f5e-437">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="e2f5e-438">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="e2f5e-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="e2f5e-439">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="e2f5e-440">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="e2f5e-441">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="e2f5e-442">1.1.2107.02</span><span class="sxs-lookup"><span data-stu-id="e2f5e-442">1.1.2107.02</span></span></summary>

<span data-ttu-id="e2f5e-443">&ensp;Versión del paquete: **1.1.2107.02**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-443">&ensp;Package version: **1.1.2107.02**  </span></span>  
<span data-ttu-id="e2f5e-444">&ensp;Versión de la **plataforma: 4.18.2105.5** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-444">&ensp;Platform version: **4.18.2105.5** </span></span>  
<span data-ttu-id="e2f5e-445">&ensp;Versión del motor: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-445">&ensp;Engine version: **1.1.18300.4**</span></span>  
<span data-ttu-id="e2f5e-446">&ensp;Versión de firma: **1.343.658.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-446">&ensp;Signature version: **1.343.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-447">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-447">Fixes</span></span>
- <span data-ttu-id="e2f5e-448">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-449">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-449">Additional information</span></span>
- <span data-ttu-id="e2f5e-450">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-451">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-451">1.1.2106.01</span></span></summary>

<span data-ttu-id="e2f5e-452">&ensp;Versión del paquete: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-452">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="e2f5e-453">&ensp;Versión de la **plataforma: 4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-453">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="e2f5e-454">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e2f5e-455">&ensp;Versión de firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-455">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-456">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-456">Fixes</span></span>
- <span data-ttu-id="e2f5e-457">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-458">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-458">Additional information</span></span>
- <span data-ttu-id="e2f5e-459">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-460">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-460">1.1.2105.01</span></span></summary>

<span data-ttu-id="e2f5e-461">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-461">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="e2f5e-462">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-462">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="e2f5e-463">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-463">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="e2f5e-464">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-464">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-465">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-465">Fixes</span></span>
- <span data-ttu-id="e2f5e-466">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-467">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-467">Additional information</span></span>
- <span data-ttu-id="e2f5e-468">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-469">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-469">1.1.2104.01</span></span></summary>

<span data-ttu-id="e2f5e-470">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-470">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="e2f5e-471">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-471">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="e2f5e-472">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-472">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="e2f5e-473">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-473">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-474">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-474">Fixes</span></span>
- <span data-ttu-id="e2f5e-475">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-476">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-476">Additional information</span></span>
- <span data-ttu-id="e2f5e-477">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-478">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-478">1.1.2103.01</span></span></summary>

<span data-ttu-id="e2f5e-479">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-479">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="e2f5e-480">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-480">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="e2f5e-481">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e2f5e-482">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-482">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-483">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-483">Fixes</span></span>
- <span data-ttu-id="e2f5e-484">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-485">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-485">Additional information</span></span>
- <span data-ttu-id="e2f5e-486">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-487">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="e2f5e-487">1.1.2102.03</span></span></summary>

<span data-ttu-id="e2f5e-488">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-488">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="e2f5e-489">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e2f5e-490">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-490">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="e2f5e-491">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-491">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-492">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-492">Fixes</span></span>
- <span data-ttu-id="e2f5e-493">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-494">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-494">Additional information</span></span>
- <span data-ttu-id="e2f5e-495">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-496">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="e2f5e-496">1.1.2101.02</span></span></summary>

<span data-ttu-id="e2f5e-497">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-497">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="e2f5e-498">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-498">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="e2f5e-499">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-499">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="e2f5e-500">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-500">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-501">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-501">Fixes</span></span>
- <span data-ttu-id="e2f5e-502">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-503">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-503">Additional information</span></span>
- <span data-ttu-id="e2f5e-504">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-505">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-505">1.1.2012.01</span></span></summary>

<span data-ttu-id="e2f5e-506">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-506">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="e2f5e-507">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e2f5e-508">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e2f5e-509">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-509">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-510">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-510">Fixes</span></span>
- <span data-ttu-id="e2f5e-511">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-512">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-512">Additional information</span></span>
- <span data-ttu-id="e2f5e-513">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-513">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-514">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="e2f5e-514">1.1.2011.02</span></span></summary>

<span data-ttu-id="e2f5e-515">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-515">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="e2f5e-516">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-516">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="e2f5e-517">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e2f5e-518">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-518">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-519">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-519">Fixes</span></span>
- <span data-ttu-id="e2f5e-520">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-521">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-521">Additional information</span></span>
- <span data-ttu-id="e2f5e-522">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="e2f5e-522">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-523">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="e2f5e-523">1.1.2011.01</span></span></summary>

<span data-ttu-id="e2f5e-524">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e2f5e-525">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-525">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="e2f5e-526">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-526">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="e2f5e-527">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-527">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-528">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-528">Fixes</span></span>
- <span data-ttu-id="e2f5e-529">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-530">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-530">Additional information</span></span>
- <span data-ttu-id="e2f5e-531">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-531">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="e2f5e-532">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="e2f5e-532">1.1.2009.10</span></span></summary>

<span data-ttu-id="e2f5e-533">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="e2f5e-533">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="e2f5e-534">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="e2f5e-534">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="e2f5e-535">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-535">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="e2f5e-536">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="e2f5e-536">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="e2f5e-537">Correcciones</span><span class="sxs-lookup"><span data-stu-id="e2f5e-537">Fixes</span></span>
- <span data-ttu-id="e2f5e-538">Ninguno</span><span class="sxs-lookup"><span data-stu-id="e2f5e-538">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2f5e-539">Información adicional</span><span class="sxs-lookup"><span data-stu-id="e2f5e-539">Additional information</span></span>
- <span data-ttu-id="e2f5e-540">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-540">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="e2f5e-541">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e2f5e-541">Additional resources</span></span>

| <span data-ttu-id="e2f5e-542">Artículo</span><span class="sxs-lookup"><span data-stu-id="e2f5e-542">Article</span></span> | <span data-ttu-id="e2f5e-543">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2f5e-543">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="e2f5e-544">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="e2f5e-544">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="e2f5e-545">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="e2f5e-545">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="e2f5e-546">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-546">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="e2f5e-547">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="e2f5e-547">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e2f5e-548">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-548">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="e2f5e-549">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="e2f5e-549">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="e2f5e-550">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-550">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="e2f5e-551">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="e2f5e-551">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="e2f5e-552">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-552">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="e2f5e-553">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="e2f5e-553">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="e2f5e-554">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-554">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="e2f5e-555">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="e2f5e-555">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="e2f5e-556">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="e2f5e-556">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
