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
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0b0f7c5a4a75fdc80509dbc02a43d28f7c93fd7c
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327052"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="b661f-104">Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso</span><span class="sxs-lookup"><span data-stu-id="b661f-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="b661f-105">Microsoft Defender para endpoint device control removable Storage Access Control permite realizar la siguiente tarea:</span><span class="sxs-lookup"><span data-stu-id="b661f-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>

- <span data-ttu-id="b661f-106">auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión</span><span class="sxs-lookup"><span data-stu-id="b661f-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="b661f-107">Privilegio</span><span class="sxs-lookup"><span data-stu-id="b661f-107">Privilege</span></span> |<span data-ttu-id="b661f-108">Permiso</span><span class="sxs-lookup"><span data-stu-id="b661f-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="b661f-109">Acceso</span><span class="sxs-lookup"><span data-stu-id="b661f-109">Access</span></span>    |  <span data-ttu-id="b661f-110">Lectura, Escritura, Ejecución</span><span class="sxs-lookup"><span data-stu-id="b661f-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="b661f-111">Modo de acción</span><span class="sxs-lookup"><span data-stu-id="b661f-111">Action Mode</span></span>    |    <span data-ttu-id="b661f-112">Auditoría, Permitir, Impedir</span><span class="sxs-lookup"><span data-stu-id="b661f-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="b661f-113">Compatibilidad con CSP</span><span class="sxs-lookup"><span data-stu-id="b661f-113">CSP Support</span></span>   |   <span data-ttu-id="b661f-114">Sí</span><span class="sxs-lookup"><span data-stu-id="b661f-114">Yes</span></span>      |
|<span data-ttu-id="b661f-115">Compatibilidad con GPO</span><span class="sxs-lookup"><span data-stu-id="b661f-115">GPO Support</span></span>    |   <span data-ttu-id="b661f-116">Sí</span><span class="sxs-lookup"><span data-stu-id="b661f-116">Yes</span></span>      |
|<span data-ttu-id="b661f-117">Soporte técnico basado en usuarios</span><span class="sxs-lookup"><span data-stu-id="b661f-117">User-based Support</span></span>     |   <span data-ttu-id="b661f-118">Sí</span><span class="sxs-lookup"><span data-stu-id="b661f-118">Yes</span></span>      |
|<span data-ttu-id="b661f-119">Compatibilidad basada en máquina</span><span class="sxs-lookup"><span data-stu-id="b661f-119">Machine-based Support</span></span>    |    <span data-ttu-id="b661f-120">Sí</span><span class="sxs-lookup"><span data-stu-id="b661f-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="b661f-121">Preparar los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="b661f-121">Prepare your endpoints</span></span>

<span data-ttu-id="b661f-122">Implemente el control Storage de acceso extraíble en Windows 10 dispositivos con cliente antimalware versión **4.18.2103.3** o posterior .</span><span class="sxs-lookup"><span data-stu-id="b661f-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="b661f-123">**4.18.2104 o** posterior: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basada en ruta de archivo, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="b661f-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="b661f-124">**4.18.2105** o posterior: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/compatibilidad con SCSI conectada a USB (UAS)</span><span class="sxs-lookup"><span data-stu-id="b661f-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

- <span data-ttu-id="b661f-125">**4.18.2107** o posterior: Agregar compatibilidad Windows dispositivo portátil (WPD) (para dispositivos móviles, como tabletas)</span><span class="sxs-lookup"><span data-stu-id="b661f-125">**4.18.2107 or later**: Add Windows Portable Device (WPD) support (for mobile devices, such as tablets)</span></span>

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell":::

> [!NOTE]
> <span data-ttu-id="b661f-127">Ninguno de Seguridad de Windows componentes deben estar activos, puede ejecutar Removable Storage Access Control independientemente Seguridad de Windows estado.</span><span class="sxs-lookup"><span data-stu-id="b661f-127">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="b661f-128">Propiedades de la directiva</span><span class="sxs-lookup"><span data-stu-id="b661f-128">Policy properties</span></span>

<span data-ttu-id="b661f-129">Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:</span><span class="sxs-lookup"><span data-stu-id="b661f-129">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="b661f-130">**Nombre de la propiedad: Id. de grupo**</span><span class="sxs-lookup"><span data-stu-id="b661f-130">**Property name: Group Id**</span></span>

1. <span data-ttu-id="b661f-131">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa el grupo y se usará en la directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-131">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="b661f-132">**Nombre de la propiedad: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="b661f-132">**Property name: DescriptorIdList**</span></span>

2. <span data-ttu-id="b661f-133">Descripción: enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="b661f-133">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="b661f-134">Para cada propiedad de dispositivo, consulta **la sección Propiedades del** dispositivo anterior para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="b661f-134">For each device property, see **Device Properties** section above for more detail.</span></span>

3. <span data-ttu-id="b661f-135">Opciones:</span><span class="sxs-lookup"><span data-stu-id="b661f-135">Options:</span></span>
    - <span data-ttu-id="b661f-136">PrimaryId</span><span class="sxs-lookup"><span data-stu-id="b661f-136">PrimaryId</span></span>
        - <span data-ttu-id="b661f-137">RemovableMediaDevices</span><span class="sxs-lookup"><span data-stu-id="b661f-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="b661f-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="b661f-138">CdRomDevices</span></span>
        - <span data-ttu-id="b661f-139">WpdDevices</span><span class="sxs-lookup"><span data-stu-id="b661f-139">WpdDevices</span></span>
    - <span data-ttu-id="b661f-140">DeviceId</span><span class="sxs-lookup"><span data-stu-id="b661f-140">DeviceId</span></span>
    - <span data-ttu-id="b661f-141">HardwareId</span><span class="sxs-lookup"><span data-stu-id="b661f-141">HardwareId</span></span>
    - <span data-ttu-id="b661f-142">InstancePathId: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="b661f-142">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="b661f-143">El número al final (por **ejemplo,&0**) representa la ranura disponible y puede cambiar de un dispositivo a otro.</span><span class="sxs-lookup"><span data-stu-id="b661f-143">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="b661f-144">Para obtener los mejores resultados, use un comodín al final.</span><span class="sxs-lookup"><span data-stu-id="b661f-144">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="b661f-145">Por ejemplo, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="b661f-145">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="b661f-146">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="b661f-146">FriendlyNameId</span></span>
    - <span data-ttu-id="b661f-147">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="b661f-147">SerialNumberId</span></span>
    - <span data-ttu-id="b661f-148">VID</span><span class="sxs-lookup"><span data-stu-id="b661f-148">VID</span></span>
    - <span data-ttu-id="b661f-149">PID</span><span class="sxs-lookup"><span data-stu-id="b661f-149">PID</span></span>
    - <span data-ttu-id="b661f-150">VID_PID</span><span class="sxs-lookup"><span data-stu-id="b661f-150">VID_PID</span></span>
        - <span data-ttu-id="b661f-151">0751_55E0: coincide con este par VID/PID exacto</span><span class="sxs-lookup"><span data-stu-id="b661f-151">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="b661f-152">_55E0: hacer coincidir cualquier medio con PID=55E0</span><span class="sxs-lookup"><span data-stu-id="b661f-152">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="b661f-153">0751_: hacer coincidir cualquier medio con VID=0751</span><span class="sxs-lookup"><span data-stu-id="b661f-153">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="b661f-154">**Nombre de la propiedad: MatchType**</span><span class="sxs-lookup"><span data-stu-id="b661f-154">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="b661f-155">Descripción: cuando se usan varias propiedades de dispositivo en descriptorIDList, MatchType define la relación.</span><span class="sxs-lookup"><span data-stu-id="b661f-155">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

2. <span data-ttu-id="b661f-156">Opciones:</span><span class="sxs-lookup"><span data-stu-id="b661f-156">Options:</span></span>

    - <span data-ttu-id="b661f-157">MatchAll: cualquier atributo bajo descriptorIdList será **relación And;** por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema comprobará si el USB cumple ambos valores.</span><span class="sxs-lookup"><span data-stu-id="b661f-157">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="b661f-158">MatchAny: los atributos de descriptorIdList serán **o** relación; por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema hará la aplicación siempre que el USB tenga un valor **DeviceID** o **InstanceID** idéntico.</span><span class="sxs-lookup"><span data-stu-id="b661f-158">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="b661f-159">Las siguientes son las propiedades de la directiva de control de acceso:</span><span class="sxs-lookup"><span data-stu-id="b661f-159">Following are the access control policy properties:</span></span>

<span data-ttu-id="b661f-160">**Nombre de la propiedad: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="b661f-160">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="b661f-161">Descripción: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa la directiva y se usará en los informes y la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="b661f-161">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="b661f-162">**Nombre de la propiedad: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="b661f-162">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="b661f-163">Descripción: los grupos a los que se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-163">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="b661f-164">Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.</span><span class="sxs-lookup"><span data-stu-id="b661f-164">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

2. <span data-ttu-id="b661f-165">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="b661f-165">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="b661f-166">En el ejemplo siguiente se muestra el uso de GroupID:</span><span class="sxs-lookup"><span data-stu-id="b661f-166">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="b661f-167">**Nombre de la propiedad: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="b661f-167">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="b661f-168">Descripción: los grupos a los que no se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-168">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="b661f-169">Opciones: El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia.</span><span class="sxs-lookup"><span data-stu-id="b661f-169">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="b661f-170">**Nombre de la propiedad: Id. de entrada**</span><span class="sxs-lookup"><span data-stu-id="b661f-170">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="b661f-171">Descripción: One PolicyRule puede tener varias entradas; cada entrada con un GUID único indica al Control de dispositivos una restricción.</span><span class="sxs-lookup"><span data-stu-id="b661f-171">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="b661f-172">**Nombre de la propiedad: Type**</span><span class="sxs-lookup"><span data-stu-id="b661f-172">**Property name: Type**</span></span>

1. <span data-ttu-id="b661f-173">Descripción: define la acción de los grupos de almacenamiento extraíbles en IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="b661f-173">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="b661f-174">Aplicación: Permitir o denegar</span><span class="sxs-lookup"><span data-stu-id="b661f-174">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="b661f-175">Auditoría: AuditAllowed o AuditDenied</span><span class="sxs-lookup"><span data-stu-id="b661f-175">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="b661f-176">Opciones:</span><span class="sxs-lookup"><span data-stu-id="b661f-176">Options:</span></span>

    - <span data-ttu-id="b661f-177">Permitir</span><span class="sxs-lookup"><span data-stu-id="b661f-177">Allow</span></span>
    - <span data-ttu-id="b661f-178">Denegar</span><span class="sxs-lookup"><span data-stu-id="b661f-178">Deny</span></span>
    - <span data-ttu-id="b661f-179">AuditAllowed: define la notificación y el evento cuando se permite el acceso</span><span class="sxs-lookup"><span data-stu-id="b661f-179">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="b661f-180">AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Denegar.**</span><span class="sxs-lookup"><span data-stu-id="b661f-180">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="b661f-181">Cuando haya tipos de conflicto para el mismo medio, el sistema aplicará el primero de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-181">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="b661f-182">Un ejemplo de tipo de conflicto **es Allow** y **Deny**.</span><span class="sxs-lookup"><span data-stu-id="b661f-182">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="b661f-183">**Nombre de la propiedad: Sid**</span><span class="sxs-lookup"><span data-stu-id="b661f-183">**Property name: Sid**</span></span>

<span data-ttu-id="b661f-184">Descripción: Equipo local Sid o sid del objeto AD, define si se va a aplicar esta directiva sobre un usuario o grupo de usuarios específicos; una entrada puede tener un máximo de un Sid y una entrada sin que ningún Sid signifique aplicar la directiva sobre la máquina.</span><span class="sxs-lookup"><span data-stu-id="b661f-184">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific user or user group; one entry can have a maximum of one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="b661f-185">**Nombre de la propiedad: ComputerSid**</span><span class="sxs-lookup"><span data-stu-id="b661f-185">**Property name: ComputerSid**</span></span>

<span data-ttu-id="b661f-186">Descripción: Equipo local Sid o Sid del objeto AD, define si se va a aplicar esta directiva sobre un equipo o grupo de máquinas específico; una entrada puede tener un máximo de un ComputerSid y una entrada sin que ComputerSid signifique aplicar la directiva sobre el equipo.</span><span class="sxs-lookup"><span data-stu-id="b661f-186">Description: Local computer Sid or the Sid of the AD object, defines whether to apply this policy over a specific machine or machine group; one entry can have a maximum of one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="b661f-187">Si desea aplicar una entrada a un usuario específico y a un equipo específico, agregue Sid y ComputerSid a la misma entrada.</span><span class="sxs-lookup"><span data-stu-id="b661f-187">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="b661f-188">**Nombre de la propiedad: Opciones**</span><span class="sxs-lookup"><span data-stu-id="b661f-188">**Property name: Options**</span></span>

<span data-ttu-id="b661f-189">Descripción: define si se va a mostrar la notificación o no.</span><span class="sxs-lookup"><span data-stu-id="b661f-189">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="La pantalla en la que se puede ver el estado del dispositivo":::

<span data-ttu-id="b661f-191">Opciones: 0-4.</span><span class="sxs-lookup"><span data-stu-id="b661f-191">Options: 0-4.</span></span> <span data-ttu-id="b661f-192">Cuando el tipo Permitir o Denegar está seleccionado:</span><span class="sxs-lookup"><span data-stu-id="b661f-192">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="b661f-193">0: nada</span><span class="sxs-lookup"><span data-stu-id="b661f-193">0: nothing</span></span>
   - <span data-ttu-id="b661f-194">4: deshabilitar **AuditAllowed** y **AuditDenied** para esta entrada.</span><span class="sxs-lookup"><span data-stu-id="b661f-194">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="b661f-195">Incluso si **se produce** block y la **configuración auditDenied** está configurada, el sistema no mostrará la notificación.</span><span class="sxs-lookup"><span data-stu-id="b661f-195">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="b661f-196">Cuando se **selecciona Tipo AuditAllowed** **o AuditDenied:**</span><span class="sxs-lookup"><span data-stu-id="b661f-196">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="b661f-197">0: nada</span><span class="sxs-lookup"><span data-stu-id="b661f-197">0: nothing</span></span>
   - <span data-ttu-id="b661f-198">1: mostrar notificación</span><span class="sxs-lookup"><span data-stu-id="b661f-198">1: show notification</span></span>
   - <span data-ttu-id="b661f-199">2: evento send</span><span class="sxs-lookup"><span data-stu-id="b661f-199">2: send event</span></span>
   - <span data-ttu-id="b661f-200">3: mostrar notificación y enviar evento</span><span class="sxs-lookup"><span data-stu-id="b661f-200">3: show notification and send event</span></span>

<span data-ttu-id="b661f-201">**Nombre de la propiedad: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="b661f-201">**Property name: AccessMask**</span></span>

<span data-ttu-id="b661f-202">Descripción: define el acceso.</span><span class="sxs-lookup"><span data-stu-id="b661f-202">Description: Defines the access.</span></span>

<span data-ttu-id="b661f-203">Opciones 1-7:</span><span class="sxs-lookup"><span data-stu-id="b661f-203">Options 1-7:</span></span>
  - <span data-ttu-id="b661f-204">1: Leer</span><span class="sxs-lookup"><span data-stu-id="b661f-204">1: Read</span></span>
  - <span data-ttu-id="b661f-205">2: Escribir</span><span class="sxs-lookup"><span data-stu-id="b661f-205">2: Write</span></span>
  - <span data-ttu-id="b661f-206">3: Lectura y escritura</span><span class="sxs-lookup"><span data-stu-id="b661f-206">3: Read and Write</span></span>
  - <span data-ttu-id="b661f-207">4: Ejecutar</span><span class="sxs-lookup"><span data-stu-id="b661f-207">4: Execute</span></span>
  - <span data-ttu-id="b661f-208">5: Leer y ejecutar</span><span class="sxs-lookup"><span data-stu-id="b661f-208">5: Read and Execute</span></span>
  - <span data-ttu-id="b661f-209">6: Escribir y ejecutar</span><span class="sxs-lookup"><span data-stu-id="b661f-209">6: Write and Execute</span></span>
  - <span data-ttu-id="b661f-210">7: Lectura y escritura y ejecución</span><span class="sxs-lookup"><span data-stu-id="b661f-210">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="b661f-211">Escenarios comunes Storage control de acceso extraíble</span><span class="sxs-lookup"><span data-stu-id="b661f-211">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="b661f-212">Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.</span><span class="sxs-lookup"><span data-stu-id="b661f-212">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="b661f-213">Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir usbs aprobados específicos</span><span class="sxs-lookup"><span data-stu-id="b661f-213">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="b661f-214">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="b661f-214">Create groups</span></span>

    1. <span data-ttu-id="b661f-215">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="b661f-215">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="b661f-216">Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="b661f-216">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b661f-217">Grupo 2: USB aprobados en función de las propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b661f-217">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="b661f-218">Un ejemplo para este caso de uso es: Id. de instancia: grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs aprobados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b661f-218">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b661f-219">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="b661f-219">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="b661f-220">Creación de la directiva</span><span class="sxs-lookup"><span data-stu-id="b661f-220">Create policy</span></span>

    1. <span data-ttu-id="b661f-221">Directiva 1: Bloquear el acceso de escritura y ejecución, pero permitir los USB aprobados.</span><span class="sxs-lookup"><span data-stu-id="b661f-221">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="b661f-222">Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el ejemplo Escenario 1 Block [Write and Execute Access,](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) pero permite el acceso USBs.xmlaprobado.</span><span class="sxs-lookup"><span data-stu-id="b661f-222">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b661f-223">Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos.</span><span class="sxs-lookup"><span data-stu-id="b661f-223">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="b661f-224">Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el ejemplo [Escenario 1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to approved USBs.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="b661f-224">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="b661f-225">Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados</span><span class="sxs-lookup"><span data-stu-id="b661f-225">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="b661f-226">Crear grupos</span><span class="sxs-lookup"><span data-stu-id="b661f-226">Create groups</span></span>

    1. <span data-ttu-id="b661f-227">Grupo 1: Cualquier almacenamiento extraíble y CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="b661f-227">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="b661f-228">Un ejemplo para este caso de uso es: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo Cualquier archivo de Storage extraíble y [CD-DVD Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="b661f-228">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b661f-229">Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, Id. de proveedor/Id. de producto, Nombre descriptivo : Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) no aprobados Group.xmlejemplo.</span><span class="sxs-lookup"><span data-stu-id="b661f-229">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b661f-230">Debe reemplazar por `&` en `&amp;` el valor.</span><span class="sxs-lookup"><span data-stu-id="b661f-230">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="b661f-231">Creación de la directiva</span><span class="sxs-lookup"><span data-stu-id="b661f-231">Create policy</span></span>

    1. <span data-ttu-id="b661f-232">Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b661f-232">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="b661f-233">Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el ejemplo [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="b661f-233">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="b661f-234">Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b661f-234">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="b661f-235">Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el ejemplo [Escenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit write and Execute access to others.xmlfile.</span><span class="sxs-lookup"><span data-stu-id="b661f-235">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="b661f-236">Implementación y administración de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b661f-236">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="b661f-237">La característica Storage control de acceso extraíble te permite aplicar directivas a través de la directiva de grupo a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="b661f-237">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="b661f-238">Concesión de licencias</span><span class="sxs-lookup"><span data-stu-id="b661f-238">Licensing</span></span>

<span data-ttu-id="b661f-239">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="b661f-239">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="b661f-240">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b661f-240">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="b661f-241">Implementación de directivas mediante directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b661f-241">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="b661f-242">Combine todos los grupos `<Groups>` `</Groups>` en un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="b661f-242">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="b661f-243">En la siguiente imagen se muestra el ejemplo del escenario 1: Impedir el acceso de escritura y ejecución a todos los usuarios, pero permitir [usbs aprobados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)</span><span class="sxs-lookup"><span data-stu-id="b661f-243">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Pantalla que muestra las opciones de configuración que permiten usbs aprobados específicos en dispositivos":::
    
2. <span data-ttu-id="b661f-245">Combine todas las reglas `<PolicyRules>` `</PolicyRules>` dentro de un archivo xml.</span><span class="sxs-lookup"><span data-stu-id="b661f-245">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="b661f-246">Si desea restringir un usuario específico, use la propiedad SID en entry.</span><span class="sxs-lookup"><span data-stu-id="b661f-246">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="b661f-247">Si no hay ningún SID en la directiva Entry, la entrada se aplicará a todas las instancias de inicio de sesión del equipo.</span><span class="sxs-lookup"><span data-stu-id="b661f-247">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="b661f-248">La siguiente imagen ilustra el uso de la propiedad SID y un ejemplo de Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir [usbs aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span><span class="sxs-lookup"><span data-stu-id="b661f-248">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Pantalla que muestra un código que indica el uso del atributo de propiedad SID":::

3. <span data-ttu-id="b661f-250">Guarde los archivos XML de regla y grupo en la carpeta de recurso compartido de red y coloque la ruta de acceso de carpeta de recurso compartido de red en la configuración de directiva de grupo: Configuración del equipo -> Plantillas administrativas -> Windows Componentes **-> Antivirus de Microsoft Defender -> Control de dispositivos: 'Definir** grupos de directivas de control de dispositivos' y 'Definir reglas de directiva de control de dispositivos'.</span><span class="sxs-lookup"><span data-stu-id="b661f-250">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="b661f-251">El equipo de destino debe poder tener acceso al recurso compartido de red para tener la directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-251">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="b661f-252">Sin embargo, una vez que se lee la directiva, la conexión de recurso compartido de red ya no es necesaria, incluso después del reinicio de la máquina.</span><span class="sxs-lookup"><span data-stu-id="b661f-252">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivos":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="b661f-254">Implementación y administración de directivas a través de Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="b661f-254">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="b661f-255">La característica Storage control de acceso extraíble permite aplicar directivas a través de OMA-URI a usuarios o dispositivos, o a ambos.</span><span class="sxs-lookup"><span data-stu-id="b661f-255">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="b661f-256">Concesión de licencias</span><span class="sxs-lookup"><span data-stu-id="b661f-256">Licensing</span></span>

<span data-ttu-id="b661f-257">Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span><span class="sxs-lookup"><span data-stu-id="b661f-257">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="b661f-258">Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b661f-258">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="b661f-259">Permiso</span><span class="sxs-lookup"><span data-stu-id="b661f-259">Permission</span></span>

<span data-ttu-id="b661f-260">Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b661f-260">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="b661f-261">Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.</span><span class="sxs-lookup"><span data-stu-id="b661f-261">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="b661f-262">Rol Administrador de directivas y perfiles</span><span class="sxs-lookup"><span data-stu-id="b661f-262">Policy and profile Manager role</span></span>
- <span data-ttu-id="b661f-263">Rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b661f-263">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="b661f-264">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b661f-264">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="b661f-265">Implementación de directivas mediante OMA-URI</span><span class="sxs-lookup"><span data-stu-id="b661f-265">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="b661f-266">**Microsoft Endpoint Manager de administración ( https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span><span class="sxs-lookup"><span data-stu-id="b661f-266">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="b661f-267">Para cada grupo, cree una regla OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="b661f-267">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="b661f-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="b661f-268">OMA-URI:</span></span>

      <span data-ttu-id="b661f-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="b661f-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="b661f-270">Por ejemplo, para cualquier almacenamiento extraíble y un grupo **de CD/DVD** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="b661f-270">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="b661f-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="b661f-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="b661f-272">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="b661f-272">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="El archivo xml para el tipo de datos STRING":::

2. <span data-ttu-id="b661f-274">Para cada directiva, también cree un OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="b661f-274">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="b661f-275">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="b661f-275">OMA-URI:</span></span>

      <span data-ttu-id="b661f-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="b661f-276">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="b661f-277">Por ejemplo, para la regla Bloquear escritura y ejecutar acceso, pero permitir **usbs aprobados** en el ejemplo, el vínculo debe ser:</span><span class="sxs-lookup"><span data-stu-id="b661f-277">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="b661f-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="b661f-278">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="b661f-279">Tipo de datos: String (archivo XML)</span><span class="sxs-lookup"><span data-stu-id="b661f-279">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visualización del archivo XML para el tipo de datos STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="b661f-281">Implementación y administración de directivas mediante la interfaz de usuario de Intune</span><span class="sxs-lookup"><span data-stu-id="b661f-281">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="b661f-282">Esta funcionalidad (en el Centro de administración de Microsoft Endpoint Manager ( https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) todavía no está disponible.</span><span class="sxs-lookup"><span data-stu-id="b661f-282">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b661f-283">Ver datos extraíbles Storage control de acceso en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b661f-283">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b661f-284">El Microsoft 365 de seguridad muestra el almacenamiento extraíble bloqueado por el control de dispositivo extraíble Storage control de acceso.</span><span class="sxs-lookup"><span data-stu-id="b661f-284">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="b661f-285">Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:</span><span class="sxs-lookup"><span data-stu-id="b661f-285">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="b661f-286">Microsoft 365 para informes E5</span><span class="sxs-lookup"><span data-stu-id="b661f-286">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="b661f-288">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="b661f-288">Frequently asked questions</span></span>

<span data-ttu-id="b661f-289">**¿Cuál es la limitación de medios de almacenamiento extraíbles para el número máximo de USB?**</span><span class="sxs-lookup"><span data-stu-id="b661f-289">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="b661f-290">Hemos validado un grupo USB con 100.000 medios, con un tamaño de hasta 7 MB.</span><span class="sxs-lookup"><span data-stu-id="b661f-290">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="b661f-291">La directiva funciona tanto en Intune como en GPO sin problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b661f-291">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="b661f-292">**¿Por qué la directiva no funciona?**</span><span class="sxs-lookup"><span data-stu-id="b661f-292">**Why does the policy not work?**</span></span>

<span data-ttu-id="b661f-293">La razón más común es que no hay ninguna versión [de cliente antimalware necesaria.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="b661f-293">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="b661f-294">Otro motivo podría ser que el archivo XML no tiene el formato correcto, por ejemplo, no se usa el formato de reducción correcto para el carácter "&" en el archivo XML, o el editor de texto puede agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione.</span><span class="sxs-lookup"><span data-stu-id="b661f-294">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="b661f-295">Una solución sencilla es descargar el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (seleccione **Sin** procesar y, a continuación, **Guardar como**) y, a continuación, actualizar.</span><span class="sxs-lookup"><span data-stu-id="b661f-295">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="b661f-296">Si hay un valor y la directiva se administra a través de la directiva de grupo, compruebe si el dispositivo cliente puede tener acceso a la ruta XML de directiva.</span><span class="sxs-lookup"><span data-stu-id="b661f-296">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="b661f-297">**¿Cómo puedo saber qué equipo está usando la versión de cliente antimalware des actualizada en la organización?**</span><span class="sxs-lookup"><span data-stu-id="b661f-297">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="b661f-298">Puede usar la siguiente consulta para obtener la versión del cliente antimalware en el portal de seguridad Microsoft 365 web:</span><span class="sxs-lookup"><span data-stu-id="b661f-298">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```
