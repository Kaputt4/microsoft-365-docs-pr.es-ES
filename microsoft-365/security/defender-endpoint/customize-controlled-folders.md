---
title: Personalizar el acceso controlado a carpetas
description: Agregue otras carpetas que deben protegerse mediante acceso controlado a carpetas o permitir aplicaciones que bloqueen incorrectamente los cambios en archivos importantes.
keywords: Acceso controlado a carpetas, windows 10, windows 11, windows defender, ransomware, protect, files, folders, customize, add folder, add app, allow, add executable
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.subservice: mde
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 711696d8b5ca745d55dc8dc7cac9259e4fe22807
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67742616"
---
# <a name="customize-controlled-folder-access"></a>Personalizar el acceso controlado a carpetas

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> [!TIP]
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

El acceso controlado a carpetas le ayuda a proteger datos valiosos de aplicaciones y amenazas malintencionadas, como ransomware. El acceso controlado a carpetas se admite en clientes de Windows Server 2019, Windows Server 2022, Windows 10 y Windows 11. En este artículo se describe cómo personalizar las funcionalidades de acceso controlado a carpetas e se incluyen las secciones siguientes:

- [Protección de carpetas adicionales](#protect-additional-folders)
- [Agregar aplicaciones a las que se debe permitir el acceso a carpetas protegidas](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Permitir que los archivos ejecutables firmados accedan a carpetas protegidas](#allow-signed-executable-files-to-access-protected-folders)
- [Personalizar la notificación](#customize-the-notification)

> [!IMPORTANT]
> El acceso controlado a carpetas supervisa las aplicaciones en busca de actividades que se detectan como malintencionadas. A veces, las aplicaciones legítimas no pueden realizar cambios en los archivos. Si el acceso controlado a carpetas afecta a la productividad de la organización, podría considerar la posibilidad de ejecutar esta característica en [modo de auditoría](audit-windows-defender.md) para evaluar completamente el impacto.

## <a name="protect-additional-folders"></a>Protección de carpetas adicionales

El acceso controlado a carpetas se aplica a muchas carpetas del sistema y ubicaciones predeterminadas, incluidas carpetas como **Documentos**, **Imágenes** y **Películas**. Puede agregar otras carpetas para protegerlas, pero no puede quitar las carpetas predeterminadas de la lista predeterminada.

Agregar otras carpetas al acceso controlado a carpetas puede ser útil en los casos en los que no almacene archivos en las bibliotecas de Windows predeterminadas o haya cambiado la ubicación predeterminada de las bibliotecas.

También puede especificar recursos compartidos de red y unidades asignadas. Se admiten variables de entorno y caracteres comodín. Para obtener información sobre el uso de caracteres comodín, consulte [Uso de caracteres comodín en las listas de exclusión de extensiones o ruta de acceso de carpeta y nombre de archivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

Puede usar la aplicación de Seguridad de Windows, directiva de grupo, cmdlets de PowerShell o proveedores de servicios de configuración de administración de dispositivos móviles para agregar y quitar carpetas protegidas.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Uso de la aplicación Seguridad de Windows para proteger carpetas adicionales

1. Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando *seguridad* en el menú Inicio.

2. Seleccione **Virus & protección contra amenazas** y desplácese hacia abajo hasta la sección **Protección contra ransomware** .

3. Seleccione **Administrar protección contra ransomware** para abrir el panel **Protección contra ransomware** .

4. En la sección **Acceso controlado a carpetas** , seleccione **Carpetas protegidas**.

5. Elija **Sí** en el símbolo del **Access Control del usuario**. Se muestra **el panel Carpetas protegidas** .

6. Seleccione **Agregar una carpeta protegida** y siga las indicaciones para agregar carpetas.

### <a name="use-group-policy-to-protect-additional-folders"></a>Uso de directiva de grupo para proteger carpetas adicionales

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true). 

2. Haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.

3. En **el Editor de administración de directiva de grupo**, vaya a **Directivas** \> de **configuración** \> del equipo **Plantillas administrativas**.

4. Expanda el árbol a **componentes** \> de **Windows Antivirus** \> de Microsoft Defender Windows Defender **acceso a carpetas controladas** de **Protección contra vulnerabilidades** \> de seguridad. <br/>**NOTA**: En versiones anteriores de Windows, es posible que vea **Antivirus de Windows Defender** en lugar de **Antivirus de Microsoft Defender**.

5. Haga doble clic en **Carpetas protegidas configuradas** y, a continuación, establezca la opción **en Habilitado**. Seleccione **Mostrar** y especifique cada carpeta que quiera proteger.

6. Implemente el objeto directiva de grupo como suele hacer.

### <a name="use-powershell-to-protect-additional-folders"></a>Uso de PowerShell para proteger carpetas adicionales

1. Escriba **PowerShell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente cmdlet de PowerShell, reemplazando `<the folder to be protected>` por la ruta de acceso de la carpeta (como `"c:\apps\"`):

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Repita el paso 2 para cada carpeta que quiera proteger. Las carpetas protegidas están visibles en la aplicación Seguridad de Windows.

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Se muestra la ventana de PowerShell con el cmdlet" lightbox="images/cfa-allow-folder-ps.png":::

> [!IMPORTANT]
> Use `Add-MpPreference` para anexar o agregar aplicaciones a la lista y no `Set-MpPreference`. El uso del `Set-MpPreference` cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Uso de CSP de MDM para proteger carpetas adicionales

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Permitir que aplicaciones específicas realicen cambios en carpetas controladas

Puede especificar si ciertas aplicaciones siempre se consideran seguras y dar acceso de escritura a los archivos de carpetas protegidas. Permitir aplicaciones puede ser útil si la característica de acceso controlado a carpetas bloquea una aplicación determinada que conozca y de confianza.

> [!IMPORTANT]
> De forma predeterminada, Windows agrega aplicaciones que se consideran fáciles de usar en la lista de permitidos. Estas aplicaciones que se agregan automáticamente no se registran en la lista que se muestra en la aplicación Seguridad de Windows o mediante los cmdlets de PowerShell asociados. No es necesario agregar la mayoría de las aplicaciones. Agregue solo aplicaciones si se están bloqueando y puede comprobar su confiabilidad.

Al agregar una aplicación, debe especificar la ubicación de la aplicación. Solo se permitirá el acceso a las carpetas protegidas a la aplicación de esa ubicación. Si la aplicación (con el mismo nombre) está en una ubicación diferente, no se agregará a la lista de permitidos y puede bloquearse mediante el acceso controlado a carpetas.

Una aplicación o servicio permitidos solo tiene acceso de escritura a una carpeta controlada después de iniciarse. Por ejemplo, un servicio de actualización seguirá desencadenando eventos después de que se permita hasta que se detenga y reinicie.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Uso de la aplicación Windows Defender Security para permitir aplicaciones específicas

1. Abra la aplicación Seguridad de Windows buscando **seguridad** en el menú inicio.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda) y, a continuación, seleccione **Administrar protección contra ransomware**.

3. En la sección **Acceso controlado a carpetas**, seleccione **Permitir una aplicación a través del acceso controlado a carpetas**.

4. Seleccione **Agregar una aplicación permitida** y siga las indicaciones para agregar aplicaciones.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Botón Agregar una aplicación permitida" lightbox="images/cfa-allow-app.png":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Uso de directiva de grupo para permitir aplicaciones específicas

1. En el dispositivo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** \> de **Windows Antivirus** \> de Microsoft Defender Windows Defender **acceso a carpetas controladas** de **Protección contra vulnerabilidades** \> de seguridad.

4. Haga doble clic en la opción **Configurar aplicaciones permitidas** y establezca la opción **en Habilitado**. Seleccione **Mostrar** y escriba cada aplicación.

### <a name="use-powershell-to-allow-specific-apps"></a>Uso de PowerShell para permitir aplicaciones específicas

1. Escriba **PowerShell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.
2. Escriba el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Por ejemplo, para agregar el *archivo ejecutabletest.exe* ubicado en la carpeta *C:\apps*, el cmdlet sería el siguiente:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Continúe usando `Add-MpPreference -ControlledFolderAccessAllowedApplications` para agregar más aplicaciones a la lista. Las aplicaciones agregadas con este cmdlet aparecerán en la aplicación de Seguridad de Windows.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet de PowerShell para permitir una aplicación" lightbox="images/cfa-allow-app-ps.png":::

> [!IMPORTANT]
> Use `Add-MpPreference` para anexar o agregar aplicaciones a la lista. El uso del `Set-MpPreference` cmdlet sobrescribirá la lista existente.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Uso de CSP de MDM para permitir aplicaciones específicas

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/ControlledFolderAccessAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Permitir que los archivos ejecutables firmados accedan a carpetas protegidas

Microsoft Defender para punto de conexión indicadores de certificado y archivo pueden permitir que los archivos ejecutables firmados accedan a carpetas protegidas. Para obtener más información sobre la implementación, consulte [Creación de indicadores basados en certificados](indicator-certificates.md).

> [!Note]
> Esto no se aplica a los motores de scripting, incluido PowerShell.

## <a name="customize-the-notification"></a>Personalizar la notificación

Para obtener más información sobre cómo personalizar la notificación cuando se desencadena una regla y bloquea una aplicación o un archivo, consulte [Configurar notificaciones de alerta en Microsoft Defender para punto de conexión](configure-email-notifications.md).

## <a name="see-also"></a>Vea también

- [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
- [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md)
- [Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)
