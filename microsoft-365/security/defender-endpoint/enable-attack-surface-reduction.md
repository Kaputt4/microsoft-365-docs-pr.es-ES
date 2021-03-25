---
title: Habilitar reglas de reducción de superficie de ataque
description: Habilita las reglas de reducción de superficie de ataque (ASR) para proteger los dispositivos de ataques que usan macros, scripts y técnicas de inserción comunes.
keywords: Reducción de superficie de ataque, caderas, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, vulnerabilidad, prevención de infecciones, habilitar, activar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1deec767c6af777b23ab5a91c9e719f690e0c048
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165146"
---
# <a name="enable-attack-surface-reduction-rules"></a>Habilitar reglas de reducción de superficie de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Las reglas de reducción de superficie de](attack-surface-reduction.md) ataque (reglas ASR) ayudan a evitar acciones que el malware suele abusar de dispositivos y redes. Puedes establecer reglas ASR para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:
- Windows 10 Pro, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Server, [versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Cada regla ASR contiene una de tres opciones:

- No configurado: deshabilitar la regla ASR
- Bloquear: habilitar la regla ASR
- Auditoría: evaluar cómo afectaría la regla ASR a su organización si está habilitada

Es muy recomendable usar reglas ASR con una licencia de Windows E5 (o SKU de licencia similar) para aprovechar las capacidades avanzadas de supervisión e informes disponibles en [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) endpoint (Defender para endpoint). Sin embargo, para otras licencias como Windows Professional o E3 que no tienen acceso a funciones avanzadas de supervisión e informes, puedes desarrollar tus propias herramientas de supervisión e informes encima de los eventos que se generan en cada punto de conexión cuando se desencadenan reglas ASR (por ejemplo, reenvío de eventos).

> [!TIP]
> Para obtener más información sobre las licencias de Windows, consulta [Licencias de Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) y obtén la Guía de licencias por [volumen para Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

Puedes habilitar las reglas de reducción de superficie de ataque mediante cualquiera de estos métodos:

- [Microsoft Intune](#intune)
- [Administración de dispositivos móviles (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Directiva de grupo](#group-policy)
- [PowerShell](#powershell)

Se recomienda la administración de nivel de empresa, como Intune o Microsoft Endpoint Manager. La administración de nivel de empresa sobrescribirá cualquier configuración de PowerShell o directiva de grupo en conflicto al iniciarse.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Excluir archivos y carpetas de reglas ASR

Puedes excluir archivos y carpetas de ser evaluados por la mayoría de las reglas de reducción de superficie de ataque. Esto significa que incluso si una regla ASR determina que el archivo o carpeta contiene un comportamiento malintencionado, no bloqueará la ejecución del archivo. Esto podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos.

También puede excluir las reglas ASR para que no se desencadene en función de los hashes de certificado y archivo, ya que permite que defender especificado para los indicadores de certificado y archivo de extremo. (Vea [Administrar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> Excluir archivos o carpetas puede reducir gravemente la protección proporcionada por las reglas ASR. Se permitirá la ejecución de archivos excluidos y no se registrará ningún informe o evento.
> Si las reglas ASR detectan archivos que cree que no deben detectarse, debe usar el modo de [auditoría primero para probar la regla](evaluate-attack-surface-reduction.md).


Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas se aplican las exclusiones. Solo se aplica una exclusión cuando se inicia la aplicación o servicio excluidos. Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.

Las reglas ASR admiten variables de entorno y caracteres comodín. Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

Los siguientes procedimientos para habilitar reglas ASR incluyen instrucciones sobre cómo excluir archivos y carpetas.

## <a name="intune"></a>Intune

1. Seleccione **Perfiles de configuración** de  >  **dispositivos**. Elija un perfil de protección de extremo existente o cree uno nuevo. Para crear uno nuevo, seleccione **Crear perfil** e introduzca información para este perfil. En **Tipo de perfil,** seleccione **Protección de extremo**. Si ha elegido un perfil existente, seleccione **Propiedades** y, a continuación, **seleccione Configuración**.

2. En el **panel Protección de** puntos de conexión, Windows Defender Protección contra **vulnerabilidades** de seguridad y, a continuación, **seleccione Reducción de superficie de ataque**. Seleccione la configuración deseada para cada regla ASR.

3. En **Excepciones de reducción de superficie de ataque,** escriba archivos y carpetas individuales. También puede seleccionar **Importar para** importar un archivo CSV que contenga archivos y carpetas que se excluirán de las reglas ASR. Cada línea del archivo CSV debe tener el siguiente formato:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Seleccione **Aceptar en** los tres paneles de configuración. A **continuación,** seleccione Crear si está creando un nuevo archivo de protección de puntos de conexión o **Guardar** si está editando uno existente.

## <a name="mdm"></a>MDM

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) para habilitar y establecer individualmente el modo de cada regla.

A continuación se muestra un ejemplo de referencia mediante [valores GUID para reglas ASR.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

Los valores para habilitar, deshabilitar o habilitar en modo auditoría son:

- Disable = 0
- Bloquear (habilitar regla ASR) = 1
- Auditoría = 2

Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.

Ejemplo:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Asegúrese de escribir valores de OMA-URI sin espacios.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.

2. Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .

3. Escribe un nombre y una descripción, selecciona **Reducción de superficie de** ataque y selecciona **Siguiente**.

4. Elija las reglas que bloquearán o auditarán las acciones y seleccione **Siguiente**.

5. Revise la configuración y seleccione **Siguiente** para crear la directiva.

6. Después de crear la directiva, **Cierre**.

## <a name="group-policy"></a>Directiva de grupo

> [!WARNING]
> Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de directiva de grupo en conflicto al iniciarse.

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender Windows Defender reducción de superficie de ataque de Protección contra  >    >    >  **vulnerabilidades.**

4. Selecciona **Configurar reglas de reducción de superficie de ataque** y selecciona **Habilitado**. A continuación, puede establecer el estado individual de cada regla en la sección de opciones.

   Seleccione **Mostrar...** y escriba el identificador de regla en la columna **Nombre** de valor y el estado elegido en la **columna** Valor de la siguiente manera:

   - Disable = 0
   - Bloquear (habilitar regla ASR) = 1
   - Auditoría = 2

   ![Configuración de directiva de grupo que muestra un identificador de regla de reducción de superficie de ataque en blanco y un valor de 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. Para excluir archivos y carpetas de  las reglas ASR, seleccione la opción Excluir archivos y rutas de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**. Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor. Escriba **0 en** la **columna Valor** de cada elemento.

> [!WARNING]
> No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de PowerShell en conflicto al iniciarse. Para permitir que los usuarios definan el valor con PowerShell, use la opción "User Defined" para la regla en la plataforma de administración.

1. Escriba **powershell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**.

2. Escriba el siguiente cmdlet:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Para habilitar las reglas ASR en modo auditoría, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Para desactivar las reglas ASR, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > Debe especificar el estado individualmente para cada regla, pero puede combinar reglas y estados en una lista separada por comas.
    >
    > En el siguiente ejemplo, se habilitarán las dos primeras reglas, se deshabilitará la tercera regla y se habilitará la cuarta regla en modo auditoría:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    También puede usar el verbo `Add-MpPreference` de PowerShell para agregar nuevas reglas a la lista existente.

    > [!WARNING]
    > `Set-MpPreference` sobrescribirá siempre el conjunto de reglas existente. Si desea agregar al conjunto existente, debe usarlo en `Add-MpPreference` su lugar.
    > Puede obtener una lista de reglas y su estado actual mediante `Get-MpPreference` .

3. Para excluir archivos y carpetas de las reglas ASR, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más archivos y carpetas a la lista.

    > [!IMPORTANT]
    > Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista. El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.

## <a name="related-articles"></a>Artículos relacionados

- [Reducir superficies de ataque con reglas de reducción de superficie de ataque](attack-surface-reduction.md)

- [Evaluar la reducción de superficie de ataque](evaluate-attack-surface-reduction.md)

- [Preguntas frecuentes sobre reducción de superficie de ataque](attack-surface-reduction.md)
