---
title: Personalizar el acceso controlado a carpetas
description: Agregue otras carpetas que deben estar protegidas por el acceso controlado a carpetas o permitir aplicaciones que bloqueen incorrectamente los cambios en archivos importantes.
keywords: Acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders, customize, add folder, add app, allow, add executable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199924"
---
# <a name="customize-controlled-folder-access"></a>Personalizar el acceso controlado a carpetas

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


El acceso controlado a carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware. El acceso controlado a carpetas es compatible con clientes de Windows Server 2019 y Windows 10.

En este artículo se describe cómo personalizar las capacidades de acceso controlado a carpetas e incluye las siguientes secciones:

- [Proteger carpetas adicionales](#protect-additional-folders)
- [Agregar aplicaciones que deben tener acceso a carpetas protegidas](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Permitir que los archivos ejecutables firmados accedan a carpetas protegidas](#allow-signed-executable-files-to-access-protected-folders)
- [Personalizar la notificación](#customize-the-notification)

> [!IMPORTANT]
> El acceso controlado a carpetas supervisa las aplicaciones para las actividades que se detectan como malintencionadas. A veces, las aplicaciones legítimas no pueden realizar cambios en los archivos. Si el acceso controlado a carpetas afecta a la productividad de la organización, es posible que considere la posibilidad de ejecutar esta característica en modo [auditoría](audit-windows-defender.md) para evaluar completamente el impacto.

## <a name="protect-additional-folders"></a>Proteger carpetas adicionales

El acceso controlado a carpetas se aplica a muchas carpetas del sistema y ubicaciones predeterminadas, incluidas carpetas como **Documentos,** **Imágenes** y **Películas.** Puede agregar carpetas adicionales para protegerse, pero no puede quitar las carpetas predeterminadas de la lista predeterminada.

Agregar otras carpetas al acceso controlado a carpetas puede ser útil para los casos en que no almacenas archivos en las bibliotecas predeterminadas de Windows o si has cambiado la ubicación predeterminada de tus bibliotecas.

También puede especificar recursos compartidos de red y unidades asignadas. Se admiten variables de entorno y caracteres comodín. Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Puede usar la aplicación seguridad de Windows, la directiva de grupo, los cmdlets de PowerShell o los proveedores de servicios de configuración de administración de dispositivos móviles para agregar y quitar carpetas protegidas adicionales.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Usar la aplicación Seguridad de Windows para proteger carpetas adicionales

1. Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando en el menú inicio **seguridad**.

2. Seleccione **Protección contra & virus y,** a continuación, desplácese hacia abajo hasta la sección Protección **contra** ransomware.

3. Seleccione **Administrar protección contra ransomware** para abrir el panel Protección **contra** ransomware.

4. En la **sección Acceso controlado a** carpetas, seleccione **Carpetas protegidas.**

5. Elija **Sí en** el símbolo del sistema de control **de** acceso de usuario. Se **muestra el panel Carpetas** protegidas.

4. Seleccione **Agregar una carpeta protegida** y siga las instrucciones para agregar carpetas.

### <a name="use-group-policy-to-protect-additional-folders"></a>Usar la directiva de grupo para proteger carpetas adicionales

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** acceso controlado a  >  carpetas de **Protección**  >  **contra vulnerabilidades de seguridad.**

4. Haga doble clic **en Carpetas protegidas configuradas** y establezca la opción en **Habilitado**. Seleccione **Mostrar** y escriba cada carpeta.

### <a name="use-powershell-to-protect-additional-folders"></a>Usar PowerShell para proteger carpetas adicionales

1. Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Repita el paso 2 hasta que haya agregado todas las carpetas que desea proteger. Las carpetas que se agregan están visibles en la aplicación Seguridad de Windows.

   ![Captura de pantalla de una ventana de PowerShell con el cmdlet anterior especificado](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Usar CSP mdm para proteger carpetas adicionales

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Permitir que aplicaciones específicas realicen cambios en carpetas controladas

Puedes especificar si determinadas aplicaciones siempre se consideran seguras y dar acceso de escritura a archivos en carpetas protegidas. Permitir aplicaciones puede ser útil si la característica de acceso controlado a carpetas bloquea una aplicación determinada que conoces y en la que confías.

> [!IMPORTANT]
> De forma predeterminada, Windows agrega aplicaciones que se consideran fáciles de usar en la lista permitida. Estas aplicaciones que se agregan automáticamente no se registran en la lista que se muestra en la aplicación seguridad de Windows o mediante los cmdlets de PowerShell asociados. No debes agregar la mayoría de las aplicaciones. Solo agrega aplicaciones si se bloquean y puedes comprobar su fiabilidad.

Cuando agregas una aplicación, debes especificar la ubicación de la aplicación. Solo se permitirá el acceso de la aplicación en esa ubicación a las carpetas protegidas. Si la aplicación (con el mismo nombre) está en una ubicación diferente, no se agregará a la lista de permitidos y puede bloquearse mediante acceso controlado a carpetas.

Una aplicación o servicio permitido solo tiene acceso de escritura a una carpeta controlada después de que se inicie. Por ejemplo, un servicio de actualización seguirá desencadenando eventos después de permitirlo hasta que se detenga y reinicie.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Usar la aplicación Windows Defender seguridad para permitir aplicaciones específicas

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio **seguridad**.

2. Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Administrar protección contra **ransomware**.

3. En la **sección Acceso controlado a carpetas,** selecciona Permitir una aplicación a través de Acceso controlado a **carpetas**

4. Selecciona **Agregar una aplicación permitida** y sigue las indicaciones para agregar aplicaciones.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Agregar un botón de aplicación permitido":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Usar la directiva de grupo para permitir aplicaciones específicas

1. En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** acceso controlado a  >  carpetas de **Protección**  >  **contra vulnerabilidades de seguridad.**

4. Haga doble clic en **la configuración Configurar aplicaciones permitidas** y establezca la opción en **Habilitado**. Selecciona **Mostrar** y escribe cada aplicación.

### <a name="use-powershell-to-allow-specific-apps"></a>Usar PowerShell para permitir aplicaciones específicas

1. Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Por ejemplo, para agregar el archivo *ejecutabletest.exe* en la carpeta *C:\apps,* el cmdlet sería el siguiente:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Sigue usando para `Add-MpPreference -ControlledFolderAccessAllowedApplications` agregar más aplicaciones a la lista. Las aplicaciones agregadas con este cmdlet aparecerán en la aplicación Seguridad de Windows.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet de PowerShell para permitir una aplicación":::

> [!IMPORTANT]
> Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Usar CSP mdm para permitir aplicaciones específicas

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Permitir que los archivos ejecutables firmados accedan a carpetas protegidas

Los indicadores de archivo y certificado de Microsoft Defender para endpoint pueden permitir que los archivos ejecutables firmados obtengan acceso a carpetas protegidas. Para obtener más información sobre la implementación, [vea Crear indicadores basados en certificados.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)

> [!Note]
> Esto no se aplica a los motores de scripting, incluido Powershell

## <a name="customize-the-notification"></a>Personalizar la notificación

Para obtener más información acerca de cómo personalizar la notificación cuando se desencadena una regla y bloquea una aplicación o archivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).

## <a name="see-also"></a>Vea también

- [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
- [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md)
- [Evaluar reglas de reducción de superficie de ataque](evaluate-attack-surface-reduction.md)
