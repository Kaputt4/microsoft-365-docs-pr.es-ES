---
title: Habilitar el acceso controlado a carpetas
keywords: Acceso controlado a carpetas, windows 10, windows 11, windows defender, ransomware, protect, files, folders, enable, turn on, use
description: Obtenga información sobre cómo proteger los archivos importantes habilitando el acceso controlado a carpetas
ms.service: microsoft-365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.subservice: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: 6d911db34081d6e67cb5f1a562bfbed6964f29c2
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67523366"
---
# <a name="enable-controlled-folder-access"></a>Habilitar el acceso controlado a carpetas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[El acceso controlado a carpetas](controlled-folders.md) le ayuda a proteger datos valiosos de aplicaciones y amenazas malintencionadas, como ransomware. El acceso controlado a carpetas se incluye con Windows 10, Windows 11 y Windows Server 2019. El acceso controlado a carpetas también se incluye como parte de la [solución moderna y unificada para Windows Server 2012R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview).

Puede habilitar el acceso controlado a carpetas mediante cualquiera de estos métodos:

- [Seguridad de Windows aplicación *](#windows-security-app)
- [Microsoft Endpoint Manager](#endpoint-manager)
- [Administración de dispositivos móviles (MDM)](#mobile-device-management-mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Directiva de grupo](#group-policy)
- [PowerShell](#powershell)

[El modo auditoría](evaluate-controlled-folder-access.md) permite probar cómo funcionaría la característica (y revisar los eventos) sin afectar al uso normal del dispositivo.

directiva de grupo configuración que deshabilita la combinación de listas de administradores locales invalidará la configuración de acceso controlado a carpetas. También invalidan las carpetas protegidas y las aplicaciones permitidas establecidas por el administrador local mediante el acceso controlado a carpetas. Estas directivas incluyen:

- Antivirus de Microsoft Defender **Configure local administrator merge behavior for lists**
- System Center Endpoint Protection **Permitir a los usuarios agregar exclusiones e invalidaciones**

Para obtener más información sobre cómo deshabilitar la combinación de listas locales, vea [Impedir o permitir que los usuarios modifiquen localmente la configuración de la directiva del Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).

## <a name="windows-security-app"></a>Aplicación Seguridad de Windows

1. Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas. También puede buscar **Seguridad de Windows** en el menú inicio.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda) y, a continuación, seleccione **Protección contra ransomware**.

3. Establezca el modificador de **Acceso controlado** a carpetas **en Activado**.

> [!NOTE]
> *Este método no está disponible en Windows Server 2012R2 o 2016.
> 
> Si el acceso controlado a carpetas está configurado con directiva de grupo, PowerShell o CSP de MDM, el estado cambiará en la aplicación Seguridad de Windows después de reiniciar el dispositivo.
> Si la característica se establece en **modo auditoría** con cualquiera de esas herramientas, la aplicación Seguridad de Windows mostrará el estado como **Desactivado**.
> Si protege los datos de perfil de usuario, se recomienda que el perfil de usuario esté en la unidad de instalación predeterminada de Windows.

## <a name="endpoint-manager"></a>Endpoint Manager

1. Inicie sesión en el [Endpoint Manager](https://endpoint.microsoft.com) y abra **Seguridad del punto de conexión**.

2. Ve a Directiva de **reducción de superficie expuesta a ataques** \> **.**

3. Seleccione **Plataforma**, elija **Windows 10 y versiones posteriores** y seleccione el perfil Reglas \> de **reducción de superficie expuesta a ataques** **Crear**.

4. Asigne un nombre a la directiva y agregue una descripción. Seleccione **Siguiente**.

5. Desplácese hacia abajo hasta la parte inferior, seleccione la lista desplegable **Habilitar protección de carpetas** y elija **Habilitar**.

6. Seleccione **Lista de carpetas adicionales que deben protegerse** y agregue las carpetas que deben protegerse.

7. Seleccione **Lista de aplicaciones que tienen acceso a carpetas protegidas** y agregue las aplicaciones que tienen acceso a carpetas protegidas.

8. Seleccione **Excluir archivos y rutas de acceso de las reglas de reducción de superficie expuesta a ataques** y agregue los archivos y rutas de acceso que deben excluirse de las reglas de reducción de superficie expuesta a ataques.

9. Seleccione el perfil **Asignaciones**, asigne a **Todos los usuarios & Todos los dispositivos** y seleccione **Guardar**.

10. Seleccione **Siguiente** para guardar cada hoja abierta y, a continuación, **Crear**.

    > [!NOTE]
    > Los caracteres comodín se admiten para las aplicaciones, pero no para las carpetas. Las subcarpetas no están protegidas. Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.

## <a name="mobile-device-management-mdm"></a>Administración de dispositivos móviles (MDM)

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. En Microsoft Endpoint Configuration Manager, vaya a **Activos y cumplimiento** \> **Endpoint Protection** \> **Protección contra vulnerabilidades de seguridad de Windows Defender**.

2. Seleccione **Inicio** \> **Crear directiva de protección contra vulnerabilidades**.

3. Escriba un nombre y una descripción, seleccione **Acceso controlado a carpetas** y seleccione **Siguiente**.

4. Elija si bloquea o audita los cambios, permite otras aplicaciones o agrega otras carpetas y selecciona **Siguiente**.

   > [!NOTE]
   > El carácter comodín se admite para las aplicaciones, pero no para las carpetas. Las subcarpetas no están protegidas. Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.

5. Revise la configuración y seleccione **Siguiente** para crear la directiva.

6. Una vez creada la directiva, **cierre**.

## <a name="group-policy"></a>Directiva de grupo

1. En el dispositivo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes de Windows > Antivirus de Microsoft Defender > Windows Defender Exploit Guard > acceso controlado a carpetas**.

4. Haga doble clic en la opción **Configurar acceso controlado a** carpetas y establezca la opción **en Habilitado**. En la sección de opciones, debe especificar una de las siguientes opciones:
   - **Habilitar** : no se permitirá que las aplicaciones malintencionadas y sospechosas realicen cambios en los archivos de carpetas protegidas. Se proporcionará una notificación en el registro de eventos de Windows.
   - **Deshabilitar (valor predeterminado):** la característica acceso controlado a carpetas no funcionará. Todas las aplicaciones pueden realizar cambios en los archivos de carpetas protegidas.
   - **Modo de auditoría** : los cambios se permitirán si una aplicación malintencionada o sospechosa intenta realizar un cambio en un archivo de una carpeta protegida. Sin embargo, se registrará en el registro de eventos de Windows, donde puede evaluar el impacto en su organización.
   - **Bloquear solo la modificación de disco** : los intentos de las aplicaciones que no son de confianza para escribir en sectores de disco se registrarán en el registro de eventos de Windows. Estos registros se pueden encontrar en Registros \> de **aplicaciones y servicios** de Microsoft \> Windows \> Windows Defender \> identificador operativo \> 1123.
   - **Solo modificación de disco de auditoría**: solo se registrarán los intentos de escritura en sectores de disco protegidos en el registro de eventos de Windows (en Registros \> de **aplicaciones y servicios** **de Microsoft** \> **Windows** \> **Windows Defender** \> identificador **operativo** \> **1124**). Los intentos de modificar o eliminar archivos en carpetas protegidas no se registrarán.

    :::image type="content" source="../../media/cfa-gp-enable.png" alt-text="Opción de directiva de grupo Habilitada y Modo de auditoría seleccionada" lightbox="../../media/cfa-gp-enable.png":::

> [!IMPORTANT]
> Para habilitar completamente el acceso controlado a carpetas, debe establecer la opción directiva de grupo **en Habilitado** y seleccionar **Bloquear** en el menú desplegable de opciones.

## <a name="powershell"></a>PowerShell

1. Escriba **powershell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Puede habilitar la característica en modo de auditoría especificando `AuditMode` en lugar de `Enabled`.

Use `Disabled` para desactivar la característica.

## <a name="see-also"></a>Vea también

- [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
- [Personalizar el acceso controlado a carpetas](customize-controlled-folders.md)
- [Microsoft Defender para punto de conexión](evaluate-mde.md)
