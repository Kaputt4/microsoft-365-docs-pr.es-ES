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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199614"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="2b9a7-104">Crear indicadores para archivos</span><span class="sxs-lookup"><span data-stu-id="2b9a7-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2b9a7-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2b9a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b9a7-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2b9a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b9a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b9a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="2b9a7-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2b9a7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2b9a7-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="2b9a7-110">Puede evitar la propagación posterior de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o malware sospechoso.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="2b9a7-111">Si conoce un archivo ejecutable portátil (PE) potencialmente malintencionado, puede bloquearlo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="2b9a7-112">Esta operación evitará que se lea, se escriba o se ejecute en equipos de la organización.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="2b9a7-113">Hay dos formas de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="2b9a7-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="2b9a7-114">Al crear un indicador a través de la página de configuración</span><span class="sxs-lookup"><span data-stu-id="2b9a7-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="2b9a7-115">Al crear un indicador contextual mediante el botón agregar indicador desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="2b9a7-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="2b9a7-116">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2b9a7-116">Before you begin</span></span>
<span data-ttu-id="2b9a7-117">Es importante comprender los siguientes requisitos previos antes de crear indicadores para archivos:</span><span class="sxs-lookup"><span data-stu-id="2b9a7-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="2b9a7-118">Esta característica está disponible si su organización usa Windows Defender antivirus y la protección basada en la nube está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="2b9a7-119">Para obtener más información, vea [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="2b9a7-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="2b9a7-120">La versión del cliente Antimalware debe ser 4.18.1901.x o posterior.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="2b9a7-121">Compatible con máquinas en Windows 10, versión 1703 o posterior, Windows Server 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="2b9a7-122">Para empezar a bloquear archivos, primero debe activar [la característica Bloquear **o**](advanced-features.md) permitir en Configuración.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="2b9a7-123">Esta característica está diseñada para evitar que el malware sospechoso (o los archivos potencialmente malintencionados) se descarguen de la web.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="2b9a7-124">Actualmente es compatible con archivos ejecutables portátiles (PE), incluidos los archivos _.exe_ y _.dll._</span><span class="sxs-lookup"><span data-stu-id="2b9a7-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="2b9a7-125">La cobertura se extenderá con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-125">The coverage will be extended over time.</span></span>

<span data-ttu-id="2b9a7-126">El rendimiento puede verse afectado si estás copiando archivos grandes de un recurso compartido de red en el dispositivo local, especialmente a través de una conexión VPN.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-126">Performance can be affected if you are copying large files from a network share onto your local device, especially over a VPN connection.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="2b9a7-127">La función permitir o bloquear no se puede realizar en archivos si la clasificación del archivo existe en la memoria caché del dispositivo antes de la acción permitir o bloquear</span><span class="sxs-lookup"><span data-stu-id="2b9a7-127">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
> - <span data-ttu-id="2b9a7-128">Los archivos firmados de confianza se tratarán de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-128">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="2b9a7-129">Defender for Endpoint está optimizado para controlar archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-129">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="2b9a7-130">Intentar bloquear archivos firmados de confianza, en algunos casos, puede tener implicaciones en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-130">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>
> - <span data-ttu-id="2b9a7-131">Normalmente, los bloques de archivos se aplican en un par de minutos, pero pueden tardar más de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-131">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> - <span data-ttu-id="2b9a7-132">Si hay directivas de indicador de archivos en conflicto, se aplica la directiva de cumplimiento de la directiva más segura.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-132">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="2b9a7-133">Por ejemplo, una directiva de indicador hash de archivo SHA-256 tiene prioridad sobre una directiva de indicador de hash de archivo MD5 si ambos tipos de hash definen el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-133">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="2b9a7-134">Crear un indicador para archivos desde la página de configuración</span><span class="sxs-lookup"><span data-stu-id="2b9a7-134">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="2b9a7-135">En el panel de navegación, seleccione  >  **Indicadores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-135">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="2b9a7-136">Seleccione la **pestaña Hash de** archivo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-136">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="2b9a7-137">Seleccione **Agregar indicador**.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-137">Select **Add indicator**.</span></span>

4. <span data-ttu-id="2b9a7-138">Especifique los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="2b9a7-138">Specify the following details:</span></span>
   - <span data-ttu-id="2b9a7-139">Indicador: especifique los detalles de la entidad y defina la expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-139">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="2b9a7-140">Action: especifique la acción que se va a realizar y proporcione una descripción.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-140">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="2b9a7-141">Ámbito: defina el ámbito del grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-141">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="2b9a7-142">Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-142">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="2b9a7-143">Crear un indicador contextual desde la página de detalles del archivo</span><span class="sxs-lookup"><span data-stu-id="2b9a7-143">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="2b9a7-144">Una de las opciones al realizar acciones [de respuesta en un archivo](respond-file-alerts.md) es agregar un indicador para el archivo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-144">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="2b9a7-145">Al agregar un hash de indicador para un archivo, puede optar por generar una alerta y bloquear el archivo siempre que un equipo de la organización intente ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-145">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="2b9a7-146">Los archivos bloqueados automáticamente por un indicador no aparecerán en el Centro de acciones del archivo, pero las alertas seguirán estando visibles en la cola de alertas.</span><span class="sxs-lookup"><span data-stu-id="2b9a7-146">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2b9a7-147">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2b9a7-147">Related topics</span></span>
- [<span data-ttu-id="2b9a7-148">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="2b9a7-148">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="2b9a7-149">Crear indicadores para direcciones IP y direcciones URL/dominios</span><span class="sxs-lookup"><span data-stu-id="2b9a7-149">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="2b9a7-150">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="2b9a7-150">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="2b9a7-151">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="2b9a7-151">Manage indicators</span></span>](indicator-manage.md)
