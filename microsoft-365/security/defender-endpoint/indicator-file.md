---
title: Crear indicadores para los archivos
ms.reviewer: ''
description: Cree indicadores para un hash de archivo que defina la detección, prevención y exclusión de entidades.
keywords: file, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256920"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="22c1c-104">Crear indicadores para los archivos</span><span class="sxs-lookup"><span data-stu-id="22c1c-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22c1c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="22c1c-105">**Applies to:**</span></span>
- [<span data-ttu-id="22c1c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="22c1c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22c1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22c1c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="22c1c-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="22c1c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="22c1c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="22c1c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="22c1c-110">Impedir la propagación posterior de un ataque en la organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="22c1c-110">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="22c1c-111">Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="22c1c-112">Esta operación evitará que se lea, se escriba o se ejecute en dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="22c1c-112">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="22c1c-113">Hay tres formas de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="22c1c-113">There are three ways you can create indicators for files:</span></span>

- <span data-ttu-id="22c1c-114">Al crear un indicador a través de la página de configuración</span><span class="sxs-lookup"><span data-stu-id="22c1c-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="22c1c-115">Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="22c1c-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>
- <span data-ttu-id="22c1c-116">Al crear un indicador a través de la [API de indicadores](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="22c1c-116">By creating an indicator through the [Indicator API](ti-indicator.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="22c1c-117">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="22c1c-117">Before you begin</span></span>

<span data-ttu-id="22c1c-118">Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="22c1c-118">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="22c1c-119">Esta característica está disponible si su organización usa **Antivirus de Microsoft Defender (en** modo activo) y la **protección basada en la nube está habilitada.**</span><span class="sxs-lookup"><span data-stu-id="22c1c-119">This feature is available if your organization uses **Microsoft Defender Antivirus (in active mode)** and **Cloud-based protection is enabled**.</span></span> <span data-ttu-id="22c1c-120">Para obtener más información, vea [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="22c1c-120">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>

- <span data-ttu-id="22c1c-121">La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.</span><span class="sxs-lookup"><span data-stu-id="22c1c-121">The Antimalware client version must be 4.18.1901.x or later.</span></span> <span data-ttu-id="22c1c-122">Ver [Versiones mensuales de la plataforma y el motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span><span class="sxs-lookup"><span data-stu-id="22c1c-122">See [Monthly platform and engine versions](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)</span></span>

- <span data-ttu-id="22c1c-123">Compatible con dispositivos con Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="22c1c-123">Supported on devices with Windows 10, version 1703 or later, Windows Server 2016 and 2019.</span></span>

- <span data-ttu-id="22c1c-124">Para empezar a bloquear archivos, primero debe activar [la característica "bloquear](advanced-features.md) o permitir" en Configuración.</span><span class="sxs-lookup"><span data-stu-id="22c1c-124">To start blocking files, you first need to [turn on the "block or allow" feature](advanced-features.md) in Settings.</span></span>

<span data-ttu-id="22c1c-125">Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web.</span><span class="sxs-lookup"><span data-stu-id="22c1c-125">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="22c1c-126">Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos .exe archivos .dll archivos.</span><span class="sxs-lookup"><span data-stu-id="22c1c-126">It currently supports portable executable (PE) files, including .exe and .dll files.</span></span> <span data-ttu-id="22c1c-127">La cobertura se extenderá con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-127">The coverage will be extended over time.</span></span>

## <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="22c1c-128">Crear un indicador para archivos desde la página de configuración</span><span class="sxs-lookup"><span data-stu-id="22c1c-128">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="22c1c-129">En el panel de navegación, **seleccione Configuración > Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="22c1c-129">In the navigation pane, select **Settings > Indicators**.</span></span>

2. <span data-ttu-id="22c1c-130">Seleccione la **pestaña Hash de**   archivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-130">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="22c1c-131">Seleccione **Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="22c1c-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="22c1c-132">Especifique los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="22c1c-132">Specify the following details:</span></span>
    - <span data-ttu-id="22c1c-133">Indicador: especifique los detalles de la entidad y defina la expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="22c1c-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
    - <span data-ttu-id="22c1c-134">Action: especifique la acción que se va a realizar y proporcione una descripción.</span><span class="sxs-lookup"><span data-stu-id="22c1c-134">Action - Specify the action to be taken and provide a description.</span></span>
    - <span data-ttu-id="22c1c-135">Ámbito: defina el ámbito del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22c1c-135">Scope - Define the scope of the device group.</span></span>

5. <span data-ttu-id="22c1c-136">Revise los detalles de la pestaña Resumen y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="22c1c-136">Review the details in the Summary tab, then select **Save**.</span></span>

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="22c1c-137">Crear un indicador contextual desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="22c1c-137">Create a contextual indicator from the file details page</span></span>

<span data-ttu-id="22c1c-138">Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md)es agregar un indicador para el   archivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-138">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> <span data-ttu-id="22c1c-139">Cuando agregas un hash de indicador para un archivo, puedes elegir generar una alerta y bloquear el archivo siempre que un dispositivo de la organización intente ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-139">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="22c1c-140">Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.</span><span class="sxs-lookup"><span data-stu-id="22c1c-140">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="22c1c-141">Normalmente, los bloques de archivos se aplican y se quitan en un par de minutos, pero pueden tardar más de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="22c1c-141">Typically, file blocks are enforced and removed within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> 
>- <span data-ttu-id="22c1c-142">Si hay directivas de IoC de archivos en conflicto con el mismo tipo de aplicación y destino, se aplicará la directiva del hash más seguro.</span><span class="sxs-lookup"><span data-stu-id="22c1c-142">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure hash will be applied.</span></span> <span data-ttu-id="22c1c-143">Una directiva de IoC de hash de archivo SHA-256 ganará una directiva de IoC de hash de archivo SHA-1, que ganará una directiva de IoC de hash de archivo MD5 si los tipos hash definen el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-143">An SHA-256 file hash IoC policy will win over an SHA-1 file hash IoC policy, which will win over an MD5 file hash IoC policy if the hash types define the same file.</span></span> <span data-ttu-id="22c1c-144">Esto siempre es así independientemente del grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22c1c-144">This is always true regardless of the device group.</span></span> 
>   <span data-ttu-id="22c1c-145">En todos los demás casos, si las directivas de IoC de archivos en conflicto con el mismo destino de aplicación se aplican a todos los dispositivos y al grupo del dispositivo, en el caso de un dispositivo, la directiva del grupo de dispositivos ganará.</span><span class="sxs-lookup"><span data-stu-id="22c1c-145">In all other cases, if conflicting file IoC policies with the same enforcement target are applied to all devices and to the device’s group, then for a device, the policy in the device group will win.</span></span> 
>   
>- <span data-ttu-id="22c1c-146">Si la directiva de grupo EnableFileHashComputation está deshabilitada, se reduce la precisión de bloqueo del archivo IoC.</span><span class="sxs-lookup"><span data-stu-id="22c1c-146">If the EnableFileHashComputation group policy is disabled, the blocking accuracy of the file IoC is reduced.</span></span> <span data-ttu-id="22c1c-147">Sin embargo, la `EnableFileHashComputation` habilitación puede afectar al rendimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-147">However, enabling `EnableFileHashComputation` may impact device performance.</span></span> <span data-ttu-id="22c1c-148">Por ejemplo, copiar archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN, puede tener un efecto en el rendimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-148">For example, copying large files from a network share onto your local device, especially over a VPN connection, might have an effect on device performance.</span></span>
>
>   <span data-ttu-id="22c1c-149">Para obtener más información acerca de la directiva de grupo EnableFileHashComputation, vea [Defender CSP](/windows/client-management/mdm/defender-csp)</span><span class="sxs-lookup"><span data-stu-id="22c1c-149">For more information about the EnableFileHashComputation group policy, see [Defender CSP](/windows/client-management/mdm/defender-csp)</span></span>

## <a name="policy-conflict-handling"></a><span data-ttu-id="22c1c-150">Control de conflictos de directivas</span><span class="sxs-lookup"><span data-stu-id="22c1c-150">Policy conflict handling</span></span>  

<span data-ttu-id="22c1c-151">Los conflictos de administración de directivas de Cert y File IoC seguirán el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="22c1c-151">Cert and File IoC policy handling conflict will follow the below order:</span></span>

- <span data-ttu-id="22c1c-152">Si el archivo no está permitido por Windows Defender control de aplicaciones y AppLocker aplican directivas o directivas de modo, **bloquee**</span><span class="sxs-lookup"><span data-stu-id="22c1c-152">If the file is not allowed by Windows Defender Application Control and AppLocker enforce mode policy/policies, then **Block**</span></span>

- <span data-ttu-id="22c1c-153">Si el archivo está permitido por la exclusión Antivirus de Microsoft Defender, **permitir**</span><span class="sxs-lookup"><span data-stu-id="22c1c-153">Else if the file is allowed by the Microsoft Defender Antivirus exclusion, then **Allow**</span></span>

- <span data-ttu-id="22c1c-154">De lo contrario, si un bloqueo o un archivo de advertencia bloquean o advierten el archivo IoC, **bloquee o advierte el archivo.**</span><span class="sxs-lookup"><span data-stu-id="22c1c-154">Else if the file is blocked or warned by a block or warn file IoC, then **Block/Warn**</span></span>

- <span data-ttu-id="22c1c-155">De lo contrario, si el archivo está permitido por una directiva de IoC de archivo de permitido, **permitir**</span><span class="sxs-lookup"><span data-stu-id="22c1c-155">Else if the file is allowed by an allow file IoC policy, then **Allow**</span></span>

- <span data-ttu-id="22c1c-156">De lo contrario, si el archivo está bloqueado por reglas ASR, CFA, AV, SmartScreen y, a continuación, **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="22c1c-156">Else if the file is blocked by ASR rules, CFA, AV, SmartScreen, then **Block**</span></span>  

- <span data-ttu-id="22c1c-157">Else **Allow** (pasa Windows Defender control de & directiva de AppLocker, no se aplica ninguna regla de IoC)</span><span class="sxs-lookup"><span data-stu-id="22c1c-157">Else **Allow** (passes Windows Defender Application Control & AppLocker policy, no IoC rules apply to it)</span></span>

<span data-ttu-id="22c1c-158">Si hay directivas de IoC de archivos en conflicto con el mismo tipo de aplicación y destino, se aplicará la directiva del hash más seguro (es decir, más largo).</span><span class="sxs-lookup"><span data-stu-id="22c1c-158">If there are conflicting file IoC policies with the same enforcement type and target, the policy of the more secure (meaning longer) hash will be applied.</span></span> <span data-ttu-id="22c1c-159">Por ejemplo, una directiva de IoC de hash de archivo SHA-256 ganará una directiva de IoC de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="22c1c-159">For example, an SHA-256 file hash IoC policy will win over an MD5 file hash IoC policy if both hash types define the same file.</span></span>

<span data-ttu-id="22c1c-160">Las características de aplicación vulnerables de bloqueo de amenazas y administración de vulnerabilidades usan el archivo IoCs para la aplicación y seguirán el orden de control de conflictos anterior.</span><span class="sxs-lookup"><span data-stu-id="22c1c-160">Threat and vulnerability management's block vulnerable application features uses the file IoCs for enforcement and will follow the above conflict handling order.</span></span>

### <a name="examples"></a><span data-ttu-id="22c1c-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="22c1c-161">Examples</span></span>

|<span data-ttu-id="22c1c-162">Componente</span><span class="sxs-lookup"><span data-stu-id="22c1c-162">Component</span></span> |<span data-ttu-id="22c1c-163">Aplicación de componentes</span><span class="sxs-lookup"><span data-stu-id="22c1c-163">Component enforcement</span></span> |<span data-ttu-id="22c1c-164">Indicador de archivo Acción</span><span class="sxs-lookup"><span data-stu-id="22c1c-164">File indicator Action</span></span> |<span data-ttu-id="22c1c-165">Resultado</span><span class="sxs-lookup"><span data-stu-id="22c1c-165">Result</span></span>
|--|--|--|--|
|<span data-ttu-id="22c1c-166">Exclusión de ruta de acceso de archivo de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="22c1c-166">Attack surface reduction file path exclusion</span></span> |<span data-ttu-id="22c1c-167">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-167">Allow</span></span> |<span data-ttu-id="22c1c-168">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-168">Block</span></span> |<span data-ttu-id="22c1c-169">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-169">Block</span></span>
|<span data-ttu-id="22c1c-170">Regla de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="22c1c-170">Attack surface reduction rule</span></span> |<span data-ttu-id="22c1c-171">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-171">Block</span></span> |<span data-ttu-id="22c1c-172">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-172">Allow</span></span> |<span data-ttu-id="22c1c-173">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-173">Allow</span></span>
|<span data-ttu-id="22c1c-174">Control de aplicaciones de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="22c1c-174">Windows Defender Application Control</span></span> |<span data-ttu-id="22c1c-175">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-175">Allow</span></span> |<span data-ttu-id="22c1c-176">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-176">Block</span></span> |<span data-ttu-id="22c1c-177">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-177">Allow</span></span> |
|<span data-ttu-id="22c1c-178">Control de aplicaciones de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="22c1c-178">Windows Defender Application Control</span></span> |<span data-ttu-id="22c1c-179">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-179">Block</span></span> |<span data-ttu-id="22c1c-180">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-180">Allow</span></span> |<span data-ttu-id="22c1c-181">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-181">Block</span></span>
|<span data-ttu-id="22c1c-182">Antivirus de Microsoft Defender exclusión</span><span class="sxs-lookup"><span data-stu-id="22c1c-182">Microsoft Defender Antivirus exclusion</span></span> |<span data-ttu-id="22c1c-183">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-183">Allow</span></span> |<span data-ttu-id="22c1c-184">Bloquear</span><span class="sxs-lookup"><span data-stu-id="22c1c-184">Block</span></span> |<span data-ttu-id="22c1c-185">Permitir</span><span class="sxs-lookup"><span data-stu-id="22c1c-185">Allow</span></span>

## <a name="see-also"></a><span data-ttu-id="22c1c-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22c1c-186">See also</span></span>

- [<span data-ttu-id="22c1c-187">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="22c1c-187">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="22c1c-188">Crear indicadores para direcciones IP y URL/dominios</span><span class="sxs-lookup"><span data-stu-id="22c1c-188">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="22c1c-189">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="22c1c-189">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="22c1c-190">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="22c1c-190">Manage indicators</span></span>](indicator-manage.md)
