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
ms.date: 06/14/2021
ms.openlocfilehash: 1c7ff52398e048aa34fd9c5ab3d8edd1004ea5ec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929448"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="8e174-104">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="8e174-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="8e174-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8e174-105">**Applies to:**</span></span>

- [<span data-ttu-id="8e174-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8e174-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="8e174-107">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8e174-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="8e174-108">Mantener Antivirus de Microsoft Defender actualizado es fundamental para garantizar que los dispositivos tienen la tecnología y las características más recientes necesarias para protegerse contra nuevas técnicas de ataque y malware.</span><span class="sxs-lookup"><span data-stu-id="8e174-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="8e174-109">Asegúrese de actualizar la protección antivirus, incluso si Antivirus de Microsoft Defender se está ejecutando en [modo pasivo](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="8e174-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="8e174-110">Hay dos tipos de actualizaciones relacionadas con mantener Antivirus de Microsoft Defender actualizado:</span><span class="sxs-lookup"><span data-stu-id="8e174-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="8e174-111">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="8e174-111">Security intelligence updates</span></span>
- <span data-ttu-id="8e174-112">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="8e174-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="8e174-113">Para ver el motor, la plataforma y la fecha de firma más actuales, visite las actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender [y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="8e174-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="8e174-114">Actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="8e174-114">Security intelligence updates</span></span>

<span data-ttu-id="8e174-115">Antivirus de Microsoft Defender la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube (también denominada Servicio de protección avanzada de Microsoft o MAPS) y descarga periódicamente actualizaciones de inteligencia de seguridad para proporcionar protección.</span><span class="sxs-lookup"><span data-stu-id="8e174-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="8e174-116">Las actualizaciones se lanzan con los números KB siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e174-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="8e174-117">Antivirus de Microsoft Defender: KB2267602</span><span class="sxs-lookup"><span data-stu-id="8e174-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="8e174-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="8e174-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="8e174-119">La protección entregada en la nube siempre está activada y requiere una conexión activa a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="8e174-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="8e174-120">Las actualizaciones de inteligencia de seguridad se producen en una cadencia programada (configurable mediante directiva).</span><span class="sxs-lookup"><span data-stu-id="8e174-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="8e174-121">Para obtener más información, vea [Use Microsoft cloud-provided protection in Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8e174-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="8e174-122">Para obtener una lista de actualizaciones de inteligencia de seguridad recientes, vea Actualizaciones de inteligencia de seguridad [para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="8e174-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="8e174-123">Las actualizaciones del motor se incluyen con actualizaciones de inteligencia de seguridad y se lanzan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="8e174-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="8e174-124">Actualizaciones de productos</span><span class="sxs-lookup"><span data-stu-id="8e174-124">Product updates</span></span>

<span data-ttu-id="8e174-125">Antivirus de Microsoft Defender requiere [actualizaciones mensuales (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (conocidas como actualizaciones de *plataforma)* y recibirá actualizaciones de características principales junto con Windows 10 versiones.</span><span class="sxs-lookup"><span data-stu-id="8e174-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="8e174-126">Puede administrar la distribución de actualizaciones a través de uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="8e174-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="8e174-127">Windows Servicio de actualización de servidores (WSUS)</span><span class="sxs-lookup"><span data-stu-id="8e174-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="8e174-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e174-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="8e174-129">El método habitual que usa para implementar Microsoft y Windows actualizaciones en los puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="8e174-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="8e174-130">Para obtener más información, vea [Manage the sources for Antivirus de Microsoft Defender protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="8e174-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="8e174-131">Las actualizaciones mensuales se liberan en fases, lo que da como resultado varios paquetes visibles en [los Servicios de actualización de Windows Server](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span><span class="sxs-lookup"><span data-stu-id="8e174-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="8e174-132">Versiones mensuales de plataforma y motor</span><span class="sxs-lookup"><span data-stu-id="8e174-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="8e174-133">Para obtener información sobre cómo actualizar o instalar la actualización de la plataforma, vea [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="8e174-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="8e174-134">Todas nuestras actualizaciones contienen</span><span class="sxs-lookup"><span data-stu-id="8e174-134">All our updates contain</span></span> 
- <span data-ttu-id="8e174-135">mejoras en el rendimiento;</span><span class="sxs-lookup"><span data-stu-id="8e174-135">performance improvements;</span></span>
- <span data-ttu-id="8e174-136">mejoras en la capacidad de servicio; y</span><span class="sxs-lookup"><span data-stu-id="8e174-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="8e174-137">mejoras de integración (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="8e174-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/><br/>
<details>
<summary> <span data-ttu-id="8e174-138">Mayo-2021 (Plataforma: 4.18.2105.4 | Motor: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="8e174-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="8e174-139">&ensp;Versión de actualización de inteligencia de seguridad: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="8e174-140">&ensp;Publicado: **3 de junio de 2021**</span><span class="sxs-lookup"><span data-stu-id="8e174-140">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="8e174-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="8e174-142">&ensp;Motor: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="8e174-143">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="8e174-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-144">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-144">What's new</span></span>
- <span data-ttu-id="8e174-145">Mejoras en la [supervisión del comportamiento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="8e174-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="8e174-146">Característica [de filtrado de notificaciones de protección](network-protection.md) de red fija</span><span class="sxs-lookup"><span data-stu-id="8e174-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-147">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-147">Known Issues</span></span>
<span data-ttu-id="8e174-148">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-149">Abril-2021 (Plataforma: 4.18.2104.14 | Motor: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="8e174-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="8e174-150">&ensp;Versión de actualización de inteligencia de seguridad: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="8e174-151">&ensp;Publicado: 26 de abril de **2021**  (Motor: 1.1.18100.6 publicado el 5 de mayo de 2021) &ensp; Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="8e174-151">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="8e174-152">&ensp;Motor: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="8e174-153">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="8e174-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-154">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-154">What's new</span></span>
- <span data-ttu-id="8e174-155">Lógica de supervisión de comportamiento adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="8e174-156">Detección de registrador de teclas de modo kernel mejorado</span><span class="sxs-lookup"><span data-stu-id="8e174-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-157">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-157">Known Issues</span></span>
<span data-ttu-id="8e174-158">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-159">Marzo-2021 (Plataforma: 4.18.2103.7 | Motor: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="8e174-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="8e174-160">&ensp;Versión de actualización de inteligencia de seguridad: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="8e174-161">&ensp;Publicado: **2 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="8e174-161">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="8e174-162">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="8e174-163">&ensp;Motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="8e174-164">&ensp;Fase de soporte técnico: **Seguridad y actualizaciones críticas**</span><span class="sxs-lookup"><span data-stu-id="8e174-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-165">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-165">What's new</span></span>

- <span data-ttu-id="8e174-166">Mejora del motor de supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="8e174-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="8e174-167">Mitigaciones de ataques de fuerza bruta de red expandida</span><span class="sxs-lookup"><span data-stu-id="8e174-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="8e174-168">Generación de eventos de intento de manipulación con error adicional cuando [la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="8e174-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-169">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-169">Known Issues</span></span>
<span data-ttu-id="8e174-170">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="8e174-171">Actualizaciones de versiones anteriores: solo compatibilidad con actualizaciones técnicas</span><span class="sxs-lookup"><span data-stu-id="8e174-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="8e174-172">Después de publicar una nueva versión del paquete, la compatibilidad con las dos versiones anteriores se reduce únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8e174-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="8e174-173">Las versiones anteriores a las que se enumeran en esta sección y solo se proporcionan para soporte técnico de actualización.</span><span class="sxs-lookup"><span data-stu-id="8e174-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="8e174-174">Febrero-2021 (Plataforma: 4.18.2102.3 | Motor: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="8e174-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="8e174-175">&ensp;Versión de actualización de inteligencia de seguridad: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="8e174-176">&ensp;Publicado: **9 de marzo de 2021**</span><span class="sxs-lookup"><span data-stu-id="8e174-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="8e174-177">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="8e174-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="8e174-178">&ensp;Motor: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="8e174-179">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-180">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-180">What's new</span></span>

- <span data-ttu-id="8e174-181">Recuperación del servicio mejorada a través de [la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="8e174-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="8e174-182">Ampliar el ámbito de protección contra alteraciones</span><span class="sxs-lookup"><span data-stu-id="8e174-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-183">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-183">Known Issues</span></span>
<span data-ttu-id="8e174-184">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-185">Enero-2021 (Plataforma: 4.18.2101.9 | Motor: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="8e174-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="8e174-186">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="8e174-187">&ensp;Publicado: **2 de febrero de 2021**</span><span class="sxs-lookup"><span data-stu-id="8e174-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="8e174-188">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="8e174-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="8e174-189">&ensp;Motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="8e174-190">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-191">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-191">What's new</span></span>

- <span data-ttu-id="8e174-192">Mejoras en la detección de vulnerabilidades de shellcode</span><span class="sxs-lookup"><span data-stu-id="8e174-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="8e174-193">Mayor visibilidad para intentos de robo de credenciales</span><span class="sxs-lookup"><span data-stu-id="8e174-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="8e174-194">Mejoras en las características de protección contra la Antivirus de Microsoft Defender servicios</span><span class="sxs-lookup"><span data-stu-id="8e174-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="8e174-195">Compatibilidad mejorada con la emulación ARM x64</span><span class="sxs-lookup"><span data-stu-id="8e174-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="8e174-196">Corrección: EDR notificación de bloqueo permanece en el historial de amenazas después de que la protección en tiempo real realizara la detección inicial</span><span class="sxs-lookup"><span data-stu-id="8e174-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-197">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-197">Known Issues</span></span>
<span data-ttu-id="8e174-198">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-199">Noviembre-2020 (Plataforma: 4.18.2011.6 | Motor: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="8e174-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="8e174-200">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="8e174-201">&ensp;Publicado: **03 de diciembre de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="8e174-202">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="8e174-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="8e174-203">&ensp;Motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="8e174-204">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-205">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-205">What's new</span></span>

- <span data-ttu-id="8e174-206">Registro de compatibilidad con el estado de [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) mejorado</span><span class="sxs-lookup"><span data-stu-id="8e174-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-207">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-207">Known Issues</span></span>
<span data-ttu-id="8e174-208">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-209">Octubre-2020 (Plataforma: 4.18.2010.7 | Motor: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="8e174-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="8e174-210">&ensp;Versión de actualización de inteligencia de seguridad: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="8e174-211">&ensp;Publicado: **29 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="8e174-212">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="8e174-213">&ensp;Motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="8e174-214">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-215">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-215">What's new</span></span>

- <span data-ttu-id="8e174-216">Nuevas descripciones para categorías de amenazas especiales</span><span class="sxs-lookup"><span data-stu-id="8e174-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="8e174-217">Capacidades de emulación mejoradas</span><span class="sxs-lookup"><span data-stu-id="8e174-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="8e174-218">Capacidades mejoradas de permitir o bloquear direcciones host</span><span class="sxs-lookup"><span data-stu-id="8e174-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="8e174-219">Nueva opción en CSP de Defender para omitir la combinación de exclusiones de usuarios locales</span><span class="sxs-lookup"><span data-stu-id="8e174-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-220">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-220">Known Issues</span></span>

<span data-ttu-id="8e174-221">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="8e174-222">Septiembre-2020 (Plataforma: 4.18.2009.7 | Motor: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="8e174-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="8e174-223">&ensp;Versión de actualización de inteligencia de seguridad: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="8e174-224">&ensp;Publicado: **01 de octubre de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="8e174-225">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="8e174-226">&ensp;Motor: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="8e174-227">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-228">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-228">What's new</span></span>

- <span data-ttu-id="8e174-229">Los permisos de administrador son necesarios para restaurar archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="8e174-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="8e174-230">Ahora se admiten eventos con formato XML</span><span class="sxs-lookup"><span data-stu-id="8e174-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="8e174-231">Compatibilidad con CSP para omitir las fusiones de exclusión</span><span class="sxs-lookup"><span data-stu-id="8e174-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="8e174-232">Nuevas interfaces de administración para:</span><span class="sxs-lookup"><span data-stu-id="8e174-232">New management interfaces for:</span></span>
   - <span data-ttu-id="8e174-233">Inspección UDP</span><span class="sxs-lookup"><span data-stu-id="8e174-233">UDP Inspection</span></span>
   - <span data-ttu-id="8e174-234">Protección de red en server 2019</span><span class="sxs-lookup"><span data-stu-id="8e174-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="8e174-235">Exclusiones de direcciones IP para protección de red</span><span class="sxs-lookup"><span data-stu-id="8e174-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="8e174-236">Visibilidad mejorada de las medidas del TPM</span><span class="sxs-lookup"><span data-stu-id="8e174-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="8e174-237">Examen mejorado Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="8e174-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-238">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-238">Known Issues</span></span>

<span data-ttu-id="8e174-239">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="8e174-240">Agosto-2020 (Plataforma: 4.18.2008.9 | Motor: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="8e174-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="8e174-241">&ensp;Versión de actualización de inteligencia de seguridad: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="8e174-242">&ensp;Publicado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="8e174-243">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="8e174-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="8e174-244">&ensp;Motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="8e174-245">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="8e174-246">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-246">What's new</span></span>

- <span data-ttu-id="8e174-247">Agregar más eventos de telemetría</span><span class="sxs-lookup"><span data-stu-id="8e174-247">Add more telemetry events</span></span>
- <span data-ttu-id="8e174-248">Telemetría de eventos de examen mejorada</span><span class="sxs-lookup"><span data-stu-id="8e174-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="8e174-249">Supervisión de comportamiento mejorada para exámenes de memoria</span><span class="sxs-lookup"><span data-stu-id="8e174-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="8e174-250">Análisis mejorado de secuencias de macros</span><span class="sxs-lookup"><span data-stu-id="8e174-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="8e174-251">Se `AMRunningMode` agregó Get-MpComputerStatus cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e174-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="8e174-252">[Se omite DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)</span><span class="sxs-lookup"><span data-stu-id="8e174-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="8e174-253">Antivirus de Microsoft Defender se desactiva automáticamente cuando detecta otro programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="8e174-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="8e174-254">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-254">Known Issues</span></span>
<span data-ttu-id="8e174-255">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-256">Julio-2020 (Plataforma: 4.18.2007.8 | Motor: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="8e174-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="8e174-257">&ensp;Versión de actualización de inteligencia de seguridad: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="8e174-258">&ensp;Publicado: **28 de julio de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="8e174-259">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="8e174-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="8e174-260">&ensp;Motor: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="8e174-261">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-262">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-262">What's new</span></span>

- <span data-ttu-id="8e174-263">Telemetría mejorada para BITS</span><span class="sxs-lookup"><span data-stu-id="8e174-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="8e174-264">Validación mejorada del certificado de firma de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="8e174-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-265">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-265">Known Issues</span></span>
<span data-ttu-id="8e174-266">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-267">Junio-2020 (Plataforma: 4.18.2006.10 | Motor: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="8e174-268">&ensp;Versión de actualización de inteligencia de seguridad: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="8e174-269">&ensp;Publicado: **22 de junio de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="8e174-270">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="8e174-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="8e174-271">&ensp;Motor: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="8e174-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="8e174-272">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-273">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-273">What's new</span></span>

- <span data-ttu-id="8e174-274">Posibilidad de especificar la [ubicación de los registros de soporte técnico](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="8e174-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="8e174-275">Omitir el examen de captura agresivo en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="8e174-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="8e174-276">Permitir que Defender actualice con conexiones medidas</span><span class="sxs-lookup"><span data-stu-id="8e174-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="8e174-277">Se ha corregido la optimización del rendimiento cuando se deshabilita el almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="8e174-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="8e174-278">Consulta fija del Registro</span><span class="sxs-lookup"><span data-stu-id="8e174-278">Fixed registry query</span></span> 
- <span data-ttu-id="8e174-279">Aleatorización de tiempo de examen fijo en ADMX</span><span class="sxs-lookup"><span data-stu-id="8e174-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-280">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-280">Known Issues</span></span>
<span data-ttu-id="8e174-281">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-282">Mayo-2020 (Plataforma: 4.18.2005.4 | Motor: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="8e174-283">&ensp;Versión de actualización de inteligencia de seguridad: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="8e174-284">&ensp;Publicado: **26 de mayo de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="8e174-285">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="8e174-286">&ensp;Motor: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="8e174-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="8e174-287">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-288">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-288">What's new</span></span>

- <span data-ttu-id="8e174-289">Registro mejorado para eventos de examen</span><span class="sxs-lookup"><span data-stu-id="8e174-289">Improved logging for scan events</span></span>
- <span data-ttu-id="8e174-290">Se ha mejorado el control de bloqueos del modo de usuario.</span><span class="sxs-lookup"><span data-stu-id="8e174-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="8e174-291">Se agregó el seguimiento de eventos para la protección contra manipulaciones</span><span class="sxs-lookup"><span data-stu-id="8e174-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="8e174-292">Envío de ejemplo de AMSI fijo</span><span class="sxs-lookup"><span data-stu-id="8e174-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="8e174-293">Se ha corregido el bloqueo de la nube de AMSI</span><span class="sxs-lookup"><span data-stu-id="8e174-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="8e174-294">Registro de instalación de actualización de seguridad fija</span><span class="sxs-lookup"><span data-stu-id="8e174-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-295">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-295">Known Issues</span></span>
<span data-ttu-id="8e174-296">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-297">Abril-2020 (Plataforma: 4.18.2004.6 | Motor: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="8e174-298">&ensp;Versión de actualización de inteligencia de seguridad: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="8e174-299">&ensp;Publicado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="8e174-300">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="8e174-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="8e174-301">&ensp;Motor: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="8e174-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="8e174-302">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-303">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-303">What's new</span></span>
- <span data-ttu-id="8e174-304">Mejoras de WDfilter</span><span class="sxs-lookup"><span data-stu-id="8e174-304">WDfilter improvements</span></span>
- <span data-ttu-id="8e174-305">Agregar más datos de eventos que se pueden usar para atacar eventos de detección de reducción de superficie</span><span class="sxs-lookup"><span data-stu-id="8e174-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="8e174-306">Información de versión fija en datos de diagnóstico y WMI</span><span class="sxs-lookup"><span data-stu-id="8e174-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="8e174-307">Se ha corregido una versión incorrecta de la plataforma en la interfaz de usuario después de la actualización de la plataforma</span><span class="sxs-lookup"><span data-stu-id="8e174-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="8e174-308">Intel de dirección URL dinámica para la protección contra amenazas sin archivos</span><span class="sxs-lookup"><span data-stu-id="8e174-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="8e174-309">Funcionalidad de examen UEFI</span><span class="sxs-lookup"><span data-stu-id="8e174-309">UEFI scan capability</span></span>
- <span data-ttu-id="8e174-310">Extender el registro para actualizaciones</span><span class="sxs-lookup"><span data-stu-id="8e174-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="8e174-311">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-311">Known Issues</span></span>
<span data-ttu-id="8e174-312">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-313">Marzo-2020 (Plataforma: 4.18.2003.8 | Motor: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="8e174-314">&ensp;Versión de actualización de inteligencia de seguridad: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="8e174-315">&ensp;Publicado: **24 de marzo de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="8e174-316">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="8e174-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="8e174-317">&ensp;Motor: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="8e174-318">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="8e174-319">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-319">What's new</span></span>

- <span data-ttu-id="8e174-320">Opción de limitación de CPU agregada a [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8e174-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="8e174-321">Mejorar la funcionalidad de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8e174-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="8e174-322">reducir el tiempo de espera de inteligencia de seguridad (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="8e174-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="8e174-323">Ampliar la funcionalidad de registro interno del motor AMSI</span><span class="sxs-lookup"><span data-stu-id="8e174-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="8e174-324">Mejorar la notificación para el bloqueo de procesos</span><span class="sxs-lookup"><span data-stu-id="8e174-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8e174-325">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-325">Known Issues</span></span>
<span data-ttu-id="8e174-326">[**Fijo**] Antivirus de Microsoft Defender está omitiendo archivos al ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="8e174-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="8e174-327">Febrero-2020 (Plataforma: - | Motor: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="8e174-328">&ensp;Versión de actualización de inteligencia de seguridad: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="8e174-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="8e174-329">&ensp;Publicado: **25 de febrero de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="8e174-330">&ensp;Plataforma/cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="8e174-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="8e174-331">&ensp;Motor: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="8e174-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="8e174-332">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="8e174-333">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="8e174-334">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-334">Known Issues</span></span>
<span data-ttu-id="8e174-335">Sin problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-336">Enero-2020 (Plataforma: 4.18.2001.10 | Motor: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="8e174-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="8e174-337">Versión de actualización de inteligencia de seguridad: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="8e174-338">Publicado: **30 de enero de 2020**</span><span class="sxs-lookup"><span data-stu-id="8e174-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="8e174-339">Plataforma/cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="8e174-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="8e174-340">Motor: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="8e174-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="8e174-341">&ensp;Fase de soporte técnico: **soporte técnico de actualización (solo)**</span><span class="sxs-lookup"><span data-stu-id="8e174-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="8e174-342">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-342">What's new</span></span>

- <span data-ttu-id="8e174-343">BSOD fijo en WS2016 con Exchange</span><span class="sxs-lookup"><span data-stu-id="8e174-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="8e174-344">Actualizaciones de plataforma de soporte técnico cuando TMP se redirige a la ruta de red</span><span class="sxs-lookup"><span data-stu-id="8e174-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="8e174-345">Las versiones de plataforma y motor se agregan a [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="8e174-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="8e174-346">extender la actualización de firma de emergencia [al modo pasivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="8e174-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="8e174-347">Corrección 4.18.1911.3 hang</span><span class="sxs-lookup"><span data-stu-id="8e174-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8e174-348">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-348">Known Issues</span></span>

<span data-ttu-id="8e174-349">[**Fijo**] los dispositivos que utilizan el modo [de](/windows-hardware/design/device-experiences/modern-standby) espera moderno pueden experimentar una suspensión con el controlador de filtro Windows Defender que da como resultado un vacío de protección.</span><span class="sxs-lookup"><span data-stu-id="8e174-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="8e174-350">Las máquinas afectadas aparecen al cliente como que no se han actualizado a la plataforma antimalware más reciente.</span><span class="sxs-lookup"><span data-stu-id="8e174-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="8e174-351">Esta actualización es:</span><span class="sxs-lookup"><span data-stu-id="8e174-351">This update is:</span></span>
> - <span data-ttu-id="8e174-352">que necesitan los dispositivos RS1 que ejecutan la versión inferior de la plataforma para admitir SHA2;</span><span class="sxs-lookup"><span data-stu-id="8e174-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="8e174-353">tiene una marca de reinicio para sistemas que tienen problemas de suspensión;</span><span class="sxs-lookup"><span data-stu-id="8e174-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="8e174-354">se vuelve a publicar en abril de 2020 y no se reemplazará por actualizaciones más recientes para mantener la disponibilidad futura;</span><span class="sxs-lookup"><span data-stu-id="8e174-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="8e174-355">se clasifica como una actualización debido al requisito de reinicio; y</span><span class="sxs-lookup"><span data-stu-id="8e174-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="8e174-356">solo se ofrece con [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="8e174-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="8e174-357">Noviembre-2019 (Plataforma: 4.18.1911.3 | Motor: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="8e174-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="8e174-358">Versión de actualización de inteligencia de seguridad: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="8e174-359">Publicado: **7 de diciembre de 2019**</span><span class="sxs-lookup"><span data-stu-id="8e174-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="8e174-360">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="8e174-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="8e174-361">Motor: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="8e174-362">Fase de soporte técnico: **sin compatibilidad**</span><span class="sxs-lookup"><span data-stu-id="8e174-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="8e174-363">Novedades</span><span class="sxs-lookup"><span data-stu-id="8e174-363">What's new</span></span>

- <span data-ttu-id="8e174-364">Nivel de seguimiento de MpCmdRun fijo</span><span class="sxs-lookup"><span data-stu-id="8e174-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="8e174-365">Información de versión de WDFilter fija</span><span class="sxs-lookup"><span data-stu-id="8e174-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="8e174-366">Mejorar las notificaciones (PUA)</span><span class="sxs-lookup"><span data-stu-id="8e174-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="8e174-367">agregar registros de MRT para admitir archivos</span><span class="sxs-lookup"><span data-stu-id="8e174-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="8e174-368">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e174-368">Known Issues</span></span>
<span data-ttu-id="8e174-369">Cuando se instala esta actualización, el dispositivo necesita el paquete de salto 4.18.2001.10 para poder actualizar a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="8e174-369">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="8e174-370">Antivirus de Microsoft Defender de plataforma</span><span class="sxs-lookup"><span data-stu-id="8e174-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="8e174-371">Las actualizaciones de plataforma y motor se proporcionan en una cadencia mensual.</span><span class="sxs-lookup"><span data-stu-id="8e174-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="8e174-372">Para ser totalmente compatible, manténgase al día con las actualizaciones más recientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="8e174-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="8e174-373">Nuestra estructura de soporte es dinámica, evolucionando en dos fases en función de la disponibilidad de la versión más reciente de la plataforma:</span><span class="sxs-lookup"><span data-stu-id="8e174-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="8e174-374">**Fase de mantenimiento** de actualizaciones críticas y de seguridad: al ejecutar la versión más reciente de la plataforma, podrá recibir actualizaciones de seguridad y críticas en la plataforma antimalware.</span><span class="sxs-lookup"><span data-stu-id="8e174-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="8e174-375">**Fase de soporte** técnico (solo): después de publicar una nueva versión de la plataforma, la compatibilidad con versiones anteriores (N-2) se reducirá únicamente al soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8e174-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="8e174-376">Las versiones de plataforma anteriores a N-2 ya no se admiten.\*</span><span class="sxs-lookup"><span data-stu-id="8e174-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="8e174-377">\*Se seguirá brindando soporte técnico para las actualizaciones de la versión de Windows 10 (consulte Versión de la plataforma incluida con [Windows 10](#platform-version-included-with-windows-10-releases)versiones) a la versión más reciente de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="8e174-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="8e174-378">Durante la fase de soporte técnico (solo), los incidentes de soporte comercialmente razonables se proporcionan a través del servicio de soporte técnico de Microsoft & y las ofertas de soporte administrado de Microsoft (como soporte premier).</span><span class="sxs-lookup"><span data-stu-id="8e174-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="8e174-379">Si un incidente de soporte requiere una escalación al desarrollo para obtener más instrucciones, requiere una actualización que no sea de seguridad o requiere una actualización de seguridad, se pedirá a los clientes que actualicen a la versión más reciente de la plataforma o a una actualización intermedia (\*).</span><span class="sxs-lookup"><span data-stu-id="8e174-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="8e174-380">Versión de plataforma incluida con Windows 10 versiones</span><span class="sxs-lookup"><span data-stu-id="8e174-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="8e174-381">En la tabla siguiente se proporciona Antivirus de Microsoft Defender plataforma y versiones del motor que se suministran con las versiones Windows 10 versiones más recientes:</span><span class="sxs-lookup"><span data-stu-id="8e174-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="8e174-382">Windows 10 versión</span><span class="sxs-lookup"><span data-stu-id="8e174-382">Windows 10 release</span></span>  |<span data-ttu-id="8e174-383">Versión de plataforma</span><span class="sxs-lookup"><span data-stu-id="8e174-383">Platform version</span></span>  |<span data-ttu-id="8e174-384">Versión del motor</span><span class="sxs-lookup"><span data-stu-id="8e174-384">Engine version</span></span> |<span data-ttu-id="8e174-385">Fase de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="8e174-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="8e174-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="8e174-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="8e174-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="8e174-387">4.18.1909.6</span></span> |<span data-ttu-id="8e174-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="8e174-388">1.1.17000.2</span></span> | <span data-ttu-id="8e174-389">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="8e174-390">1909  (19H2)</span></span> |<span data-ttu-id="8e174-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="8e174-391">4.18.1902.5</span></span> |<span data-ttu-id="8e174-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="8e174-392">1.1.16700.3</span></span> | <span data-ttu-id="8e174-393">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="8e174-394">1903  (19H1)</span></span> |<span data-ttu-id="8e174-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="8e174-395">4.18.1902.5</span></span> |<span data-ttu-id="8e174-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="8e174-396">1.1.15600.4</span></span> | <span data-ttu-id="8e174-397">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="8e174-398">1809  (RS5)</span></span> |<span data-ttu-id="8e174-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="8e174-399">4.18.1807.18075</span></span> |<span data-ttu-id="8e174-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="8e174-400">1.1.15000.2</span></span> | <span data-ttu-id="8e174-401">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="8e174-402">1803  (RS4)</span></span> |<span data-ttu-id="8e174-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="8e174-403">4.13.17134.1</span></span> |<span data-ttu-id="8e174-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="8e174-404">1.1.14600.4</span></span> | <span data-ttu-id="8e174-405">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="8e174-406">1709  (RS3)</span></span> |<span data-ttu-id="8e174-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="8e174-407">4.12.16299.15</span></span> |<span data-ttu-id="8e174-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="8e174-408">1.1.14104.0</span></span> | <span data-ttu-id="8e174-409">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="8e174-410">1703  (RS2)</span></span> |<span data-ttu-id="8e174-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="8e174-411">4.11.15603.2</span></span> |<span data-ttu-id="8e174-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="8e174-412">1.1.13504.0</span></span> | <span data-ttu-id="8e174-413">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="8e174-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="8e174-414">1607 (RS1)</span></span> |<span data-ttu-id="8e174-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="8e174-415">4.10.14393.3683</span></span> |<span data-ttu-id="8e174-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="8e174-416">1.1.12805.0</span></span> | <span data-ttu-id="8e174-417">Soporte técnico de actualización (solo)</span><span class="sxs-lookup"><span data-stu-id="8e174-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="8e174-418">Para obtener Windows 10 de la versión, consulte la Windows de datos del ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="8e174-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="8e174-419">Actualizaciones para administración y mantenimiento de imágenes de implementación (DISM)</span><span class="sxs-lookup"><span data-stu-id="8e174-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="8e174-420">Se recomienda actualizar las ediciones Windows 10 (Enterprise, Pro y Home), Windows Server 2019 y las imágenes de instalación del sistema operativo Windows Server 2016 con las últimas actualizaciones de antivirus y antimalware.</span><span class="sxs-lookup"><span data-stu-id="8e174-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="8e174-421">Mantener las imágenes de instalación del sistema operativo actualizadas ayuda a evitar un vacío en la protección.</span><span class="sxs-lookup"><span data-stu-id="8e174-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="8e174-422">Para obtener más información, vea [Actualización de Microsoft Defender para obtener Windows de instalación del sistema operativo](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="8e174-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="8e174-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="8e174-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="8e174-424">&ensp;Versión del paquete: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="8e174-425">&ensp;Versión de la **plataforma: 4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="8e174-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="8e174-426">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="8e174-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="8e174-427">&ensp;Versión de firma: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-428">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-428">Fixes</span></span>
- <span data-ttu-id="8e174-429">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-430">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-430">Additional information</span></span>
- <span data-ttu-id="8e174-431">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="8e174-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="8e174-433">&ensp;Versión del paquete: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="8e174-434">&ensp;Versión de plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="8e174-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="8e174-435">&ensp;Versión del motor: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="8e174-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="8e174-436">&ensp;Versión de firma: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-437">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-437">Fixes</span></span>
- <span data-ttu-id="8e174-438">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-439">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-439">Additional information</span></span>
- <span data-ttu-id="8e174-440">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="8e174-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="8e174-442">&ensp;Versión del paquete: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="8e174-443">&ensp;Versión de plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="8e174-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="8e174-444">&ensp;Versión del motor: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="8e174-445">&ensp;Versión de firma: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-446">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-446">Fixes</span></span>
- <span data-ttu-id="8e174-447">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-448">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-448">Additional information</span></span>
- <span data-ttu-id="8e174-449">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="8e174-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="8e174-451">&ensp;Versión del paquete: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="8e174-452">&ensp;Versión de la **plataforma: 4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="8e174-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="8e174-453">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="8e174-454">&ensp;Versión de firma: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-455">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-455">Fixes</span></span>
- <span data-ttu-id="8e174-456">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-457">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-457">Additional information</span></span>
- <span data-ttu-id="8e174-458">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="8e174-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="8e174-460">&ensp;Versión del paquete: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="8e174-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="8e174-461">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="8e174-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="8e174-462">&ensp;Versión del motor: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="8e174-463">&ensp;Versión de firma: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-464">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-464">Fixes</span></span>
- <span data-ttu-id="8e174-465">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-466">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-466">Additional information</span></span>
- <span data-ttu-id="8e174-467">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="8e174-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="8e174-469">&ensp;Versión del paquete: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="8e174-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="8e174-470">&ensp;Versión de plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="8e174-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="8e174-471">&ensp;Versión del motor: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="8e174-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="8e174-472">&ensp;Versión de firma: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-473">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-473">Fixes</span></span>
- <span data-ttu-id="8e174-474">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-475">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-475">Additional information</span></span>
- <span data-ttu-id="8e174-476">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="8e174-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="8e174-478">&ensp;Versión del paquete: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="8e174-479">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="8e174-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="8e174-480">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8e174-481">&ensp;Versión de firma: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-482">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-482">Fixes</span></span>
- <span data-ttu-id="8e174-483">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-484">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-484">Additional information</span></span>
- <span data-ttu-id="8e174-485">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="8e174-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="8e174-487">&ensp;Versión del paquete: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="8e174-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="8e174-488">&ensp;Versión de la **plataforma: 4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="8e174-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="8e174-489">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8e174-490">&ensp;Versión de firma: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-491">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-491">Fixes</span></span>
- <span data-ttu-id="8e174-492">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-493">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-493">Additional information</span></span>
- <span data-ttu-id="8e174-494">Firmas Antivirus de Microsoft Defender actualización</span><span class="sxs-lookup"><span data-stu-id="8e174-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="8e174-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="8e174-496">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="8e174-497">&ensp;Versión de plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="8e174-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="8e174-498">&ensp;Versión del motor: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="8e174-499">&ensp;Versión de firma: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-500">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-500">Fixes</span></span>
- <span data-ttu-id="8e174-501">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-502">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-502">Additional information</span></span>
- <span data-ttu-id="8e174-503">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="8e174-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="8e174-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="8e174-505">&ensp;Versión del paquete: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="8e174-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="8e174-506">&ensp;Versión de plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="8e174-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="8e174-507">&ensp;Versión del motor: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="8e174-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="8e174-508">&ensp;Versión de firma: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="8e174-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="8e174-509">Correcciones</span><span class="sxs-lookup"><span data-stu-id="8e174-509">Fixes</span></span>
- <span data-ttu-id="8e174-510">Ninguno</span><span class="sxs-lookup"><span data-stu-id="8e174-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="8e174-511">Información adicional</span><span class="sxs-lookup"><span data-stu-id="8e174-511">Additional information</span></span>
- <span data-ttu-id="8e174-512">Se agregó compatibilidad con Windows 10 imágenes de instalación del sistema operativo RS1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8e174-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="8e174-513">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8e174-513">Additional resources</span></span>

| <span data-ttu-id="8e174-514">Artículo</span><span class="sxs-lookup"><span data-stu-id="8e174-514">Article</span></span> | <span data-ttu-id="8e174-515">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e174-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="8e174-516">Actualización de Microsoft Defender para Windows de instalación del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="8e174-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="8e174-517">Revisar los paquetes de actualización de antimalware para las imágenes de instalación del sistema operativo (archivos WIM y VHD).</span><span class="sxs-lookup"><span data-stu-id="8e174-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="8e174-518">Obtenga Antivirus de Microsoft Defender actualizaciones de Windows 10 (ediciones Enterprise, Pro y Home), Windows Server 2019 y Windows Server 2016 de instalación.</span><span class="sxs-lookup"><span data-stu-id="8e174-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="8e174-519">Administrar cómo se descargan y aplican las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="8e174-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="8e174-520">Las actualizaciones de protección se pueden entregar a través de muchos orígenes.</span><span class="sxs-lookup"><span data-stu-id="8e174-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="8e174-521">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="8e174-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="8e174-522">Puede programar cuándo deben descargarse las actualizaciones de protección.</span><span class="sxs-lookup"><span data-stu-id="8e174-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="8e174-523">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="8e174-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="8e174-524">Si un extremo pierde una actualización o un examen programado, puede forzar una actualización o examinar la próxima vez que un usuario inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="8e174-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="8e174-525">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="8e174-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="8e174-526">Puede configurar las actualizaciones de protección para que se descarguen al inicio o después de determinados eventos de protección entregados en la nube.</span><span class="sxs-lookup"><span data-stu-id="8e174-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="8e174-527">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="8e174-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="8e174-528">Puede especificar la configuración, como si las actualizaciones deben producirse en la batería, que son especialmente útiles para dispositivos móviles y máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="8e174-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
