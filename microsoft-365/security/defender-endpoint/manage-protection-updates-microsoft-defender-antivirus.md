---
title: Administrar cómo y dónde Antivirus de Microsoft Defender recibe actualizaciones
description: Administrar el orden de reserva de cómo Antivirus de Microsoft Defender actualizaciones de protección.
keywords: actualizaciones, líneas base de seguridad, protección, orden de reserva, ADL, MMPC, UNC, ruta de acceso de archivo, recurso compartido, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 52fe64b096b24dfc52a97fb664e408c5aeb701f4
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624214"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="75753-104">Administrar el original para las actualizaciones de protección del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="75753-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75753-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="75753-105">**Applies to:**</span></span>

- [<span data-ttu-id="75753-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="75753-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="75753-107">Mantener la protección antivirus actualizada es fundamental.</span><span class="sxs-lookup"><span data-stu-id="75753-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="75753-108">Hay dos componentes para administrar actualizaciones de protección para Antivirus de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="75753-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="75753-109">*Desde* donde se descargan las actualizaciones; y</span><span class="sxs-lookup"><span data-stu-id="75753-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="75753-110">*Cuando* las actualizaciones se descargan y se aplican.</span><span class="sxs-lookup"><span data-stu-id="75753-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="75753-111">En este artículo se describe cómo especificar desde dónde deben descargarse las actualizaciones (esto también se conoce como orden de reserva).</span><span class="sxs-lookup"><span data-stu-id="75753-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="75753-112">Consulte [Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic para obtener información general sobre cómo funcionan las actualizaciones y cómo configurar otros aspectos de las actualizaciones (como las actualizaciones de programación).</span><span class="sxs-lookup"><span data-stu-id="75753-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75753-113">Antivirus de Microsoft Defender Las actualizaciones de inteligencia de seguridad se entregan a través de Windows Update y, a partir del lunes 21 de octubre de 2019, todas las actualizaciones de inteligencia de seguridad se firmarán exclusivamente con SHA-2.</span><span class="sxs-lookup"><span data-stu-id="75753-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="75753-114">Los dispositivos deben actualizarse para admitir SHA-2 con el fin de actualizar la inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75753-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="75753-115">Para obtener más información, vea [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span><span class="sxs-lookup"><span data-stu-id="75753-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="75753-116">Orden de reserva</span><span class="sxs-lookup"><span data-stu-id="75753-116">Fallback order</span></span>

<span data-ttu-id="75753-117">Normalmente, los puntos de conexión se configuran para descargar actualizaciones individualmente de un origen principal seguidos de otros orígenes en orden de prioridad, en función de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="75753-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="75753-118">Las actualizaciones se obtienen de orígenes en el orden especificado.</span><span class="sxs-lookup"><span data-stu-id="75753-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="75753-119">Si un origen no está disponible, el siguiente origen de la lista se usa inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="75753-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="75753-120">Cuando se publican actualizaciones, se aplica cierta lógica para minimizar el tamaño de la actualización.</span><span class="sxs-lookup"><span data-stu-id="75753-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="75753-121">En la mayoría de los casos, solo se descargan y aplican las diferencias entre la actualización más reciente y la actualización que está instalada actualmente (esto se conoce como delta) en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75753-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="75753-122">Sin embargo, el tamaño del delta depende de dos factores principales:</span><span class="sxs-lookup"><span data-stu-id="75753-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="75753-123">La antigüedad de la última actualización del dispositivo; y</span><span class="sxs-lookup"><span data-stu-id="75753-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="75753-124">El origen usado para descargar y aplicar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="75753-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="75753-125">Cuanto más antiguas sean las actualizaciones de un punto de conexión, mayor será la descarga.</span><span class="sxs-lookup"><span data-stu-id="75753-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="75753-126">Sin embargo, también debe considerar la frecuencia de descarga.</span><span class="sxs-lookup"><span data-stu-id="75753-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="75753-127">Una programación de actualización más frecuente puede provocar un mayor uso de la red, mientras que una programación menos frecuente puede dar como resultado tamaños de archivo más grandes por descarga.</span><span class="sxs-lookup"><span data-stu-id="75753-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="75753-128">Hay cinco ubicaciones donde puede especificar dónde debe obtener actualizaciones un punto de conexión:</span><span class="sxs-lookup"><span data-stu-id="75753-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="75753-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="75753-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="75753-130">Windows Servicio de actualización de servidor</span><span class="sxs-lookup"><span data-stu-id="75753-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="75753-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="75753-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="75753-132">Recurso compartido de archivos de red</span><span class="sxs-lookup"><span data-stu-id="75753-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="75753-133">[Actualizaciones de inteligencia de](https://www.microsoft.com/en-us/wdsi/defenderupdates) seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft (Es posible que la directiva y el registro tengan esta lista como inteligencia de seguridad de Centro de protección contra malware de Microsoft (MMPC), su nombre anterior).</span><span class="sxs-lookup"><span data-stu-id="75753-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="75753-134">Para garantizar el mejor nivel de protección, Microsoft Update permite versiones rápidas, lo que significa descargas más pequeñas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="75753-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="75753-135">El Windows de actualización de servidor, los Microsoft Endpoint Configuration Manager y los orígenes de actualizaciones de inteligencia de seguridad de Microsoft proporcionan actualizaciones menos frecuentes.</span><span class="sxs-lookup"><span data-stu-id="75753-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="75753-136">Por lo tanto, el delta puede ser más grande, lo que da como resultado descargas más grandes.</span><span class="sxs-lookup"><span data-stu-id="75753-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="75753-137">Si ha establecido las actualizaciones de la página de inteligencia de Seguridad de [Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx) como origen de reserva después de Windows Server Update Service o Microsoft Update, las actualizaciones solo se descargan de las actualizaciones de inteligencia de seguridad cuando la actualización actual se considera anticuada.</span><span class="sxs-lookup"><span data-stu-id="75753-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="75753-138">(De forma predeterminada, se trata de siete días consecutivos de no poder aplicar actualizaciones de los servicios Windows Server Update Service o Microsoft Update).</span><span class="sxs-lookup"><span data-stu-id="75753-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="75753-139">Sin embargo, puede establecer el número de días antes de que se notifica la protección [como desaprotebada](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span><span class="sxs-lookup"><span data-stu-id="75753-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="75753-140">A partir del lunes 21 de octubre de 2019, las actualizaciones de inteligencia de seguridad se firmarán exclusivamente con SHA-2.</span><span class="sxs-lookup"><span data-stu-id="75753-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="75753-141">Los dispositivos deben actualizarse para admitir SHA-2 con el fin de obtener las últimas actualizaciones de inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75753-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="75753-142">Para obtener más información, vea [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span><span class="sxs-lookup"><span data-stu-id="75753-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="75753-143">Cada origen tiene escenarios típicos que dependen de la configuración de la red, además de la frecuencia con la que publican actualizaciones, como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="75753-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="75753-144">Ubicación</span><span class="sxs-lookup"><span data-stu-id="75753-144">Location</span></span> | <span data-ttu-id="75753-145">Ejemplo ficticio</span><span class="sxs-lookup"><span data-stu-id="75753-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="75753-146">Windows Servicio de actualización de servidor</span><span class="sxs-lookup"><span data-stu-id="75753-146">Windows Server Update Service</span></span> | <span data-ttu-id="75753-147">Está usando el Windows de actualización de servidor para administrar las actualizaciones de la red.</span><span class="sxs-lookup"><span data-stu-id="75753-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="75753-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="75753-148">Microsoft Update</span></span> | <span data-ttu-id="75753-149">Desea que los puntos de conexión se conecten directamente a Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="75753-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="75753-150">Esto puede ser útil para los puntos de conexión que se conectan de forma irregular a la red empresarial, o si no usa Windows servicio de actualización de servidor para administrar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="75753-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="75753-151">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="75753-151">File share</span></span> | <span data-ttu-id="75753-152">Tiene dispositivos no conectados a Internet (como máquinas virtuales).</span><span class="sxs-lookup"><span data-stu-id="75753-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="75753-153">Puede usar el host de vm conectado a Internet para descargar las actualizaciones en un recurso compartido de red, desde el que las máquinas virtuales pueden obtener las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="75753-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="75753-154">Consulte la [guía de implementación de VDI](deployment-vdi-microsoft-defender-antivirus.md) para obtener información sobre cómo se pueden usar recursos compartidos de archivos en entornos de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="75753-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="75753-155">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="75753-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="75753-156">Está usando Microsoft Endpoint Manager para actualizar los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="75753-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="75753-157">Actualizaciones de inteligencia de seguridad Antivirus de Microsoft Defender y otros antimalware de Microsoft (anteriormente denominadas MMPC)</span><span class="sxs-lookup"><span data-stu-id="75753-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="75753-158">[Asegúrese de que los dispositivos estén actualizados para admitir SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span><span class="sxs-lookup"><span data-stu-id="75753-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="75753-159">Antivirus de Microsoft Defender Las actualizaciones de inteligencia de seguridad se entregan a través de Windows Update y, a partir del lunes 21 de octubre de 2019, las actualizaciones de inteligencia de seguridad se firmarán exclusivamente con SHA-2.</span><span class="sxs-lookup"><span data-stu-id="75753-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="75753-160">Descargue las actualizaciones de protección más recientes debido a una infección reciente o para ayudar a aprovisionar una imagen base sólida para la [implementación de VDI](deployment-vdi-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="75753-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="75753-161">Por lo general, esta opción solo se debe usar como origen final de reserva y no como origen principal.</span><span class="sxs-lookup"><span data-stu-id="75753-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="75753-162">Solo se usará si las actualizaciones no se pueden descargar desde Windows Server Update Service o Microsoft Update durante un número especificado [de días](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span><span class="sxs-lookup"><span data-stu-id="75753-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="75753-163">Puede administrar el orden en que se usan los orígenes de actualización con la directiva de grupo, los Microsoft Endpoint Configuration Manager, los cmdlets de PowerShell y WMI.</span><span class="sxs-lookup"><span data-stu-id="75753-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75753-164">Si establece el Windows de actualización de servidor como una ubicación de descarga, debe aprobar las actualizaciones, independientemente de la herramienta de administración que use para especificar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="75753-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="75753-165">Puede configurar una regla de aprobación automática con Windows servicio de actualización de servidor, lo que puede resultar útil a medida que las actualizaciones llegan al menos una vez al día.</span><span class="sxs-lookup"><span data-stu-id="75753-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="75753-166">Para obtener más información, vea [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="75753-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="75753-167">En los procedimientos de este artículo se describe primero cómo establecer el orden y, a continuación, cómo configurar la opción **Recurso** compartido de archivos si la ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="75753-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="75753-168">Usar la directiva de grupo para administrar la ubicación de actualización</span><span class="sxs-lookup"><span data-stu-id="75753-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="75753-169">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="75753-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="75753-170">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="75753-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="75753-171">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="75753-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="75753-172">Expanda el árbol para Windows **componentes > Windows Defender > actualizaciones de firma** y configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="75753-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="75753-173">Haga doble clic en **la opción Definir el orden de los orígenes para** descargar actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="75753-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="75753-174">Escriba el orden de los orígenes, separados por una sola canalización, por ejemplo: , como `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` se muestra en la siguiente captura de pantalla.</span><span class="sxs-lookup"><span data-stu-id="75753-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![Captura de pantalla de la configuración de directiva de grupo que enumera el orden de los orígenes](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="75753-176">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75753-176">Click **OK**.</span></span> <span data-ttu-id="75753-177">Esto establecerá el orden de los orígenes de actualización de protección.</span><span class="sxs-lookup"><span data-stu-id="75753-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="75753-178">Haga doble clic en la **opción Definir recursos compartidos de** archivos para descargar actualizaciones de inteligencia de seguridad y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="75753-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="75753-179">Escriba el origen del recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="75753-179">Enter the file share source.</span></span> <span data-ttu-id="75753-180">Si tiene varios orígenes, escriba cada origen en el orden en que deben usarse, separados por una sola canalización.</span><span class="sxs-lookup"><span data-stu-id="75753-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="75753-181">Use [la notación UNC estándar](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) para denoticar la ruta de acceso, por ejemplo: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .</span><span class="sxs-lookup"><span data-stu-id="75753-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="75753-182">Si no escribe ninguna ruta de acceso, se omitirá este origen cuando se actualice la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="75753-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="75753-183">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="75753-183">Click **OK**.</span></span> <span data-ttu-id="75753-184">Esto establecerá el orden de los recursos compartidos de archivos cuando se haga referencia a ese origen en la configuración de directiva de grupo Definir **el orden de orígenes...**</span><span class="sxs-lookup"><span data-stu-id="75753-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="75753-185">Para Windows 10, versiones 1703 hasta 1809 incluidas, la ruta de acceso de directiva es **componentes de Windows** > Antivirus de Microsoft Defender > Actualizaciones de firma Para Windows 10, versión 1903, la ruta de acceso de directiva es Windows Components > Antivirus de Microsoft Defender > Security Intelligence **Updates**</span><span class="sxs-lookup"><span data-stu-id="75753-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="75753-186">Usar Configuration Manager para administrar la ubicación de actualización</span><span class="sxs-lookup"><span data-stu-id="75753-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="75753-187">Consulte [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual).</span><span class="sxs-lookup"><span data-stu-id="75753-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="75753-188">Usar cmdlets de PowerShell para administrar la ubicación de actualización</span><span class="sxs-lookup"><span data-stu-id="75753-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="75753-189">Use los siguientes cmdlets de PowerShell para establecer el orden de actualización.</span><span class="sxs-lookup"><span data-stu-id="75753-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="75753-190">Vea los siguientes artículos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="75753-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="75753-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="75753-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="75753-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="75753-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="75753-193">Use cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75753-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-194">Cmdlets de Defender</span><span class="sxs-lookup"><span data-stu-id="75753-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="75753-195">Use Windows Management Instruction (WMI) para administrar la ubicación de actualización</span><span class="sxs-lookup"><span data-stu-id="75753-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="75753-196">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="75753-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="75753-197">Vea los siguientes artículos para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="75753-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="75753-198">Windows Defender API wmiv2</span><span class="sxs-lookup"><span data-stu-id="75753-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="75753-199">Usar administración de dispositivos móviles (MDM) para administrar la ubicación de actualización</span><span class="sxs-lookup"><span data-stu-id="75753-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="75753-200">Consulta [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) para obtener más información sobre cómo configurar MDM.</span><span class="sxs-lookup"><span data-stu-id="75753-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="75753-201">¿Qué ocurre si estamos usando un proveedor de terceros?</span><span class="sxs-lookup"><span data-stu-id="75753-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="75753-202">En este artículo se describe cómo configurar y administrar actualizaciones para Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="75753-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="75753-203">Sin embargo, se pueden usar proveedores de terceros para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="75753-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="75753-204">Por ejemplo, supongamos que Contoso ha contratado Fabrikam para administrar su solución de seguridad, que incluye Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="75753-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="75753-205">Fabrikam suele usar [Windows Management Instrumentation,](./use-wmi-microsoft-defender-antivirus.md)cmdlets de [PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)o Windows línea de comandos [para](./command-line-arguments-microsoft-defender-antivirus.md) implementar revisiones y actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="75753-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="75753-206">Microsoft no prueba soluciones de terceros para administrar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="75753-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="75753-207">Crear un recurso compartido UNC para actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="75753-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="75753-208">Configurar un recurso compartido de archivos de red (unidad asignada o UNC) para descargar actualizaciones de inteligencia de seguridad desde el sitio MMPC mediante una tarea programada.</span><span class="sxs-lookup"><span data-stu-id="75753-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="75753-209">En el sistema en el que desea aprovisionar el recurso compartido y descargar las actualizaciones, cree una carpeta en la que guardará el script.</span><span class="sxs-lookup"><span data-stu-id="75753-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="75753-210">Cree la carpeta en la que guardará las actualizaciones de firma.</span><span class="sxs-lookup"><span data-stu-id="75753-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="75753-211">Descargue el script de PowerShell desde [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span><span class="sxs-lookup"><span data-stu-id="75753-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="75753-212">Haga **clic en Descargar manualmente**.</span><span class="sxs-lookup"><span data-stu-id="75753-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="75753-213">Haga **clic en Descargar el archivo nupkg sin formato**.</span><span class="sxs-lookup"><span data-stu-id="75753-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="75753-214">Extraiga el archivo.</span><span class="sxs-lookup"><span data-stu-id="75753-214">Extract the file.</span></span>

7. <span data-ttu-id="75753-215">Copie el archivo SignatureDownloadCustomTask.ps1 a la carpeta que creó anteriormente, C:\Tool\PS-Scripts\ .</span><span class="sxs-lookup"><span data-stu-id="75753-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="75753-216">Use la línea de comandos para configurar la tarea programada.</span><span class="sxs-lookup"><span data-stu-id="75753-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="75753-217">Hay dos tipos de actualizaciones: full y delta.</span><span class="sxs-lookup"><span data-stu-id="75753-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="75753-218">Para x64 delta:</span><span class="sxs-lookup"><span data-stu-id="75753-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="75753-219">Para x64 completo:</span><span class="sxs-lookup"><span data-stu-id="75753-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="75753-220">Para x86 delta:</span><span class="sxs-lookup"><span data-stu-id="75753-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - <span data-ttu-id="75753-221">Para x86 completo:</span><span class="sxs-lookup"><span data-stu-id="75753-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > <span data-ttu-id="75753-222">Cuando se crean las tareas programadas, puede encontrar estas en el Programador de tareas en Microsoft\Windows\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="75753-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="75753-223">Ejecute cada tarea manualmente y compruebe que tiene datos (mpam-d.exe, mpam-fe.exe y nis_full.exe) en las siguientes carpetas (es posible que haya elegido diferentes ubicaciones):</span><span class="sxs-lookup"><span data-stu-id="75753-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="75753-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="75753-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="75753-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="75753-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="75753-226">Si se produce un error en la tarea programada, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="75753-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > <span data-ttu-id="75753-227">Los problemas también podrían deberse a la directiva de ejecución.</span><span class="sxs-lookup"><span data-stu-id="75753-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="75753-228">Cree un recurso compartido que apunte a C:\Temp\TempSigs (por \\ ejemplo, server\updates).</span><span class="sxs-lookup"><span data-stu-id="75753-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="75753-229">Como mínimo, los usuarios autenticados deben tener acceso de "Lectura".</span><span class="sxs-lookup"><span data-stu-id="75753-229">At a minimum, authenticated users must have "Read" access.</span></span>
11. <span data-ttu-id="75753-230">Establezca la ubicación del recurso compartido en la directiva en el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="75753-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75753-231">No agregue la carpeta x64 (o x86) en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="75753-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="75753-232">El mpcmdrun.exe agrega automáticamente.</span><span class="sxs-lookup"><span data-stu-id="75753-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="75753-233">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="75753-233">Related articles</span></span>

- [<span data-ttu-id="75753-234">Implementar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75753-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-235">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="75753-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-236">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="75753-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-237">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="75753-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-238">Administrar actualizaciones para dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="75753-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="75753-239">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="75753-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
