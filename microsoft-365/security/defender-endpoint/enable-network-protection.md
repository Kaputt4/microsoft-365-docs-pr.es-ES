---
title: Habilitar protección de red
description: Habilite la protección de red con la directiva de grupo, PowerShell o Mobile Device Management y Configuration Manager.
keywords: Protección de ANetwork, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, habilitar, activar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6afdcc16493839e83771ac831831fdbb121663a1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841779"
---
# <a name="turn-on-network-protection"></a>Habilitar protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Puedes [auditar la protección de red](evaluate-network-protection.md) en un entorno de prueba para ver qué aplicaciones se bloquearían antes de habilitarla.

[Más información sobre las opciones de configuración de filtrado de red](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Comprobar si la protección de red está habilitada

Compruebe si la protección de red se ha habilitado en un dispositivo local mediante el editor del Registro.

1. Seleccione el **botón Inicio** en la barra de tareas y escriba **regedit** para abrir el editor del Registro

2. Elija **HKEY_LOCAL_MACHINE** en el menú lateral

3. Navegue por los menús anidados hasta **Directivas**  >  **de**  >  **SOFTWARE Microsoft**  >  **Windows Defender**  >  **Policy Manager** 

4. Selecciona **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo

    * 0 o **Desactivado**
    * 1 o **On**
    * 2, o modo **auditoría**
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Habilitar la protección de red

Habilite la protección de red mediante cualquiera de estos métodos:

* [PowerShell](#powershell)
* [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Directiva de grupo](#group-policy)

### <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el botón Windows PowerShell **y** seleccione Ejecutar como **administrador**
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

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) para habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (anteriormente Intune)

1. Inicie sesión en el centro Microsoft Endpoint Manager de administración (https://endpoint.microsoft.com)

2. Crear o editar un perfil de [configuración de endpoint protection](/mem/intune/protect/endpoint-protection-configure)

3. En **Configuración Configuración** en el flujo de perfiles, vaya a Protección contra vulnerabilidades de seguridad de Microsoft Defender  >  **Network filtering** Network  >  **protection**  >  **Enable** or **Audit only**

### <a name="group-policy"></a>Directiva de grupo

Use el siguiente procedimiento para habilitar la protección de red en equipos unidos a un dominio o en un equipo independiente.

1. En un equipo independiente, vaya a **Inicio** y, a continuación, escriba y seleccione **Editar directiva de grupo**.

    *-Or-*

    En un equipo de administración de directivas de grupo unido a un dominio, abra la Consola de administración de directivas de grupo [,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** Windows Defender protección de la red  >    >  **de Protección**  >  **contra vulnerabilidades de seguridad**.

> [!NOTE]
> En versiones anteriores de Windows, la ruta de acceso de directiva de grupo puede decir "Antivirus de Windows Defender" en lugar de "Antivirus de Microsoft Defender".

4. Haz doble clic en la configuración **Impedir que los usuarios y aplicaciones** tengan acceso a sitios web peligrosos y establece la opción en **Habilitado**. En la sección opciones, debe especificar una de las siguientes opciones:
    * **Bloquear:** los usuarios no pueden acceder a direcciones IP malintencionadas y dominios
    * **Deshabilitar (predeterminado):** la característica de protección de red no funcionará. Los usuarios no se bloquearán para acceder a dominios malintencionados
    * **Modo auditoría:** si un usuario visita una dirección IP malintencionada o un dominio, se registrará un evento en el Windows de eventos. Sin embargo, no se bloqueará al usuario para que visite la dirección.

> [!IMPORTANT]
> Para habilitar completamente la protección de red, debe establecer la opción Directiva de grupo en **Habilitado** y también seleccionar **Bloquear** en el menú desplegable opciones.

Confirme que la protección de red está habilitada en un equipo local mediante el editor del Registro:

1. Seleccione **Inicio** y escriba **regedit** para abrir **el Editor del Registro**.

2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**

3. Seleccione **EnableNetworkProtection** y confirme el valor:
   * 0=Off
   * 1=On
   * 2=Auditoría

## <a name="see-also"></a>Consulte también

* [Protección de red](network-protection.md)
* [Evaluar protección de red](evaluate-network-protection.md)
* [Solucionar problemas de protección de red](troubleshoot-np.md)
