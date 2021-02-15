---
title: Comprobador de la evaluación de preparación descargable
description: Comprueba la configuración de dispositivo y red, incluidos los puntos de conexión necesarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922025"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="4a163-104">Comprobador de la evaluación de preparación descargable</span><span class="sxs-lookup"><span data-stu-id="4a163-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="4a163-105">Para funcionar bien con el Escritorio administrado de Microsoft, los dispositivos deben cumplir ciertos requisitos de hardware y configuración.</span><span class="sxs-lookup"><span data-stu-id="4a163-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="4a163-106">Además, cada dispositivo debe ser capaz de alcanzar puntos de conexión clave.</span><span class="sxs-lookup"><span data-stu-id="4a163-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="4a163-107">Descargue y ejecute esta herramienta para obtener un informe HTML, ver los resultados y, a continuación, tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="4a163-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="4a163-108">Deberás descargar la herramienta y los archivos de soporte técnico y, a continuación, ejecutarla manualmente en cada dispositivo que quieras inscribir en el Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a163-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a163-109">Para cada comprobación, la herramienta mostrará uno de los tres resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="4a163-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="4a163-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="4a163-110">Result</span></span>  |<span data-ttu-id="4a163-111">Significado</span><span class="sxs-lookup"><span data-stu-id="4a163-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4a163-112">Listo</span><span class="sxs-lookup"><span data-stu-id="4a163-112">Ready</span></span>     | <span data-ttu-id="4a163-113">No se requiere ninguna acción antes de completar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="4a163-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="4a163-114">Aviso</span><span class="sxs-lookup"><span data-stu-id="4a163-114">Advisory</span></span>    | <span data-ttu-id="4a163-115">Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4a163-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4a163-116">Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4a163-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4a163-117">No preparado</span><span class="sxs-lookup"><span data-stu-id="4a163-117">Not ready</span></span> | <span data-ttu-id="4a163-118">*Si no* solucionas estos problemas, se producirá un error en la inscripción.</span><span class="sxs-lookup"><span data-stu-id="4a163-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="4a163-119">Siga los pasos de la herramienta para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="4a163-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="4a163-120">Obtener el checker</span><span class="sxs-lookup"><span data-stu-id="4a163-120">Obtain the checker</span></span>

<span data-ttu-id="4a163-121">Descargue el archivo .zip desde https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="4a163-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="4a163-122">El usuario que ejecuta la herramienta debe tener derechos de administrador local en el dispositivo donde la está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4a163-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="4a163-123">A continuación, ejecute la herramienta siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4a163-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="4a163-124">Copia el archivo .zip descargado en cada dispositivo que quieras comprobar.</span><span class="sxs-lookup"><span data-stu-id="4a163-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="4a163-125">Extraiga todos los archivos de la descarga comprimida.</span><span class="sxs-lookup"><span data-stu-id="4a163-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="4a163-126">Ejecute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="4a163-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="4a163-127">Cuando aparezca el mensaje Control de acceso de usuario, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4a163-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="4a163-128">La herramienta se ejecuta y abre un informe en el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4a163-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="4a163-129">También puedes descargar y extraer el archivo .zip en una ubicación compartida, acceder a **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** de cada dispositivo y, a continuación, ejecutarlo localmente.</span><span class="sxs-lookup"><span data-stu-id="4a163-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="4a163-130">Comprobaciones</span><span class="sxs-lookup"><span data-stu-id="4a163-130">Checks</span></span>

<span data-ttu-id="4a163-131">La herramienta descargable comprueba estos elementos relacionados con el dispositivo y la red:</span><span class="sxs-lookup"><span data-stu-id="4a163-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="4a163-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="4a163-132">Hardware</span></span>

<span data-ttu-id="4a163-133">Los dispositivos deben cumplir requisitos de hardware específicos para trabajar con escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a163-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a163-134">Actualmente, solo pueden [inscribirse](../service-description/device-list.md) dispositivos aprobados específicos.</span><span class="sxs-lookup"><span data-stu-id="4a163-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="4a163-135">Si el dispositivo produce un error en cualquiera de las comprobaciones, no es compatible con el Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a163-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="4a163-136">Puntos de conexión de red</span><span class="sxs-lookup"><span data-stu-id="4a163-136">Network endpoints</span></span>

<span data-ttu-id="4a163-137">Los dispositivos pueden llegar a varios [puntos de conexión clave para](network.md) trabajar con escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a163-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a163-138">Si la herramienta informa de un **resultado** no listo, consulta el informe detallado para averiguar a qué puntos de conexión no se ha accesible.</span><span class="sxs-lookup"><span data-stu-id="4a163-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="4a163-139">A continuación, ajusta el firewall u otra configuración de red para garantizar que se puedan alcanzar esos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4a163-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="4a163-140">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="4a163-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="4a163-141">Perfiles wi-fi empresariales</span><span class="sxs-lookup"><span data-stu-id="4a163-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="4a163-142">Un **resultado de** aviso significa que estás usando algunos perfiles wi-fi que necesitan certificados y perfiles para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a163-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4a163-143">Para obtener más información, consulta [Implementar certificados y perfil de Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)</span><span class="sxs-lookup"><span data-stu-id="4a163-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="4a163-144">Perfiles LAN</span><span class="sxs-lookup"><span data-stu-id="4a163-144">LAN profiles</span></span>

<span data-ttu-id="4a163-145">Un **resultado de** aviso significa que tiene LAN que necesitan certificados y perfiles para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a163-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4a163-146">Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="4a163-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="4a163-147">Perfiles de VPN</span><span class="sxs-lookup"><span data-stu-id="4a163-147">VPN profiles</span></span>

<span data-ttu-id="4a163-148">Un **resultado de** aviso significa que estás usando una red privada virtual (VPN).</span><span class="sxs-lookup"><span data-stu-id="4a163-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="4a163-149">Cree un perfil de VPN que implemente certificados integrados con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="4a163-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="4a163-150">Para obtener más información, vea Preparar certificados [y perfiles de red para escritorio administrado de Microsoft.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="4a163-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="4a163-151">Unidades asignadas</span><span class="sxs-lookup"><span data-stu-id="4a163-151">Mapped drives</span></span>

<span data-ttu-id="4a163-152">Un **resultado de aviso** significa que tienes algunas unidades asignadas, lo cual no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="4a163-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="4a163-153">Para obtener más información, vea [Preparar unidades asignadas para escritorio administrado de Microsoft.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="4a163-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="4a163-154">Colas de impresión</span><span class="sxs-lookup"><span data-stu-id="4a163-154">Print queues</span></span>

<span data-ttu-id="4a163-155">Un **resultado de aviso** significa que tiene algunas colas de impresión pendientes, que no se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="4a163-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="4a163-156">Una solución es usar la impresión en la nube.</span><span class="sxs-lookup"><span data-stu-id="4a163-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="4a163-157">Para obtener más información, vea [Preparar los recursos de impresión para escritorio administrado de Microsoft.](printing.md)</span><span class="sxs-lookup"><span data-stu-id="4a163-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="4a163-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="4a163-158">Proxies</span></span>

<span data-ttu-id="4a163-159">Un **resultado de** aviso significa que tiene un servidor proxy en uso.</span><span class="sxs-lookup"><span data-stu-id="4a163-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="4a163-160">Para obtener más información, vea [Configuración de red para Escritorio administrado de Microsoft.](network.md)</span><span class="sxs-lookup"><span data-stu-id="4a163-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

