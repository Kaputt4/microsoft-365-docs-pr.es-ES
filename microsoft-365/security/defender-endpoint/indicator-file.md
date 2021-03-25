---
title: Crear indicadores para archivos
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
ms.openlocfilehash: 4edff7a9c7f541e31363519e4bafc2a21602e011
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075752"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="211e9-104">Crear indicadores para archivos</span><span class="sxs-lookup"><span data-stu-id="211e9-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="211e9-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="211e9-105">**Applies to:**</span></span>
- [<span data-ttu-id="211e9-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="211e9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="211e9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="211e9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="211e9-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="211e9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="211e9-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="211e9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="211e9-110">Puede evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="211e9-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="211e9-111">Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo.</span><span class="sxs-lookup"><span data-stu-id="211e9-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="211e9-112">Esta operación evitará que se lea, se escriba o se ejecute en equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="211e9-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="211e9-113">Hay dos formas de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="211e9-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="211e9-114">Al crear un indicador a través de la página de configuración</span><span class="sxs-lookup"><span data-stu-id="211e9-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="211e9-115">Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="211e9-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="211e9-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="211e9-116">Before you begin</span></span>
<span data-ttu-id="211e9-117">Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="211e9-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="211e9-118">Esta característica está disponible si su organización usa Windows Defender antivirus y la protección basada en la nube está habilitada.</span><span class="sxs-lookup"><span data-stu-id="211e9-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="211e9-119">Para obtener más información, vea [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="211e9-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="211e9-120">La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.</span><span class="sxs-lookup"><span data-stu-id="211e9-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="211e9-121">Compatible con máquinas en Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="211e9-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="211e9-122">Para empezar a bloquear archivos, primero debe activar [la característica Bloquear **o**](advanced-features.md) permitir en Configuración.</span><span class="sxs-lookup"><span data-stu-id="211e9-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="211e9-123">Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web.</span><span class="sxs-lookup"><span data-stu-id="211e9-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="211e9-124">Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos los archivos _.exe_ y _.dll._</span><span class="sxs-lookup"><span data-stu-id="211e9-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="211e9-125">La cobertura se extenderá con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="211e9-125">The coverage will be extended over time.</span></span>

>[!IMPORTANT]
>- <span data-ttu-id="211e9-126">La función permitir o bloquear no se puede realizar en archivos si la clasificación del archivo existe en la memoria caché del dispositivo antes de la acción permitir o bloquear</span><span class="sxs-lookup"><span data-stu-id="211e9-126">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
>- <span data-ttu-id="211e9-127">Los archivos firmados de confianza se tratarán de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="211e9-127">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="211e9-128">Defender for Endpoint está optimizado para controlar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="211e9-128">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="211e9-129">Intentar bloquear archivos firmados de confianza, en algunos casos, puede tener implicaciones en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="211e9-129">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>

 
>[!NOTE]
><span data-ttu-id="211e9-130">Normalmente, los bloques de archivos se aplican en un par de minutos, pero pueden tardar más de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="211e9-130">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="211e9-131">Crear un indicador para archivos desde la página de configuración</span><span class="sxs-lookup"><span data-stu-id="211e9-131">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="211e9-132">En el panel de navegación, seleccione  >  **Indicadores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="211e9-132">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="211e9-133">Seleccione la **pestaña Hash de** archivo.</span><span class="sxs-lookup"><span data-stu-id="211e9-133">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="211e9-134">Seleccione **Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="211e9-134">Select **Add indicator**.</span></span>

4. <span data-ttu-id="211e9-135">Especifique los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="211e9-135">Specify the following details:</span></span>
   - <span data-ttu-id="211e9-136">Indicador: especifique los detalles de la entidad y defina la expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="211e9-136">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="211e9-137">Action: especifique la acción que se va a realizar y proporcione una descripción.</span><span class="sxs-lookup"><span data-stu-id="211e9-137">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="211e9-138">Ámbito: defina el ámbito del grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="211e9-138">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="211e9-139">Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.</span><span class="sxs-lookup"><span data-stu-id="211e9-139">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="211e9-140">Crear un indicador contextual desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="211e9-140">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="211e9-141">Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md) es agregar un indicador para el archivo.</span><span class="sxs-lookup"><span data-stu-id="211e9-141">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="211e9-142">Al agregar un hash de indicador para un archivo, puede optar por generar una alerta y bloquear el archivo siempre que un equipo de la organización intente ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="211e9-142">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="211e9-143">Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.</span><span class="sxs-lookup"><span data-stu-id="211e9-143">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="211e9-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="211e9-144">Related topics</span></span>
- [<span data-ttu-id="211e9-145">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="211e9-145">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="211e9-146">Crear indicadores para direcciones IP y direcciones URL/dominios</span><span class="sxs-lookup"><span data-stu-id="211e9-146">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="211e9-147">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="211e9-147">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="211e9-148">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="211e9-148">Manage indicators</span></span>](indicator-manage.md)
