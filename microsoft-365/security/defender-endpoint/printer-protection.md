---
title: Protección de impresora de control de dispositivos de Microsoft Defender para Endpoint
description: Microsoft Defender para Endpoint Device Control Printer Protection bloquea la impresión de personas a través de impresoras no corporativas o impresoras USB no aprobadas.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289696"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="0524d-103">Protección de la impresora de control de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0524d-103">Device Control Printer Protection</span></span>

<span data-ttu-id="0524d-104">Microsoft Defender para Endpoint Device Control Printer Protection bloquea la impresión de personas a través de impresoras no corporativas o impresoras USB no aprobadas.</span><span class="sxs-lookup"><span data-stu-id="0524d-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="0524d-105">Licencias</span><span class="sxs-lookup"><span data-stu-id="0524d-105">Licensing</span></span>

<span data-ttu-id="0524d-106">Antes de empezar a usar Printer Protection, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="0524d-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="0524d-107">Para obtener acceso y usar la protección de impresoras, debe tener lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0524d-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="0524d-108">Microsoft 365 E3 para la implementación de directivas/funcionalidad</span><span class="sxs-lookup"><span data-stu-id="0524d-108">Microsoft 365 E3 for functionality/policy deployment</span></span>
- <span data-ttu-id="0524d-109">Microsoft 365 E5 para informes</span><span class="sxs-lookup"><span data-stu-id="0524d-109">Microsoft 365 E5 for reporting</span></span>

## <a name="permission"></a><span data-ttu-id="0524d-110">Permiso</span><span class="sxs-lookup"><span data-stu-id="0524d-110">Permission</span></span>

<span data-ttu-id="0524d-111">Para la implementación de directivas en Intune, para implementar la directiva a través de OMA-URI, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0524d-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="0524d-112">Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos:</span><span class="sxs-lookup"><span data-stu-id="0524d-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>

- <span data-ttu-id="0524d-113">Rol Administrador de directivas y perfiles.</span><span class="sxs-lookup"><span data-stu-id="0524d-113">Policy and profile Manager role.</span></span>
- <span data-ttu-id="0524d-114">O rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0524d-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="0524d-115">O Administrador global</span><span class="sxs-lookup"><span data-stu-id="0524d-115">Or Global admin</span></span>

<span data-ttu-id="0524d-116">Para ver los informes de configuración del dispositivo, la cuenta debe tener permisos de vista de informes.</span><span class="sxs-lookup"><span data-stu-id="0524d-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="0524d-117">Puede crear roles personalizados o usar los roles integrados con estos permisos:</span><span class="sxs-lookup"><span data-stu-id="0524d-117">You can create custom roles or use the built-in roles with these permissions:</span></span>

- <span data-ttu-id="0524d-118">Administrador de seguridad global</span><span class="sxs-lookup"><span data-stu-id="0524d-118">Global security admin</span></span>
- <span data-ttu-id="0524d-119">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="0524d-119">Security admin</span></span>
- <span data-ttu-id="0524d-120">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="0524d-120">Security Reader</span></span>

## <a name="prepare-your-endpoints"></a><span data-ttu-id="0524d-121">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0524d-121">Prepare your endpoints</span></span>

<span data-ttu-id="0524d-122">Asegúrese de que los dispositivos Windows 10 que planee implementar Printer Protection cumplan estos requisitos.</span><span class="sxs-lookup"><span data-stu-id="0524d-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="0524d-123">Únase al programa Insider.</span><span class="sxs-lookup"><span data-stu-id="0524d-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="0524d-124">Se instalan las siguientes actualizaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="0524d-124">The following Windows Updates are installed.</span></span>
    - <span data-ttu-id="0524d-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="0524d-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span>
    - <span data-ttu-id="0524d-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="0524d-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="0524d-127">Para Windows 2004 o posterior</span><span class="sxs-lookup"><span data-stu-id="0524d-127">For Windows 2004 or later</span></span>

1. <span data-ttu-id="0524d-128">Si estás planeando implementar la directiva a través de la directiva de grupo, el dispositivo debe estar unido a MDATP; si planea implementar la directiva a través de MEM, el dispositivo debe estar unido a Intune.</span><span class="sxs-lookup"><span data-stu-id="0524d-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="0524d-129">Implementar directiva de protección de impresoras de control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0524d-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="0524d-130">Puedes implementar la directiva a través de la directiva de grupo o Intune.</span><span class="sxs-lookup"><span data-stu-id="0524d-130">You can deploy the policy via Group Policy or Intune.</span></span>

<br>

****

|<span data-ttu-id="0524d-131">Título</span><span class="sxs-lookup"><span data-stu-id="0524d-131">Title</span></span>|<span data-ttu-id="0524d-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="0524d-132">Description</span></span>|<span data-ttu-id="0524d-133">Compatibilidad con CSP</span><span class="sxs-lookup"><span data-stu-id="0524d-133">CSP Support</span></span> | <span data-ttu-id="0524d-134">Compatibilidad con GPO</span><span class="sxs-lookup"><span data-stu-id="0524d-134">GPO Support</span></span> | <span data-ttu-id="0524d-135">Soporte técnico basado en usuarios</span><span class="sxs-lookup"><span data-stu-id="0524d-135">User-based Support</span></span> | <span data-ttu-id="0524d-136">Compatibilidad basada en máquina</span><span class="sxs-lookup"><span data-stu-id="0524d-136">Machine-based Support</span></span> |
|---|---|:---:|:---:|:---:|:---:|
|<span data-ttu-id="0524d-137">**Habilitar restricciones de impresión del control de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="0524d-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="0524d-138">Bloquear la impresión de personas a través de impresoras no corporativas</span><span class="sxs-lookup"><span data-stu-id="0524d-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="0524d-139">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-139">Yes</span></span>|<span data-ttu-id="0524d-140">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-140">Yes</span></span>|<span data-ttu-id="0524d-141">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-141">Yes</span></span>|<span data-ttu-id="0524d-142">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-142">Yes</span></span>|
|<span data-ttu-id="0524d-143">**Lista de dispositivos de impresión conectados a USB aprobados**\*</span><span class="sxs-lookup"><span data-stu-id="0524d-143">**List of Approved USB-connected print devices**\*</span></span>|<span data-ttu-id="0524d-144">Permitir una impresora USB específica</span><span class="sxs-lookup"><span data-stu-id="0524d-144">Allow specific USB printer</span></span>|<span data-ttu-id="0524d-145">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-145">Yes</span></span>|<span data-ttu-id="0524d-146">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-146">Yes</span></span>|<span data-ttu-id="0524d-147">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-147">Yes</span></span>|<span data-ttu-id="0524d-148">Sí</span><span class="sxs-lookup"><span data-stu-id="0524d-148">Yes</span></span>|
|

<span data-ttu-id="0524d-149">\*Esta directiva debe usarse junto con **Habilitar restricciones de impresión del control de dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="0524d-149">\* This policy must be used together with **Enable Device control Printing Restrictions**.</span></span>

## <a name="deploy-policy-via-intune"></a><span data-ttu-id="0524d-150">Implementar la directiva a través de Intune</span><span class="sxs-lookup"><span data-stu-id="0524d-150">Deploy policy via Intune</span></span>

<span data-ttu-id="0524d-151">En Intune, actualmente Device Control Printer Protection solo admite OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="0524d-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a><span data-ttu-id="0524d-152">Escenario 1: Bloquear la impresión de personas a través de cualquier impresora no corporativa con Intune</span><span class="sxs-lookup"><span data-stu-id="0524d-152">Scenario 1: Block people from printing via any non-corporate printer using Intune</span></span>

- <span data-ttu-id="0524d-153">Aplicar directiva sobre el equipo:</span><span class="sxs-lookup"><span data-stu-id="0524d-153">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- <span data-ttu-id="0524d-154">Aplicar directiva sobre el usuario:</span><span class="sxs-lookup"><span data-stu-id="0524d-154">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

<span data-ttu-id="0524d-155">La cadena de compatibilidad de CSP con `<enabled/>` :</span><span class="sxs-lookup"><span data-stu-id="0524d-155">The CSP support string with `<enabled/>`:</span></span>

:::image type="content" source="../../media/customeditrow.png" alt-text="fila de edición personalizada":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a><span data-ttu-id="0524d-157">Escenario 2: Permitir impresoras USB aprobadas específicas con Intune</span><span class="sxs-lookup"><span data-stu-id="0524d-157">Scenario 2: Allow specific approved USB printers using Intune</span></span>

- <span data-ttu-id="0524d-158">Aplicar directiva sobre el equipo:</span><span class="sxs-lookup"><span data-stu-id="0524d-158">Apply policy over machine:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- <span data-ttu-id="0524d-159">Aplicar directiva sobre el usuario:</span><span class="sxs-lookup"><span data-stu-id="0524d-159">Apply policy over user:</span></span>

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

<span data-ttu-id="0524d-160">La cadena de compatibilidad de CSP con impresoras USB aprobadas a través de la propiedad "ApprovedUsbPrintDevices", por `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0524d-160">The CSP support string with approved USB printers via 'ApprovedUsbPrintDevices' property, example `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">`:</span></span>

:::image type="content" source="../../media/editrow.png" alt-text="editar fila":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="0524d-162">Implementar la directiva a través de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="0524d-162">Deploy policy via Group Policy</span></span>

<span data-ttu-id="0524d-163">Si el dispositivo no está unido a Intune, también puedes implementar la directiva a través de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="0524d-163">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span>

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a><span data-ttu-id="0524d-164">Escenario 1: Bloquear la impresión de personas a través de cualquier impresora no corporativa mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="0524d-164">Scenario 1: Block people from printing via any non-corporate printer using Group Policy</span></span>

- <span data-ttu-id="0524d-165">Aplicar directiva sobre el equipo:</span><span class="sxs-lookup"><span data-stu-id="0524d-165">Apply policy over machine:</span></span>

  <span data-ttu-id="0524d-166">Impresora de plantillas administrativas de configuración \> \> del equipo: Habilitar restricciones de impresión del control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0524d-166">Computer Configuration \> Administrative Templates \> Printer: Enable Device control Printing Restrictions</span></span>

- <span data-ttu-id="0524d-167">Aplicar directiva sobre el usuario:</span><span class="sxs-lookup"><span data-stu-id="0524d-167">Apply policy over user:</span></span>

  <span data-ttu-id="0524d-168">Configuración de usuario \> Plantillas administrativas \> Impresoras del panel de \> control: Habilitar restricciones de impresión del control de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0524d-168">User Configuration \> Administrative Templates \> Control Panel \> Printers: Enable Device control Printing Restrictions</span></span>

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="habilitar restricciones de impresión de dispositivos":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a><span data-ttu-id="0524d-170">Escenario 2: Permitir impresoras USB aprobadas específicas con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="0524d-170">Scenario 2: Allow specific approved USB printers using Group Policy</span></span>

- <span data-ttu-id="0524d-171">Aplicar directiva sobre el equipo:</span><span class="sxs-lookup"><span data-stu-id="0524d-171">Apply policy over machine:</span></span>

  <span data-ttu-id="0524d-172">Impresora de plantillas administrativas de configuración \> \> del equipo: lista de dispositivos de impresión conectados a USB aprobados</span><span class="sxs-lookup"><span data-stu-id="0524d-172">Computer Configuration \> Administrative Templates \> Printer:  List of Approved USB-connected print devices</span></span>

- <span data-ttu-id="0524d-173">Aplicar directiva sobre el usuario:</span><span class="sxs-lookup"><span data-stu-id="0524d-173">Apply policy over user:</span></span>

  <span data-ttu-id="0524d-174">Impresoras de panel de control de plantillas administrativas de configuración \> \> de \> usuario: lista de dispositivos de impresión conectados a USB aprobados</span><span class="sxs-lookup"><span data-stu-id="0524d-174">User Configuration \> Administrative Templates \> Control Panel \> Printers: List of Approved USB-connected print devices</span></span>

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista de dispositivos de impresión conectados usb aprobados":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="0524d-176">Ver datos de protección de impresoras de control de dispositivos en Microsoft Defender para el portal de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0524d-176">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span>

<span data-ttu-id="0524d-177">El [Microsoft 365 de seguridad muestra](https://security.microsoft.com) la impresión bloqueada por la directiva de protección de impresoras de control de dispositivos anterior.</span><span class="sxs-lookup"><span data-stu-id="0524d-177">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="búsqueda avanzada":::
