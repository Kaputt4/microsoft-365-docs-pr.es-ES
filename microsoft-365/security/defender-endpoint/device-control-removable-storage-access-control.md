---
title: Microsoft Defender para Endpoint Device Control Extraíble Storage Access Control, medios de almacenamiento extraíbles
description: Una información general sobre Microsoft Defender para endpoint
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.date: 03/18/2022
ms.openlocfilehash: def22b83dc5c84a3b222d4e50f2d2dce8d5d36ef
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682755"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Control de dispositivo extraíble de Microsoft Defender para endpoint Storage Control de acceso

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directivas de grupo y la administración de directivas personalizadas y OMA-URI de Intune de este producto están disponibles por lo general (4.18.2106): consulte Tech [Community blog: Protect your removable storage and printer with Microsoft Defender for Endpoint](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).


Microsoft Defender for Endpoint Device Control Removable Storage Access Control permite realizar la siguiente tarea:

- auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión

|Privilegio|Permiso|
|---|---|
|Access|Lectura, Escritura, Ejecución|
|Modo de acción|Auditoría, Permitir, Impedir|
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en usuarios|Sí|
|Compatibilidad basada en máquina|Sí|

|Funcionalidad|Descripción|Implementar a través de Intune|Implementar a través de la directiva de grupo|
|---|---|---|---|
|Creación de grupos multimedia extraíbles|Permite crear un grupo de medios extraíble reutilizable|Paso 1 de la sección Implementar [directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 1 de la sección Implementar [directiva mediante directiva de grupo](#deploying-policy-via-group-policy)|
|Creación de directivas|Permite crear una directiva para aplicar cada grupo de medios extraíble|Paso 2 de la sección Implementar [directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Pasos 2 y 3 de la sección Implementación de directivas [mediante directiva de grupo](#deploying-policy-via-group-policy) |
|Cumplimiento predeterminado|Permite establecer el acceso predeterminado (Denegar o Permitir) a medios extraíbles si no hay ninguna directiva|Paso 3 de la sección Implementar [directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 4 de la sección Implementar [directiva mediante directiva de grupo](#deploying-policy-via-group-policy) |
|Habilitar o deshabilitar el control de acceso Storage extraíble|Si estableces Deshabilitar, deshabilitará la directiva de control Storage acceso extraíble en este equipo| Paso 4 de la sección Implementar [directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 5 de la sección Implementar [directiva mediante directiva de grupo](#deploying-policy-via-group-policy) |
|Capturar información de archivo|Permite crear una directiva para capturar información de archivos cuando se produce el acceso de escritura| Pasos 2 y 5 de la sección Implementación [de directivas a través de OMA-URI](#deploying-policy-via-oma-uri) | Pasos 2 y 6 de la sección Implementación de directivas [mediante directiva de grupo](#deploying-policy-via-group-policy) |

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente el control Storage de acceso extraíble en Windows 10 y Windows 11 dispositivos con cliente antimalware versión **4.18.2103.3 o posterior**.

- **4.18.2104 o** posterior: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basada en filepath, ComputerSid

- **4.18.2105** o posterior: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de un usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/compatibilidad con SCSI conectada a USB (UAS)

- **4.18.2107** o posterior: Agregar compatibilidad con dispositivos portátiles (WPD) Windows (para dispositivos móviles, como tabletas); agregar AccountName a la búsqueda [avanzada](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

- **4.18.2111** o posterior: Agregar "Habilitar o deshabilitar el control de acceso Storage extraíble", "Aplicación predeterminada", tiempo de actualización de directivas de máquina cliente a través de PowerShell, información de archivos

- **4.18.2201 o posterior**: admite una copia del archivo escrito en el almacenamiento permitido a través de OMA-URI

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell.":::

> [!NOTE]
> Ninguno de Seguridad de Windows componentes debe estar activo, ya que puede ejecutar Removable Storage Access Control independientemente Seguridad de Windows estado.

## <a name="policy-properties"></a>Propiedades de la directiva

Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:

> [!NOTE]
> Los comentarios que usan la notación de comentario XML `<!-- COMMENT -->` se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

### <a name="removable-storage-group"></a>Grupo Storage extraíble

|Nombre de propiedad|Descripción|Opciones|
|---|---|---|
|**Id. de grupo**|GUID, un identificador único, representa el grupo y se usará en la directiva como GroupId||
|**DescriptorIdList**|Enumera las propiedades del dispositivo que quieres usar para cubrir en el grupo. Para cada propiedad de dispositivo, consulta [Propiedades del dispositivo](device-control-removable-storage-protection.md) para obtener más detalles. Todas las propiedades distinguen mayúsculas de minúsculas. |**PrimaryId**: `RemovableMediaDevices`, `CdRomDevices`, `WpdDevices`<p>**BusId**: Por ejemplo, USB, SCSI<p>**DeviceId**<p>**HardwareId**<p>**InstancePathId**: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`. El número al final (por ejemplo, &0) representa la ranura disponible y puede cambiar de un dispositivo a otro. Para obtener los mejores resultados, use un comodín al final. Por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`.<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: coincide con este par VID/PID exacto<p>`_55E0`: coincide con cualquier medio con PID=55E0 <p>`0751_`: coincide con cualquier medio con VID=0751|
|**MatchType**|Cuando se usan varias propiedades de dispositivo en `DescriptorIDList`, MatchType define la relación.|**MatchAll**: cualquier `DescriptorIdList` atributo de la relación **será And** ; por ejemplo, `DeviceID` `InstancePathID`si el administrador pone y , por cada USB conectado, el sistema comprobará si el USB cumple ambos valores. <p> **MatchAny**: los atributos de descriptorIdList serán **o** relación; por ejemplo, si el administrador pone `DeviceID` `InstancePathID`y, por cada USB conectado, el sistema hará la aplicación siempre que el USB tenga un valor **DeviceID** o **InstanceID** idéntico. |

### <a name="access-control-policy"></a>Directiva de control de acceso

| Nombre de propiedad | Descripción | Opciones |
|---|---|---|
| **Id. de PolicyRule** | GUID, un identificador único, representa la directiva y se usará en los informes y la solución de problemas. | |
| **IncludedIdList** | Los grupos a los que se aplicará la directiva. Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.|El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia. <p> En el ejemplo siguiente se muestra el uso de GroupID: <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | Los grupos a los que no se aplicará la directiva. | El IDENTIFICADOR de grupo/GUID debe usarse en esta instancia. |
| **Id. de entrada** | Un PolicyRule puede tener varias entradas; cada entrada con un GUID único indica al Control de dispositivos una restricción.| |
| **Type** | Define la acción de los grupos de almacenamiento extraíbles en IncludedIDList. <p>Aplicación: Permitir o denegar <p>Auditoría: AuditAllowed o AuditDenied<p> | Permitir<p>Denegar <p>AuditAllowed: define la notificación y el evento cuando se permite el acceso <p>AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Denegar** .<p> Cuando haya tipos de conflicto para el mismo medio, el sistema aplicará el primero de la directiva. Un ejemplo de tipo de conflicto es **Allow** y **Deny**. |
| **Sid** | El sid de usuario local o el grupo sid de usuario o el Sid del objeto AD, define si se va a aplicar esta directiva sobre un usuario o grupo de usuarios específicos; una entrada puede tener un máximo de un Sid y una entrada sin que ningún Sid signifique aplicar la directiva sobre la máquina. |  |
| **ComputerSid** | El equipo local Sid o el grupo Sid del equipo o el Sid del objeto AD, define si se va a aplicar esta directiva sobre un equipo o grupo de máquinas específico; una entrada puede tener un máximo de un ComputerSid y una entrada sin que ComputerSid signifique aplicar la directiva sobre el equipo. Si desea aplicar una entrada a un usuario específico y a un equipo específico, agregue Sid y ComputerSid a la misma entrada. |  |
| **Opciones** | Define si se va a mostrar la notificación o no |**Cuando se selecciona Permitir tipo**: <p>0: nada<p>4: deshabilitar **AuditAllowed** y **AuditDenied** para esta entrada. Incluso si **allow** sucede y la configuración AuditAllowed está configurada, el sistema no enviará el evento. <p>8: capturar la información del archivo y tener una copia del archivo como evidencia para el acceso de escritura. <p>16: capturar información de archivo para el acceso de escritura. <p>**Cuando se selecciona Denegar tipo**: <p>0: nada<p>4: deshabilitar **AuditDenied** para esta entrada. Incluso si **se produce** block y la configuración auditDenied está configurada, el sistema no mostrará la notificación. <p>**Cuando se **selecciona Tipo AuditAllowed****: <p>0: nada <p>1: nada <p>2: evento send<p>3: evento send <p> **Cuando se **selecciona Tipo AuditDenied****: <p>0: nada <p>1: mostrar notificación <p>2: evento send<p>3: mostrar notificación y enviar evento |
|AccessMask|Define el acceso. | **Acceso a nivel de disco**: <p>1: Leer <p>2: Escribir <p>4: Ejecutar <p>**Acceso a nivel de sistema de archivos**: <p>8: Lectura del sistema de archivos <p>16: Escritura del sistema de archivos <p>32: Ejecución del sistema de archivos <p><p>Puede tener acceso múltiple mediante la operación OR binaria, por ejemplo, accessmask para lectura y escritura y ejecución será 7; AccessMask para lectura y escritura será 3.|

## <a name="common-removable-storage-access-control-scenarios"></a>Escenarios comunes Storage control de acceso extraíble

Para ayudarle a familiarizarse con Microsoft Defender para Endpoint Removable Storage Access Control, hemos reunido algunos escenarios comunes que puede seguir.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir usbs aprobados específicos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo. Un ejemplo para este caso de uso es: Id. de instancia - Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs aprobados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo.

    > [!TIP]
    > Reemplazar `&` por `&amp;` en el valor.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución, pero permitir los USB aprobados. Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el ejemplo [Escenario 1 Block Write and Execute Access](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) , pero permite el acceso USBs.xmlaprobado.

    2. Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos. Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el ejemplo [Escenario 1 Audit write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo para este caso de uso es: Grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el ejemplo Cualquier archivo de Storage extraíble y [CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples).

    2. Grupo 2: USB no aprobados basados en propiedades de dispositivo, por ejemplo, Id. de proveedor/Id. de producto, Nombre descriptivo : Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [usbs no aprobados Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo.

    > [!TIP]
    > Reemplazar `&` por `&amp;` en el valor.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloqueados. Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el ejemplo [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

    2. Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios. Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el ejemplo [Escenario 2 Audit write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Implementación y administración de directivas mediante directiva de grupo

La característica Control de acceso Storage permite aplicar directivas a través de la directiva de grupo a usuarios, dispositivos o ambos.

### <a name="licensing"></a>Licencias

Antes de empezar con Removable Storage Access Control, debes confirmar tu [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Implementación de directivas mediante directiva de grupo

1. Combine todos los grupos en `<Groups>` `</Groups>` un archivo xml.

    En la siguiente imagen se muestra el ejemplo del escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir [usbs aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Pantalla que muestra las opciones de configuración que permiten USB aprobados específicos en dispositivos.":::

2. Combine todas las reglas dentro `<PolicyRules>` `</PolicyRules>` de un archivo xml.

    Si desea restringir un usuario específico, use la propiedad SID en entry. Si no hay ningún SID en la directiva Entry, la entrada se aplicará a todas las instancias de inicio de sesión del equipo.
    
    Si desea supervisar la información de archivos para el acceso de escritura, use accessmask correcto con la opción correcta (16); Este es el ejemplo de [capturar información de archivo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Audit%20File%20Information.xml).

    En la siguiente imagen se muestra el uso de la propiedad SID y un ejemplo de Escenario 1: Impedir el acceso de escritura y ejecución a todos los [USB aprobados, pero permitir determinados USB aprobados](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).

    :::image type="content" source="images/usage-sid-property.png" alt-text="Pantalla que muestra un código que indica el uso del atributo de la propiedad SID.":::

3. Guarde los archivos XML de regla y grupo en la carpeta de recurso compartido de red y coloque la ruta de acceso de la carpeta de recurso compartido de red en la configuración de directiva de **grupo:** \>  \> Configuración del equipo Plantillas administrativas **Windows Componentes** \> **Antivirus de Microsoft Defender** \> **Control** de dispositivos: 'Definir grupos de directivas de **control de dispositivos'** **y 'Definir reglas de directiva de control de dispositivos'**.

   Si no encuentra la experiencia de usuario de configuración de directiva en la directiva de grupo, puede descargar los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) seleccionando Raw y, a continuación, **Guardar como**.

   - El equipo de destino debe poder tener acceso al recurso compartido de red para tener la directiva. Sin embargo, una vez que se lee la directiva, la conexión de recurso compartido de red ya no es necesaria, incluso después del reinicio de la máquina.

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivos.":::

4. Aplicación predeterminada: le permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva. Por ejemplo, solo tienes una directiva (denegar o permitir) para RemovableMediaDevices, pero no tienes ninguna directiva para CdRomDevices o WpdDevices, y estableces denegar de forma predeterminada a través de esta directiva, se bloqueará el acceso de lectura y escritura/ejecución a CdRomDevices o WpdDevices.

   - Una vez que implemente esta configuración, verá **Default Allow** o **Default Deny**.
   - Tenga en cuenta tanto el nivel de disco como el nivel del sistema de archivos AccessMask al configurar esta configuración, por ejemplo, si desea denegar de forma predeterminada pero permitir un almacenamiento específico, debe permitir el acceso a nivel de disco y a nivel del sistema de archivos, debe establecer AccessMask en 63.

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="Código predeterminado de PowerShell Permitir o Denegar predeterminado":::

5. Habilitar o deshabilitar el control de acceso Storage extraíble: puede establecer este valor para deshabilitar temporalmente El control de acceso Storage extraíble.

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="Configuración del control de dispositivos":::

   - Una vez que implemente esta configuración, verá **Habilitado** o **Deshabilitado**. Deshabilitado significa que esta máquina no tiene removible Storage de control de acceso en ejecución.

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="Control de dispositivo habilitado o deshabilitado en código de PowerShell":::

6. Establezca la ubicación de una copia del archivo: si desea tener una copia del archivo cuando se produce el acceso de escritura, debe establecer la ubicación donde el sistema puede guardar la copia.
    
    Implemente esto junto con las opciones AccessMask y Option correctas: vea el paso 2 anterior.

    :::image type="content" source="../../media/define-device-control-policy-rules.png" alt-text="Directiva de grupo: establecer la ubicación para la evidencia del archivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Implementación y administración de directivas a través de Intune OMA-URI

La característica Storage control de acceso extraíble te permite aplicar directivas a través de OMA-URI a usuarios o dispositivos, o a ambos.

### <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar con Removable Storage Access Control, debes confirmar tu [Microsoft 365 suscripción](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para obtener acceso y usar el control Storage de acceso extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivos. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.

- Rol Administrador de directivas y perfiles

- Rol personalizado con permisos Create/Edit/Update/Read/Delete/View Reports activados para perfiles de configuración de dispositivos

- Administrador global

### <a name="deploying-policy-via-oma-uri"></a>Implementación de directivas mediante OMA-URI

Microsoft Endpoint Manager centro  de administración (<https://endpoint.microsoft.com/>) **Dispositivos** \> \> **Perfiles** \> \> de configuración Crear perfil **Plataforma: Windows 10 y posterior &: Personalizado**

1. Para cada grupo, cree una regla OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      Por ejemplo, para **cualquier almacenamiento extraíble y un grupo de CD/DVD** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - Tipo de datos: String (archivo XML)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="Archivo xml para el tipo de datos STRING.":::

2. Para cada directiva, también cree un OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      Por ejemplo, para la **regla Bloquear escritura y ejecutar acceso, pero permitir usbs aprobados** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - Tipo de datos: String (archivo XML)
       
    Si desea supervisar la información de archivos para el acceso de escritura, use accessmask correcto con la opción correcta (16); Este es el ejemplo de [capturar información de archivo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20File%20Information.xml).

3. Aplicación predeterminada: le permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva. Por ejemplo, solo tienes una directiva (denegar o permitir) para RemovableMediaDevices, pero no tienes ninguna directiva para CdRomDevices o WpdDevices, y estableces denegar de forma predeterminada a través de esta directiva, se bloqueará el acceso de lectura y escritura/ejecución a CdRomDevices o WpdDevices.

    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - Tipo de datos: Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - Una vez que implemente esta configuración, verá **Default Allow** o **Default Deny**
    - Tenga en cuenta tanto el nivel de disco como el nivel del sistema de archivos AccessMask al configurar esta configuración, por ejemplo, si desea denegar de forma predeterminada pero permitir un almacenamiento específico, debe permitir el acceso a nivel de disco y a nivel del sistema de archivos, debe establecer AccessMask en 63.

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="Código de PowerShell de la aplicación predeterminada":::

4. Habilitar o deshabilitar el control de acceso Storage extraíble: puede establecer este valor para deshabilitar temporalmente El control de acceso Storage extraíble.

   - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - Tipo de datos: Int `Disable: 0`
     `Enable: 1`

   - Una vez que implemente esta configuración, verá **Habilitado** o **Deshabilitado**

    **Deshabilitado** significa que esta máquina no tiene una directiva extraíble Storage control de acceso en ejecución

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="Control de Storage de acceso extraíble en código de PowerShell":::

5. Establezca la ubicación de una copia del archivo: si desea tener una copia del archivo cuando se produce el acceso de escritura, debe establecer la ubicación donde el sistema puede guardar la copia.
    
    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation;**username**;**password**`

    - Tipo de datos: String
    
    Tiene que implementar esto junto con accessmask correcto y la opción correcta - vea el paso 2 anterior.

    :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="Establecer locaiton para pruebas de archivo":::
    
## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Implementación y administración de directivas mediante la interfaz de usuario de Intune

(*Próximamente!*) Esta funcionalidad estará disponible en el Centro Microsoft Endpoint Manager administración (<https://endpoint.microsoft.com/>). Ve a **Endpoint SecurityAttack** >  **Surface ReductionCreate** >  **Policy**. Elija **Plataforma: Windows 10 y posterior** con **Perfil: Control de dispositivo**.

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos extraíbles de control Storage control de acceso en Microsoft Defender para endpoint

El [Microsoft 365 Defender muestra](https://security.microsoft.com/advanced-hunting) los eventos desencadenados por el control de dispositivo extraíble Storage control de acceso. Para obtener acceso a Microsoft 365 seguridad, debe tener la siguiente suscripción:

- Microsoft 365 para informes E5

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
|project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber
| order by Timestamp desc
```

```kusto
//RemovableStorageFileEvent: event triggered by File level enforcement, information of files written to removable storage 
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
| extend DuplicatedOperation = tostring(parsed.DuplicatedOperation)
| extend FileEvidenceLocation = tostring(parsed.TargetFileLocation) 
| project Timestamp, DeviceId, DeviceName, InitiatingProcessAccountName, 
    ActionType, Policy, PolicyRuleId, DuplicatedOperation, 
    MediaClassName, MediaInstanceId, MediaName, MediaProductId, MediaVendorId, MediaSerialNumber,
    FileName, FolderPath, FileSize, FileEvidenceLocation,
    AdditionalFields
| order by Timestamp desc
```
    
:::image type="content" source="images/block-removable-storage.png" alt-text="Pantalla que muestra el bloqueo del almacenamiento extraíble.":::

## <a name="frequently-asked-questions"></a>Preguntas frecuentes


### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>¿Cómo generar GUID para id. de grupo/id. de policyrule/id. de entrada?

Puede generar GUID a través del código abierto en línea o a través de PowerShell: [cómo generar GUID a través de PowerShell](/powershell/module/microsoft.powershell.utility/new-guid?msclkid=c1398a25a6d911ec9c888875fa1f24f5&view=powershell-7.2)
    
![imagen](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)
    
### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>¿Cuál es la limitación de medios de almacenamiento extraíbles para el número máximo de USB?

Hemos validado un grupo USB con 100.000 medios, con un tamaño de hasta 7 MB. La directiva funciona tanto en Intune como en GPO sin problemas de rendimiento.

### <a name="why-does-the-policy-not-work"></a>¿Por qué la directiva no funciona?

1. La razón más común es que no hay ninguna versión de [cliente antimalware necesaria](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).

2. Otro motivo podría ser que el archivo XML no tiene el formato correcto, por ejemplo, no se usa el formato de reducción correcto para el carácter "&" en el archivo XML, o el editor de texto puede agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione. Una solución sencilla es descargar el [archivo de](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) ejemplo (seleccione **Sin** procesar y, a continuación, **Guardar como**) y, a continuación, actualizar.

3. Si va a implementar y administrar la directiva a través de la directiva de grupo, asegúrese de combinar todo PolicyRule en un archivo XML dentro de un nodo primario denominado PolicyRules y todos los grupos en un archivo XML dentro de un nodo primario denominado Grupos; si administra a través de Intune, mantenga un archivo XML PolicyRule, lo mismo, un archivo XML de grupo uno.
    
Si aún no funciona, puede ponerse en contacto con nosotros y compartir la cabina de soporte técnico ejecutando cmd con el administrador: "%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>No hay ninguna experiencia de usuario de configuración para "Definir grupos de directivas de control de dispositivos" y "Definir reglas de directiva de control de dispositivos" en mi directiva de grupo

No se vuelve a mostrar la experiencia de usuario de configuración de directiva de grupo, pero puede obtener los archivos adml y admx relacionados haciendo clic en "Raw" y "Guardar como" en los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) .

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>¿Cómo puedo saber si la directiva más reciente se ha implementado en el equipo de destino?

Puede ejecutar "Get-MpComputerStatus" en PowerShell como administrador. El siguiente valor mostrará si la directiva más reciente se ha aplicado al equipo de destino.

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

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
