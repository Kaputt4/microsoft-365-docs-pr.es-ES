---
title: Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso
description: Una información general sobre Microsoft Defender para endpoint
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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841191"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="f512d-104">Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso</span><span class="sxs-lookup"><span data-stu-id="f512d-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="f512d-105">Microsoft Defender para endpoint device control removable Storage Access Control permite realizar la siguiente tarea:</span><span class="sxs-lookup"><span data-stu-id="f512d-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="f512d-106">auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión</span><span class="sxs-lookup"><span data-stu-id="f512d-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="f512d-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="f512d-107">Privilege</span></span> |<span data-ttu-id="f512d-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="f512d-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="f512d-109">Acceso</span><span class="sxs-lookup"><span data-stu-id="f512d-109">Access</span></span>    |  <span data-ttu-id="f512d-110">Lectura, Escritura, Ejecución</span><span class="sxs-lookup"><span data-stu-id="f512d-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="f512d-111">Modo de acción</span><span class="sxs-lookup"><span data-stu-id="f512d-111">Action Mode</span></span>    |    <span data-ttu-id="f512d-112">Auditoría, Permitir, Impedir</span><span class="sxs-lookup"><span data-stu-id="f512d-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="f512d-113">Compatibilidad con CSP</span><span class="sxs-lookup"><span data-stu-id="f512d-113">CSP Support</span></span>   |   <span data-ttu-id="f512d-114">Sí</span><span class="sxs-lookup"><span data-stu-id="f512d-114">Yes</span></span>      |
|<span data-ttu-id="f512d-115">Compatibilidad con GPO</span><span class="sxs-lookup"><span data-stu-id="f512d-115">GPO Support</span></span>    |   <span data-ttu-id="f512d-116">Sí</span><span class="sxs-lookup"><span data-stu-id="f512d-116">Yes</span></span>      |
|<span data-ttu-id="f512d-117">Soporte técnico basado en usuarios</span><span class="sxs-lookup"><span data-stu-id="f512d-117">User-based Support</span></span>     |   <span data-ttu-id="f512d-118">Sí</span><span class="sxs-lookup"><span data-stu-id="f512d-118">Yes</span></span>      |
|<span data-ttu-id="f512d-119">Compatibilidad basada en máquina</span><span class="sxs-lookup"><span data-stu-id="f512d-119">Machine-based Support</span></span>    |    <span data-ttu-id="f512d-120">Sí</span><span class="sxs-lookup"><span data-stu-id="f512d-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="f512d-121">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="f512d-121">Prepare your endpoints</span></span>

<span data-ttu-id="f512d-122">Implemente el control Storage de acceso extraíble en dispositivos Windows 10 que tengan la versión de cliente antimalware **4.18.2103.3 o posterior.**</span><span class="sxs-lookup"><span data-stu-id="f512d-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="f512d-123">**4.18.2104 o** posterior: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basada en filepath</span><span class="sxs-lookup"><span data-stu-id="f512d-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="f512d-124">**4.18.2105** o posterior: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/compatibilidad con SCSI conectada a USB (UAS)</span><span class="sxs-lookup"><span data-stu-id="f512d-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell":::

## <a name="policy-properties"></a><span data-ttu-id="f512d-126">Propiedades de la directiva</span><span class="sxs-lookup"><span data-stu-id="f512d-126">Policy properties</span></span>

<span data-ttu-id="f512d-127">Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:</span><span class="sxs-lookup"><span data-stu-id="f512d-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="f512d-128">**Nombre de la propiedad: Id. de grupo**</span><span class="sxs-lookup"><span data-stu-id="f512d-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="f512d-129">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa el grupo y se usará en la directiva.</span><span class="sxs-lookup"><span data-stu-id="f512d-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="f512d-130">**Nombre de la propiedad: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="f512d-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="f512d-131">Descripción: enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f512d-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="f512d-132">Enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="f512d-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="f512d-133">Para cada propiedad de dispositivo, consulta **la sección Propiedades del** dispositivo anterior para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="f512d-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="f512d-134">Opciones:</span><span class="sxs-lookup"><span data-stu-id="f512d-134">Options:</span></span>
    - <span data-ttu-id="f512d-135">Id. principal</span><span class="sxs-lookup"><span data-stu-id="f512d-135">Primary ID</span></span>
        - <span data-ttu-id="f512d-136">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="f512d-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="f512d-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="f512d-137">CdRomDevices</span></span>
    - <span data-ttu-id="f512d-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="f512d-138">DeviceId</span></span>
    - <span data-ttu-id="f512d-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="f512d-139">HardwareId</span></span>
    - <span data-ttu-id="f512d-140">InstancePathId: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="f512d-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="f512d-141">El número al final (por **ejemplo,&0**) representa la ranura disponible y puede cambiar de un dispositivo a otro.</span><span class="sxs-lookup"><span data-stu-id="f512d-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="f512d-142">Para obtener los mejores resultados, use un comodín al final.</span><span class="sxs-lookup"><span data-stu-id="f512d-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="f512d-143">Por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="f512d-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="f512d-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="f512d-144">FriendlyNameId</span></span>
    - <span data-ttu-id="f512d-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="f512d-145">SerialNumberId</span></span>
    - <span data-ttu-id="f512d-146">VID</span><span class="sxs-lookup"><span data-stu-id="f512d-146">VID</span></span>
    - <span data-ttu-id="f512d-147">PID</span><span class="sxs-lookup"><span data-stu-id="f512d-147">PID</span></span>
    - <span data-ttu-id="f512d-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="f512d-148">VID_PID</span></span>
        - <span data-ttu-id="f512d-149">0751_55E0: coincide con este par VID/PID exacto</span><span class="sxs-lookup"><span data-stu-id="f512d-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="f512d-150">_55E0: hacer coincidir cualquier medio con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="f512d-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="f512d-151">0751_: hacer coincidir cualquier medio con VID=0751</span><span class="sxs-lookup"><span data-stu-id="f512d-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="f512d-152">**Nombre de la propiedad: MatchType**</span><span class="sxs-lookup"><span data-stu-id="f512d-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="f512d-153">Descripción: cuando se usan varias propiedades de dispositivo en descriptorIDList, MatchType define la relación.</span><span class="sxs-lookup"><span data-stu-id="f512d-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="f512d-154">Opciones:</span><span class="sxs-lookup"><span data-stu-id="f512d-154">Options:</span></span>
    - <span data-ttu-id="f512d-155">MatchAll: cualquier atributo bajo descriptorIdList será **relación And;** por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema comprobará si el USB cumple ambos valores.</span><span class="sxs-lookup"><span data-stu-id="f512d-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="f512d-156">MatchAny: los atributos de descriptorIdList serán **o** relación; por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema hará la aplicación siempre que el USB tenga un valor **DeviceID** o **InstanceID** idéntico.</span><span class="sxs-lookup"><span data-stu-id="f512d-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="f512d-157">Las siguientes son las propiedades de la directiva de control de acceso:</span><span class="sxs-lookup"><span data-stu-id="f512d-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="f512d-158">**Nombre de la propiedad: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="f512d-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="f512d-159">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa la directiva y se usará en los informes y la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="f512d-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="f512d-160">**Nombre de la propiedad: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="f512d-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="f512d-161">Descripción: los grupos a los que se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="f512d-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="f512d-162">Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.</span><span class="sxs-lookup"><span data-stu-id="f512d-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="f512d-163">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="f512d-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="f512d-164">En el ejemplo siguiente se muestra el uso de GroupID:</span><span class="sxs-lookup"><span data-stu-id="f512d-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="f512d-165">**Nombre de la propiedad: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="f512d-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="f512d-166">Descripción: los grupos a los que no se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="f512d-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="f512d-167">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="f512d-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="f512d-168">**Nombre de la propiedad: Id. de entrada**</span><span class="sxs-lookup"><span data-stu-id="f512d-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="f512d-169">Descripción: One PolicyRule puede tener varias entradas; cada entrada con un GUID único indica al Control de dispositivos una restricción.</span><span class="sxs-lookup"><span data-stu-id="f512d-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="f512d-170">**Nombre de la propiedad: Type**</span><span class="sxs-lookup"><span data-stu-id="f512d-170">**Property name: Type**</span></span>

1. <span data-ttu-id="f512d-171">Descripción: define la acción de los grupos de almacenamiento extraíbles en IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="f512d-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="f512d-172">Aplicación: Permitir o denegar</span><span class="sxs-lookup"><span data-stu-id="f512d-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="f512d-173">Auditoría: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="f512d-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="f512d-174">Opciones:</span><span class="sxs-lookup"><span data-stu-id="f512d-174">Options:</span></span>
    - <span data-ttu-id="f512d-175">Permitir</span><span class="sxs-lookup"><span data-stu-id="f512d-175">Allow</span></span>
    - <span data-ttu-id="f512d-176">Denegar</span><span class="sxs-lookup"><span data-stu-id="f512d-176">Deny</span></span>
    - <span data-ttu-id="f512d-177">AuditAllowed: define la notificación y el evento cuando se permite el acceso</span><span class="sxs-lookup"><span data-stu-id="f512d-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="f512d-178">AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Denegar.**</span><span class="sxs-lookup"><span data-stu-id="f512d-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="f512d-179">Cuando haya tipos de conflicto para el mismo medio, el sistema aplicará el primero de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f512d-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="f512d-180">Un ejemplo de tipo de conflicto **es Allow** y **Deny**.</span><span class="sxs-lookup"><span data-stu-id="f512d-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="f512d-181">**Nombre de la propiedad: Opciones**</span><span class="sxs-lookup"><span data-stu-id="f512d-181">**Property name: Options**</span></span>

1. <span data-ttu-id="f512d-182">Descripción: define si se va a mostrar la notificación o no.</span><span class="sxs-lookup"><span data-stu-id="f512d-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="La pantalla en la que se puede ver el estado del dispositivo":::

1. <span data-ttu-id="f512d-184">Opciones: 0-4.</span><span class="sxs-lookup"><span data-stu-id="f512d-184">Options: 0-4.</span></span> <span data-ttu-id="f512d-185">Cuando el tipo Permitir o Denegar está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="f512d-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="f512d-186">0: nada</span><span class="sxs-lookup"><span data-stu-id="f512d-186">0: nothing</span></span>
   - <span data-ttu-id="f512d-187">4: deshabilitar **AuditAllowed** y **AuditDenied** para esta entrada.</span><span class="sxs-lookup"><span data-stu-id="f512d-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="f512d-188">Incluso si **se produce** block y la **configuración auditDenied** está configurada, el sistema no mostrará la notificación.</span><span class="sxs-lookup"><span data-stu-id="f512d-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="f512d-189">Cuando se **selecciona Tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="f512d-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="f512d-190">0: nada</span><span class="sxs-lookup"><span data-stu-id="f512d-190">0: nothing</span></span>
   - <span data-ttu-id="f512d-191">1: mostrar notificación</span><span class="sxs-lookup"><span data-stu-id="f512d-191">1: show notification</span></span>
   - <span data-ttu-id="f512d-192">2: evento send</span><span class="sxs-lookup"><span data-stu-id="f512d-192">2: send event</span></span>
   - <span data-ttu-id="f512d-193">3: mostrar notificación y enviar evento</span><span class="sxs-lookup"><span data-stu-id="f512d-193">3: show notification and send event</span></span>

<span data-ttu-id="f512d-194">**Nombre de la propiedad: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="f512d-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="f512d-195">Descripción: define el acceso.</span><span class="sxs-lookup"><span data-stu-id="f512d-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="f512d-196">Opciones: 1-7:</span><span class="sxs-lookup"><span data-stu-id="f512d-196">Options: 1-7:</span></span>
    - <span data-ttu-id="f512d-197">1: Leer</span><span class="sxs-lookup"><span data-stu-id="f512d-197">1: Read</span></span>
    - <span data-ttu-id="f512d-198">2: Escribir</span><span class="sxs-lookup"><span data-stu-id="f512d-198">2: Write</span></span>
    - <span data-ttu-id="f512d-199">3: Lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="f512d-199">3: Read and Write</span></span>
    - <span data-ttu-id="f512d-200">4: Ejecutar</span><span class="sxs-lookup"><span data-stu-id="f512d-200">4: Execute</span></span>
    - <span data-ttu-id="f512d-201">5: Leer y ejecutar</span><span class="sxs-lookup"><span data-stu-id="f512d-201">5: Read and Execute</span></span>
    - <span data-ttu-id="f512d-202">6: Escribir y ejecutar</span><span class="sxs-lookup"><span data-stu-id="f512d-202">6: Write and Execute</span></span>
    - <span data-ttu-id="f512d-203">7: Lectura y escritura y ejecución</span><span class="sxs-lookup"><span data-stu-id="f512d-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="f512d-204">Escenarios comunes Storage control de acceso extraíble</span><span class="sxs-lookup"><span data-stu-id="f512d-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="f512d-205">Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.</span><span class="sxs-lookup"><span data-stu-id="f512d-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="f512d-206">Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir usbs aprobados específicos</span><span class="sxs-lookup"><span data-stu-id="f512d-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="f512d-207">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="f512d-207">Create groups</span></span>
    1. <span data-ttu-id="f512d-208">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="f512d-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="f512d-209">Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="f512d-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="f512d-210">Grupo 2: USB aprobados en función de las propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f512d-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="f512d-211">Un ejemplo para este caso de uso es: Id. de instancia: grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs aprobados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f512d-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f512d-212">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="f512d-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="f512d-213">Creación de la directiva</span><span class="sxs-lookup"><span data-stu-id="f512d-213">Create policy</span></span>
    1. <span data-ttu-id="f512d-214">Directiva 1: Bloquear el acceso de escritura y ejecución, pero permitir los USB aprobados.</span><span class="sxs-lookup"><span data-stu-id="f512d-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="f512d-215">Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el ejemplo Escenario 1 Block Write and Execute Access, pero permite a los [USB aprobados .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) archivo.</span><span class="sxs-lookup"><span data-stu-id="f512d-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="f512d-216">Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos.</span><span class="sxs-lookup"><span data-stu-id="f512d-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="f512d-217">Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el ejemplo [Escenario 1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to approved USBs.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="f512d-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="f512d-218">Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados</span><span class="sxs-lookup"><span data-stu-id="f512d-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="f512d-219">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="f512d-219">Create groups</span></span>
    1. <span data-ttu-id="f512d-220">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="f512d-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="f512d-221">Un ejemplo para este caso de uso es: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo Cualquier archivo de Storage extraíble y [CD-DVD Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="f512d-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="f512d-222">Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, Id. de proveedor/Id. de producto, Nombre descriptivo : Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) no aprobados Group.xmlejemplo.</span><span class="sxs-lookup"><span data-stu-id="f512d-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f512d-223">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="f512d-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="f512d-224">Creación de la directiva</span><span class="sxs-lookup"><span data-stu-id="f512d-224">Create policy</span></span>
    1. <span data-ttu-id="f512d-225">Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados.</span><span class="sxs-lookup"><span data-stu-id="f512d-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="f512d-226">Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el ejemplo [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="f512d-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="f512d-227">Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="f512d-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="f512d-228">Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el ejemplo [Escenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit write and Execute access to others.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="f512d-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="f512d-229">Implementación y administración de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="f512d-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="f512d-230">La característica Storage control de acceso extraíble te permite aplicar directivas a través de la directiva de grupo a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="f512d-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="f512d-231">Licencias</span><span class="sxs-lookup"><span data-stu-id="f512d-231">Licensing</span></span>

<span data-ttu-id="f512d-232">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="f512d-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="f512d-233">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f512d-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="f512d-234">Implementación de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="f512d-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="f512d-235">Combine todos los grupos `<Groups>` `</Groups>` en un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="f512d-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="f512d-236">En la siguiente imagen se muestra el ejemplo del escenario 1: Impedir el acceso de escritura y ejecución a todos los usuarios, pero permitir [usbs aprobados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="f512d-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Pantalla que muestra las opciones de configuración que permiten usbs aprobados específicos en dispositivos":::
    
2. <span data-ttu-id="f512d-238">Combine todas las reglas `<PolicyRules>` `</PolicyRules>` dentro de un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="f512d-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="f512d-239">Si desea restringir un usuario específico, use la propiedad SID en entry.</span><span class="sxs-lookup"><span data-stu-id="f512d-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="f512d-240">Si no hay ningún SID en la directiva Entry, la entrada se aplicará a todas las instancias de inicio de sesión del equipo.</span><span class="sxs-lookup"><span data-stu-id="f512d-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="f512d-241">La siguiente imagen ilustra el uso de la propiedad SID y un ejemplo de Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir [usbs aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span><span class="sxs-lookup"><span data-stu-id="f512d-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Pantalla que muestra un código que indica el uso del atributo de propiedad SID":::

3. <span data-ttu-id="f512d-243">Guarde los archivos XML de regla y grupo en la carpeta de recurso compartido de red y coloque la ruta de acceso de carpeta de recurso compartido de red en la configuración de directiva de grupo: Configuración del equipo -> Plantillas administrativas -> Windows Componentes **-> Antivirus de Microsoft Defender -> Control de dispositivos: 'Definir** grupos de directivas de control de dispositivos' y 'Definir reglas de directiva de control de dispositivos'.</span><span class="sxs-lookup"><span data-stu-id="f512d-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="f512d-244">El equipo de destino debe poder tener acceso al recurso compartido de red para tener la directiva.</span><span class="sxs-lookup"><span data-stu-id="f512d-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="f512d-245">Sin embargo, una vez que se lee la directiva, la conexión de recurso compartido de red ya no es necesaria, incluso después del reinicio de la máquina.</span><span class="sxs-lookup"><span data-stu-id="f512d-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivos":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="f512d-247">Implementación y administración de directivas a través de Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="f512d-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="f512d-248">La característica Storage control de acceso extraíble permite aplicar directivas a través de OMA-URI a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="f512d-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="f512d-249">Licencias</span><span class="sxs-lookup"><span data-stu-id="f512d-249">Licensing</span></span>

<span data-ttu-id="f512d-250">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="f512d-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="f512d-251">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f512d-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="f512d-252">Permiso</span><span class="sxs-lookup"><span data-stu-id="f512d-252">Permission</span></span>

<span data-ttu-id="f512d-253">Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f512d-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="f512d-254">Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.</span><span class="sxs-lookup"><span data-stu-id="f512d-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="f512d-255">Rol Administrador de directivas y perfiles</span><span class="sxs-lookup"><span data-stu-id="f512d-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="f512d-256">Rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f512d-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="f512d-257">Administrador global</span><span class="sxs-lookup"><span data-stu-id="f512d-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="f512d-258">Implementación de directivas mediante OMA-URI</span><span class="sxs-lookup"><span data-stu-id="f512d-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="f512d-259">**Microsoft Endpoint Manager de administración ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="f512d-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="f512d-260">Para cada grupo, cree una regla OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="f512d-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="f512d-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="f512d-261">OMA-URI:</span></span>

      <span data-ttu-id="f512d-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="f512d-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="f512d-263">Por ejemplo, para cualquier almacenamiento extraíble y un grupo **de CD/DVD** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="f512d-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="f512d-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="f512d-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="f512d-265">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="f512d-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="El archivo xml para el tipo de datos STRING":::

2. <span data-ttu-id="f512d-267">Para cada directiva, también cree un OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="f512d-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="f512d-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="f512d-268">OMA-URI:</span></span>

      <span data-ttu-id="f512d-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="f512d-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="f512d-270">Por ejemplo, para la regla Bloquear escritura y ejecutar acceso, pero permitir **usbs aprobados** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="f512d-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="f512d-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="f512d-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="f512d-272">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="f512d-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualización del archivo XML para el tipo de datos STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="f512d-274">Implementación y administración de directivas mediante la interfaz de usuario de Intune</span><span class="sxs-lookup"><span data-stu-id="f512d-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="f512d-275">Esta funcionalidad (en el Centro de administración de Microsoft Endpoint Manager ( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) todavía no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f512d-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="f512d-276">Ver datos extraíbles Storage control de acceso en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="f512d-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="f512d-277">El Microsoft 365 de seguridad muestra el almacenamiento extraíble bloqueado por el control de dispositivo extraíble Storage control de acceso.</span><span class="sxs-lookup"><span data-stu-id="f512d-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="f512d-278">Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:</span><span class="sxs-lookup"><span data-stu-id="f512d-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="f512d-279">Microsoft 365 para informes E5</span><span class="sxs-lookup"><span data-stu-id="f512d-279">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="La pantalla que muestra el bloqueo del almacenamiento extraíble":::
