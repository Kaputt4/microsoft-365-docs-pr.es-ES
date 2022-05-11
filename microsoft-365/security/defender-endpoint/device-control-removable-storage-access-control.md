---
title: Microsoft Defender para punto de conexión dispositivo control extraíble Storage Access Control, medios de almacenamiento extraíbles
description: Un tutorial sobre Microsoft Defender para punto de conexión
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
ms.date: 05/09/2022
ms.openlocfilehash: a472a2183d642ca8c3231e6ca5129fdf79cad8fd
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317634"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender para punto de conexión control de dispositivo Storage Access Control extraíble

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directiva de grupo y Intune OMA-URI/Administración de directivas personalizadas de este producto ya están disponibles con carácter general (4.18.2106): Consulte [el blog tech Community: Proteger el almacenamiento extraíble y la impresora con Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

Microsoft Defender para punto de conexión Storage Access Control extraíble de Device Control le permite realizar la siguiente tarea:

- auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión

|Privilegio|Permiso|
|---|---|
|Acceso|Lectura, Escritura, Ejecución|
|Modo de acción|Auditar, permitir, impedir|
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en el usuario|Sí|
|Compatibilidad basada en máquinas|Sí|

|Funcionalidad|Descripción|Implementación a través de Intune|Implementación a través de directiva de grupo|
|---|---|---|---|
|Creación de grupos de medios extraíbles|Permite crear un grupo de medios extraíble reutilizable|Paso 1 de la sección [Implementación de la directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 1 de la sección [Implementación de la directiva a través de directiva de grupo](#deploying-policy-via-group-policy)|
|Creación de directivas|Permite crear una directiva para aplicar cada grupo de medios extraíble|Paso 2 de la sección [Implementación de la directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Los pasos 2 y 3 de la sección [Implementación de la directiva a través de directiva de grupo](#deploying-policy-via-group-policy) |
|Aplicación predeterminada|Permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva|Paso 3 de la sección [Implementación de la directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 4 de la sección [Implementación de la directiva a través de directiva de grupo](#deploying-policy-via-group-policy) |
|Habilitar o deshabilitar Storage Access Control extraíbles|Si establece Deshabilitar, deshabilitará la directiva de Storage Access Control extraíble en este equipo.| Paso 4 de la sección [Implementación de directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 5 de la sección [Implementación de la directiva a través de directiva de grupo](#deploying-policy-via-group-policy) |
|Captura de información de archivo|Permite crear una directiva para capturar información de archivo cuando se produce el acceso de escritura| Los pasos 2 y 5 de la sección [Implementación de la directiva a través de OMA-URI](#deploying-policy-via-oma-uri) | Paso 2 y 6 de la sección [Implementación de directiva a través de directiva de grupo](#deploying-policy-via-group-policy) |

## <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente Storage Access Control extraíbles en dispositivos Windows 10 y Windows 11 que tengan la versión de cliente antimalware **4.18.2103.3 o posterior**.

- **4.18.2104 o posterior**: Agregar SerialNumberId, VID_PID, compatibilidad con GPO basado en filepath, ComputerSid

- **4.18.2105 o posterior**: Agregar compatibilidad con caracteres comodín para HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, la combinación de un usuario específico en una máquina específica, SSD extraíble (un SSD extremo de SanDisk)/Compatibilidad con SCSI conectado a USB (UAS)

- **4.18.2107 o posterior**: Agregue Windows compatibilidad con dispositivos portátiles (WPD) (para dispositivos móviles, como tabletas); agregue AccountName a la [búsqueda avanzada](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint).

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell" lightbox="images/powershell.png":::

> [!NOTE]
> No es necesario que ninguno de los componentes de Seguridad de Windows esté activo, ya que puede ejecutar Storage Access Control extraíbles independientemente del estado de Seguridad de Windows.

## <a name="policy-properties"></a>Propiedades de directiva

Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

### <a name="removable-storage-group"></a>Grupo de Storage extraíble

|Nombre de propiedad|Descripción|Opciones|
|---|---|---|
|**Id. de grupo**|GUID, un identificador único, representa el grupo y se usará en la directiva como GroupId.||
|**DescriptorIdList**|Enumere las propiedades del dispositivo que desea usar para cubrir en el grupo. Para cada propiedad de dispositivo, consulte [Propiedades del dispositivo](device-control-removable-storage-protection.md) para obtener más detalles. Todas las propiedades distinguen mayúsculas de minúsculas. |**PrimaryId**: `RemovableMediaDevices`, , `CdRomDevices``WpdDevices`<p>**BusId**: por ejemplo, USB, SCSI<p>**Deviceid**<p>**HardwareId**<p>**InstancePathId**: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`. El número al final (por ejemplo, &0) representa la ranura disponible y puede cambiar de dispositivo a dispositivo. Para obtener los mejores resultados, use un carácter comodín al final. Por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`.<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: coincide con este par VID/PID exacto<p>`_55E0`: coincide con cualquier medio con PID=55E0 <p>`0751_`: coincide con cualquier medio con VID=0751|
|**MatchType**|Cuando se usan varias propiedades de `DescriptorIDList`dispositivo en , MatchType define la relación.|**MatchAll**: los atributos de la `DescriptorIdList` relación serán **Y** ; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema comprobará si el USB cumple ambos valores. <p> **MatchAny**: los atributos de DescriptorIdList serán **O** relationship; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema realizará la aplicación siempre y cuando el USB tenga un valor **de DeviceID** o **InstanceID** idéntico. |

### <a name="access-control-policy"></a>directiva de Access Control

| Nombre de propiedad | Descripción | Opciones |
|---|---|---|
| **Id. de PolicyRule** | GUID, un identificador único, representa la directiva y se usará en la generación de informes y la solución de problemas. | |
| **IncludedIdList** | Los grupos a los que se aplicará la directiva. Si se agregan varios grupos, la directiva se aplicará a cualquier medio de todos esos grupos.|El identificador de grupo o GUID debe usarse en esta instancia. <p> En el ejemplo siguiente se muestra el uso de GroupID: <p> `<IncludedIdList> <GroupId> {EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>` |
| **ExcludedIDList** | Los grupos a los que no se aplicará la directiva. | El identificador de grupo o GUID debe usarse en esta instancia. |
| **Id. de entrada** | Una policyRule puede tener varias entradas; cada entrada con un GUID único indica a Device Control una restricción.| |
| **Tipo** | Define la acción para los grupos de almacenamiento extraíbles en IncludedIDList. <p>Cumplimiento: Permitir o denegar <p>Auditoría: AuditAllowed o AuditDenied<p> | Permitir<p>Denegar <p>AuditAllowed: define la notificación y el evento cuando se permite el acceso. <p>AuditDenied: define la notificación y el evento cuando se deniega el acceso; tiene que trabajar junto con **la entrada Deny** .<p> Cuando haya tipos de conflicto para los mismos medios, el sistema aplicará el primero de la directiva. Un ejemplo de un tipo de conflicto es **Allow** y **Deny**. |
| **Sid** | Sid de usuario local, grupo de sid de usuario o sid del objeto de AD, define si se debe aplicar esta directiva sobre un usuario o grupo de usuarios específico; una entrada puede tener un máximo de un Sid y una entrada sin ningún Sid significa aplicar la directiva sobre la máquina. |  |
| **ComputerSid** | Sid de equipo local, grupo de sid de equipo o sid del objeto de AD, define si se debe aplicar esta directiva en un equipo o grupo de máquinas específico; una entrada puede tener un máximo de un ComputerSid y una entrada sin ningún ComputerSid significa aplicar la directiva sobre el equipo. Si desea aplicar una entrada a un usuario específico y a una máquina específica, agregue Sid y ComputerSid a la misma entrada. |  |
| **Opciones** | Define si se va a mostrar la notificación o no |**Cuando se selecciona Permitir tipo**: <p>0: nada<p>4: deshabilite **AuditAllowed** y **AuditDenied** para esta entrada. Incluso si **se produce Allow** y la opción AuditAllowed está configurada, el sistema no enviará el evento. <p>8: capturar información del archivo y tener una copia del archivo como evidencia para el acceso de escritura. <p>16: capturar información de archivo para el acceso de escritura. <p>**Cuando se selecciona Tipo denegado**: <p>0: nada<p>4: deshabilite **AuditDenied** para esta entrada. Incluso si **se produce Block** y la opción AuditDenied está configurada, el sistema no mostrará la notificación. <p>**Cuando se selecciona **Type AuditAllowed (AuditAllowed** de tipo):** <p>0: nada <p>1: nada <p>2: enviar evento<p> **Cuando se selecciona **Auditoría de tipos denegada****: <p>0: nada <p>1: mostrar notificación <p>2: enviar evento<p>3: mostrar notificación y enviar evento |
|AccessMask|Define el acceso. | **Acceso a nivel de disco**: <p>1: Lectura <p>2: Escritura <p>4: Ejecutar <p>**Acceso a nivel del sistema de archivos**: <p>8: Lectura del sistema de archivos <p>16: Escritura del sistema de archivos <p>32: Ejecución del sistema de archivos <p><p>Puede tener varios accesos realizando una operación O binaria; por ejemplo, AccessMask para lectura y escritura y Ejecución será 7; AccessMask for Read and Write será 3.|

## <a name="common-removable-storage-access-control-scenarios"></a>Escenarios de Storage Access Control extraíbles comunes

Para ayudarle a familiarizarse con Microsoft Defender para punto de conexión Storage Access Control extraíbles, hemos elaborado algunos escenarios comunes que debe seguir.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el archivo [de Group.xmlde cd-DVD y Storage extraíbles](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo. Un ejemplo para este caso de uso es: Id. de instancia: Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [de Group.xmlusb aprobados](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear escritura y ejecutar acceso, pero permitir USB aprobados. Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el [escenario de ejemplo 1 Bloquear escritura y ejecutar acceso, pero permitir USBs.xmlarchivo aprobado](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

    2. Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos. Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el [escenario de ejemplo 1 Auditar escritura y ejecutar el acceso a USBs.xmlarchivo aprobado](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloquearlos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo para este caso de uso es el grupo **9b28fae8-72f7-4267-a1a5-685f747a7146** en el archivo [de Storage extraíble y CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    2. Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, id. de proveedor/id. de producto, nombre descriptivo : grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [de Group.xmlusbs no aprobados](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloquearlos. Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el [escenario de ejemplo 2 Escritura y ejecución de auditoría de acceso a todos los archivos de USBs.xmlno aprobados específicos, pero sin aprobar](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

    2. Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios. Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el [escenario de ejemplo 2 Auditar escritura y ejecutar acceso a others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) archivo.

## <a name="deploying-and-managing-policy-via-group-policy"></a>Implementación y administración de directivas mediante directiva de grupo

La característica de Storage Access Control extraíble le permite aplicar la directiva a través de directiva de grupo al usuario o dispositivo, o a ambos.

### <a name="licensing"></a>Licencias

Antes de empezar a usar la Storage Access Control extraíble, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar Storage Access Control extraíbles, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="deploying-policy-via-group-policy"></a>Implementación de directivas a través de directiva de grupo

1. Combine todos los grupos dentro de `<Groups>` `</Groups>` en un archivo xml.

    En la imagen siguiente se muestra el ejemplo de [Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).

    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Los valores de configuración que permiten USB aprobados específicos en dispositivos" lightbox="images/prevent-write-access-allow-usb.png":::

2. Combine todas las reglas dentro de `<PolicyRules>` `</PolicyRules>` en un archivo xml.

    Si desea restringir un usuario específico, use la propiedad SID en la entrada. Si no hay ningún SID en la entrada de directiva, la entrada se aplicará a todas las instancias de inicio de sesión de la máquina.

    Si desea supervisar la información de archivo para el acceso de escritura, use accessMask adecuado con la opción correcta (16); este es el ejemplo de [captura de información de archivo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Audit%20File%20Information.xml).

    En la imagen siguiente se muestra el uso de la propiedad SID y un ejemplo de [Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).

    :::image type="content" source="images/usage-sid-property.png" alt-text="Código que indica el uso del atributo de propiedad SID" lightbox="images/usage-sid-property.png":::

3. Guarde los archivos XML de regla y grupo en la carpeta del recurso compartido de red y coloque la ruta de acceso de la carpeta del recurso compartido de red en la configuración de directiva de grupo: **Plantillas** \> administrativas **de configuración** \> del equipo **Windows componentes** \> **Antivirus de Microsoft Defender** \> **control de dispositivo**: **"Definir grupos de directivas de control de dispositivos"** y **"Definir reglas de directiva de control de dispositivos"**.

   Si no encuentra la experiencia de usuario de configuración de directiva en el directiva de grupo, puede descargar los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx) seleccionando **Sin procesar** y, a continuación, **Guardar como**.

   - La máquina de destino debe poder acceder al recurso compartido de red para tener la directiva. Sin embargo, una vez que se lee la directiva, ya no se requiere la conexión del recurso compartido de red, incluso después del reinicio de la máquina.

    :::image type="content" source="images/device-control.png" alt-text="Pantalla Control de dispositivo" lightbox="images/device-control.png":::

4. Aplicación predeterminada: permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva. Por ejemplo, solo tiene una directiva (Denegar o Permitir) para RemovableMediaDevices, pero no tiene ninguna directiva para CdRomDevices o WpdDevices, y establece el valor predeterminado Denegar a través de esta directiva, se bloqueará el acceso de lectura, escritura y ejecución a CdRomDevices o WpdDevices.

   - Una vez que implemente esta configuración, verá **Permitir predeterminado** o **Denegar predeterminado**.
   - Tenga en cuenta el nivel de disco y el nivel de sistema de archivos AccessMask al configurar esta configuración, por ejemplo, si desea denegar de forma predeterminada pero permitir almacenamiento específico, tiene que permitir el acceso tanto a nivel de disco como a nivel de sistema de archivos, debe establecer AccessMask en 63.

    :::image type="content" source="images/148609579-a7df650b-7792-4085-b552-500b28a35885.png" alt-text="Permitir o denegar código de PowerShell predeterminado":::

5. Habilitar o deshabilitar Storage Access Control extraíbles: puede establecer este valor para deshabilitar temporalmente Storage Access Control extraíbles.

    :::image type="content" source="images/148608318-5cda043d-b996-4146-9642-14fccabcb017.png" alt-text="Configuración del control de dispositivo":::

   - Una vez que implemente esta configuración, verá **Habilitado** o **Deshabilitado**. Deshabilitado significa que esta máquina no tiene directiva de Storage Access Control extraíble en ejecución.

    :::image type="content" source="images/148609685-4c05f002-5cbe-4aab-9245-83e730c5449e.png" alt-text="Control de dispositivo habilitado o deshabilitado en código de PowerShell":::

6. Establecer la ubicación de una copia del archivo: si desea tener una copia del archivo cuando se produce el acceso de escritura, debe establecer la ubicación en la que el sistema puede guardar la copia.

    Implemente esto junto con accessmask y option correctos; consulte el paso 2 anterior.

    :::image type="content" source="../../media/define-device-control-policy-rules.png" alt-text="directiva de grupo: establecer locaiton para la evidencia de archivo":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a>Implementación y administración de directivas mediante Intune OMA-URI

La característica de Storage Access Control extraíble le permite aplicar la directiva a través de OMA-URI al usuario o dispositivo, o a ambos.

### <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar a usar la Storage Access Control extraíble, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar Storage Access Control extraíbles, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivo. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.

- Rol de administrador de perfiles y directivas

- Rol personalizado con los permisos Crear/Editar/Actualizar/Leer/Eliminar/Ver informes activados para los perfiles de configuración de dispositivos

- Administrador global

### <a name="deploying-policy-via-oma-uri"></a>Implementación de directivas a través de OMA-URI

Microsoft Endpoint Manager centro de administración (<https://endpoint.microsoft.com/>) \> **Dispositivos Perfiles** \> \> **de configuración** **Crear plataforma de perfil** \> **: Windows 10 y versiones posteriores & Perfil: Personalizado**

1. Para cada grupo, cree una regla OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**GroupGUID**%7d/GroupData`

      Por ejemplo, para **cualquier almacenamiento extraíble y grupo de CD/DVD** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

    - Tipo de datos: Cadena (archivo XML)

      :::image type="content" source="images/xml-data-type-string.png" alt-text="Campo Tipo de datos en la página Agregar fila" lightbox="images/xml-data-type-string.png":::

2. Para cada directiva, cree también un OMA-URI:

    - OMA-URI: 

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**PolicyRuleGUID**%7d/RuleData`

      Por ejemplo, para la regla **Bloquear escritura y ejecutar acceso, pero permitir usbs aprobados** en el ejemplo, el vínculo debe ser:

      `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData`

    - Tipo de datos: Cadena (archivo XML)

    Si desea supervisar la información de archivo para el acceso de escritura, use accessMask adecuado con la opción correcta (16); este es el ejemplo de [captura de información de archivo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20File%20Information.xml).

3. Aplicación predeterminada: permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva. Por ejemplo, solo tiene una directiva (Denegar o Permitir) para RemovableMediaDevices, pero no tiene ninguna directiva para CdRomDevices o WpdDevices, y establece el valor predeterminado Denegar a través de esta directiva, se bloqueará el acceso de lectura, escritura y ejecución a CdRomDevices o WpdDevices.

    - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`

    - Tipo de datos: Int

      `DefaultEnforcementAllow = 1`
      `DefaultEnforcementDeny = 2`

    - Una vez que implemente esta configuración, verá **Permitir** predeterminado o **Denegar predeterminado**
    - Tenga en cuenta el nivel de disco y el nivel de sistema de archivos AccessMask al configurar esta configuración, por ejemplo, si desea denegar de forma predeterminada pero permitir almacenamiento específico, tiene que permitir el acceso tanto a nivel de disco como a nivel de sistema de archivos, debe establecer AccessMask en 63.

    :::image type="content" source="images/148609590-c67cfab8-8e2c-49f8-be2b-96444e9dfc2c.png" alt-text="Aplicación predeterminada Permitir código de PowerShell":::

4. Habilitar o deshabilitar Storage Access Control extraíbles: puede establecer este valor para deshabilitar temporalmente Storage Access Control extraíbles.

   - OMA-URI: `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`

   - Tipo de datos: Int `Disable: 0`
     `Enable: 1`

   - Una vez que implemente esta configuración, verá **Habilitado** o **Deshabilitado**.

    **Deshabilitado** significa que esta máquina no tiene directiva de Storage Access Control extraíble en ejecución

    :::image type="content" source="images/148609770-3e555883-f26f-45ab-9181-3fb1ff7a38ac.png" alt-text="Storage Access Control extraíbles en código de PowerShell":::

5. Establezca la ubicación de una copia del archivo: si desea tener una copia del archivo cuando se produzca el acceso de escritura, debe establecer la ubicación donde el sistema puede guardar la copia.

    - OMA-URI: './Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation

    - Tipo de datos: String

    Tiene que implementar esto junto con accessmask correcto y la opción correcta: consulte el paso 2 anterior.

    :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="Establecimiento de locaiton para la evidencia de archivo":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Implementación y administración de directivas mediante Intune interfaz de usuario

(*Próximamente!*) Esta funcionalidad estará disponible en el centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com/>). Vaya a **Seguridad del punto de** >  **conexiónAcción de superficie** >  de **ataqueCrear directiva**. Elija **Plataforma: Windows 10 y versiones posteriores** con **Perfil: Control de dispositivo**.

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos de Storage Access Control extraíbles de Control de dispositivos en Microsoft Defender para punto de conexión

El [portal de Microsoft 365 Defender](https://security.microsoft.com/advanced-hunting) muestra los eventos desencadenados por la Storage Access Control extraíble del control de dispositivos. Para acceder a la seguridad de Microsoft 365, debe tener la siguiente suscripción:

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

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>¿Cómo generar GUID para el id. de grupo/PolicyRule Id/Entry Id?

Puede generar GUID a través de código abierto en línea o mediante PowerShell: [cómo generar GUID a través de PowerShell](/powershell/module/microsoft.powershell.utility/new-guid)

![imagen](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

### <a name="what-is-the-removable-storage-media-limitation-for-the-maximum-number-of-usbs"></a>¿Cuál es la limitación de medios de almacenamiento extraíble para el número máximo de USB?

Hemos validado un grupo USB con 100 000 medios: hasta 7 MB de tamaño. La directiva funciona tanto en Intune como en GPO sin problemas de rendimiento.

### <a name="why-does-the-policy-not-work"></a>¿Por qué la directiva no funciona?

1. La razón más común es que no hay ninguna [versión de cliente antimalware](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints) necesaria.

2. Otra razón podría ser que el archivo XML no tiene el formato correcto, por ejemplo, no usar el formato de markdown correcto para el carácter "&" en el archivo XML, o el editor de texto podría agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione. Una solución sencilla consiste en descargar el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (seleccione **Sin procesar** y, a continuación, **Guardar como**) y, a continuación, actualizar.

3. Si va a implementar y administrar la directiva a través de directiva de grupo, asegúrese de combinar todo PolicyRule en un archivo XML dentro de un nodo primario denominado PolicyRules y todos los grupos en un archivo XML dentro de un nodo primario denominado Grupos; si administra a través de Intune, mantenga un archivo POLICYRule un archivo XML, lo mismo, un archivo XML de grupo uno.

Si aún no funciona, es posible que quiera ponerse en contacto con nosotros y compartir la cabina de soporte técnico ejecutando cmd con el administrador: "%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>No hay ninguna experiencia de usuario de configuración para "Definir grupos de directivas de control de dispositivos" y "Definir reglas de directiva de control de dispositivos" en mi directiva de grupo

No respaldamos la experiencia de usuario de configuración de directiva de grupo, pero puede obtener los archivos adml y admx relacionados haciendo clic en "Raw" y "Guardar como" en los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx).

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>¿Cómo puedo saber si la directiva más reciente se ha implementado en la máquina de destino?

Puede ejecutar "Get-MpComputerStatus" en PowerShell como administrador. El siguiente valor mostrará si la directiva más reciente se ha aplicado a la máquina de destino.

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>¿Cómo puedo saber qué máquina usa la versión de cliente antimalware obsoleta en la organización?

Puede usar la siguiente consulta para obtener la versión del cliente antimalware en el portal de seguridad de Microsoft 365:

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
