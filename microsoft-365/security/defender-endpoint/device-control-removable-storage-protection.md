---
title: Microsoft Defender para Endpoint Device Control Removable Storage Protection
description: Comprender las "funcionalidades que ayudan a impedir que el usuario o la máquina o ambos utilicen medios de almacenamiento extraíbles no autorizados
keywords: medios de almacenamiento extraíbles
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 55171429d3ea447de32eb7e2ec12b8b2c3542e95
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861712"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="78b98-104">Microsoft Defender para Endpoint Device Control Removable Storage Protection</span><span class="sxs-lookup"><span data-stu-id="78b98-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="78b98-105">Microsoft Defender para Endpoint Device Control Removable Storage Protection impide que el usuario o la máquina o ambos utilicen medios de almacenamiento extraíbles no autorizados.</span><span class="sxs-lookup"><span data-stu-id="78b98-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="78b98-106">Directivas de protección</span><span class="sxs-lookup"><span data-stu-id="78b98-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="78b98-107">Instalación del dispositivo</span><span class="sxs-lookup"><span data-stu-id="78b98-107">Device installation</span></span>

<span data-ttu-id="78b98-108">**Funcionalidades:** impedir la instalación con o sin exclusión basada en varias propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="78b98-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="78b98-109">**Windows 10 de soporte técnico**</span><span class="sxs-lookup"><span data-stu-id="78b98-109">**Windows 10 support details**</span></span>
- <span data-ttu-id="78b98-110">Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="78b98-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="78b98-111">Admite MEM y GPO.</span><span class="sxs-lookup"><span data-stu-id="78b98-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="78b98-112">Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.</span><span class="sxs-lookup"><span data-stu-id="78b98-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="78b98-113">Para obtener más información Windows, vea [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span><span class="sxs-lookup"><span data-stu-id="78b98-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="78b98-114">**Plataforma compatible:** Windows 10</span><span class="sxs-lookup"><span data-stu-id="78b98-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="78b98-115">**Detalles de soporte técnico de macOS**</span><span class="sxs-lookup"><span data-stu-id="78b98-115">**macOS support details**</span></span>
- <span data-ttu-id="78b98-116">Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión</span><span class="sxs-lookup"><span data-stu-id="78b98-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="78b98-117">Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78b98-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="78b98-118">**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas)</span><span class="sxs-lookup"><span data-stu-id="78b98-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="78b98-119">Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-119">Removable storage Access Control</span></span>

<span data-ttu-id="78b98-120">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="78b98-120">**Capabilities**</span></span>
- <span data-ttu-id="78b98-121">*Auditoría* Acceso de lectura o escritura o ejecución al almacenamiento extraíble basado en varias propiedades del dispositivo, con o sin exclusión.</span><span class="sxs-lookup"><span data-stu-id="78b98-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="78b98-122">*Impedir* Acceso de lectura o escritura o ejecución con o sin exclusión: permitir un dispositivo específico basado en varias propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="78b98-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="78b98-123">**Windows 10 de soporte técnico**</span><span class="sxs-lookup"><span data-stu-id="78b98-123">**Windows 10 support details**</span></span>
- <span data-ttu-id="78b98-124">Se aplica a la máquina o al usuario o a ambos: solo permite a personas específicas que realizan lectura,escritura/ejecución acceder al almacenamiento extraíble específico en un equipo específico.</span><span class="sxs-lookup"><span data-stu-id="78b98-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="78b98-125">Admite MEM OMA-URI y GPO.</span><span class="sxs-lookup"><span data-stu-id="78b98-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="78b98-126">Compatible con '[Propiedades de dispositivo](#device-properties)' como se muestra.</span><span class="sxs-lookup"><span data-stu-id="78b98-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="78b98-127">Para obtener información sobre la Windows, [consulte Control de acceso de almacenamiento extraíble](device-control-removable-storage-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="78b98-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="78b98-128">**Plataforma compatible:** Windows 10</span><span class="sxs-lookup"><span data-stu-id="78b98-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="78b98-129">**Detalles de soporte técnico de macOS**</span><span class="sxs-lookup"><span data-stu-id="78b98-129">**macOS support details**</span></span>
- <span data-ttu-id="78b98-130">Se aplica a nivel de máquina: se aplica la misma directiva para cualquier usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="78b98-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="78b98-131">Para obtener información específica de macOS, consulta [Control de dispositivos para macOS](mac-device-control-overview.md).</span><span class="sxs-lookup"><span data-stu-id="78b98-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="78b98-132">**Plataforma compatible:** macOS Catalina 10.15.4+ (con extensiones del sistema habilitadas)</span><span class="sxs-lookup"><span data-stu-id="78b98-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="78b98-133">Windows Control de acceso de dispositivo portátil</span><span class="sxs-lookup"><span data-stu-id="78b98-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="78b98-134">**Funcionalidades:** denegar el acceso de lectura o escritura a [cualquier Windows dispositivo](/windows-hardware/drivers/portable/)portátil , por ejemplo: Tableta, iPhone.</span><span class="sxs-lookup"><span data-stu-id="78b98-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="78b98-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="78b98-135">**Description**</span></span>
- <span data-ttu-id="78b98-136">Se aplica a la máquina o al usuario o a ambos.</span><span class="sxs-lookup"><span data-stu-id="78b98-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="78b98-137">Admite MEM OMA-URI y GPO.</span><span class="sxs-lookup"><span data-stu-id="78b98-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="78b98-138">**Plataforma compatible:** Windows 10</span><span class="sxs-lookup"><span data-stu-id="78b98-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="78b98-139">Almacenamiento extraíble dlp de extremo</span><span class="sxs-lookup"><span data-stu-id="78b98-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="78b98-140">**Capacidades:** auditar o advertir o impedir que un usuario copie un elemento o información en medios extraíbles o dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="78b98-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="78b98-141">**Descripción:** para obtener más información sobre Windows, vea [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="78b98-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="78b98-142">**Plataforma compatible:** Windows 10</span><span class="sxs-lookup"><span data-stu-id="78b98-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="78b98-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="78b98-143">BitLocker</span></span> 

<span data-ttu-id="78b98-144">**Capabilities**</span><span class="sxs-lookup"><span data-stu-id="78b98-144">**Capabilities**</span></span>
- <span data-ttu-id="78b98-145">Bloquee los datos que se escribirán en unidades extraíbles que no están BitLocker protegidas.</span><span class="sxs-lookup"><span data-stu-id="78b98-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="78b98-146">Bloquear el acceso a unidades extraíbles a menos que estén cifradas en un equipo propiedad de su organización</span><span class="sxs-lookup"><span data-stu-id="78b98-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="78b98-147">**Descripción:** para obtener más información sobre Windows, vea [BitLocker – Removable Drive Configuración](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="78b98-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="78b98-148">**Plataforma compatible:** Windows 10</span><span class="sxs-lookup"><span data-stu-id="78b98-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="78b98-149">Propiedades del dispositivo</span><span class="sxs-lookup"><span data-stu-id="78b98-149">Device properties</span></span>

<span data-ttu-id="78b98-150">Microsoft Defender para Endpoint Device Control Removable Storage Protection le permite restringir el acceso de almacenamiento extraíble en función de las propiedades descritas en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="78b98-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="78b98-151">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="78b98-151">Property Name</span></span>  |<span data-ttu-id="78b98-152">Directivas aplicables</span><span class="sxs-lookup"><span data-stu-id="78b98-152">Applicable Policies</span></span>  |<span data-ttu-id="78b98-153">Se aplica a sistemas operativos</span><span class="sxs-lookup"><span data-stu-id="78b98-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="78b98-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="78b98-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="78b98-155">Clase device</span><span class="sxs-lookup"><span data-stu-id="78b98-155">Device Class</span></span>    |     [<span data-ttu-id="78b98-156">Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="78b98-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="78b98-157">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-157">Windows</span></span>      |  <span data-ttu-id="78b98-158">Para obtener información acerca de los formatos de id. de dispositivo, consulta [clase de configuración del dispositivo](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span><span class="sxs-lookup"><span data-stu-id="78b98-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="78b98-159">**Nota:** La instalación del dispositivo se puede aplicar a cualquier dispositivo, no solo al almacenamiento extraíble.</span><span class="sxs-lookup"><span data-stu-id="78b98-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="78b98-160">Id. principal</span><span class="sxs-lookup"><span data-stu-id="78b98-160">Primary ID</span></span>   |     <span data-ttu-id="78b98-161">Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="78b98-162">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-162">Windows</span></span>      |      <span data-ttu-id="78b98-163">El identificador principal incluye almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="78b98-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="78b98-164">Id. de dispositivo</span><span class="sxs-lookup"><span data-stu-id="78b98-164">Device ID</span></span>     |  <span data-ttu-id="78b98-165">[Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint;](control-usb-devices-using-intune.md) Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="78b98-166">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-166">Windows</span></span>   |    <span data-ttu-id="78b98-167">Para obtener información sobre los formatos de id. de dispositivo, consulte [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="78b98-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="78b98-168">Id. de hardware</span><span class="sxs-lookup"><span data-stu-id="78b98-168">Hardware ID</span></span>     |     <span data-ttu-id="78b98-169">[Cómo controlar dispositivos USB y otros medios extraíbles con Microsoft Defender para endpoint;](control-usb-devices-using-intune.md) Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="78b98-170">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-170">Windows</span></span>    |    <span data-ttu-id="78b98-171">Una cadena identificó el dispositivo en el sistema, por ejemplo, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Nota:** El identificador de hardware no es único; diferentes dispositivos pueden compartir el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="78b98-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="78b98-172">Id. de instancia</span><span class="sxs-lookup"><span data-stu-id="78b98-172">Instance ID</span></span>    | <span data-ttu-id="78b98-173">Instalación de dispositivos; Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="78b98-174">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-174">Windows</span></span>    |   <span data-ttu-id="78b98-175">Una cadena identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="78b98-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="78b98-176">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="78b98-176">Friendly Name</span></span>     |     <span data-ttu-id="78b98-177">Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="78b98-178">Windows</span><span class="sxs-lookup"><span data-stu-id="78b98-178">Windows</span></span>      |    <span data-ttu-id="78b98-179">Una cadena adjunta al dispositivo, por ejemplo, Dispositivo USB de disco flash genérico</span><span class="sxs-lookup"><span data-stu-id="78b98-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="78b98-180">Id. de proveedor /Id. de producto</span><span class="sxs-lookup"><span data-stu-id="78b98-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="78b98-181">Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="78b98-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="78b98-182">Windows Mac</span></span>      |     <span data-ttu-id="78b98-183">Id. de proveedor es el código de proveedor de cuatro dígitos que el comité USB asigna al proveedor.</span><span class="sxs-lookup"><span data-stu-id="78b98-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="78b98-184">Id. de producto es el código de producto de cuatro dígitos que el proveedor asigna al dispositivo; Admite caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="78b98-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="78b98-185">NumberId de serie</span><span class="sxs-lookup"><span data-stu-id="78b98-185">Serial NumberId</span></span>     |     <span data-ttu-id="78b98-186">Control de acceso de almacenamiento extraíble</span><span class="sxs-lookup"><span data-stu-id="78b98-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="78b98-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="78b98-187">Windows Mac</span></span>   |     <span data-ttu-id="78b98-188">Por ejemplo, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="78b98-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="78b98-189">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="78b98-189">Related topic</span></span>

- [<span data-ttu-id="78b98-190">Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso</span><span class="sxs-lookup"><span data-stu-id="78b98-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

