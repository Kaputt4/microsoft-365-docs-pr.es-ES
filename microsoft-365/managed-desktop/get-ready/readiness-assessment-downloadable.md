---
title: Comprobador de la evaluación de preparación descargable
description: Comprueba la configuración del dispositivo y la red, incluidos los puntos de conexión necesarios
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581039"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="4ee52-104">Comprobador de la evaluación de preparación descargable</span><span class="sxs-lookup"><span data-stu-id="4ee52-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="4ee52-105">Para funcionar bien con Microsoft Managed Desktop, los dispositivos deben cumplir ciertos requisitos de hardware y configuración.</span><span class="sxs-lookup"><span data-stu-id="4ee52-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="4ee52-106">Además, cada dispositivo debe poder alcanzar puntos de conexión clave.</span><span class="sxs-lookup"><span data-stu-id="4ee52-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="4ee52-107">Descargue y ejecute esta herramienta para obtener un informe HTML, ver los resultados y, a continuación, realizar acciones.</span><span class="sxs-lookup"><span data-stu-id="4ee52-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="4ee52-108">Deberás descargar la herramienta y los archivos de soporte técnico y, a continuación, ejecutarla manualmente en cada dispositivo que quieras inscribir en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ee52-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4ee52-109">Para cada comprobación, la herramienta mostrará uno de los tres resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="4ee52-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="4ee52-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="4ee52-110">Result</span></span>  |<span data-ttu-id="4ee52-111">Significado</span><span class="sxs-lookup"><span data-stu-id="4ee52-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4ee52-112">Listo</span><span class="sxs-lookup"><span data-stu-id="4ee52-112">Ready</span></span>     | <span data-ttu-id="4ee52-113">No se requiere ninguna acción antes de completar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="4ee52-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="4ee52-114">Advertencia</span><span class="sxs-lookup"><span data-stu-id="4ee52-114">Advisory</span></span>    | <span data-ttu-id="4ee52-115">Siga los pasos de la herramienta para obtener la mejor experiencia con la inscripción y para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4ee52-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4ee52-116">Puedes *completar* la inscripción, pero debes solucionar estos problemas antes de implementar el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4ee52-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4ee52-117">No preparado</span><span class="sxs-lookup"><span data-stu-id="4ee52-117">Not ready</span></span> | <span data-ttu-id="4ee52-118">*La inscripción producirá un* error si no se solucionan estos problemas.</span><span class="sxs-lookup"><span data-stu-id="4ee52-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="4ee52-119">Siga los pasos de la herramienta para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="4ee52-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="4ee52-120">Obtener el control</span><span class="sxs-lookup"><span data-stu-id="4ee52-120">Obtain the checker</span></span>

<span data-ttu-id="4ee52-121">Descargue el archivo .zip de https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="4ee52-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="4ee52-122">El usuario que ejecuta la herramienta debe tener derechos de administrador local en el dispositivo donde la está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="4ee52-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="4ee52-123">A continuación, ejecute la herramienta siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4ee52-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="4ee52-124">Copia el archivo .zip descargado en cada dispositivo que quieras comprobar.</span><span class="sxs-lookup"><span data-stu-id="4ee52-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="4ee52-125">Extraiga todos los archivos de la descarga comprimida.</span><span class="sxs-lookup"><span data-stu-id="4ee52-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="4ee52-126">Ejecute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="4ee52-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="4ee52-127">Cuando aparezca el símbolo del sistema control de acceso de usuario, seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4ee52-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="4ee52-128">La herramienta se ejecuta y abre un informe en el explorador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4ee52-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="4ee52-129">También puedes descargar y extraer el archivo .zip en una ubicación compartida, acceder aMicrosoft.MMD.DeviceReadinessAssessmentTool.exe **desde** cada dispositivo y, a continuación, ejecutarlo localmente.</span><span class="sxs-lookup"><span data-stu-id="4ee52-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="4ee52-130">Comprobaciones</span><span class="sxs-lookup"><span data-stu-id="4ee52-130">Checks</span></span>

<span data-ttu-id="4ee52-131">La herramienta descargable comprueba estos elementos relacionados con el dispositivo y la red:</span><span class="sxs-lookup"><span data-stu-id="4ee52-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="4ee52-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="4ee52-132">Hardware</span></span>

<span data-ttu-id="4ee52-133">Los dispositivos deben cumplir requisitos de hardware específicos para trabajar con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ee52-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4ee52-134">Actualmente, solo se [pueden](../service-description/device-list.md) inscribir dispositivos aprobados específicos.</span><span class="sxs-lookup"><span data-stu-id="4ee52-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="4ee52-135">Si el dispositivo falla alguna de las comprobaciones, no es compatible con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ee52-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="4ee52-136">Puntos de conexión de red</span><span class="sxs-lookup"><span data-stu-id="4ee52-136">Network endpoints</span></span>

<span data-ttu-id="4ee52-137">Los dispositivos pueden llegar a varios [puntos de conexión clave](network.md) para trabajar con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="4ee52-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4ee52-138">Si la herramienta informa de **un resultado** no listo, consulte el informe detallado para averiguar qué puntos de conexión no eran accesibles.</span><span class="sxs-lookup"><span data-stu-id="4ee52-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="4ee52-139">A continuación, ajuste el firewall u otra configuración de red para asegurarse de que se pueda alcanzar esos puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="4ee52-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="4ee52-140">Otras opciones de configuración</span><span class="sxs-lookup"><span data-stu-id="4ee52-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="4ee52-141">Perfiles wi-fi empresariales</span><span class="sxs-lookup"><span data-stu-id="4ee52-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="4ee52-142">Un **resultado de asesoramiento** significa que está usando algunos perfiles wi-fi que necesitan certificados y perfiles para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ee52-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4ee52-143">Para obtener más información, vea [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span><span class="sxs-lookup"><span data-stu-id="4ee52-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="4ee52-144">Perfiles DE LAN</span><span class="sxs-lookup"><span data-stu-id="4ee52-144">LAN profiles</span></span>

<span data-ttu-id="4ee52-145">Un **resultado de asesoramiento** significa que tiene LAN que necesitan certificados y perfiles para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ee52-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4ee52-146">Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="4ee52-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="4ee52-147">Perfiles vpn</span><span class="sxs-lookup"><span data-stu-id="4ee52-147">VPN profiles</span></span>

<span data-ttu-id="4ee52-148">Un **resultado de aviso** significa que está usando una red privada virtual (VPN).</span><span class="sxs-lookup"><span data-stu-id="4ee52-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="4ee52-149">Cree un perfil de VPN que implemente certificados integrados con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="4ee52-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="4ee52-150">Para obtener más información, vea [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="4ee52-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="4ee52-151">Unidades asignadas</span><span class="sxs-lookup"><span data-stu-id="4ee52-151">Mapped drives</span></span>

<span data-ttu-id="4ee52-152">Un **resultado de aviso** significa que tiene algunas unidades asignadas, lo que no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="4ee52-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="4ee52-153">Para obtener más información, vea [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span><span class="sxs-lookup"><span data-stu-id="4ee52-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="4ee52-154">Colas de impresión</span><span class="sxs-lookup"><span data-stu-id="4ee52-154">Print queues</span></span>

<span data-ttu-id="4ee52-155">Un **resultado de aviso** significa que tiene algunas colas de impresión pendientes, que no se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="4ee52-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="4ee52-156">Una solución es usar la impresión en la nube.</span><span class="sxs-lookup"><span data-stu-id="4ee52-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="4ee52-157">Para obtener más información, vea [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span><span class="sxs-lookup"><span data-stu-id="4ee52-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="4ee52-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="4ee52-158">Proxies</span></span>

<span data-ttu-id="4ee52-159">Un **resultado de aviso** significa que tiene un servidor proxy en uso.</span><span class="sxs-lookup"><span data-stu-id="4ee52-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="4ee52-160">Para obtener más información, vea [Configuración de red para Microsoft Managed Desktop](network.md).</span><span class="sxs-lookup"><span data-stu-id="4ee52-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

