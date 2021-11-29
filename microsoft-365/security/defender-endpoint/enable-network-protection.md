---
title: Habilitar protección de red
description: Habilite la protección de red con la directiva de grupo, PowerShell o Mobile Device Management y Configuration Manager.
keywords: Protección de ANetwork, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, habilitar, activar
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 465a510ef25b0be0ba406c1265096476959d8c19
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218027"
---
# <a name="turn-on-network-protection"></a>Habilitar protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Puedes [auditar la protección de red](evaluate-network-protection.md) en un entorno de prueba para ver qué aplicaciones se bloquearían antes de habilitarla.

[Obtenga más información sobre las opciones de configuración de filtrado de red.](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Comprobar si la protección de red está habilitada

Compruebe si la protección de red se ha habilitado en un dispositivo local mediante el editor del Registro.

1. Seleccione el **botón Inicio** en la barra de tareas y escriba **regedit** para abrir el editor del Registro.

2. Elija **HKEY_LOCAL_MACHINE** en el menú lateral.

3. Navegue a través de los menús anidados a **Directivas** de SOFTWARE Microsoft Windows Defender Windows Defender Protección de red \>  \>  \>  \> **de Protección** \> **contra vulnerabilidades de seguridad**.

Si falta la clave, vaya a **SOFTWARE** Microsoft Windows Defender Windows Defender Protección de red \>  \>  \> **de Protección** \> **contra vulnerabilidades de seguridad**.

4. Seleccione **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo:

   - 0 o **Desactivado**
   - 1 o **On**
   - 2, o modo **auditoría**

    :::image type="content" alt-text="Clave del Registro de Protección de red." source="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png" lightbox="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png":::

## <a name="enable-network-protection"></a>Habilitar la protección de red

Habilite la protección de red mediante cualquiera de estos métodos:

- [PowerShell](#powershell)
- [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Manager](#microsoft-endpoint-manager)
- [Directiva de grupo](#group-policy)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)

### <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el botón secundario **en Windows PowerShell** y seleccione Ejecutar como **administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Opcional: habilite la característica en modo auditoría con el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Use `Disabled` en lugar de o para desactivar la `AuditMode` `Enabled` característica.

### <a name="mobile-device-management-mdm"></a>Administración de dispositivos móviles (MDM)

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) para habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.

### <a name="microsoft-endpoint-manager"></a>Microsoft Endpoint Manager

1. Inicie sesión en el Microsoft Endpoint Manager de administración ( https://endpoint.microsoft.com) .

2. Vaya a  >  **Perfiles de configuración de dispositivos**  >  **Crear perfil**.

3. En el **control desplegable Crear un perfil,** seleccione **Plataforma** y elija el Tipo **de perfil** como **Plantillas**.

4. En el **nombre de plantilla**, elija Protección de **extremo** de la lista de plantillas y, a continuación, **seleccione Crear**.

4. Vaya a **Endpoint protection**  >  **Basics**, proporcione un nombre para su perfil y, a continuación, seleccione **Siguiente**.

5. En la **sección Configuración,** vaya a **Protección contra vulnerabilidades de seguridad de Microsoft Defender**  >  **Network filtering**  >  **Network protection**  >  **Enable** or **Audit**. Seleccione **Siguiente**.

6. Seleccione las etiquetas **de ámbito,** **las asignaciones** y las reglas de **aplicabilidad** adecuadas según lo requiera la organización. Los administradores pueden establecer más requisitos.

7. Revise toda la información y, a continuación, **seleccione Crear**.

### <a name="group-policy"></a>Directiva de grupo

Use el siguiente procedimiento para habilitar la protección de red en equipos unidos a un dominio o en un equipo independiente.

1. En un equipo independiente, vaya a **Inicio** y, a continuación, escriba y seleccione **Editar directiva de grupo**.

    *-Or-*

    En un equipo de administración de directivas de grupo unido a un dominio, abra la Consola de administración de directivas de grupo [,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** Windows Defender protección de la red \>  \> **de Protección** \> **contra vulnerabilidades de seguridad**.

   > [!NOTE]
   > En versiones anteriores de Windows, la ruta de acceso de directiva de grupo puede decir "Antivirus de Windows Defender" en lugar de "Antivirus de Microsoft Defender".

4. Haz doble clic en la configuración **Impedir que los usuarios y aplicaciones** tengan acceso a sitios web peligrosos y establece la opción en **Habilitado**. En la sección opciones, debe especificar una de las siguientes opciones:
    - **Bloquear:** los usuarios no pueden acceder a direcciones IP malintencionadas y dominios.
    - **Deshabilitar (predeterminado):** la característica de protección de red no funcionará. No se bloqueará el acceso a dominios malintencionados a los usuarios.
    - **Modo auditoría:** si un usuario visita una dirección IP malintencionada o un dominio, se registrará un evento en el Windows de eventos. Sin embargo, no se bloqueará al usuario para que visite la dirección.

   > [!IMPORTANT]
   > Para habilitar completamente la protección de red, debe establecer la opción Directiva de grupo en **Habilitado** y también seleccionar **Bloquear** en el menú desplegable opciones.

Confirme que la protección de red está habilitada en un equipo local mediante el editor del Registro:

1. Seleccione **Inicio** y escriba **regedit** para abrir **el Editor del Registro**.

2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. Seleccione **EnableNetworkProtection** y confirme el valor:
   - 0=Off
   - 1=On
   - 2=Auditoría

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Abre la consola de Configuration Manager.

2. Vaya a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**. 

3. Seleccione **Crear directiva de protección contra vulnerabilidades** de seguridad en la cinta de opciones para crear una nueva directiva.
   - Para editar una directiva existente, seleccione la directiva y, a continuación, seleccione **Propiedades** en la cinta de opciones o en el menú contextual. Edite la **opción Configurar protección de** red en la pestaña Protección **de** red.  

4. En la **página General,** especifique un nombre para la nueva directiva y compruebe que la **opción Protección de** red está habilitada. 

5. En la **página Protección de** red, seleccione una de las opciones siguientes para la opción Configurar protección **de** red:
   - **Bloquear**
   - **Auditoría**
   - **Disabled**
   
6. Complete el resto de los pasos y guarde la directiva. 

7. En la cinta de opciones, seleccione **Implementar** para implementar la directiva en una colección.

> [!IMPORTANT]
> Una vez que implemente una directiva de Protección contra vulnerabilidades de seguridad desde Configuration Manager, la configuración de Protección contra vulnerabilidades de seguridad no se quitará de los clientes si quita la implementación. `Delete not supported` se registra en el exploitguardhandler.log del cliente de Configuration Manager si se quita la implementación de Exploit Guard del cliente. <!--CMADO8538577-->
> El siguiente script de PowerShell se puede ejecutar en contexto system para quitar esta configuración:<!--CMADO9907132-->
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

## <a name="see-also"></a>Consulte también

- [Protección de red](network-protection.md)

- [Protección de red y el protocolo de enlace triple TCP](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [Evaluar protección de red](evaluate-network-protection.md)

- [Solucionar problemas de protección de red](troubleshoot-np.md)
