---
title: Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en los dispositivos de modo que se incorpore al servicio.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769518"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="badaf-103">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="badaf-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="badaf-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="badaf-104">**Applies to:**</span></span>

- [<span data-ttu-id="badaf-105">Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="badaf-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="badaf-106">Puedes usar soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="badaf-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="badaf-107">La prevención de pérdida de datos de puntos de conexión de Microsoft 365 admite MDM al OMA-URIs crear directivas para administrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="badaf-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="badaf-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="badaf-108">Before you begin</span></span>
<span data-ttu-id="badaf-109">Si usas Microsoft Intune, debes tener el dispositivo inscrito en MDM.</span><span class="sxs-lookup"><span data-stu-id="badaf-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="badaf-110">De lo contrario, la configuración no se aplicará correctamente.</span><span class="sxs-lookup"><span data-stu-id="badaf-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="badaf-111">Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulta [Inscripción de dispositivos (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="badaf-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="badaf-112">Incorporar dispositivos con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="badaf-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="badaf-113">Siga las instrucciones de [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="badaf-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="badaf-114">La **directiva Estado de mantenimiento de los dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="badaf-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="badaf-115">Quitar y supervisar dispositivos con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="badaf-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="badaf-116">Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="badaf-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="badaf-117">Se rechazarán los paquetes de baja expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="badaf-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="badaf-118">Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="badaf-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="badaf-119">Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="badaf-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="badaf-120">Obtenga el paquete de descarga del Centro [de cumplimiento de Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="badaf-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="badaf-121">En el panel de navegación, selecciona **Configuración**  >  **de la incorporación de dispositivos.**  >  </span><span class="sxs-lookup"><span data-stu-id="badaf-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="badaf-122">En el **campo Método de** implementación, seleccione Administración de **dispositivos móviles / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="badaf-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="badaf-123">Haga **clic en Descargar** paquete y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="badaf-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="badaf-124">Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que puedan acceder los administradores de red que implementarán el paquete.</span><span class="sxs-lookup"><span data-stu-id="badaf-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="badaf-125">Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="badaf-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="badaf-126">Usa la directiva de configuración personalizada de Microsoft Intune para implementar la siguiente configuración de OMA-URI compatible.</span><span class="sxs-lookup"><span data-stu-id="badaf-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="badaf-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="badaf-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="badaf-128">Tipo de fecha: String</span><span class="sxs-lookup"><span data-stu-id="badaf-128">Date type: String</span></span>      
      <span data-ttu-id="badaf-129">Valor: [Copiar y pegar el valor del contenido del archivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="badaf-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="badaf-130">Para obtener más información sobre la configuración de directiva de Microsoft Intune, consulta la configuración de directiva de [Windows 10 en Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="badaf-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="badaf-131">La **directiva Estado de mantenimiento de los dispositivos** desactivados usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="badaf-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="badaf-132">La baja hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="badaf-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="badaf-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="badaf-133">Related topics</span></span>
- [<span data-ttu-id="badaf-134">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="badaf-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="badaf-135">Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="badaf-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="badaf-136">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="badaf-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="badaf-137">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="badaf-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="badaf-138">Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="badaf-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
