---
title: Activar la protección de red
description: Habilite la protección de red con la directiva de grupo, PowerShell o Mobile Device Management y Configuration Manager.
keywords: Protección de ANetwork, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, habilitar, activar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 84a0e94b653eb426fab14d9c55ba8d29df388fe5
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164779"
---
# <a name="turn-on-network-protection"></a>Activar la protección de red

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Puedes [auditar la protección de red](evaluate-network-protection.md) en un entorno de prueba para ver qué aplicaciones se bloquearían antes de habilitarla.

[Más información sobre las opciones de configuración de filtrado de red](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Comprobar si la protección de red está habilitada

Compruebe si la protección de red se ha habilitado en un dispositivo local mediante el editor del Registro.

1. Seleccione el **botón Inicio** en la barra de tareas y escriba **regedit** para abrir el editor del Registro
1. Elija **HKEY_LOCAL_MACHINE** en el menú lateral
1. Navegue por los menús anidados a **Directivas de SOFTWARE** de  >    >  **Microsoft**  >  **Windows Defender** Windows Defender Protección  >  **de red de Protección contra**  >  **vulnerabilidades de seguridad**
1. Selecciona **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo

    * 0 o **Desactivado**
    * 1 o **On**
    * 2, o modo **auditoría**
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Habilitar la protección de red

Habilite la protección de red mediante cualquiera de estos métodos:

* [PowerShell](#powershell)
* [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager /Intune](#microsoft-endpoint-manager-formerly-intune)
* [Directiva de grupo](#group-policy)

### <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el Windows PowerShell **y** seleccione Ejecutar como **administrador**
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

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) para habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (anteriormente Intune)

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com)

2. Crear o editar un perfil de [configuración de endpoint protection](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)

3. En "Configuración de configuración" en el flujo de perfiles, vaya a Protección de red de Protección contra vulnerabilidades de seguridad de **Microsoft Defender** Habilitar o  >    >    >   **auditar solo**

### <a name="group-policy"></a>Directiva de grupo

Use el siguiente procedimiento para habilitar la protección de red en equipos unidos a un dominio o en un equipo independiente.

1. En un equipo independiente, vaya a **Inicio** y, a continuación, escriba y seleccione **Editar directiva de grupo**.

    *-Or-*

    En un equipo de administración de directivas de grupo unido a un dominio, abra la Consola de administración de directivas de grupo [,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** protección de la red de  >  **Protección** contra  >  **vulnerabilidades de seguridad**.

> [!NOTE]
> En versiones anteriores de Windows, la ruta de acceso de directiva de grupo puede decir "Windows Defender Antivirus" en lugar de "Antivirus de Microsoft Defender".

4. Haz doble clic en la configuración **Impedir que los usuarios y aplicaciones** tengan acceso a sitios web peligrosos y establece la opción en **Habilitado**. En la sección opciones, debe especificar una de las siguientes opciones:
    * **Bloquear:** los usuarios no pueden acceder a direcciones IP malintencionadas y dominios
    * **Deshabilitar (predeterminado):** la característica de protección de red no funcionará. Los usuarios no se bloquearán para acceder a dominios malintencionados
    * **Modo auditoría:** si un usuario visita una dirección IP malintencionada o un dominio, se registrará un evento en el registro de eventos de Windows. Sin embargo, no se bloqueará al usuario para que visite la dirección.

> [!IMPORTANT]
> Para habilitar completamente la protección de red, debe establecer la opción Directiva de grupo en **Habilitado** y también seleccionar **Bloquear** en el menú desplegable opciones.

Confirme que la protección de red está habilitada en un equipo local mediante el editor del Registro:

1. Seleccione **Inicio** y escriba **regedit** para abrir **el Editor del Registro**.

2. Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**

3. Seleccione **EnableNetworkProtection** y confirme el valor:
   * 0=Off
   * 1=On
   * 2=Auditoría

## <a name="see-also"></a>Ver también

* [Protección de red](network-protection.md)
* [Evaluar la protección de red](evaluate-network-protection.md)
* [Solucionar problemas de protección de red](troubleshoot-np.md)
