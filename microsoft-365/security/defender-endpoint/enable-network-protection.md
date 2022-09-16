---
title: Habilitar protección de red
description: Habilite la protección de red con directiva de grupo, PowerShell o Mobile Administración de dispositivos y Configuration Manager.
keywords: Protección de red, vulnerabilidades de seguridad, sitio web malintencionado, ip, dominio, dominios, habilitar, activar
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.subservice: mde
ms.collection: m365-security-compliance
search.appverid: met150
ms.openlocfilehash: 0523ba3cd0e9d32cd58675ead39fdabc1718b5c0
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67742967"
---
# <a name="turn-on-network-protection"></a>Habilitar protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**

- Windows
- Linux \(Consulte [Protección de red para Linux](network-protection-linux.md)\)
- macOS \(Consulte [Protección de red para macOS](network-protection-macos.md)\)

> [!TIP]
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[La protección de red](network-protection.md) ayuda a evitar que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de suplantación de identidad (phishing), vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Puede [auditar la protección de red](evaluate-network-protection.md) en un entorno de prueba para ver qué aplicaciones se bloquearían antes de habilitar la protección de red.

[Obtenga más información sobre las opciones de configuración de filtrado de red.](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Comprobación de si la protección de red está habilitada

Compruebe si se ha habilitado la protección de red en un dispositivo local mediante el editor del Registro.

1. Seleccione el botón **Inicio** en la barra de tareas y escriba **regedit** para abrir el editor del Registro.

2. Elija **HKEY_LOCAL_MACHINE** en el menú lateral.

3. Navegue por los menús anidados a **Directivas** \> **de SOFTWARE** \> **de Microsoft** \> **Windows Defender** \> **Windows Defender Protección de red de Protección contra vulnerabilidades** \> de **seguridad**.

Si falta la clave, vaya a **SOFTWARE** \> **Microsoft** \> **Windows Defender** \> **Windows Defender Protección de red de Protección contra vulnerabilidades** \> de **seguridad**.

4. Seleccione **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo:

   - 0 o **desactivado**
   - 1, o **activado**
   - 2, o modo **auditoría**

    :::image type="content" source="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png" alt-text="Clave del Registro de Protección de red" lightbox="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png":::

## <a name="enable-network-protection"></a>Habilitación de la protección de red

Habilite la protección de red mediante cualquiera de estos métodos:

- [PowerShell](#powershell)
- [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Manager](#microsoft-endpoint-manager)
- [Directiva de grupo](#group-policy)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)

### <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Opcional: habilite la característica en modo de auditoría mediante el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Use `Disabled` en lugar de `AuditMode` o `Enabled` para desactivar la característica.

### <a name="mobile-device-management-mdm"></a>Administración de dispositivos móviles (MDM)

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) (CSP) para habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.

[Actualice la plataforma antimalware de Microsoft Defender a la versión más reciente](https://support.microsoft.com/topic/update-for-microsoft-defender-antimalware-platform-92e21611-8cf1-8e0e-56d6-561a07d144cc) antes de habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.

### <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

#### <a name="microsoft-defender-for-endpoint-baseline-method"></a>Microsoft Defender para punto de conexión método baseline

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).
2. Vaya a Líneas **base** >  de **seguridad** >  de punto de conexión **Microsoft Defender para punto de conexión línea base**.
3. Seleccione **Crear un perfil**, proporcione un nombre para el perfil y, a continuación, seleccione **Siguiente**.
4. En la sección **Configuración** , vaya a **Reglas de reducción de superficie expuesta a ataques** > establezca **Bloquear**, **Habilitar** o **Auditar** para **habilitar la protección de red**. Seleccione **Siguiente**.
5. Seleccione las **etiquetas y asignaciones** de **ámbito** adecuadas según sea necesario para su organización.
7. Revise toda la información y, a continuación, seleccione **Crear**.

#### <a name="antivirus-policy-method"></a>Método de directiva antivirus
1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).
2. Vaya a **Antivirus** de seguridad  > **de puntos de conexión**.
3. Seleccione **Crear una directiva.**
4. En el control flotante **Crear una directiva**, elija **Windows 10, Windows 11 y Windows Server** en la lista **Plataforma**.
5. Elija **Antivirus de Microsoft Defender** en la lista **Perfil** y, a continuación, elija **Crear.**
6. Proporcione un nombre para el perfil y, a continuación, seleccione **Siguiente**.
7. En la sección **Configuración** , seleccione **Deshabilitado**, **Habilitado (modo de bloque)** o **Habilitado (modo de auditoría)** para **Habilitar protección de red** y, a continuación, seleccione **Siguiente**.
8. Seleccione las **etiquetas Asignaciones** y **Ámbito** adecuadas según sea necesario para su organización.
9. Revise toda la información y, a continuación, seleccione **Crear**.

#### <a name="configuration-profile-method"></a>Método de perfil de configuración

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2. Vaya a **Dispositivos** > **Perfiles de configuración** > **Crear perfil**.

3. En el control flotante **Crear un perfil** , seleccione **Plataforma** y elija **Tipo de perfil** como **plantillas**.

4. En El **nombre de la plantilla**, elija **Endpoint Protection** en la lista de plantillas y, a continuación, seleccione **Crear**.

4. Vaya a **Aspectos básicos** **de Endpoint protection** > , proporcione un nombre para el perfil y, a continuación, seleccione **Siguiente**.

5. En la sección **Configuración**, vaya a **Protección contra vulnerabilidades** >  de seguridad de Microsoft Defender **Network filtrando** > **Protección** >  de red **Habilitar** o **Auditar**. Seleccione **Siguiente**.

6. Seleccione las **etiquetas de ámbito**, **las asignaciones** y **las reglas de aplicabilidad** adecuadas según sea necesario para su organización. Los administradores pueden establecer más requisitos.

7. Revise toda la información y, a continuación, seleccione **Crear**.

### <a name="group-policy"></a>Directiva de grupo

Use el procedimiento siguiente para habilitar la protección de red en equipos unidos a un dominio o en un equipo independiente.

1. En un equipo independiente, vaya a **Inicio** y escriba y seleccione **Editar directiva de grupo**.

    *-O bien-*

    En un equipo de administración de directiva de grupo unido a un dominio, abra la [consola de administración de directiva de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** \> de **Windows Antivirus** \> de Microsoft Defender **Windows Defender Protección de red de Protección contra vulnerabilidades** \> de **seguridad**.

   > [!NOTE]
   > En versiones anteriores de Windows, la ruta de acceso de la directiva de grupo puede decir "Antivirus de Windows Defender" en lugar de "Antivirus de Microsoft Defender".

4. Haga doble clic en la configuración **Impedir que usuarios y aplicaciones accedan a sitios web peligrosos** y establezca la opción **en Habilitado**. En la sección de opciones, debe especificar una de las siguientes opciones:
    - **Bloquear** : los usuarios no pueden acceder a direcciones IP y dominios malintencionados.
    - **Deshabilitar (valor predeterminado):** la característica Protección de red no funcionará. No se bloqueará el acceso a dominios malintencionados a los usuarios.
    - **Modo de auditoría** : si un usuario visita una dirección IP o dominio malintencionados, se registrará un evento en el registro de eventos de Windows. Sin embargo, no se impedirá que el usuario visite la dirección.

   > [!IMPORTANT]
   > Para habilitar completamente la protección de red, debe establecer la opción directiva de grupo **en Habilitado** y también seleccionar **Bloquear** en el menú desplegable de opciones.

   > [!NOTE]
   > Opcional: siga los pasos descritos en [Comprobación de si la protección de red está habilitada](#check-if-network-protection-is-enabled) para comprobar que la configuración de directiva de grupo es correcta.

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Abre la consola de Configuration Manager.

2. Vaya a **Assets and Compliance** > **Endpoint Protection** >  **Windows Defender Exploit Guard**.

3. Seleccione **Crear directiva de Protección contra vulnerabilidades** en la cinta de opciones para crear una nueva directiva.
   - Para editar una directiva existente, seleccione la directiva y, a continuación, seleccione **Propiedades** en la cinta de opciones o en el menú contextual. Edite la opción **Configurar protección de red** en la pestaña **Protección de red** .  

4. En la página **General** , especifique un nombre para la nueva directiva y compruebe que la opción **Protección** de red está habilitada.

5. En la página **Protección** de red, seleccione una de las opciones siguientes para la opción **Configurar protección de red** :
   - **Bloquear**
   - **Auditoría**
   - **Disabled**

6. Complete el resto de los pasos y guarde la directiva.

7. En la cinta de opciones, seleccione **Implementar** para implementar la directiva en una colección.

> [!IMPORTANT]
> Una vez que implemente una directiva de Protección contra vulnerabilidades de seguridad de Configuration Manager, la configuración de Protección contra vulnerabilidades de seguridad no se quitará de los clientes si quita la implementación. `Delete not supported`se registra en el archivo ExploitGuardHandler.log del cliente de Configuration Manager si quita la implementación de Exploit Guard del cliente. <!--CMADO8538577-->
> El siguiente script de PowerShell se puede ejecutar en el contexto SYSTEM para quitar esta configuración:<!--CMADO9907132-->
>
> ```powershell
> $defenderObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_Defender02" -Filter "InstanceID='Defender' and ParentID='./Vendor/MSFT/Policy/Config'"
> $defenderObject.AttackSurfaceReductionRules = $null
> $defenderObject.AttackSurfaceReductionOnlyExclusions = $null
> $defenderObject.EnableControlledFolderAccess = $null
> $defenderObject.ControlledFolderAccessAllowedApplications = $null
> $defenderObject.ControlledFolderAccessProtectedFolders = $null
> $defenderObject.EnableNetworkProtection = $null
> $defenderObject.Put()
>
> $exploitGuardObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_ExploitGuard02" -Filter "InstanceID='ExploitGuard' and ParentID='./Vendor/MSFT/Policy/Config'"
> $exploitGuardObject.ExploitProtectionSettings = $null
> $exploitGuardObject.Put()
>```  

## <a name="see-also"></a>Vea también

- [Protección de red](network-protection.md)

- [Protección de red para Linux](network-protection-linux.md)

- [Protección de red para macOS](network-protection-macos.md)

- [Protección de red y protocolo de enlace de tres vías TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [Evaluar protección de red](evaluate-network-protection.md)

- [Solución de problemas de protección de red](troubleshoot-np.md)
