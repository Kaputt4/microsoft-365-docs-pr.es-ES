---
title: Implementación y administración de Access Control de almacenamiento extraíble mediante la directiva de grupo
description: Use la directiva de grupo para implementar y administrar el control de acceso de almacenamiento extraíble.
ms.service: microsoft-365-security
ms.subservice: mde
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
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.date: 09/09/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 947388cd2840c94e7faeb956d3fcaac309303307
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174938"
---
# <a name="deploy-and-manage-removable-storage-access-control-using-group-policy"></a>Implementación y administración de Access Control de almacenamiento extraíble mediante la directiva de grupo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> La administración de directiva de grupo y Intune OMA-URI/Administración de directivas personalizadas de este producto ya están disponibles con carácter general (4.18.2106): Consulte [el blog de Tech Community: Proteger el almacenamiento extraíble y la impresora con Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

La característica De almacenamiento extraíble Access Control permite aplicar una directiva mediante la directiva de grupo a un usuario o dispositivo, o a ambos.

## <a name="device-control-removable-storage-access-control-policies"></a>Directivas de Access Control de almacenamiento extraíble de Control de dispositivos

Puede usar las siguientes propiedades para crear un grupo de almacenamiento extraíble.

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

## <a name="licensing-requirements"></a>Requisitos de licencias

Antes de empezar a usar el almacenamiento extraíble Access Control, debe confirmar la [suscripción de Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2). Para acceder y usar el almacenamiento extraíble Access Control a través de la directiva de grupo, debe tener Microsoft 365 E5.

## <a name="deploy-using-group-policy"></a>Implementación mediante la directiva de grupo

1. Habilite o deshabilite el almacenamiento extraíble Access Control:

   Puede habilitar o deshabilitar el control De dispositivo como se indica a continuación:

   - Vaya a **Configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  de Windows **Microsoft Defender Antivirus** > **Features** > **Device Control**.
   - En la ventana **Control de dispositivos** , seleccione **Habilitado**.

   :::image type="content" source="images/enable-rsac-gp.png" alt-text="Captura de pantalla de habilitación de RSAC mediante directiva de grupo " lightbox="images/enable-rsac-gp.png":::

> [!NOTE]
> Si no ve estos objetos de directiva de grupo, debe agregar la plantilla administrativa de directiva de grupo. Puede descargar la plantilla administrativa (WindowsDefender.adml y WindowsDefender.admx) desde https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples.

2. Establecer aplicación predeterminada:

   Puede establecer el acceso predeterminado (Denegar o Permitir) para todas las características de Control de dispositivos (RemovableMediaDevices, CdRomDevices, WpdDevices, PrinterDevices).

   Por ejemplo, puede tener una directiva Deny o Allow para RemovableMediaDevices, pero no para CdRomDevices o WpdDevices. Establezca Denegación predeterminada a través de esta directiva y, a continuación, se bloqueará el acceso de lectura, escritura y ejecución a CdRomDevices o WpdDevices. Si solo desea administrar el almacenamiento, asegúrese de crear la directiva Permitir para impresora. De lo contrario, esta aplicación predeterminada también se aplicará a la impresora.

   - Vaya a **Configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  de Windows **Microsoft Defender** > **Antivirus Features** > **Device Control** > **Select Device Control Default Enforcement**

   - En el panel **Seleccionar aplicación predeterminada del control de dispositivos** , seleccione **Denegar predeterminado**:

   :::image type="content" source="images/set-default-enforcement-deny-gp.png" alt-text="Captura de pantalla de la configuración de Aplicación predeterminada = Denegar mediante directiva de grupo" lightbox="images/set-default-enforcement-deny-gp.png":::

3. Cree un archivo XML para grupos de almacenamiento extraíbles:

   Use las propiedades del grupo de almacenamiento extraíble para crear un archivo XML para los grupos de almacenamiento extraíbles, guardar el archivo XML en el recurso compartido de red y definir la configuración de la siguiente manera:

   - Vaya a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> **de Windows Microsoft Defender** **Control** \> de dispositivos antivirus \> **Definir grupos de directivas de control de dispositivos**.

    :::image type="content" source="images/define-device-control-policy-grps-gp.png" alt-text="Captura de pantalla de Definir grupos de directivas de control de dispositivos" lightbox="images/define-device-control-policy-grps-gp.png":::

   - En la ventana **Definir grupos de directivas de control de dispositivo** , especifique la ruta de acceso del archivo de recurso compartido de red que contiene los datos de grupos XML.

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

4. Cree un archivo XML para las reglas de directiva de acceso:

   Use las propiedades de las reglas de directiva de acceso de almacenamiento extraíbles para crear un XML para la regla de directiva de acceso de almacenamiento extraíble de cada grupo, guarde el archivo XML en el recurso compartido de red y devlier la configuración como se indica a continuación:

   - Vaya a **Configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  de Windows Microsoft Defender **Control** >  de dispositivos **antivirus** > **Definir reglas de directiva de control de dispositivos**.

     :::image type="content" source="images/define-device-cntrl-policy-rules-gp.png" alt-text="Captura de pantalla de la definición de reglas de directiva de control de dispositivos" lightbox="images/define-device-cntrl-policy-rules-gp.png":::

   - En la ventana **Definir reglas de directiva de control de dispositivos** , seleccione **Habilitado** y escriba la ruta de acceso del archivo de recurso compartido de red que contiene los datos de reglas XML.

> [!NOTE]
> Los comentarios que usan la notación de `<!-- COMMENT -->` comentarios XML se pueden usar en los archivos XML de regla y grupo, pero deben estar dentro de la primera etiqueta XML, no en la primera línea del archivo XML.

5. Establezca la ubicación de una copia del archivo (evidencia):

    Si desea tener una copia del archivo (evidencia) cuando se produzca el acceso de escritura, establezca **las opciones** adecuadas en la regla de directiva de acceso de almacenamiento extraíble en el archivo XML y, a continuación, especifique la ubicación donde el sistema puede guardar la copia.

    - Vaya a **Configuración** >  del equipo **Plantillas** >  administrativas **Componentes** >  de Windows Microsoft Defender **Control** >  de dispositivos **antivirus** > **Definir ubicación remota de datos de prueba de Control de dispositivos**.

    - En el panel **Definir ubicación remota de datos de evidencia de Control** de dispositivos, seleccione **Habilitado** y, a continuación, especifique la ruta de acceso de la carpeta del recurso compartido de red o local.

      :::image type="content" source="images/evidence-data-remote-location-gp.png" alt-text="Captura de pantalla de Definición de la ubicación remota de datos de evidencia de Device Control." lightbox="images/evidence-data-remote-location-gp.png":::

## <a name="scenarios"></a>Escenarios

Estos son algunos escenarios comunes que le ayudarán a familiarizarse con Microsoft Defender para punto de conexión Access Control de almacenamiento extraíble. Tenga en cuenta que, en los ejemplos siguientes, no se ha usado "Aplicación predeterminada" porque el "Cumplimiento predeterminado" se aplicará tanto al almacenamiento extraíble como a la impresora.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Escenario 1: Impedir el acceso de escritura y ejecución a todos, pero permitir USB aprobados específicos

En este escenario, debe crear dos grupos: uno para cualquier almacenamiento extraíble y otro para los USB aprobados. También debe crear dos directivas: una directiva para denegar el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble y la otra para auditar el grupo de USB aprobado.

1. Crear grupos

    1. Grupo 1: cualquier almacenamiento extraíble, CD/DVD y dispositivos portátiles Windows.

    ![Captura de pantalla del almacenamiento extraíble](https://user-images.githubusercontent.com/81826151/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png)

    2. Grupo 2: USB aprobados en función de las propiedades del dispositivo.

    ![Captura de pantalla de los USB aprobados](https://user-images.githubusercontent.com/81826151/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png)
    
    Combine estos dos grupos en [un archivo XML](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml). Consulte el paso 3 de la sección [Implementar mediante](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) directiva de grupo para implementar esta configuración.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble, pero permitir USB aprobados.

    ![Captura de pantalla del acceso de escritura en bloque y ejecución](https://user-images.githubusercontent.com/81826151/188237490-d736ace1-4912-4788-9e94-3fc506692a41.png)


    2. Directiva 2: Auditar el acceso de escritura y ejecución para los USB permitidos.

    ![Captura de pantalla del acceso de escritura y ejecución de auditoría](https://user-images.githubusercontent.com/81826151/188237598-b28dd534-9ea4-4cdd-832b-afff50f9897b.png)

    ¿Qué significa "54" en la directiva? Es 18 + 36 = 54:

    - Acceso de escritura: nivel de disco 2 + nivel de sistema de archivos 16 = 18.
    - Ejecutar: nivel de disco 4 + nivel de sistema de archivos 32 = 36.

    Combine estas dos reglas de directiva en [un archivo XML](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Scenario%201%20GPO%20Policy%20-%20Prevent%20Write%20and%20Execute%20access%20to%20all%20but%20allow%20specific%20approved%20USBs.xml). Consulte el paso 4 de la sección [Implementar mediante](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) directiva de grupo para implementar esta configuración.

### <a name="scenario-2-audit-write-and-execute-access-for-all-but-block-specific-blocked-usbs"></a>Escenario 2: Auditoría de escritura y ejecución de acceso para todos los USB bloqueados específicos, pero bloqueados

En este escenario, debe crear dos grupos: un grupo para cualquier almacenamiento extraíble y otro para los USB bloqueados. También debe crear dos directivas: una directiva para auditar el acceso de escritura y ejecución para cualquier grupo de almacenamiento extraíble y la otra para denegar el grupo de USB bloqueados.

1. Crear grupos

    1. Grupo 1: cualquier almacenamiento extraíble, CD/DVD y dispositivos portátiles windows.

    ![Captura de pantalla del almacenamiento extraíble en grupos](https://user-images.githubusercontent.com/81826151/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png)

    2. Grupo 2: USB bloqueados en función de las propiedades del dispositivo.

    ![Captura de pantalla de los USB bloqueados](https://user-images.githubusercontent.com/81826151/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png)
    
    Combine estos dos grupos en [un archivo XML](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml). Consulte el paso 3 de la sección [Implementar mediante](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) directiva de grupo para implementar esta configuración.

    > [!TIP]
    > Reemplace por `&` `&amp;` en el valor .

2. Creación de la directiva

    1. Directiva 1: Bloquear el acceso de escritura y ejecución para todos los USB no aprobados específicos, pero bloquearlos.

    ![Captura de pantalla de los USB no aprobados específicos](https://user-images.githubusercontent.com/81826151/188239025-218a1985-b198-4f7e-b323-b4b6fb7e274e.png)

    2. Directiva 2: Auditar el acceso de escritura y ejecución para otros usuarios. 

    ![Captura de pantalla del acceso de escritura y ejecución de auditoría en la directiva de grupo](https://user-images.githubusercontent.com/81826151/188239144-3e6a2781-6927-487a-aa01-498a0904ad98.png)

    ¿Qué significa "54" en la directiva? Es 18 + 36 = 54:

    - Acceso de escritura: nivel de disco 2 + nivel de sistema de archivos 16 = 18.
    - Ejecutar: nivel de disco 4 + nivel de sistema de archivos 32 = 36.

    Combine estas dos reglas de directiva en [un archivo XML](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Scenario%202%20GPO%20Policy%20-%20Audit%20Write%20and%20Execute%20access%20to%20all%20but%20block%20specific%20unapproved%20USBs.xml). Consulte el paso 4 de la sección [Implementar mediante](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) directiva de grupo para implementar esta configuración.

