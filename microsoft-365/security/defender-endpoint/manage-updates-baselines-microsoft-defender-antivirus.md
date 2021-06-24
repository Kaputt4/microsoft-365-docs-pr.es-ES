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
ms.date: 06/23/2021
ms.openlocfilehash: 88be32a2c1e9204629682ec678f80ab6daf701f4
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105337"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="26da0-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="26da0-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="26da0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="26da0-105">**Applies to:**</span></span>

- [<span data-ttu-id="26da0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="26da0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="26da0-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="26da0-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="26da0-108">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="26da0-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="26da0-109">Asegúrese de actualizar la protección antivirus, incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="26da0-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="26da0-110">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="26da0-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="26da0-111">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="26da0-111">Security intelligence updates</span></span>
- <span data-ttu-id="26da0-112">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="26da0-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="26da0-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender [y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="26da0-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="26da0-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="26da0-114">Security intelligence updates</span></span>

<span data-ttu-id="26da0-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="26da0-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="26da0-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="26da0-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="26da0-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="26da0-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="26da0-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="26da0-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="26da0-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="26da0-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="26da0-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="26da0-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="26da0-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="26da0-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="26da0-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="26da0-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="26da0-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="26da0-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="26da0-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="26da0-124">Product updates</span></span>

<span data-ttu-id="26da0-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="26da0-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="26da0-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="26da0-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="26da0-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="26da0-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="26da0-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="26da0-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="26da0-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="26da0-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="26da0-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="26da0-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="26da0-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="26da0-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="26da0-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="26da0-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="26da0-133">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="26da0-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="26da0-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="26da0-134">All our updates contain</span></span> 
- <span data-ttu-id="26da0-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="26da0-135">performance improvements;</span></span>
- <span data-ttu-id="26da0-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="26da0-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="26da0-137">mejoras de integración (cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="26da0-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="26da0-138">Mayo-2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="26da0-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="26da0-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="26da0-140">&ensp;Publicado: **3 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="26da0-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="26da0-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="26da0-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="26da0-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="26da0-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-144">What's new</span></span>
- <span data-ttu-id="26da0-145">Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="26da0-146">Característica [de filtrado de notificaciones de protección](network-protection.md) de red fija</span><span class="sxs-lookup"><span data-stu-id="26da0-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-147">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-147">Known Issues</span></span>
<span data-ttu-id="26da0-148">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-149">Abril-2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="26da0-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="26da0-150">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="26da0-151">&ensp;Publicado: 26 de abril de **2021**  (Motor: 1.1.18100.6 publicado el 5 de mayo de 2021) &ensp; Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="26da0-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="26da0-152">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="26da0-153">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="26da0-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-154">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-154">What's new</span></span>
- <span data-ttu-id="26da0-155">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="26da0-156">Detección de registrador de teclas de modo kernel mejorado</span><span class="sxs-lookup"><span data-stu-id="26da0-156">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="26da0-157">Se agregaron nuevos controles para administrar el proceso de implementación gradual de actualizaciones [de Microsoft Defender](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-157">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="26da0-158">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-158">Known Issues</span></span>
<span data-ttu-id="26da0-159">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-160">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="26da0-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="26da0-161">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="26da0-162">&ensp;Publicado: **2 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="26da0-162">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="26da0-163">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="26da0-164">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="26da0-165">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="26da0-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-166">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-166">What's new</span></span>

- <span data-ttu-id="26da0-167">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="26da0-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="26da0-168">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="26da0-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="26da0-169">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="26da0-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-170">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-170">Known Issues</span></span>
<span data-ttu-id="26da0-171">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="26da0-172">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="26da0-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="26da0-173">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="26da0-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="26da0-174">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="26da0-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="26da0-175">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="26da0-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="26da0-176">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="26da0-177">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="26da0-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="26da0-178">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="26da0-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="26da0-179">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="26da0-180">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-181">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-181">What's new</span></span>

- <span data-ttu-id="26da0-182">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="26da0-183">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="26da0-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-184">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-184">Known Issues</span></span>
<span data-ttu-id="26da0-185">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-186">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="26da0-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="26da0-187">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="26da0-188">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="26da0-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="26da0-189">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="26da0-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="26da0-190">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="26da0-191">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-192">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-192">What's new</span></span>

- <span data-ttu-id="26da0-193">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="26da0-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="26da0-194">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="26da0-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="26da0-195">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="26da0-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="26da0-196">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="26da0-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="26da0-197">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="26da0-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-198">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-198">Known Issues</span></span>
<span data-ttu-id="26da0-199">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-200">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="26da0-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="26da0-201">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="26da0-202">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="26da0-203">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="26da0-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="26da0-204">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="26da0-205">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-206">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-206">What's new</span></span>

- <span data-ttu-id="26da0-207">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="26da0-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-208">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-208">Known Issues</span></span>
<span data-ttu-id="26da0-209">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-210">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="26da0-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="26da0-211">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="26da0-212">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="26da0-213">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="26da0-214">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="26da0-215">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-216">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-216">What's new</span></span>

- <span data-ttu-id="26da0-217">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="26da0-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="26da0-218">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="26da0-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="26da0-219">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="26da0-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="26da0-220">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="26da0-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-221">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-221">Known Issues</span></span>

<span data-ttu-id="26da0-222">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="26da0-223">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="26da0-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="26da0-224">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="26da0-225">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="26da0-226">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="26da0-227">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="26da0-228">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-229">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-229">What's new</span></span>

- <span data-ttu-id="26da0-230">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="26da0-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="26da0-231">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="26da0-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="26da0-232">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="26da0-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="26da0-233">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="26da0-233">New management interfaces for:</span></span>
   - <span data-ttu-id="26da0-234">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="26da0-234">UDP Inspection</span></span>
   - <span data-ttu-id="26da0-235">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="26da0-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="26da0-236">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="26da0-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="26da0-237">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="26da0-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="26da0-238">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="26da0-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-239">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-239">Known Issues</span></span>

<span data-ttu-id="26da0-240">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="26da0-241">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="26da0-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="26da0-242">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="26da0-243">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="26da0-244">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="26da0-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="26da0-245">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="26da0-246">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="26da0-247">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-247">What's new</span></span>

- <span data-ttu-id="26da0-248">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="26da0-248">Add more telemetry events</span></span>
- <span data-ttu-id="26da0-249">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="26da0-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="26da0-250">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="26da0-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="26da0-251">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="26da0-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="26da0-252">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="26da0-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="26da0-253">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="26da0-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="26da0-254">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="26da0-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="26da0-255">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-255">Known Issues</span></span>
<span data-ttu-id="26da0-256">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-257">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="26da0-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="26da0-258">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="26da0-259">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="26da0-260">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="26da0-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="26da0-261">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="26da0-262">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-263">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-263">What's new</span></span>

- <span data-ttu-id="26da0-264">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="26da0-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="26da0-265">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="26da0-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-266">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-266">Known Issues</span></span>
<span data-ttu-id="26da0-267">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-268">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="26da0-269">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="26da0-270">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="26da0-271">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="26da0-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="26da0-272">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="26da0-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="26da0-273">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-274">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-274">What's new</span></span>

- <span data-ttu-id="26da0-275">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="26da0-276">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="26da0-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="26da0-277">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="26da0-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="26da0-278">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="26da0-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="26da0-279">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="26da0-279">Fixed registry query</span></span> 
- <span data-ttu-id="26da0-280">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="26da0-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-281">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-281">Known Issues</span></span>
<span data-ttu-id="26da0-282">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-283">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="26da0-284">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="26da0-285">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="26da0-286">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="26da0-287">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="26da0-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="26da0-288">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-289">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-289">What's new</span></span>

- <span data-ttu-id="26da0-290">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="26da0-290">Improved logging for scan events</span></span>
- <span data-ttu-id="26da0-291">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="26da0-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="26da0-292">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="26da0-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="26da0-293">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="26da0-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="26da0-294">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="26da0-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="26da0-295">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="26da0-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-296">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-296">Known Issues</span></span>
<span data-ttu-id="26da0-297">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-298">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="26da0-299">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="26da0-300">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="26da0-301">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="26da0-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="26da0-302">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="26da0-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="26da0-303">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-304">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-304">What's new</span></span>
- <span data-ttu-id="26da0-305">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="26da0-305">WDfilter improvements</span></span>
- <span data-ttu-id="26da0-306">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="26da0-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="26da0-307">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="26da0-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="26da0-308">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="26da0-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="26da0-309">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="26da0-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="26da0-310">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="26da0-310">UEFI scan capability</span></span>
- <span data-ttu-id="26da0-311">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="26da0-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="26da0-312">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-312">Known Issues</span></span>
<span data-ttu-id="26da0-313">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-314">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="26da0-315">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="26da0-316">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="26da0-317">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="26da0-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="26da0-318">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="26da0-319">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="26da0-320">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-320">What's new</span></span>

- <span data-ttu-id="26da0-321">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="26da0-322">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="26da0-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="26da0-323">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="26da0-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="26da0-324">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="26da0-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="26da0-325">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="26da0-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="26da0-326">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-326">Known Issues</span></span>
<span data-ttu-id="26da0-327">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="26da0-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="26da0-328">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="26da0-329">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="26da0-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="26da0-330">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="26da0-331">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="26da0-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="26da0-332">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="26da0-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="26da0-333">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="26da0-334">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="26da0-335">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-335">Known Issues</span></span>
<span data-ttu-id="26da0-336">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-337">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="26da0-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="26da0-338">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="26da0-339">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="26da0-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="26da0-340">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="26da0-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="26da0-341">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="26da0-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="26da0-342">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="26da0-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="26da0-343">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-343">What's new</span></span>

- <span data-ttu-id="26da0-344">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="26da0-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="26da0-345">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="26da0-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="26da0-346">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="26da0-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="26da0-347">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="26da0-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="26da0-348">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="26da0-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="26da0-349">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-349">Known Issues</span></span>

<span data-ttu-id="26da0-350">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="26da0-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="26da0-351">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="26da0-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="26da0-352">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="26da0-352">This update is:</span></span>
> - <span data-ttu-id="26da0-353">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="26da0-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="26da0-354">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="26da0-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="26da0-355">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="26da0-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="26da0-356">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="26da0-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="26da0-357">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="26da0-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="26da0-358">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="26da0-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="26da0-359">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="26da0-360">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="26da0-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="26da0-361">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="26da0-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="26da0-362">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="26da0-363">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="26da0-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="26da0-364">Novedades</span><span class="sxs-lookup"><span data-stu-id="26da0-364">What's new</span></span>

- <span data-ttu-id="26da0-365">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="26da0-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="26da0-366">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="26da0-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="26da0-367">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="26da0-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="26da0-368">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="26da0-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="26da0-369">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="26da0-369">Known Issues</span></span>
<span data-ttu-id="26da0-370">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="26da0-370">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="26da0-371">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="26da0-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="26da0-372">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="26da0-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="26da0-373">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="26da0-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="26da0-374">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="26da0-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="26da0-375">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="26da0-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="26da0-376">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="26da0-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="26da0-377">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="26da0-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="26da0-378">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="26da0-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="26da0-379">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="26da0-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="26da0-380">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="26da0-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="26da0-381">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="26da0-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="26da0-382">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="26da0-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="26da0-383">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="26da0-383">Windows 10 release</span></span>  |<span data-ttu-id="26da0-384">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="26da0-384">Platform version</span></span>  |<span data-ttu-id="26da0-385">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="26da0-385">Engine version</span></span> |<span data-ttu-id="26da0-386">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="26da0-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="26da0-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="26da0-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="26da0-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="26da0-388">4.18.1909.6</span></span> |<span data-ttu-id="26da0-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="26da0-389">1.1.17000.2</span></span> | <span data-ttu-id="26da0-390">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="26da0-391">1909  (19H2)</span></span> |<span data-ttu-id="26da0-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="26da0-392">4.18.1902.5</span></span> |<span data-ttu-id="26da0-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="26da0-393">1.1.16700.3</span></span> | <span data-ttu-id="26da0-394">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="26da0-395">1903  (19H1)</span></span> |<span data-ttu-id="26da0-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="26da0-396">4.18.1902.5</span></span> |<span data-ttu-id="26da0-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="26da0-397">1.1.15600.4</span></span> | <span data-ttu-id="26da0-398">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="26da0-399">1809  (RS5)</span></span> |<span data-ttu-id="26da0-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="26da0-400">4.18.1807.18075</span></span> |<span data-ttu-id="26da0-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="26da0-401">1.1.15000.2</span></span> | <span data-ttu-id="26da0-402">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="26da0-403">1803  (RS4)</span></span> |<span data-ttu-id="26da0-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="26da0-404">4.13.17134.1</span></span> |<span data-ttu-id="26da0-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="26da0-405">1.1.14600.4</span></span> | <span data-ttu-id="26da0-406">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="26da0-407">1709  (RS3)</span></span> |<span data-ttu-id="26da0-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="26da0-408">4.12.16299.15</span></span> |<span data-ttu-id="26da0-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="26da0-409">1.1.14104.0</span></span> | <span data-ttu-id="26da0-410">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="26da0-411">1703  (RS2)</span></span> |<span data-ttu-id="26da0-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="26da0-412">4.11.15603.2</span></span> |<span data-ttu-id="26da0-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="26da0-413">1.1.13504.0</span></span> | <span data-ttu-id="26da0-414">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="26da0-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="26da0-415">1607 (RS1)</span></span> |<span data-ttu-id="26da0-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="26da0-416">4.10.14393.3683</span></span> |<span data-ttu-id="26da0-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="26da0-417">1.1.12805.0</span></span> | <span data-ttu-id="26da0-418">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="26da0-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="26da0-419">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="26da0-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="26da0-420">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="26da0-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="26da0-421">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="26da0-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="26da0-422">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="26da0-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="26da0-423">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="26da0-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="26da0-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="26da0-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="26da0-425">&ensp;Versión del paquete: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="26da0-426">&ensp;Versión de la **plataforma: 4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="26da0-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="26da0-427">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="26da0-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="26da0-428">&ensp;Versión de firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-429">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-429">Fixes</span></span>
- <span data-ttu-id="26da0-430">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-431">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-431">Additional information</span></span>
- <span data-ttu-id="26da0-432">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="26da0-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="26da0-434">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="26da0-435">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="26da0-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="26da0-436">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="26da0-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="26da0-437">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-438">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-438">Fixes</span></span>
- <span data-ttu-id="26da0-439">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-440">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-440">Additional information</span></span>
- <span data-ttu-id="26da0-441">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="26da0-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="26da0-443">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="26da0-444">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="26da0-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="26da0-445">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="26da0-446">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-447">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-447">Fixes</span></span>
- <span data-ttu-id="26da0-448">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-449">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-449">Additional information</span></span>
- <span data-ttu-id="26da0-450">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="26da0-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="26da0-452">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="26da0-453">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="26da0-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="26da0-454">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="26da0-455">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-456">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-456">Fixes</span></span>
- <span data-ttu-id="26da0-457">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-458">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-458">Additional information</span></span>
- <span data-ttu-id="26da0-459">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="26da0-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="26da0-461">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="26da0-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="26da0-462">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="26da0-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="26da0-463">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="26da0-464">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-465">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-465">Fixes</span></span>
- <span data-ttu-id="26da0-466">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-467">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-467">Additional information</span></span>
- <span data-ttu-id="26da0-468">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="26da0-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="26da0-470">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="26da0-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="26da0-471">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="26da0-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="26da0-472">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="26da0-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="26da0-473">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-474">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-474">Fixes</span></span>
- <span data-ttu-id="26da0-475">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-476">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-476">Additional information</span></span>
- <span data-ttu-id="26da0-477">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="26da0-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="26da0-479">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="26da0-480">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="26da0-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="26da0-481">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="26da0-482">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-483">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-483">Fixes</span></span>
- <span data-ttu-id="26da0-484">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-485">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-485">Additional information</span></span>
- <span data-ttu-id="26da0-486">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="26da0-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="26da0-488">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="26da0-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="26da0-489">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="26da0-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="26da0-490">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="26da0-491">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-492">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-492">Fixes</span></span>
- <span data-ttu-id="26da0-493">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-494">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-494">Additional information</span></span>
- <span data-ttu-id="26da0-495">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="26da0-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="26da0-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="26da0-497">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="26da0-498">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="26da0-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="26da0-499">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="26da0-500">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-501">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-501">Fixes</span></span>
- <span data-ttu-id="26da0-502">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-503">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-503">Additional information</span></span>
- <span data-ttu-id="26da0-504">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="26da0-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="26da0-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="26da0-506">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="26da0-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="26da0-507">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="26da0-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="26da0-508">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="26da0-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="26da0-509">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="26da0-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="26da0-510">Correcciones</span><span class="sxs-lookup"><span data-stu-id="26da0-510">Fixes</span></span>
- <span data-ttu-id="26da0-511">Ninguno</span><span class="sxs-lookup"><span data-stu-id="26da0-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="26da0-512">Información adicional</span><span class="sxs-lookup"><span data-stu-id="26da0-512">Additional information</span></span>
- <span data-ttu-id="26da0-513">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="26da0-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="26da0-514">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="26da0-514">Additional resources</span></span>

| <span data-ttu-id="26da0-515">Artículo</span><span class="sxs-lookup"><span data-stu-id="26da0-515">Article</span></span> | <span data-ttu-id="26da0-516">Descripción</span><span class="sxs-lookup"><span data-stu-id="26da0-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="26da0-517">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="26da0-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="26da0-518">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="26da0-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="26da0-519">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="26da0-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="26da0-520">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="26da0-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="26da0-521">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="26da0-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="26da0-522">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="26da0-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="26da0-523">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="26da0-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="26da0-524">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="26da0-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="26da0-525">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="26da0-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="26da0-526">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="26da0-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="26da0-527">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="26da0-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="26da0-528">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="26da0-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="26da0-529">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="26da0-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
