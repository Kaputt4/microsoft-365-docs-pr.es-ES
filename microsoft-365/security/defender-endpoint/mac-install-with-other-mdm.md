---
title: Implementación con un sistema de administración de dispositivos móviles (MDM) diferente para ATP de Microsoft Defender para Mac
description: Instale ATP de Microsoft Defender para Mac en otras soluciones de administración.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 28e57f1749ea9dce22e1a8a210f73cc3c7993738
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074880"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="357a8-104">Implementación con un sistema de administración de dispositivos móviles (MDM) diferente para Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="357a8-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="357a8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="357a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="357a8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="357a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="357a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="357a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="357a8-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="357a8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="357a8-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="357a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="357a8-110">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="357a8-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="357a8-111">Antes de empezar, consulta la página principal de [Microsoft Defender para](microsoft-defender-endpoint-mac.md) Endpoint para Mac para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.</span><span class="sxs-lookup"><span data-stu-id="357a8-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="357a8-112">Enfoque</span><span class="sxs-lookup"><span data-stu-id="357a8-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="357a8-113">Actualmente, Microsoft solo admite Intune y JAMF para la implementación y administración de Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="357a8-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="357a8-114">Microsoft no ofrece garantías, explícitas o implícitas, con respecto a la información que se proporciona a continuación.</span><span class="sxs-lookup"><span data-stu-id="357a8-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="357a8-115">Si su organización usa una solución de administración de dispositivos móviles (MDM) que no es compatible oficialmente, esto no significa que no pueda implementar o ejecutar Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="357a8-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="357a8-116">Microsoft Defender para Endpoint para Mac no depende de las características específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="357a8-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="357a8-117">Se puede usar con cualquier solución MDM que admita las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="357a8-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="357a8-118">Implementar un .pkg de macOS en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="357a8-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="357a8-119">Implementar perfiles de configuración del sistema macOS en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="357a8-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="357a8-120">Ejecute una herramienta o un script arbitrarios configurados por el administrador en dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="357a8-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="357a8-121">La mayoría de las soluciones MDM modernas incluyen estas características, sin embargo, pueden llamarlas de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="357a8-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="357a8-122">Sin embargo, puede implementar Defender sin el último requisito de la lista anterior:</span><span class="sxs-lookup"><span data-stu-id="357a8-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="357a8-123">No podrá recopilar el estado de forma centralizada</span><span class="sxs-lookup"><span data-stu-id="357a8-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="357a8-124">Si decide desinstalar Defender, tendrá que iniciar sesión en el dispositivo cliente localmente como administrador</span><span class="sxs-lookup"><span data-stu-id="357a8-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="357a8-125">Implementación</span><span class="sxs-lookup"><span data-stu-id="357a8-125">Deployment</span></span>

<span data-ttu-id="357a8-126">La mayoría de las soluciones MDM usan el mismo modelo para administrar dispositivos macOS, con terminología similar.</span><span class="sxs-lookup"><span data-stu-id="357a8-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="357a8-127">Use [la implementación basada en JAMF](mac-install-with-jamf.md) como plantilla.</span><span class="sxs-lookup"><span data-stu-id="357a8-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="357a8-128">Paquete</span><span class="sxs-lookup"><span data-stu-id="357a8-128">Package</span></span>

<span data-ttu-id="357a8-129">Configure la implementación de un [paquete de aplicación](mac-install-with-jamf.md)necesario, con el paquete de instalación (wdav.pkg) descargado del Centro de seguridad de Microsoft [Defender](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="357a8-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="357a8-130">Para implementar el paquete en tu empresa, usa las instrucciones asociadas con la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="357a8-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="357a8-131">Configuración de licencia</span><span class="sxs-lookup"><span data-stu-id="357a8-131">License settings</span></span>

<span data-ttu-id="357a8-132">Configurar un [perfil de configuración del sistema](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="357a8-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="357a8-133">La solución MDM puede llamarla algo así como "Perfil de configuración personalizada", ya que Microsoft Defender para Endpoint para Mac no forma parte de macOS.</span><span class="sxs-lookup"><span data-stu-id="357a8-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="357a8-134">Usa la lista de propiedades, jamf/WindowsDefenderATPOnboarding.plist, que se puede extraer de un paquete de incorporación descargado del Centro de seguridad [de Microsoft Defender](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="357a8-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="357a8-135">El sistema puede admitir una lista de propiedades arbitrarias en formato XML.</span><span class="sxs-lookup"><span data-stu-id="357a8-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="357a8-136">Puedes cargar el archivo jamf/WindowsDefenderATPOnboarding.plist tal como está en ese caso.</span><span class="sxs-lookup"><span data-stu-id="357a8-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="357a8-137">Como alternativa, es posible que primero necesites convertir la lista de propiedades a otro formato.</span><span class="sxs-lookup"><span data-stu-id="357a8-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="357a8-138">Normalmente, el perfil personalizado tiene un identificador, un nombre o un atributo de dominio.</span><span class="sxs-lookup"><span data-stu-id="357a8-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="357a8-139">Debe usar exactamente "com.microsoft.wdav.atp" para este valor.</span><span class="sxs-lookup"><span data-stu-id="357a8-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="357a8-140">MDM lo usa para implementar el archivo de configuración en **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** en un dispositivo cliente y Defender usa este archivo para cargar la información de incorporación.</span><span class="sxs-lookup"><span data-stu-id="357a8-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="357a8-141">Directiva de extensión de kernel</span><span class="sxs-lookup"><span data-stu-id="357a8-141">Kernel extension policy</span></span>

<span data-ttu-id="357a8-142">Configurar una directiva de extensión de kernel o KEXT.</span><span class="sxs-lookup"><span data-stu-id="357a8-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="357a8-143">Use el identificador de equipo **UBF8T346G9** para permitir extensiones de kernel proporcionadas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="357a8-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="357a8-144">Directiva de extensión del sistema</span><span class="sxs-lookup"><span data-stu-id="357a8-144">System extension policy</span></span>

<span data-ttu-id="357a8-145">Configurar una directiva de extensión del sistema.</span><span class="sxs-lookup"><span data-stu-id="357a8-145">Set up a system extension policy.</span></span> <span data-ttu-id="357a8-146">Use el identificador de equipo **UBF8T346G9** y apruebe los siguientes identificadores de agrupación:</span><span class="sxs-lookup"><span data-stu-id="357a8-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="357a8-147">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="357a8-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="357a8-148">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="357a8-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="357a8-149">Directiva de acceso a disco completo</span><span class="sxs-lookup"><span data-stu-id="357a8-149">Full disk access policy</span></span>

<span data-ttu-id="357a8-150">Conceder acceso en disco completo a los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="357a8-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="357a8-151">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="357a8-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="357a8-152">Identificador: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="357a8-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="357a8-153">Tipo de identificador: Id. de agrupación</span><span class="sxs-lookup"><span data-stu-id="357a8-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="357a8-154">Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="357a8-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="357a8-155">Microsoft Defender para la extensión de seguridad de extremo</span><span class="sxs-lookup"><span data-stu-id="357a8-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="357a8-156">Identificador: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="357a8-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="357a8-157">Tipo de identificador: Id. de agrupación</span><span class="sxs-lookup"><span data-stu-id="357a8-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="357a8-158">Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="357a8-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="357a8-159">Directiva de extensión de red</span><span class="sxs-lookup"><span data-stu-id="357a8-159">Network extension policy</span></span>

<span data-ttu-id="357a8-160">Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint para Mac inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="357a8-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="357a8-161">La siguiente directiva permite que la extensión de red realice esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="357a8-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="357a8-162">Tipo de filtro: Complemento</span><span class="sxs-lookup"><span data-stu-id="357a8-162">Filter type: Plugin</span></span>
- <span data-ttu-id="357a8-163">Identificador de agrupación de complementos: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="357a8-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="357a8-164">Identificador de agrupación del proveedor de datos de filtro: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="357a8-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="357a8-165">Requisito designado por el proveedor de datos de filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="357a8-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="357a8-166">Sockets de filtro: `true`</span><span class="sxs-lookup"><span data-stu-id="357a8-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="357a8-167">Comprobar el estado de la instalación</span><span class="sxs-lookup"><span data-stu-id="357a8-167">Check installation status</span></span>

<span data-ttu-id="357a8-168">Ejecute [Microsoft Defender para endpoint](mac-install-with-jamf.md) en un dispositivo cliente para comprobar el estado de incorporación.</span><span class="sxs-lookup"><span data-stu-id="357a8-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
