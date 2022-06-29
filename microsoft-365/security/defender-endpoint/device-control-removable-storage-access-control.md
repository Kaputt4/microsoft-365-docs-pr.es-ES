---
title: Microsoft Defender para punto de conexión dispositivo control almacenamiento extraíble Access Control, medios de almacenamiento extraíbles
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
ms.date: 06/24/2022
ms.openlocfilehash: d9ff97aa50a03c1a75f073328a250a9acc3faf54
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490761"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a>Microsoft Defender para punto de conexión almacenamiento extraíble de control de dispositivos Access Control

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directiva de grupo y Intune OMA-URI/Administración de directivas personalizadas de este producto ya están disponibles con carácter general (4.18.2106): Consulte [el blog de Tech Community: Proteger el almacenamiento extraíble y la impresora con Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

## <a name="device-control-removable-storage-access-control-overview"></a>Información general sobre el almacenamiento extraíble de Control de dispositivos Access Control

Microsoft Defender para punto de conexión característica de almacenamiento extraíble de control de dispositivos Access Control permite auditar, permitir o impedir el acceso de lectura, escritura o ejecución al almacenamiento extraíble con o sin exclusión.

|Privilegio|Permiso|
|---|---|
|Access|Lectura, Escritura, Ejecución|
|Modo de acción|Auditar, permitir, impedir|
|Compatibilidad con CSP|Sí|
|Compatibilidad con GPO|Sí|
|Soporte técnico basado en el usuario|Sí|
|Compatibilidad basada en máquinas|Sí|

Microsoft Defender para punto de conexión característica de almacenamiento extraíble de control de dispositivos Access Control proporciona las siguientes funcionalidades:

|Funcionalidad|Descripción|Implementación a través de Intune|Implementación a través de directiva de grupo|
|---|---|---|---|
|Creación de grupos de medios extraíbles|Permite crear un grupo de medios extraíble reutilizable|Paso 4 y 6 de la sección [Implementación de Access Control de almacenamiento extraíble mediante Intune OMA-URI](#deploying-removable-storage-access-control-by-using-intune-oma-uri)| Paso 4 y 6 de la sección [Implementación de almacenamiento extraíble Access Control mediante directiva de grupo](#deploying-removable-storage-access-control-by-using-group-policy)|
|Creación de directivas|Permite crear una directiva para aplicar cada grupo de medios extraíble|Paso 5 y 7 de la sección [Implementación de almacenamiento extraíble Access Control mediante Intune OMA-URI](#deploying-removable-storage-access-control-by-using-intune-oma-uri)| Los pasos 5 y 7 de la sección Implementación de [almacenamiento extraíble Access Control mediante directiva de grupo](#deploying-removable-storage-access-control-by-using-group-policy)|
|Aplicación predeterminada|Permite establecer el acceso predeterminado (Denegar o Permitir) en medios extraíbles si no hay ninguna directiva|Paso 2 de la sección [Implementación de almacenamiento extraíble Access Control mediante Intune OMA-URI](#deploying-removable-storage-access-control-by-using-intune-oma-uri) | Paso 2 de la sección [Implementación de almacenamiento extraíble Access Control mediante directiva de grupo](#deploying-removable-storage-access-control-by-using-group-policy)|
|Habilitar o deshabilitar el almacenamiento extraíble Access Control|Si establece Deshabilitar, deshabilitará la directiva de Access Control de almacenamiento extraíble en esta máquina.| Paso 1 de la sección Implementación de [Access Control de almacenamiento extraíble mediante Intune OMA-URI](#deploying-removable-storage-access-control-by-using-intune-oma-uri)| Paso 1 de la sección [Implementación de almacenamiento extraíble Access Control mediante directiva de grupo](#deploying-removable-storage-access-control-by-using-group-policy)|
|Captura de información de archivo|Permite crear una directiva para capturar información de archivo cuando se produce el acceso de escritura|  | Paso 10 de la sección Implementación de [almacenamiento extraíble Access Control mediante directiva de grupo](#deploying-removable-storage-access-control-by-using-group-policy) |

### <a name="prepare-your-endpoints"></a>Preparar los puntos de conexión

Implemente Access Control de almacenamiento extraíble en dispositivos Windows 10 y Windows 11 que tengan la versión de cliente antimalware **4.18.2103.3 o posterior**.

- **4.18.2104 o posterior**: Agregar `SerialNumberId`, , `VID_PID`compatibilidad con GPO basado en filepath y `ComputerSid`

- **4.18.2105 o posterior**: Agregar compatibilidad con caracteres comodín para `HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId`, la combinación de un usuario específico en una máquina específica, SSD extraíble (un SSD Extremo sanDisk)/Compatibilidad con SCSI conectado a USB (UAS)

- **4.18.2107 o posterior**: Agregar compatibilidad con dispositivos portátiles Windows (WPD) (para dispositivos móviles, como tabletas); agregar `AccountName` a [la búsqueda avanzada](device-control-removable-storage-access-control.md#view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint)

- **4.18.2205 o posterior**: expanda el cumplimiento predeterminado a **Impresora**. Si lo establece en **Denegar**, también bloqueará La impresora, por lo que si solo desea administrar el almacenamiento, asegúrese de crear una directiva personalizada para permitir la impresora.

:::image type="content" source="images/powershell.png" alt-text="La interfaz de PowerShell" lightbox="images/powershell.png":::

> [!NOTE]
> No es necesario que ninguno de los componentes de Seguridad de Windows esté activo, ya que puede ejecutar almacenamiento extraíble Access Control independientemente del estado de Seguridad de Windows.

## <a name="device-control-removable-storage-access-control-policies"></a>Directivas de Access Control de almacenamiento extraíble de Control de dispositivos

Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble:

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

### <a name="removable-storage-group"></a>Grupo de almacenamiento extraíble

|Nombre de propiedad|Descripción|Opciones|
|---|---|---|
|**Groupid**|GUID, un identificador único, representa el grupo y se usará en la directiva.||
|**DescriptorIdList**|Enumere las propiedades del dispositivo que desea usar para cubrir en el grupo. Para cada propiedad de dispositivo, consulte [Propiedades del dispositivo](device-control-removable-storage-protection.md) para obtener más detalles. Todas las propiedades distinguen mayúsculas de minúsculas. |**PrimaryId**: `RemovableMediaDevices`, , `CdRomDevices``WpdDevices`<p>**BusId**: por ejemplo, USB, SCSI<p>**Deviceid**<p>**HardwareId**<p>**InstancePathId**: InstancePathId es una cadena que identifica de forma única el dispositivo en el sistema, por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0`. El número al final (por ejemplo, &0) representa la ranura disponible y puede cambiar de dispositivo a dispositivo. Para obtener los mejores resultados, use un carácter comodín al final. Por ejemplo, `USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611*`.<p>**FriendlyNameId**<p>**SerialNumberId**<p>**VID**<p>**PID**<p>**VID_PID**<p>`0751_55E0`: coincide con este par VID/PID exacto<p>`_55E0`: coincide con cualquier medio con PID=55E0 <p>`0751_`: coincide con cualquier medio con VID=0751|
|**MatchType**|Cuando se usan varias propiedades de `DescriptorIDList`dispositivo en , MatchType define la relación.|**MatchAll**: los atributos de la `DescriptorIdList` relación serán **Y** ; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema comprobará si el USB cumple ambos valores. <p> **MatchAny**: los atributos de DescriptorIdList serán **O** relationship; por ejemplo, si el administrador coloca `DeviceID` y `InstancePathID`, para cada USB conectado, el sistema realizará la aplicación siempre y cuando el USB tenga un valor **de DeviceID** o **InstanceID** idéntico.|

### <a name="access-control-policy"></a>directiva de Access Control
Puede usar las siguientes propiedades para crear la directiva de control de acceso:

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

## <a name="device-control-removable-storage-access-control-scenarios"></a>Escenarios de Access Control de almacenamiento extraíble de Control de dispositivos

Para ayudarle a familiarizarse con Microsoft Defender para punto de conexión Access Control de almacenamiento extraíble, hemos elaborado algunos escenarios comunes que debe seguir.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo de almacenamiento extraíble y CD/DVD es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el archivo [de Group.xmlde cd-DVD y almacenamiento extraíble](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo. Un ejemplo para este caso de uso es: Id. de instancia: Grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [de Group.xmlusb aprobados](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear escritura y ejecutar acceso, pero permitir USB aprobados. Un ejemplo para este caso de uso es: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** en el [escenario de ejemplo 1 Bloquear escritura y ejecutar acceso, pero permitir USBs.xmlarchivo aprobado](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

    2. Directiva 2: Auditar el acceso de escritura y ejecución a los USB permitidos. Un ejemplo para este caso de uso es: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** en el [escenario de ejemplo 1 Auditar escritura y ejecutar el acceso a USBs.xmlarchivo aprobado](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a>Escenario 2: Auditar el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloquearlos

1. Crear grupos

    1. Grupo 1: Cualquier almacenamiento extraíble y CD/DVD. Un ejemplo para este caso de uso es: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** en el archivo [de Group.xmlde ejemplo Any Removable Storage and CD-DVD](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

    2. Grupo 2: USB no aprobados en función de las propiedades del dispositivo, por ejemplo, id. de proveedor/id. de producto, nombre descriptivo : grupo **65fa649a-a111-4912-9294-fb6337a25038** en el archivo [de Group.xmlusbs no aprobados](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) de ejemplo.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución a todos los USB no aprobados específicos, pero bloquearlos. Un ejemplo de este caso de uso es: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** en el [escenario de ejemplo 2 Escritura y ejecución de auditoría de acceso a todos los archivos de USBs.xmlno aprobados específicos, pero sin aprobar](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) .

    2. Directiva 2: Auditar el acceso de escritura y ejecución a otros usuarios. Un ejemplo de este caso de uso es: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** en el [escenario de ejemplo 2 Auditar escritura y ejecutar acceso a others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) archivo.

## <a name="deploying-and-managing-removable-storage-access-control-by-using-intune-oma-uri"></a>Implementación y administración de Access Control de almacenamiento extraíble mediante Intune OMA-URI

La característica De almacenamiento extraíble Access Control le permite aplicar la directiva mediante OMA-URI a un usuario o dispositivo, o ambos.

### <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar a usar el almacenamiento extraíble Access Control, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar la Access Control de almacenamiento extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivo. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.

- Rol de administrador de perfiles y directivas
- Rol personalizado con los permisos Crear/Editar/Actualizar/Leer/Eliminar/Ver informes activados para los perfiles de configuración de dispositivos
- Administrador global

### <a name="deploying-removable-storage-access-control-by-using-intune-oma-uri"></a>Implementación de Access Control de almacenamiento extraíble mediante Intune OMA-URI

Vaya al Centro de administración de Microsoft Endpoint Manager () dispositivos **> > Crear perfil > Plataforma: Windows 10 y versiones posteriores, Tipo de perfil: Plantillas > Personalizado**<https://endpoint.microsoft.com/>

1. Habilite o deshabilite el control Dispositivo como se indica a continuación:

   - En **Configuración personalizada >**, haga clic en **Agregar**.
   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **Habilitar control de dispositivo**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`
     - **Tipo de datos** como **entero**
     - **Valor** como **1**

       `Disable: 0`
       `Enable: 1`

     - Haga clic en **Guardar**.

   :::image type="content" source="images/enable-rsac.png" alt-text="Captura de pantalla de la habilitación de la directiva de Access Control de almacenamiento extraíble" lightbox="images/enable-rsac.png":::

2. Establecer aplicación predeterminada:

   Puede establecer el acceso predeterminado (Denegar o Permitir) para todas las características de Control de dispositivos (`RemovableMediaDevices`, `CdRomDevices`, `WpdDevices`, `PrinterDevices`).

   Por ejemplo, tiene una directiva **Deny** o **Allow** para `RemovableMediaDevices`, pero no tiene una directiva para `CdRomDevices` o `WpdDevices`. Puede establecer **La denegación predeterminada** a través de esta directiva y, a continuación, el acceso de lectura, escritura y ejecución a `CdRomDevices` o `WpdDevices` se bloqueará. Si solo desea administrar el almacenamiento, asegúrese de crear una directiva **Allow** para la impresora; De lo contrario, esta aplicación predeterminada también se aplicará a las impresoras.

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **denegación predeterminada**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`
     - **Tipo de datos** como **entero**
     - **Valor** como **1** o **2**

       `DefaultEnforcementAllow = 1`
       `DefaultEnforcementDeny = 2`

     - Haga clic en **Guardar**.

   :::image type="content" source="images/default-deny.png" alt-text="Captura de pantalla de la configuración de La aplicación predeterminada como Denegar" lightbox="images/default-deny.png":::

3. Auditar denegación predeterminada:

   Puede crear una directiva de auditoría para Denegar predeterminada como se indica a continuación:

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **denegación predeterminada de auditoría**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bf3520ea7-fd1b-4237-8ebc-96911db44f8e%7d/RuleData`

       :::image type="content" source="images/audit-default-deny-1.png" alt-text="Captura de pantalla de la creación de la directiva de denegación predeterminada de auditoría" lightbox="images/audit-default-deny-1.png":::

     - **Tipo de datos** como **cadena (archivo XML)**
     - **XML personalizado** como archivo **de Deny.xmlpredeterminado de auditoría** .

       Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Audit%20Default%20Deny.xml>

       Use los siguientes datos XML para crear la directiva de auditoría para la denegación predeterminada:

       :::image type="content" source="images/audit-default-deny-xml-file-1.png" alt-text="Captura de pantalla del archivo xml de denegación predeterminado de auditoría":::

4. ReadOnly : grupo:

   Puede crear un grupo de almacenamiento extraíble con acceso ReadOnly de la siguiente manera:

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **cualquier grupo de almacenamiento extraíble**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData`

       :::image type="content" source="images/any-removable-storage-group.png" alt-text="Captura de pantalla de la creación de cualquier grupo de almacenamiento extraíble" lightbox="images/any-removable-storage-group.png":::

     - **Tipo de datos** como **cadena (archivo XML)**
       - **XML personalizado** como **cualquier archivo de almacenamiento extraíble y CD-DVD y WPD Group.xml**

         Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml>

         Use los siguientes datos XML para crear "Cualquier almacenamiento extraíble y CD-DVD y grupo WPD" con acceso ReadOnly:

         :::image type="content" source="images/read-only-group-xml-file.png" alt-text="Captura de pantalla del archivo xml de grupo de solo lectura":::

5. ReadOnly: directiva:

   Puede crear una directiva ReadOnly y aplicarla al grupo de almacenamiento extraíble ReadOnly para permitir la actividad de lectura como se indica a continuación:

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **Permitir actividad de lectura**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bf7e75634-7eec-4e67-bec5-5e7750cb9e02%7d/RuleData`

       :::image type="content" source="images/allow-read-activity.png" alt-text="Captura de pantalla de la directiva Permitir actividad de lectura" lightbox= "images/allow-read-activity.png":::

     - **Tipo de datos** como **cadena (archivo XML)**
     - **XML personalizado** como **permitir Read.xml**  archivo

       Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20Read.xml>

       Use los siguientes datos XML para crear la directiva ReadOnly y aplicarlos al grupo de almacenamiento extraíble ReadOnly:

       :::image type="content" source="images/read-only-policy-xml-file.png" alt-text="Captura de pantalla del archivo xml de directiva de solo lectura":::

6. Crear un grupo para medios permitidos: puede crear el grupo de medios permitido de la siguiente manera:
   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **grupo de USB aprobados**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b65fa649a-a111-4912-9294-fb6337a25038%7d/GroupData`

       :::image type="content" source="images/create-group-allowed-medias.png" alt-text="Captura de pantalla de la creación de un grupo de USB aprobados" lightbox="images/create-group-allowed-medias.png":::

     - **Tipo de datos** como **cadena (archivo XML)**
     - **XML personalizado** como **usb aprobado Group.xml** archivo

       Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Approved%20USBs%20Group.xml>

       Use los siguientes datos XML para crear un grupo de medios permitido:

       :::image type="content" source="images/create-group-allowed-medias-xml-file.png" alt-text="Captura de pantalla de la creación de un grupo para el archivo xml de medias permitido":::

7. Crear una directiva para permitir el grupo USB aprobado: puede crear una directiva para permitir el grupo USB aprobado de la siguiente manera:
   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **Permitir acceso e Información de archivo de auditoría**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bb2061588-029e-427d-8404-6dfec096a571%7d/RuleData`

       :::image type="content" source="images/allow-access-audit-file-information-1.png" alt-text="Captura de pantalla de Permitir acceso y auditar la información del archivo" lightbox= "images/allow-access-audit-file-information-1.png":::

     - **Tipo de datos** como **cadena (archivo XML)**
     - **XML personalizado** como **Permitir acceso completo y auditar file.xml**  archivo

       Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20full%20access%20and%20audit%20file.xml>

       Use los siguientes datos XML para crear una directiva que permita el grupo USB aprobado:

       :::image type="content" source="images/create-policy-allow-approved-usb-group-xml-intune.png" alt-text="Captura de pantalla de la creación de una directiva para permitir el archivo XML de grupo USB aprobado":::

       ¿Qué significa "47" en la directiva? Es 9 + 2 + 36 = 47:

       - Acceso de lectura: 1 + 8 = 9.
       - Acceso de escritura: nivel de disco 2.
       - Ejecutar: 4 + 32 = 36.

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a>Implementación y administración de directivas mediante Intune interfaz de usuario

Esta funcionalidad está disponible en el Centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com/>). Vaya a Directiva de **creación de reducción de superficie expuesta a ataques** >  **de seguridad** > **de punto de** conexión. Elija **Plataforma: Windows 10 y versiones posteriores** con **Perfil: Control de dispositivo**.

## <a name="deploying-and-managing-removable-storage-access-control-by-using-group-policy"></a>Implementación y administración de Access Control de almacenamiento extraíble mediante directiva de grupo

La característica de Access Control de almacenamiento extraíble le permite aplicar una directiva mediante directiva de grupo a un usuario o dispositivo, o a ambos.

### <a name="licensing"></a>Licencias

Antes de empezar a usar el almacenamiento extraíble Access Control, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar la Access Control de almacenamiento extraíble, debe tener Microsoft 365 E3 o Microsoft 365 E5.

### <a name="deploying-removable-storage-access-control-by-using-group-policy"></a>Implementación de Access Control de almacenamiento extraíble mediante directiva de grupo

1. Habilite o deshabilite el almacenamiento extraíble Access Control:

   Puede habilitar el control De dispositivo de la siguiente manera:

   - Vaya a **Configuración del equipo > Plantillas administrativas > componentes de Windows > Antivirus de Microsoft Defender > Características > control de dispositivos**
   - En la ventana **Control de dispositivos** , seleccione **Habilitado**.

   :::image type="content" source="images/enable-rsac-gp.png" alt-text="Captura de pantalla de habilitación de RSAC mediante directiva de grupo " lightbox="images/enable-rsac-gp.png":::

2. Establecer aplicación predeterminada:

   Puede establecer el acceso predeterminado (Denegar o Permitir) para todas las características de Control de dispositivos (RemovableMediaDevices, CdRomDevices, WpdDevices, PrinterDevices).

   Por ejemplo, tiene la directiva Denegar o Permitir para RemovableMediaDevices, pero no tiene ninguna directiva para CdRomDevices o WpdDevices. Establezca Denegación predeterminada a través de esta directiva y, a continuación, se bloqueará el acceso de lectura, escritura y ejecución a CdRomDevices o WpdDevices. Si solo desea administrar el almacenamiento, asegúrese de crear la directiva Permitir para impresora; de lo contrario, esta aplicación predeterminada también se aplicará a la impresora.

   - Vaya a **Configuración del equipo > Plantillas administrativas > componentes de Windows > Antivirus de Microsoft Defender > Características > Control de dispositivos > Seleccionar aplicación predeterminada del control de dispositivos**

   - En la ventana **Seleccionar aplicación predeterminada del control de dispositivos** , seleccione **Denegar predeterminado**:

   :::image type="content" source="images/set-default-enforcement-deny-gp.png" alt-text="Captura de pantalla de la configuración de Aplicación predeterminada = Denegar mediante directiva de grupo" lightbox="images/set-default-enforcement-deny-gp.png":::

3. Auditar denegación predeterminada:

   Use los siguientes datos XML para crear la directiva de auditoría para la denegación predeterminada:

   :::image type="content" source="images/audit-default-deny-gp.png" alt-text="Captura de pantalla de los datos xml de denegación predeterminados de auditoría":::

4. ReadOnly : grupo:

   Use los siguientes datos XML para crear un grupo de almacenamiento extraíble con acceso ReadOnly:

   :::image type="content" source="images/read-only-group-gp.png" alt-text="Captura de pantalla de datos xml de grupo de almacenamiento extraíble de solo lectura":::

5. ReadOnly: directiva:

   Use los siguientes datos XML para crear la directiva ReadOnly y aplicarlos al grupo de almacenamiento extraíble ReadOnly para permitir la actividad de lectura:

    :::image type="content" source="images/read-only-policy-gp.png" alt-text="Captura de pantalla de datos xml de directiva de solo lectura" lightbox="images/read-only-policy-gp.png":::

6. Crear grupo para medios permitidos:

   Use los siguientes datos XML para crear un grupo de medios permitidos de almacenamiento extraíble:

   :::image type="content" source="images/create-group-allowed-medias-gp.png" alt-text="Captura de pantalla de los datos xml para crear un grupo para los medios permitidos" lightbox="images/create-group-allowed-medias-gp.png":::

7. Cree una directiva para permitir el grupo USB aprobado:

   Use los siguientes datos XML para crear una directiva que permita el grupo USB aprobado:

   :::image type="content" source="images/create-policy-allow-approved-usb-group-xml.png" alt-text="Captura de pantalla de los datos XML para crear la directiva para permitir que el grupo USB aprobado use directiva de grupo" lightbox="images/create-policy-allow-approved-usb-group-xml.png":::

   ¿Qué significa "47" en la directiva? Es 9 + 2 + 36 = 47:

   - Acceso de lectura: 1+8 = 9.
   - Acceso de escritura: nivel de disco 2.
   - Ejecutar: 4 + 32 = 36.

8. Combine grupos en un archivo XML:

   Puede combinar grupos de directivas de control de dispositivos en un archivo XML como se indica a continuación:

   - Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows **Control de** \> dispositivos antivirus \> de **Microsoft Defender** **Definir grupos de directivas de control de dispositivos**.

    :::image type="content" source="images/define-device-control-policy-grps-gp.png" alt-text="Captura de pantalla de Definir grupos de directivas de control de dispositivos" lightbox="images/define-device-control-policy-grps-gp.png":::

   - En la ventana **Definir grupos de directivas de control de dispositivos** , escriba la ruta de acceso del archivo que contiene los datos de los grupos XML.

     Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml>

     A continuación se muestra el esquema xml de los grupos de directivas de control de dispositivos:

     :::image type="content" source="images/combine-grps-xml-file-gp.png" alt-text="Captura de pantalla de la combinación de grupos en un archivo XML":::

9. Combine directivas en un archivo XML:

   Puede combinar reglas de directiva de control de dispositivos en un archivo XML como se indica a continuación:

   - Vaya a **Configuración del equipo > Plantillas administrativas > componentes de Windows > Antivirus de Microsoft Defender > Control de dispositivos > Definir reglas de directiva de control de dispositivos**

     :::image type="content" source="images/define-device-cntrl-policy-rules-gp.png" alt-text="Captura de pantalla de la definición de reglas de directiva de control de dispositivos" lightbox="images/define-device-cntrl-policy-rules-gp.png":::

   - En la ventana **Definir reglas de directiva de control de dispositivos** , seleccione **Habilitado** y escriba la ruta de acceso del archivo que contiene los datos de reglas XML.

     Ruta de acceso del archivo XML: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Policies.xml>

     A continuación se muestra el esquema xml de reglas de directiva de control de dispositivos:

    :::image type="content" source="images/combine-policies-xml-gp.png" alt-text="Captura de pantalla de la combinación de directivas en un archivo XML":::

10. Establezca la ubicación de una copia del archivo (evidencia):

    Si desea tener una copia del archivo (evidencia) cuando se produce el acceso de escritura, tiene que establecer la ubicación donde el sistema puede guardar la copia.

    - Vaya a **Configuración del equipo > Plantillas administrativas > componentes de Windows > Antivirus de Microsoft Defender > Control de dispositivos > Definir ubicación remota de datos de prueba de Control de dispositivos**.

    - En la ventana **Definir ubicación remota de datos de evidencia de Control** de dispositivos, seleccione **Habilitado** y escriba la ruta de acceso de la carpeta del recurso compartido local o de red.

      :::image type="content" source="images/evidence-data-remote-location-gp.png" alt-text="Captura de pantalla de Definir ubicación remota de datos de evidencia de Control de dispositivos" lightbox="images/evidence-data-remote-location-gp.png":::

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a>Ver datos de Access Control de almacenamiento extraíble de Control de dispositivos en Microsoft Defender para punto de conexión

El [portal de Microsoft 365 Defender](https://security.microsoft.com/advanced-hunting) muestra los eventos desencadenados por la Access Control de almacenamiento extraíble de Device Control. Para acceder a la seguridad de Microsoft 365, debe tener la siguiente suscripción:

- Informes de Microsoft 365 para E5

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

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="how-to-generate-guid-for-group-idpolicyrule-identry-id"></a>¿Cómo generar GUID para el id. de grupo/PolicyRule Id/Entry Id?

Puede generar GUID a través de código abierto en línea o mediante PowerShell: [cómo generar GUID a través de PowerShell](/powershell/module/microsoft.powershell.utility/new-guid)

![imagen](https://user-images.githubusercontent.com/81826151/159046476-26ea0a21-8087-4f01-b8ae-5aa73b392d8f.png)

### <a name="what-are-the-removable-storage-media-and-policy-limitations"></a>¿Cuáles son las limitaciones de directivas y medios de almacenamiento extraíbles?

Ya sea desde el Centro de administración de Microsoft Endpoint Manager (Intune) o a través de Microsoft Graph API, la llamada de back-end se realiza a través de OMA-URI (GET para leer o PATCH para actualizar) y, por lo tanto, la limitación es la misma que cualquier perfil de configuración personalizada de OMA-URI en Microsoft que es oficialmente de 350 000 caracteres para archivos XML.

Por ejemplo, si necesita dos bloques de entradas por SID de usuario para "Permitir"/"Auditar permitidos" usuarios específicos y dos bloques de entradas al final para "Denegar", podrá administrar 2.276 usuarios.

### <a name="why-does-the-policy-not-work"></a>¿Por qué la directiva no funciona?

1. La razón más común es que no hay ninguna [versión de cliente antimalware](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints) necesaria.

2. Otra razón podría ser que el archivo XML no tiene el formato correcto, por ejemplo, no usar el formato de markdown correcto para el carácter "&" en el archivo XML, o el editor de texto podría agregar una marca de orden de bytes (BOM) 0xEF 0xBB 0xBF al principio de los archivos, lo que hace que el análisis XML no funcione. Una solución sencilla consiste en descargar el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (seleccione **Sin procesar** y, a continuación, **Guardar como**) y, a continuación, actualizar.

3. Si va a implementar y administrar la directiva mediante directiva de grupo, asegúrese de combinar todo PolicyRule en un archivo XML dentro de un nodo primario denominado PolicyRules y todos los grupos en un archivo XML dentro de un nodo primario denominado Groups; si administra a través de Intune, mantenga un archivo PolicyRule un archivo XML, lo mismo, un archivo XML de grupo uno.

Si todavía no funciona, es posible que quiera ponerse en contacto con nosotros y compartir la cabina de soporte técnico ejecutando cmd con el administrador: "%programfiles%\Windows Defender\MpCmdRun.exe" -GetFiles

### <a name="there-is-no-configuration-ux-for-define-device-control-policy-groups-and-define-device-control-policy-rules-on-my-group-policy"></a>No hay ninguna experiencia de usuario de configuración para "Definir grupos de directivas de control de dispositivos" y "Definir reglas de directiva de control de dispositivos" en mi directiva de grupo

No respaldamos la experiencia de usuario de configuración de directiva de grupo, pero puede obtener los archivos adml y admx relacionados haciendo clic en "Raw" y "Guardar como" en los archivos [WindowsDefender.adml](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.adml) y [WindowsDefender.admx](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/WindowsDefender.admx).

### <a name="how-can-i-know-whether-the-latest-policy-has-been-deployed-to-the-target-machine"></a>¿Cómo puedo saber si la directiva más reciente se ha implementado en la máquina de destino?

Puede ejecutar "Get-MpComputerStatus" en PowerShell como administrador. El siguiente valor mostrará si la directiva más reciente se ha aplicado a la máquina de destino.

:::image type="icon" source="images/148609885-bea388a9-c07d-47ef-b848-999d794d24b8.png" border="false":::

### <a name="how-can-i-know-which-machine-is-using-out-of-date-antimalware-client-version-in-the-organization"></a>¿Cómo puedo saber qué máquina usa la versión de cliente antimalware obsoleta en la organización?

Puede usar la siguiente consulta para obtener la versión de cliente antimalware en el portal de seguridad de Microsoft 365:

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
