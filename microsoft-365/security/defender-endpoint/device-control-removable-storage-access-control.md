---
title: Microsoft Defender para Endpoint Device Control Extraíble Storage control de acceso, medios de almacenamiento extraíbles
description: Una información general sobre Microsoft Defender para endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 10/05/2021
ms.openlocfilehash: c42e79317371419367cef5375f7f0aeaeba1fe1f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60184742"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Control de dispositivo extraíble de Microsoft Defender para endpoint Storage control de acceso

> [!NOTE]
> La administración de directivas de grupo de este producto ahora es generalmente disponible (4.18.2106): vea el blog tech [Community: Proteger](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806) el almacenamiento extraíble y la impresora con Microsoft Defender para endpoint 


Microsoft Defender para endpoint device control removable Storage Access Control permite realizar la siguiente tarea:

- auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión

<br/><br/>

|Privilegio|Permiso|
|---|---|
|Acceso|Lectura, Escritura, Ejecución|
|Modo de acción|Auditoría, Permitir, Impedir|
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en usuarios|Sí|
|Compatibilidad basada en máquina|Sí|

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente el control Storage de acceso extraíble en Windows 10 dispositivos con cliente antimalware versión **4.18.2103.3** o posterior .

- **4.18.2104 o** posterior: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basada en ruta de archivo, ComputerSid
- **4.18.2105** o posterior: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/compatibilidad con SCSI conectada a USB (UAS)
- **4.18.2107** o posterior: Agregar compatibilidad Windows dispositivo portátil (WPD) (para dispositivos móviles, como tabletas); agregar AccountName a la [búsqueda avanzada](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell.":::

> [!NOTE]
> Ninguno de Seguridad de Windows componentes debe estar activo, ya que puede ejecutar Removable Storage Access Control independientemente Seguridad de Windows estado.

## <a name="policy-properties"></a>Propiedades de la directiva

Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:

> [!NOTE]
> Los comentarios que usan la notación de comentario XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea `<!-- COMMENT -->` del archivo XML.

### <a name="removable-storage-group"></a>Grupo Storage extraíble

<br/><br/>

|Nombre de propiedad|Descripción|Opciones|
|---|---|---|
|**GroupId**|[GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa el grupo y se usará en la directiva.||
|**DescriptorIdList**|Enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo. Para cada propiedad de dispositivo, consulta [Propiedades del dispositivo](device-control-removable-storage-protection.md) para obtener más detalles. Todas las propiedades distinguen mayúsculas de minúsculas. |<ul><li>**PrimaryId**: RemovableMediaDevices, CdRomDevices, WpdDevices</li><li>**DeviceId**</li><li>**HardwareId**</li><li>**InstancePathId**: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0` . El número al final (por ejemplo, &0) representa la ranura disponible y puede cambiar de un dispositivo a otro. Para obtener los mejores resultados, use un comodín al final. Por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`.</li><li>**FriendlyNameId**</li><li>**SerialNumberId**</li><li>**VID**</li><li>**PID**</li><li>**VID_PID**<ul><li>0751_55E0: coincide con este par VID/PID exacto</li><li>55E0: hacer coincidir cualquier medio con PID=55E0 </li><li>0751: hacer coincidir cualquier medio con VID=0751</li></ul></li></ul>|
|**MatchType**|Cuando se usan varias propiedades de dispositivo en descriptorIDList, MatchType define la relación.|**MatchAll:** cualquier atributo bajo descriptorIdList será **relación And;** por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema comprobará si el USB cumple ambos valores. <p> **MatchAny:** los atributos de descriptorIdList serán **o** relación; por ejemplo, si el administrador pone DeviceID e InstancePathID, por cada USB conectado, el sistema hará la aplicación siempre que el USB tenga un valor **DeviceID** o **InstanceID** idéntico. |

### <a name="access-control-policy"></a>Directiva de control de acceso

<br/><br/>

| Nombre de propiedad | Descripción | Opciones |
|---|---|---|
| **PolicyRuleId** | [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), un identificador único, representa la directiva y se usará en los informes y la solución de problemas. | |
| **IncludedIdList** | Los grupos a los que se aplicará la directiva. Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.|El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia. <p> En el ejemplo siguiente se muestra el uso de GroupID: <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | Los grupos a los que no se aplicará la directiva. | El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia. |
| **Id. de entrada** | Un PolicyRule puede tener varias entradas; cada entrada con un GUID único indica al Control de dispositivos una restricción.| |
| **Type** | Define la acción de los grupos de almacenamiento extraíbles en IncludedIDList. <ul><li>Aplicación: Permitir o denegar </li><li>Auditoría: AuditAllowed o AuditDenied</ul></li> | <ul><li>Permitir</li><li>Denegar </li><li>AuditAllowed: define la notificación y el evento cuando se permite el acceso</li><li>AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Denegar.**</li></ul> <p> Cuando haya tipos de conflicto para el mismo medio, el sistema aplicará el primero de la directiva. Un ejemplo de tipo de conflicto **es Allow** y **Deny**. |
| **Sid** | El sid del equipo local o el Sid del objeto AD, define si se va a aplicar esta directiva a un usuario o grupo de usuarios específicos; una entrada puede tener un máximo de un Sid y una entrada sin que ningún Sid signifique aplicar la directiva sobre la máquina. |  |
| **ComputerSid** | Sid de equipo local o Sid del objeto AD, define si se va a aplicar esta directiva sobre un equipo o grupo de máquinas específicos; una entrada puede tener un máximo de un ComputerSid y una entrada sin que ComputerSid signifique aplicar la directiva sobre el equipo. Si desea aplicar una entrada a un usuario específico y a un equipo específico, agregue Sid y ComputerSid a la misma entrada. |  |
| **Opciones** | Define si se va a mostrar la notificación o no |**0-4:** cuando se selecciona Tipo Permitir o Denegar. <ul><li>0: nada</li><li>4: deshabilitar **AuditAllowed** y **AuditDenied** para esta entrada. Incluso si **se produce** block y la configuración auditDenied está configurada, el sistema no mostrará la notificación. </li></ul> <p> Cuando se **selecciona Tipo AuditAllowed** **o AuditDenied:** <ul><li>0: nada</li><li>1: mostrar notificación</li><li>2: evento send</li><li>3: mostrar notificación y enviar evento </li></ul>|
|AccessMask|Define el acceso. | **1-7**: <ol><li>Lectura</li><li>Escritura</li><li>Lectura y escritura</li><li>Ejecutar</li><li>Lectura y ejecución</li><li>Escritura y ejecución </li><li>Lectura y escritura y ejecución</li></ol> |

## <a name="common-removable-storage-access-control-scenarios"></a>Escenarios comunes Storage control de acceso extraíble

Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir usbs aprobados específicos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo. Un ejemplo para este caso de uso es: Id. de instancia - Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo de ejemplo [USBs Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)

    > [!TIP]
    > Reemplazar `&` por en el `&amp;` valor.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución, pero permitir los USB aprobados. Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el ejemplo Escenario 1 Block [Write and Execute Access,](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) pero permite el acceso USBs.xmlaprobado.
    2. Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos. Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el ejemplo [Escenario 1](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit Write and Execute access to approved USBs.xmlfile.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo para este caso de uso es: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo Cualquier archivo de Storage extraíble y [CD-DVD Group.xml.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)
    2. Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, Id. de proveedor/Id. de producto, Nombre descriptivo : Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) no aprobados Group.xmlejemplo.

    > [!TIP]
    > Reemplazar `&` por en el `&amp;` valor.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados. Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el ejemplo [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.
    2. Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios. Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el ejemplo [Escenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Audit write and Execute access to others.xmlfile.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Implementación y administración de directivas mediante directiva de grupo

La característica Storage control de acceso extraíble te permite aplicar directivas a través de la directiva de grupo a usuarios o dispositivos, o a ambos.

### <a name="licensing"></a>Licencias

Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Implementación de directivas mediante directiva de grupo

1. Combine todos los grupos `<Groups>` `</Groups>` en un archivo xml.

    En la siguiente imagen se muestra el ejemplo del escenario 1: Impedir el acceso de escritura y ejecución a todos los usuarios, pero permitir [usbs aprobados específicos.](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Pantalla que muestra las opciones de configuración que permiten USB aprobados específicos en dispositivos.":::

2. Combine todas las reglas `<PolicyRules>` `</PolicyRules>` dentro de un archivo xml.

    Si desea restringir un usuario específico, use la propiedad SID en entry. Si no hay ningún SID en la directiva Entry, la entrada se aplicará a todas las instancias de inicio de sesión del equipo.

    La siguiente imagen ilustra el uso de la propiedad SID y un ejemplo de Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir [usbs aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).

    :::image type="content" source="images/usage-sid-property.png" alt-text="Pantalla que muestra un código que indica el uso del atributo de la propiedad SID.":::

3. Guarde los archivos XML de regla y grupo en la carpeta de recurso compartido de red y coloque la ruta de acceso de la carpeta de recurso compartido de red en la configuración de directiva de **grupo:** Configuración del equipo Plantillas administrativas Windows Componentes Antivirus de Microsoft Defender Control de \>  \>  \>  \> dispositivos: 'Definir  grupos de directivas de control de dispositivos' y **'Definir dispositivo' reglas de directiva de control'**.

   Si no encuentra la experiencia de usuario de configuración de directiva en la directiva de grupo,  puede descargar los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) seleccionando Raw y, a continuación, **Guardar como**.

   - El equipo de destino debe poder tener acceso al recurso compartido de red para tener la directiva. Sin embargo, una vez que se lee la directiva, la conexión de recurso compartido de red ya no es necesaria, incluso después del reinicio de la máquina.

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivos.":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Implementación y administración de directivas a través de Intune OMA-URI

La característica Storage control de acceso extraíble permite aplicar directivas a través de OMA-URI a usuarios o dispositivos, o a ambos.

### <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar con Removable Storage Access Control, debe confirmar su [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.

- Rol Administrador de directivas y perfiles
- Rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos
- Administrador global

### <a name="deploying-policy-via-oma-uri"></a>Implementación de directivas mediante OMA-URI

Microsoft Endpoint Manager centro de administración ( ) Perfiles de configuración de dispositivos Crear perfil Plataforma: Windows 10 y posterior <https://endpoint.microsoft.com/> \>  \>  \>  \> **&: Personalizado**

1. Para cada grupo, cree una regla OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      Por ejemplo, para cualquier almacenamiento extraíble y un grupo **de CD/DVD** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - Tipo de datos: String (archivo XML)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="Archivo xml para el tipo de datos STRING.":::

2. Para cada directiva, también cree un OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      Por ejemplo, para la regla Bloquear escritura y ejecutar acceso, pero permitir **usbs aprobados** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - Tipo de datos: String (archivo XML)

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Implementación y administración de directivas mediante la interfaz de usuario de Intune

Esta funcionalidad está disponible en el centro Microsoft Endpoint Manager administración ( <https://endpoint.microsoft.com/> ). Ve a **Endpoint Security Attack** Surface  >  **Reduction**  >  **Create Policy**. Elija **Plataforma: Windows 10 y posterior** con **Perfil: Control de dispositivo**.

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos extraíbles Storage control de acceso en Microsoft Defender para endpoint

El [Microsoft 365 Defender muestra](https://security.microsoft.com/advanced-hunting) los eventos desencadenados por el control de dispositivo extraíble Storage control de acceso. Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:

- Microsoft 365 para informes E5

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == "RemovableStoragePolicyTriggered"
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
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Pantalla que muestra el bloqueo del almacenamiento extraíble.":::

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>¿Cuál es la limitación de medios de almacenamiento extraíbles para el número máximo de USB?

Hemos validado un grupo USB con 100.000 medios, con un tamaño de hasta 7 MB. La directiva funciona tanto en Intune como en GPO sin problemas de rendimiento.

### <a name="why-does-the-policy-not-work"></a>¿Por qué la directiva no funciona?

La razón más común es que no hay ninguna versión de [cliente antimalware necesaria.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)

Otro motivo podría ser que el archivo XML no tenga el formato correcto, por ejemplo, no usar el formato de reducción correcto para el carácter "&" en el archivo XML, o que el editor de texto pueda agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione. Una solución sencilla es descargar el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (seleccione **Sin** procesar y, a continuación, **Guardar como**) y, a continuación, actualizar.

Si va a implementar y administrar la directiva a través de la directiva de grupo, asegúrese de combinar todo PolicyRule en un archivo XML dentro de un nodo primario denominado PolicyRules y todos los grupos en un archivo XML dentro de un nodo primario denominado Grupos; si administra a través de Intune, mantenga un archivo XML PolicyRule, lo mismo, un archivo XML de grupo uno.

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>No hay ninguna experiencia de usuario de configuración para "Definir grupos de directivas de control de dispositivos" y "Definir reglas de directiva de control de dispositivos" en mi directiva de grupo

No se vuelve a mostrar la experiencia de usuario de configuración de directiva de grupo, pero puede obtener los archivos adml y admx relacionados haciendo clic en "Raw" y "Guardar como" en los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx.](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx)

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>¿Cómo puedo saber qué equipo está usando la versión de cliente antimalware des actualizada en la organización?

Puede usar la siguiente consulta para obtener la versión del cliente antimalware en el portal de seguridad Microsoft 365 web:

```kusto
//check the antimalware client version
DeviceFileEvents
|where FileName == "MsMpEng.exe"
|where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
|extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//|project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
|summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
|order by PlatformVersion desc
```
