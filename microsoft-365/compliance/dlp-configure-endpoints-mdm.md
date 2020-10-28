---
title: Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles
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
description: Use las herramientas de administración de dispositivos móviles para implementar el paquete de configuración en dispositivos para que estén integrados en el servicio.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769518"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="c5ce5-103">Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c5ce5-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="c5ce5-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c5ce5-104">**Applies to:**</span></span>

- [<span data-ttu-id="c5ce5-105">Prevención de pérdida de datos (DLP) de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5ce5-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="c5ce5-106">Puede usar las soluciones de administración de dispositivos móviles (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="c5ce5-107">La prevención de pérdida de datos de extremos de Microsoft 365 admite MDMs proporcionando OMA-URIs para crear directivas para administrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="c5ce5-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c5ce5-108">Before you begin</span></span>
<span data-ttu-id="c5ce5-109">Si está usando Microsoft Intune, debe estar inscrito en MDM del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="c5ce5-110">De lo contrario, la configuración no se aplicará correctamente.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="c5ce5-111">Para obtener más información sobre cómo habilitar MDM con Microsoft Intune, consulte [Device Enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="c5ce5-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="c5ce5-112">Dispositivos integrados con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c5ce5-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="c5ce5-113">Siga las instrucciones de [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c5ce5-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="c5ce5-114">El **Estado de mantenimiento de la Directiva de dispositivos incorporados** usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="c5ce5-115">Desincorpora y supervisión de dispositivos con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c5ce5-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="c5ce5-116">Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="c5ce5-117">Los paquetes de retirada expirados enviados a un dispositivo se rechazarán.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="c5ce5-118">Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="c5ce5-119">Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="c5ce5-120">Obtenga el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c5ce5-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="c5ce5-121">En el panel de navegación, seleccione **configuración** de la  >  **incorporación de dispositivos** de configuración  >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="c5ce5-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding** .</span></span>

3. <span data-ttu-id="c5ce5-122">En el campo **método de implementación** , seleccione Administración de **dispositivos móviles/Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="c5ce5-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune** .</span></span>
    
4. <span data-ttu-id="c5ce5-123">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-123">Click **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="c5ce5-124">Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que puedan tener acceso los administradores de red que van a implementar el paquete.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="c5ce5-125">Debe tener un archivo denominado *DeviceCompliance_valid_until_YYYY-mm-dd. de descarga* .</span><span class="sxs-lookup"><span data-stu-id="c5ce5-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding* .</span></span>

6. <span data-ttu-id="c5ce5-126">Use la Directiva de configuración personalizada de Microsoft Intune para implementar la siguiente configuración de OMA-URI admitida.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="c5ce5-127">OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="c5ce5-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="c5ce5-128">Tipo de datos: String</span><span class="sxs-lookup"><span data-stu-id="c5ce5-128">Date type: String</span></span>      
      <span data-ttu-id="c5ce5-129">Valor: [copie y pegue el valor del contenido del archivo DeviceCompliance_valid_until_YYYY-MM-DD. de descarga]</span><span class="sxs-lookup"><span data-stu-id="c5ce5-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="c5ce5-130">Para obtener más información sobre la configuración de directiva de Microsoft Intune, consulte [configuración de la Directiva de Windows 10 en Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c5ce5-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="c5ce5-131">El **Estado de mantenimiento de la Directiva de dispositivos de offboarded** usa propiedades de solo lectura y no se puede corregir.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5ce5-132">La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a cualquier alerta que haya tenido, se conservará durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="c5ce5-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5ce5-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c5ce5-133">Related topics</span></span>
- [<span data-ttu-id="c5ce5-134">Dispositivos de Windows 10 incorporados mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="c5ce5-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="c5ce5-135">Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="c5ce5-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="c5ce5-136">Dispositivos de Windows 10 incorporados que usan un script local</span><span class="sxs-lookup"><span data-stu-id="c5ce5-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="c5ce5-137">Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados</span><span class="sxs-lookup"><span data-stu-id="c5ce5-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="c5ce5-138">Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="c5ce5-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
