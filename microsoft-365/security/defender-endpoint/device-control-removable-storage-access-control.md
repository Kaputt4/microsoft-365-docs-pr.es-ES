---
title: Microsoft Defender para punto de conexión dispositivo control almacenamiento extraíble Access Control, medios de almacenamiento extraíbles
description: Un tutorial sobre Microsoft Defender para punto de conexión
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
ms.date: 09/29/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: f84351b7f32edad98659ca27a9ae7e4d67f13364
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233868"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender para punto de conexión almacenamiento extraíble de control de dispositivos Access Control

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directiva de grupo y Intune OMA-URI/Administración de directivas personalizadas de este producto ya están disponibles con carácter general (4.18.2106): Consulte [el blog de Tech Community: Proteger el almacenamiento extraíble y la impresora con Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

## <a name="overview"></a>Información general

Microsoft Defender para punto de conexión característica de almacenamiento extraíble de control de dispositivos Access Control permite auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión.

|Privilegio|Permiso|
|---|---|
|Acceso|Lectura, Escritura, Ejecución|
|Modo de acción|Auditar, permitir, impedir|
|Compatibilidad con CSP|Yes|
|Compatibilidad con GPO|Yes|
|Soporte técnico basado en el usuario|Yes|
|Compatibilidad basada en máquinas|Yes|

Microsoft Defender para punto de conexión característica de almacenamiento extraíble de control de dispositivos Access Control proporciona las siguientes funcionalidades:

### <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente Access Control de almacenamiento extraíble en dispositivos Windows 10 y Windows 11 que tengan la versión de cliente antimalware **4.18.2103.3 o posterior**.

- **4.18.2104 o posterior**: Agregar `SerialNumberId`, , `VID_PID`compatibilidad con GPO basado en filepath y `ComputerSid`

- **4.18.2105 o posterior**: Agregar compatibilidad con caracteres comodín para `HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId`, la combinación de un usuario específico en una máquina específica, SSD extraíble (un SSD Extremo sanDisk)/Compatibilidad con SCSI conectado a USB (UAS)

- **4.18.2107 o posterior**: Agregar compatibilidad con dispositivos portátiles Windows (WPD) (para dispositivos móviles, como tabletas); agregar `AccountName` a [la búsqueda avanzada](device-control-removable-storage-access-control.md#view-data-in-microsoft-defender-for-endpoint)

- **4.18.2205 o posterior**: expanda el cumplimiento predeterminado a **Impresora**. Si lo establece en **Denegar**, también bloqueará La impresora, por lo que si solo desea administrar el almacenamiento, asegúrese de crear una directiva personalizada para permitir la impresora.

:::image type="content" source="images/powershell.png" alt-text="Captura de pantalla de la interfaz de PowerShell" lightbox="images/powershell.png":::

> [!NOTE]
> No es necesario que ninguno de los componentes de Seguridad de Windows esté activo, ya que puede ejecutar almacenamiento extraíble Access Control independientemente del estado de Seguridad de Windows.

## <a name="device-control-removable-storage-access-control-properties"></a>Propiedades de Access Control de almacenamiento extraíble de Control de dispositivos

El Access Control De almacenamiento extraíble incluye la creación de grupos de almacenamiento extraíbles y la creación de reglas de directiva de acceso:

- El grupo de almacenamiento extraíble permite crear un grupo. Por ejemplo, grupo USB autorizado o grupo USB cifrado.
- La regla de directiva de acceso permite crear una directiva para restringir cada grupo de almacenamiento extraíble. Por ejemplo, solo permitir que el usuario autorizado escriba un grupo USB autorizado de acceso.
- Para bloquear una clase de almacenamiento extraíble específica pero permitir medios específicos, puede usar "`IncludedIdList` un grupo a través `PrimaryId` de y `ExcludedIDList` un grupo a través`HardwareId``DeviceId`\/ de /etc.". Para obtener instrucciones adicionales, vea [Deploy Removable Storage Access Control by using Intune OMA-URI](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri).

Estas son las propiedades que puede usar al crear los archivos XML de grupo y directiva.

### <a name="removable-storage-group"></a>Grupo de almacenamiento extraíble

|Nombre de la propiedad|Descripción|Opciones|
|---|---|---|
|**Groupid**|GUID, un identificador único, representa el grupo y se usará en la directiva.||
|**DescriptorIdList**|Enumere las propiedades del dispositivo que desea usar para cubrir en el grupo. Todas las propiedades distinguen mayúsculas de minúsculas. |**PrimaryId**: el identificador principal incluye `RemovableMediaDevices`, `CdRomDevices`, `WpdDevices`, `PrinterDevices`. <p>**InstancePathId**: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`. Es en la `Device instance path` Administrador de dispositivos. El número al final (por ejemplo, &0) representa la ranura disponible y puede cambiar de dispositivo a dispositivo. Para obtener los mejores resultados, use un carácter comodín al final. Por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`. <p>**DeviceId**: para transformar `Device instance path` al formato de id. de dispositivo, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers), por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07` <p>**HardwareId**: cadena que identifica el dispositivo en el sistema, por ejemplo, `USBSTOR\DiskGeneric_Flash_Disk___8.07`. Está `Hardware Ids` en la Administrador de dispositivos. <br>**Nota**: El identificador de hardware no es único; diferentes dispositivos pueden compartir el mismo valor.<p>**FriendlyNameId**: es una cadena adjunta al dispositivo, por ejemplo, `Generic Flash Disk USB Device`. Es en la `Friendly name` Administrador de dispositivos. <p>**BusId**: por ejemplo, USB, SCSI <p>**SerialNumberId**: puede encontrar SerialNumberId en `Device instance path` el Administrador de dispositivos, por ejemplo, `03003324080520232521` es SerialNumberId en USBSTOR\DISK&VEN__USB&PROD__SANDISK_3.2GEN1&REV_1.00\\`03003324080520232521`&0 <p>**VID_PID**: Id. de proveedor es el código de proveedor de cuatro dígitos que el comité USB asigna al proveedor. Id. de producto es el código de producto de cuatro dígitos que el proveedor asigna al dispositivo. Admite caracteres comodín. Para transformar `Device instance path` a id. de proveedor y formato de id. de producto, consulte [Identificadores USB estándar](/windows-hardware/drivers/install/standard-usb-identifiers). Por ejemplo: <br>`0751_55E0`: coincide con este par VID/PID exacto<br>`_55E0`: coincide con cualquier medio con PID=55E0 <br>`0751_`: coincide con cualquier medio con VID=0751 <p> **Nota**: Consulte [Cómo buscar la propiedad media en el Administrador de dispositivos?](device-control-removable-storage-access-control-faq.md#how-do-i-find-the-media-property-in-the-device-manager) para comprender cómo encontrar la propiedad en Administrador de dispositivos.|
|**MatchType**|Cuando se usan varias propiedades de `DescriptorIDList`dispositivo en , MatchType define la relación.|**MatchAll**: los atributos de la `DescriptorIdList` relación serán **Y** ; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema comprobará si el USB cumple ambos valores. <p> **MatchAny**: los atributos de DescriptorIdList serán **O** relationship; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema realizará la aplicación siempre y cuando el USB tenga un valor **de DeviceID** o **InstanceID** idéntico.|

### <a name="access-policy-rule"></a>Regla de directiva de acceso

Puede usar las siguientes propiedades para crear la directiva de control de acceso:

| Nombre de la propiedad | Descripción | Opciones |
|---|---|---|
| **Id. de PolicyRule** | GUID, un identificador único, representa la directiva y se usará en la generación de informes y la solución de problemas. | |
| **IncludedIdList** | Los grupos a los que se aplicará la directiva. Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.|El identificador de grupo o GUID debe usarse en esta instancia. <p> En el ejemplo siguiente se muestra el uso de GroupID: <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | Los grupos a los que no se aplicará la directiva. | El identificador de grupo o GUID debe usarse en esta instancia. |
| **Id. de entrada** | Una policyRule puede tener varias entradas; cada entrada con un GUID único indica a Device Control una restricción.| |
| **Tipo** | Define la acción para los grupos de almacenamiento extraíbles en IncludedIDList. <p>Cumplimiento: Permitir o denegar <p>Auditoría: AuditAllowed o AuditDenied<p> | Permitir<p>Denegar <p>AuditAllowed: define la notificación y el evento cuando se permite el acceso. <p>AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Deny** .<p> Cuando haya tipos de conflicto para los mismos medios, el sistema aplicará el primero de la directiva. Un ejemplo de un tipo de conflicto es **Allow** y **Deny**. |
| **SID** | El SID de usuario local, el grupo de SID de usuario o el SID del objeto de AD, define si se debe aplicar esta directiva a un usuario o grupo de usuarios específico. Una entrada puede tener un máximo de un SID y una entrada sin ningún SID significa aplicar la directiva sobre la máquina. |  |
| **ComputerSID** | SiD de equipo local, grupo de SID de equipo o SID del objeto de AD, define si se debe aplicar esta directiva a través de un equipo o grupo de máquinas específico. Una entrada puede tener un máximo de un ComputerSID y una entrada sin ningún ComputerSID significa aplicar la directiva sobre el equipo. Si desea aplicar una entrada a un usuario específico y a una máquina específica, agregue tanto SID como ComputerSID a la misma entrada. |  |
| **Opciones** | Define si se va a mostrar la notificación o no |**Cuando se selecciona Permitir tipo**: <p>0: nada<p>4: deshabilite **AuditAllowed** y **AuditDenied** para esta entrada. Incluso si **se produce Allow** y la opción AuditAllowed está configurada, el sistema no enviará ningún evento. <p>8: capturar información del archivo y tener una copia del archivo como evidencia para el acceso de escritura. <p>16: capturar información de archivo para el acceso de escritura. <p>**Cuando se selecciona Tipo denegado**: <p>0: nada<p>4: deshabilite **AuditDenied** para esta entrada. Incluso si **se produce Block** y la opción AuditDenied está configurada, el sistema no mostrará la notificación. <p>**Cuando se selecciona **Type AuditAllowed (AuditAllowed** de tipo):** <p>0: nada <p>1: nada <p>2: enviar evento<p> **Cuando se selecciona **Auditoría de tipos denegada****: <p>0: nada <p>1: mostrar notificación <p>2: enviar evento<p>3: mostrar notificación y enviar evento |
|AccessMask|Define el acceso. | **Acceso a nivel de disco**: <p>1: Lectura <p>2: Escritura <p>4: Ejecutar <p>**Acceso a nivel del sistema de archivos**: <p>8: Lectura del sistema de archivos <p>16: Escritura del sistema de archivos <p>32: Ejecución del sistema de archivos <p><p>Puede tener varios accesos realizando una operación O binaria; por ejemplo, AccessMask para lectura y escritura y Ejecución será 7; AccessMask for Read and Write será 3.|

Para obtener instrucciones específicas, consulte:

| Tema | Descripción |
|---|---|
| [Implementación de Access Control de almacenamiento extraíble mediante directiva de grupo](deploy-manage-removable-storage-group-policy.md) | Use directiva de grupo para implementar la directiva.|
| [Implementación de Access Control de almacenamiento extraíble mediante Intune OMA-URI](deploy-manage-removable-storage-intune.md) | Use Intune para implementar la directiva.|

## <a name="view-data-in-microsoft-defender-for-endpoint"></a>Visualización de datos en Microsoft Defender para punto de conexión

El [portal de Microsoft 365 Defender](https://security.microsoft.com/advanced-hunting) muestra los eventos desencadenados por la Access Control de almacenamiento extraíble de Device Control. Para acceder a la seguridad de Microsoft 365, debe tener la siguiente suscripción:

- Informes de Microsoft 365 para E5

Si `AuditAllowed` o `AuditDenied` está configurado en la directiva y el **evento Send** está seleccionado en **Opciones**, se enviará un evento a búsqueda avanzada o al informe control dispositivo para cada acceso cubierto (`AccessMask` en la entrada), independientemente de si el sistema o el usuario que inició sesión lo iniciaron.

```kusto
//RemovableStoragePolicyTriggered: event triggered by Disk level enforcement
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
| extend parsed=parse_json(AdditionalFields)
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)
| extend MediaBusType = tostring(parsed.BusType)
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId)
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, FolderPath, FileSize
| order by Timestamp desc
```

```kusto
//information of file written to removable storage
DeviceEvents
| where ActionType contains "RemovableStorageFileEvent"
| extend parsed=parse_json(AdditionalFields)
| extend Policy = tostring(parsed.Policy)
| extend PolicyRuleId = tostring(parsed.PolicyRuleId)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaInstanceId = tostring(parsed.InstanceId)
| extend MediaName = tostring(parsed.MediaName)
| extend MediaProductId = tostring(parsed.ProductId)
| extend MediaVendorId = tostring(parsed.VendorId)
| extend MediaSerialNumber = tostring(parsed.SerialNumber)
| extend FileInformationOperation = tostring(parsed.DuplicatedOperation)
| extend FileEvidenceLocation = tostring(parsed.TargetFileLocation)
| project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, Policy, PolicyRuleId, FileInformationOperation, MediaClassName, MediaInstanceId, MediaName, MediaProductId, MediaVendorId, MediaSerialNumber, FileName, FolderPath, FileSize, FileEvidenceLocation, AdditionalFields
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Pantalla que muestra el bloqueo del almacenamiento extraíble.":::
