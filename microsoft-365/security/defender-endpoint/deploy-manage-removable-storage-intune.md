---
title: Implementación y administración de Access Control de almacenamiento extraíble mediante Intune
description: Use Intune OMA-URI y Intune interfaz de usuario para implementar y administrar el control de acceso de almacenamiento extraíble.
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
ms.date: 09/09/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 880be65c0d221d92af41d2835804f8252feb4e75
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711870"
---
# <a name="deploy-and-manage-removable-storage-access-control-using-intune"></a>Implementación y administración de Access Control de almacenamiento extraíble mediante Intune

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directiva de grupo y Intune OMA-URI/Administración de directivas personalizadas de este producto ya están disponibles con carácter general (4.18.2106): Consulte [el blog de Tech Community: Proteger el almacenamiento extraíble y la impresora con Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

La característica De almacenamiento extraíble Access Control le permite aplicar la directiva mediante OMA-URI a un usuario o dispositivo, o ambos.

## <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar a usar el almacenamiento extraíble Access Control, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar la Access Control de almacenamiento extraíble, debe tener Microsoft 365 E3.

### <a name="permission"></a>Permiso

Para la implementación de directivas en Intune, la cuenta debe tener permisos para crear, editar, actualizar o eliminar perfiles de configuración de dispositivo. Puede crear roles personalizados o usar cualquiera de los roles integrados con estos permisos.

- Rol de administrador de perfiles y directivas
- Rol personalizado con los permisos Crear/Editar/Actualizar/Leer/Eliminar/Ver informes activados para los perfiles de configuración de dispositivos
- Administrador global

## <a name="deploy-removable-storage-access-control-by-using-intune-oma-uri"></a>Implementación de Access Control de almacenamiento extraíble mediante Intune OMA-URI

Vaya al Centro de administración de Microsoft Endpoint Manager () ><https://endpoint.microsoft.com/> **Dispositivos** > **Crear plataforma de perfil** > **: Windows 10 y versiones posteriores, Tipo de perfil: Plantillas** > Personalizado**.

1. Habilite o deshabilite el control Dispositivo como se indica a continuación:

   - En **Configuración** **personalizada** > , seleccione **Agregar**.
   - En el panel **Agregar fila** , especifique la siguiente configuración:
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

   Por ejemplo, puede tener una directiva **Deny** o **Allow** para `RemovableMediaDevices`, pero no para `CdRomDevices` o `WpdDevices`. Puede establecer **La denegación predeterminada** a través de esta directiva y, a continuación, el acceso de lectura, escritura y ejecución a `CdRomDevices` o `WpdDevices` se bloqueará. Si solo desea administrar el almacenamiento, asegúrese de crear una directiva **Allow** para la impresora; De lo contrario, esta aplicación predeterminada también se aplicará a las impresoras.

   - En el panel **Agregar fila** , especifique la siguiente configuración:
     - **Nombre** como **denegación predeterminada**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`
     - **Tipo de datos** como **entero**
     - **Valor** como **1** o **2**

       `DefaultEnforcementAllow = 1`
       `DefaultEnforcementDeny = 2`

     - Haga clic en **Guardar**.

   :::image type="content" source="images/default-deny.png" alt-text="Captura de pantalla de la configuración de La aplicación predeterminada como Denegar" lightbox="images/default-deny.png":::

3. Cree un archivo XML para cada grupo:

   Puede crear un grupo de almacenamiento extraíble para cada grupo de la siguiente manera:

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **cualquier grupo de almacenamiento extraíble**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**[GroupId]**%7d/GroupData`
     - **Tipo de datos** como **cadena (archivo XML)**
       - **XML personalizado** como archivo XML seleccionado

         Este es un archivo XML de ejemplo de grupo para cualquier almacenamiento extraíble y dispositivos portátiles CDROM y Windows: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml>

       :::image type="content" source="images/any-removable-storage-group.png" alt-text="Captura de pantalla de la creación de cualquier grupo de almacenamiento extraíble." lightbox="images/any-removable-storage-group.png":::

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

4. Cree un archivo XML para cada control de acceso o regla de directiva:

   Puede crear una directiva y aplicarla al grupo de almacenamiento extraíble relacionado de la siguiente manera:

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **Permitir actividad de lectura**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**[PolicyRule Id]**%7d/RuleData`
     - **Tipo de datos** como **cadena (archivo XML)**
     - **XML personalizado** como **permitir Read.xml**  archivo

       Este es un archivo XML de ejemplo de grupo para permitir el acceso de lectura para cada almacenamiento extraíble: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20Read.xml>

       :::image type="content" source="images/allow-read-activity.png" alt-text="Captura de pantalla de la directiva Permitir actividad de lectura" lightbox= "images/allow-read-activity.png":::

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

5. Establezca la ubicación de una copia del archivo (evidencia):
   
   Si desea tener una copia del archivo (evidencia) cuando se produzca el acceso de escritura, establezca **las opciones** adecuadas en la regla de directiva de acceso de almacenamiento extraíble en el archivo XML y, a continuación, especifique la ubicación donde el sistema puede guardar la copia.

   - En el panel **Agregar fila** , escriba:
     - **Nombre** como **ubicación de la carpeta Evidence**
     - **OMA-URI** como `./Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation`
     - **Tipo de datos** como **cadena**

       :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="Establecimiento de la ubicación de la evidencia de archivo":::

## <a name="scenarios"></a>Escenarios

Estos son algunos escenarios comunes que le ayudarán a familiarizarse con Microsoft Defender para punto de conexión Access Control de almacenamiento extraíble.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos

En este escenario, debe crear dos grupos: uno para cualquier almacenamiento extraíble y otro para los USB aprobados. También debe crear dos directivas: una directiva para denegar el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble y la otra para auditar el grupo de USB aprobado.

1. Crear grupos

    1. Grupo 1: cualquier almacenamiento extraíble, CD/DVD y dispositivos portátiles Windows.

       :::image type="content" source="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png" alt-text="Captura de pantalla que muestra el almacenamiento extraíble" lightbox= "media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png":::

    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml). Consulte el paso 3 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo.

        :::image type="content" source="media/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png" alt-text="Captura de pantalla de los USB aprobados" lightbox= "media/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png":::

    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Approved%20USBs%20Group.xml). Consulte el paso 3 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor del archivo XML.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble, pero permitir USB aprobados.

        :::image type="content" source="media/188243425-c0772ed4-6537-4c6a-9a1d-1dbb48018578.png" alt-text="Captura de pantalla de la directiva 1" lightbox= "media/188243425-c0772ed4-6537-4c6a-9a1d-1dbb48018578.png":::

    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%201%20Block%20Write%20and%20Execute%20Access%20but%20allow%20approved%20USBs.xml). Consulte el paso 4 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

    2. Directiva 2: Auditar el acceso de escritura y ejecución para los USB permitidos.

        :::image type="content" source="media/188243552-5d2a90ab-dba6-450f-ad8f-86a862f6e739.png" alt-text="Captura de pantalla de la directiva 2" lightbox= "media/188243552-5d2a90ab-dba6-450f-ad8f-86a862f6e739.png":::

    ¿Qué significa "54" en la directiva? Es 18 + 36 = 54:

    - Acceso de escritura: nivel de disco 2 + nivel de sistema de archivos 16 = 18.
    - Ejecutar: nivel de disco 4 + nivel de sistema de archivos 32 = 36.

    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%201%20Audit%20Write%20and%20Execute%20access%20to%20aproved%20USBs.xml). Consulte el paso 4 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

### <a name="scenario-2-audit-write-and-execute-access-for-all-but-block-specific-blocked-usbs"></a>Escenario 2: Auditoría de escritura y ejecución de acceso para todos los USB bloqueados específicos, pero bloqueados

En este escenario, debe crear dos grupos: un grupo para cualquier almacenamiento extraíble y otro para los USB bloqueados. También debe crear dos directivas: una directiva para auditar el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble y la otra para denegar el grupo de USB bloqueados.

1. Crear grupos

    1. Grupo 1: cualquier almacenamiento extraíble, CD/DVD y dispositivos portátiles Windows.

        :::image type="content" source="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png" alt-text="Captura de pantalla del grupo 1" lightbox="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png":::
    
    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml). Consulte el paso 3 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

    2. Grupo 2: USB no aprobados en función de las propiedades del dispositivo.

        :::image type="content" source="media/188243875-0693ebcf-00c3-45bd-afd3-57a79df9dce6.png" alt-text="Captura de pantalla del grupo 2" lightbox= "media/188243875-0693ebcf-00c3-45bd-afd3-57a79df9dce6.png":::
     
    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Unapproved%20USBs%20Group.xml). Consulte el paso 3 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.


    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor del archivo XML.

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución para todos los USB no aprobados específicos, pero bloquearlos.

        :::image type="content" source="media/188244024-62355ded-353c-4d3a-ba61-4520d48f5a18.png" alt-text="Captura de pantalla de la directiva para bloquear los USB no aprobados" lightbox= "media/188244024-62355ded-353c-4d3a-ba61-4520d48f5a18.png":::
    
    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%202%20Audit%20Write%20and%20Execute%20access%20to%20all%20but%20block%20specific%20unapproved%20USBs.xml). Consulte el paso 4 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

    2. Directiva 2: Auditar el acceso de escritura y ejecución para otros usuarios.

        :::image type="content" source="media/188244203-36c869b6-9330-4e2a-854b-494c342bb77d.png" alt-text="Captura de pantalla del acceso de escritura y ejecución de auditoría" lightbox= "media/188244203-36c869b6-9330-4e2a-854b-494c342bb77d.png":::
    
    ¿Qué significa "54" en la directiva? Es 18 + 36 = 54:

    - Acceso de escritura: nivel de disco 2 + nivel de sistema de archivos 16 = 18.
    - Ejecutar: nivel de disco 4 + nivel de sistema de archivos 32 = 36.
    
    Este es el [archivo de ejemplo](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%202%20Audit%20Write%20and%20Execute%20access%20to%20others.xml). Consulte el paso 4 de la sección [Implementar almacenamiento extraíble Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) para implementar la configuración.

## <a name="use-intune-user-interface"></a>Uso de Intune interfaz de usuario

Esta funcionalidad está disponible en el Centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com/>). 

Vaya a Directiva de **creación de reducción de superficie expuesta a ataques** >  **de seguridad** > **de punto de** conexión. Elija **Plataforma: Windows 10 y versiones posteriores** con **Perfil: Control de dispositivo**.
