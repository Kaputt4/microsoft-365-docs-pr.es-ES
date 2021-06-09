---
title: Habilitar el acceso controlado a carpetas
keywords: Acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders, enable, turn on, use
description: Obtenga información sobre cómo proteger los archivos importantes habilitando acceso controlado a carpetas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841983"
---
# <a name="enable-controlled-folder-access"></a>Habilitar el acceso controlado a carpetas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[El acceso controlado a](controlled-folders.md) carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware. El acceso controlado a carpetas se incluye Windows 10 y Windows Server 2019.

Puede habilitar el acceso controlado a carpetas mediante cualquiera de estos métodos:

* [Seguridad de Windows app](#windows-security-app)
* [Microsoft Intune](#intune)
* [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Directiva de grupo](#group-policy)
* [PowerShell](#powershell)

[El modo auditoría](evaluate-controlled-folder-access.md) te permite probar cómo funcionaría la característica (y revisar los eventos) sin afectar al uso normal del dispositivo.

La configuración de directiva de grupo que deshabilita la combinación de listas de administradores locales invalidará la configuración de acceso controlado a carpetas. También invalidan las carpetas protegidas y las aplicaciones permitidas establecidas por el administrador local a través del acceso controlado a carpetas. Estas directivas incluyen:

* Antivirus de Microsoft Defender configurar **el comportamiento de combinación de administradores locales para listas**
* System Center Endpoint Protection permitir **a los usuarios agregar exclusiones e invalidaciones**

Para obtener más información sobre cómo deshabilitar la combinación de listas locales, vea [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).

## <a name="windows-security-app"></a>Seguridad de Windows app

1. Abra la aplicación Seguridad de Windows mediante la selección del icono de escudo en la barra de tareas. También puede buscar en el menú inicio de **Defender**.

2. Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Protección contra **ransomware**.

3. Establezca el modificador para **Acceso controlado a carpetas** en **On**.

> [!NOTE]
> Si el acceso controlado a carpetas está configurado con directivas de grupo, PowerShell o CSP mdm, el estado cambiará en la aplicación Seguridad de Windows después de reiniciar el dispositivo.
> Si la característica está establecida en **modo auditoría** con cualquiera de estas herramientas, la Seguridad de Windows aplicación mostrará el estado como **Desactivado**.
> Si protege los datos de perfil de usuario, se recomienda que el perfil de usuario esté en la unidad de instalación Windows usuario predeterminada.

## <a name="intune"></a>Intune

1. Inicie sesión en [Azure Portal y](https://portal.azure.com) abra Intune.

2. Vaya a **Perfiles de configuración**  >  **de dispositivo Crear**  >  **perfil**.

3. Asigne un nombre al perfil, **elija Windows 10 y posterior y** Endpoint **protection**. <br/> ![Crear perfil de protección de puntos de conexión](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Vaya a **Configure Windows Defender**  >  **Exploit Guard** Controlled folder  >  **access**  >  **Enable**.

5. Escriba la ruta de acceso a cada aplicación que tenga acceso a carpetas protegidas y la ruta de acceso a cualquier carpeta adicional que necesite protección. Seleccione **Agregar**.<br/> ![Habilitar el acceso controlado a carpetas en Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard es compatible con aplicaciones, pero no para carpetas. Las subcarpetas no están protegidas. Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.

6. Seleccione **Aceptar** para guardar cada hoja abierta y **Crear**.

7. Seleccione el perfil **Asignaciones**, asignar a Todos los usuarios & Todos los **dispositivos** y **Guardar**.

## <a name="mobile-device-management-mdm"></a>Administración de dispositivos móviles (MDM)

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.

2. Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .

3. Escriba un nombre y una descripción, seleccione Acceso controlado a **carpetas** y seleccione **Siguiente**.

4. Elige si bloquea o audita los cambios, permite otras aplicaciones o agrega otras carpetas y selecciona **Siguiente**.
   > [!NOTE]
   > Wilcard es compatible con aplicaciones, pero no para carpetas. Las subcarpetas no están protegidas. Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.

5. Revise la configuración y seleccione **Siguiente** para crear la directiva.

6. Después de crear la directiva, **Cierre**.

## <a name="group-policy"></a>Directiva de grupo

1. En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > Windows Defender Exploit Guard > acceso controlado a carpetas**.

4. Haga doble clic en la **opción Configurar acceso controlado a carpetas** y establezca la opción en **Habilitado**. En la sección opciones, debe especificar una de las siguientes opciones:
    * **Habilitar:** las aplicaciones malintencionadas y sospechosas no podrán realizar cambios en los archivos de carpetas protegidas. Se proporciona una notificación en el registro Windows eventos.
    * **Deshabilitar (valor predeterminado):** la característica acceso controlado a carpetas no funcionará. Todas las aplicaciones pueden realizar cambios en los archivos de carpetas protegidas.
    * **Modo auditoría:** se permitirán cambios si una aplicación malintencionada o sospechosa intenta realizar un cambio en un archivo de una carpeta protegida. Sin embargo, se registrará en el registro Windows eventos donde puede evaluar el impacto en su organización.
    * **Bloquear solo modificación de disco:** los intentos de las aplicaciones que no son de confianza de escribir en los sectores de disco se iniciarán en Windows registro de eventos. Estos registros se pueden encontrar en **Registros** de aplicaciones y servicios > Microsoft > Windows > Windows Defender > Operational > ID. 1123.
    * **Solo modificación** de disco de auditoría: solo se registrarán los intentos de escritura en los sectores de disco protegido en el registro de eventos de Windows (en Registros de aplicaciones y servicios Microsoft Windows Windows Defender Identificador operativo  >    >    >    >    >  **1124**). No se registrarán los intentos de modificar o eliminar archivos en carpetas protegidas.

      ![Captura de pantalla de la opción de directiva de grupo Habilitada y modo auditoría seleccionada en la lista desplegable](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Para habilitar completamente el acceso controlado a carpetas, debe establecer la opción Directiva de grupo en **Habilitado** y seleccionar **Bloquear** en el menú desplegable opciones.

## <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el botón **Windows PowerShell** y seleccione Ejecutar **como administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Puede habilitar la característica en modo auditoría especificando en `AuditMode` lugar de `Enabled` .

Se `Disabled` usa para desactivar la característica.

## <a name="see-also"></a>Consulte también

* [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
* [Personalizar el acceso controlado a carpetas](customize-controlled-folders.md)
* [Microsoft Defender para punto de conexión](evaluate-mde.md)
