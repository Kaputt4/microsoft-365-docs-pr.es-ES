---
title: Habilitar reglas de reducción de superficie expuesta a ataques
description: Habilite reglas de reducción de la superficie expuesta a ataques (ASR) para proteger los dispositivos frente a ataques que usan macros, scripts y técnicas de inyección comunes.
keywords: Reducción de la superficie expuesta a ataques, caderas, sistema de prevención de intrusiones del host, reglas de protección, anti-vulnerabilidad, antiexploit, vulnerabilidad de seguridad, prevención de infecciones, habilitar, activar
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.date: 1/18/2022
ms.openlocfilehash: 04eee4c44e0cf2b712ecab84b18837d7b3705cef
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669812"
---
# <a name="enable-attack-surface-reduction-rules"></a>Habilitar reglas de reducción de superficie expuesta a ataques

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> [!TIP]
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Las reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md) (reglas ASR) ayudan a evitar acciones que el malware suele abusar para poner en peligro dispositivos y redes.

## <a name="requirements"></a>Requirements

Características de reducción de superficie expuesta a ataques en versiones Windows

Puede establecer reglas de reducción de superficie expuesta a ataques para dispositivos que ejecutan cualquiera de las siguientes ediciones y versiones de Windows:

- [Windows 11 Pro](/windows/whats-new/windows-11-overview)
- [Windows 11 Enterprise](https://www.microsoft.com/microsoft-365/windows/windows-11-enterprise)
- Windows 10 Pro, [versión 1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows 10 Enterprise, [versión 1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior
- Windows Server, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior
- [Windows Server 2012 R2](/windows/win32/srvnodes/what-s-new-for-windows-server-2012-r2)
- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Windows Server 2022](/windows-server/get-started/whats-new-in-windows-server-2022)

Para usar todo el conjunto de características de las reglas de reducción de superficie expuesta a ataques, necesita:

- Antivirus de Windows Defender como antivirus principal (protección en tiempo real activada)
- [Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) en (algunas reglas lo requieren)
- Windows 10 Enterprise licencia E5 o E3

Aunque las reglas de reducción de superficie expuesta a ataques no requieren una [licencia de Windows E5](/windows/deployment/deploy-enterprise-licenses), con una licencia Windows E5, se obtienen funcionalidades avanzadas de administración, como la supervisión, el análisis y los flujos de trabajo disponibles en Defender para punto de conexión, así como funcionalidades de informes y configuración en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>. Estas funcionalidades avanzadas no están disponibles con una licencia E3, pero puede seguir usando Visor de eventos para revisar los eventos de regla de reducción de superficie expuesta a ataques.

Cada regla de ASR contiene una de cuatro configuraciones:

- **No configurado** |  **Deshabilitado**: deshabilitar la regla ASR
- **Bloquear**: habilitar la regla ASR
- **Auditoría**: evalúe cómo afectaría la regla ASR a su organización si está habilitada.
- **Advertir**: Habilite la regla ASR, pero permita que el usuario final omita el bloque.

Se recomienda usar reglas de ASR con una licencia Windows E5 (o SKU de licencia similar) para aprovechar las funcionalidades avanzadas de supervisión e informes disponibles en [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) (Defender para punto de conexión). Sin embargo, si tiene otra licencia, como Windows Professional o Windows E3 que no incluyen funcionalidades avanzadas de supervisión e informes, puede desarrollar sus propias herramientas de supervisión e informes además de los eventos que se generan en cada punto de conexión cuando se desencadenan reglas de ASR (por ejemplo, reenvío de eventos).

> [!TIP]
> Para obtener más información sobre las licencias de Windows, consulte [licencias de Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) y obtenga la [guía de licencias por volumen para Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

Puede habilitar las reglas de reducción de superficie expuesta a ataques mediante cualquiera de estos métodos:

- [Microsoft Intune](#intune)
- [Administración de dispositivos móviles (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Directiva de grupo](#group-policy)
- [PowerShell](#powershell)

se recomienda administrar Enterprise nivel, como Intune o Microsoft Endpoint Manager. Enterprise nivel de administración sobrescribirá cualquier directiva de grupo en conflicto o la configuración de PowerShell durante el inicio.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Exclusión de archivos y carpetas de reglas asr

Puede excluir que la mayoría de las reglas de reducción de superficie expuesta a ataques evalúen archivos y carpetas. Esto significa que, incluso si una regla ASR determina que el archivo o la carpeta contiene un comportamiento malintencionado, no bloqueará la ejecución del archivo. Esto podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos.

También puede excluir que las reglas de ASR se desencadenen en función de los hash de certificado y archivo al permitir indicadores de certificado y archivo de Defender para punto de conexión especificados. (Consulte [Administrar indicadores](manage-indicators.md)).

> [!IMPORTANT]
> La exclusión de archivos o carpetas puede reducir considerablemente la protección proporcionada por las reglas de ASR. Los archivos excluidos podrán ejecutarse y no se registrará ningún informe o evento.
> Si las reglas de ASR detectan archivos que cree que no deben detectarse, primero debe [usar el modo de auditoría para probar la regla](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit).

Puede especificar archivos o carpetas individuales (mediante rutas de acceso de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas se aplican las exclusiones. Una exclusión solo se aplica cuando se inicia la aplicación o el servicio excluidos. Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.

Las reglas de ASR admiten variables de entorno y caracteres comodín. Para obtener información sobre el uso de caracteres comodín, consulte [Uso de caracteres comodín en las listas de exclusión de extensiones o ruta de acceso de carpeta y nombre de archivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).

## <a name="policy-conflict"></a>Conflicto de directiva

1. Si se aplica una directiva en conflicto a través de MDM y GP, la configuración aplicada desde MDM tendrá prioridad.

2. Las reglas de reducción de superficie expuesta a ataques para dispositivos administrados por MEM ahora admiten el comportamiento de la fusión de la configuración de diferentes directivas, con el fin de crear un superconjunto de directivas para cada dispositivo. Solo se combinan las opciones de configuración que no están en conflicto, mientras que las que están en conflicto no se agregan al superconjunto de reglas. Anteriormente, si dos directivas incluían conflictos para una sola configuración, ambas directivas se marcaban como en conflicto y no se implementaría ninguna configuración de ninguno de los perfiles. El comportamiento de combinación de reglas de reducción de superficie expuesta a ataques es el siguiente:
   - Las reglas de reducción de superficie expuesta a ataques de los perfiles siguientes se evalúan para cada dispositivo al que se aplican las reglas:
     - La directiva de configuración de dispositivos > > perfil de Endpoint Protection > **Protección contra vulnerabilidades de seguridad de Microsoft Defender** >  [Attack Surface Reduction](/mem/intune/protect/endpoint-protection-windows-10#attack-surface-reduction-rules).
     - Directiva de reducción de superficie expuesta a ataques > seguridad del punto de conexión Reglas de **reducción** >  de [superficie expuesta a ataques](/mem/intune/protect/endpoint-security-asr-policy#devices-managed-by-intune).
     - Líneas base de seguridad > seguridad de puntos de conexión >[reglas de reducción de superficie expuesta a ataques](/mem/intune/protect/security-baseline-settings-defender-atp#attack-surface-reduction-rules) **de base** >  de ATP de Microsoft Defender.
   - Configuración que no tienen conflictos se agregan a un superconjunto de directivas para el dispositivo.
   - Cuando dos o más directivas tienen una configuración en conflicto, la configuración en conflicto no se agrega a la directiva combinada, mientras que la configuración que no entra en conflicto se agrega a la directiva de superconjunto que se aplica a un dispositivo.
   - Solo se retienen las configuraciones de configuración en conflicto.

## <a name="configuration-methods"></a>Métodos de configuración

En esta sección se proporcionan detalles de configuración para los siguientes métodos de configuración:

- [Intune](#intune)
- [MEM](#mem)
- [MDM](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Directiva de grupo](#group-policy)
- [PowerShell](#powershell)

Los procedimientos siguientes para habilitar las reglas de ASR incluyen instrucciones para excluir archivos y carpetas.

### <a name="intune"></a>Intune

#### <a name="device-configuration-profiles"></a>Perfiles de configuración de dispositivo

1. Seleccione Perfiles **de configuración** \> de **dispositivos**. Elija un perfil de Endpoint Protection existente o cree uno nuevo. Para crear uno nuevo, seleccione **Crear perfil** y escriba información para este perfil. En **Tipo de perfil**, seleccione **Endpoint Protection**. Si ha elegido un perfil existente, seleccione **Propiedades** y, a continuación, seleccione **Configuración**.

2. En el panel **Protección contra puntos de conexión**, seleccione **Windows Defender Protección contra vulnerabilidades** de seguridad y, a continuación, seleccione **Reducción de superficie expuesta a ataques**. Seleccione la configuración deseada para cada regla de ASR.

3. En **Excepciones de reducción de superficie expuesta a ataques**, escriba archivos y carpetas individuales. También puede seleccionar **Importar** para importar un archivo CSV que contenga archivos y carpetas que se excluirán de las reglas de ASR. Cada línea del archivo CSV debe tener el formato siguiente:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Seleccione **Aceptar** en los tres paneles de configuración. A continuación, seleccione **Crear** si va a crear un nuevo archivo de Endpoint Protection o **Guardar** si está editando uno existente.

#### <a name="endpoint-security-policy"></a>Directiva de seguridad de punto de conexión**

1. Seleccione **Reducción de la superficie expuesta a ataques** de seguridad \> de **punto de conexión**. Elija una regla ASR existente o cree una nueva. Para crear uno nuevo, seleccione **Crear directiva** y escriba información para este perfil. En **Tipo de perfil**, seleccione **Reglas de reducción de superficie expuesta a ataques**. Si ha elegido un perfil existente, seleccione **Propiedades** y, a continuación, seleccione **Configuración**.

2. En el panel **Configuración** , seleccione **Reducción de superficie expuesta a ataques** y, a continuación, seleccione la configuración deseada para cada regla de ASR.

3. En **Lista de carpetas adicionales que deben protegerse**, **Lista de aplicaciones que tienen acceso a carpetas protegidas** y **Excluir archivos y rutas de acceso de las reglas de reducción de la superficie expuesta a ataques**, escriba archivos y carpetas individuales. También puede seleccionar **Importar** para importar un archivo CSV que contenga archivos y carpetas que se excluirán de las reglas de ASR. Cada línea del archivo CSV debe tener el formato siguiente:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Seleccione **Siguiente** en los tres paneles de configuración y, a continuación, seleccione **Crear** si va a crear una nueva directiva o **Guardar** si está editando una directiva existente.

### <a name="mem"></a>MEM

Puede usar Microsoft Endpoint Manager (MEM) OMA-URI para configurar reglas ASR personalizadas. En el procedimiento siguiente se usa la regla [Bloquear el abuso de controladores firmados vulnerables explotados](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers) para el ejemplo.

1. Abra el centro de administración de Microsoft Endpoint Manager (MEM). En el menú **Inicio** , haga clic en  **Dispositivos**, seleccione **Perfiles de configuración** y, a continuación, haga clic en **Crear perfil**.

   > [!div class="mx-imgBorder"]
   >  :::image type="content" source="images/mem01-create-profile.png" alt-text="Página Crear perfil en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/mem01-create-profile.png":::

2. En **Crear un perfil**, en las dos listas desplegables siguientes, seleccione lo siguiente:

   - En **Plataforma**, seleccione **Windows 10 y versiones posteriores.**
   - En **Tipo de perfil**, seleccione **Plantillas.**
   - Si las reglas de ASR ya están establecidas a través de Seguridad del punto de conexión, en **Tipo de perfil**, seleccione **Configuración catálogo**.

   Seleccione **Personalizado** y, después, **Crear**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem02-profile-attributes.png" alt-text="Atributos de perfil de regla en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/mem02-profile-attributes.png":::

3. La herramienta Plantilla personalizada se abre en el paso **1 Aspectos básicos**. En **1 Conceptos básicos**, en **Nombre**, escriba un nombre para la plantilla y, en **Descripción** , puede escribir una descripción (opcional).

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem03-1-basics.png" alt-text="Los atributos básicos del portal del centro de administración de Microsoft Endpoint Manager" lightbox="images/mem03-1-basics.png":::

4. Haga clic en **Siguiente**. Se abre el paso **2 Configuración** . Para Configuración OMA-URI, haga clic en **Agregar**. Ahora aparecen dos opciones: **Agregar** y **Exportar**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem04-2-configuration-settings.png" alt-text="Los valores de configuración del portal del centro de administración de Microsoft Endpoint Manager" lightbox="images/mem04-2-configuration-settings.png":::

5. Haga clic en **Agregar** de nuevo. Se abre **el Configuración Agregar fila OMA-URI**. En **Agregar fila**, haga lo siguiente:

   - En **Nombre**, escriba un nombre para la regla.
   - En **Descripción**, escriba una breve descripción.
   - En **OMA-URI**, escriba o pegue el vínculo OMA-URI específico para la regla que va a agregar. Consulte la sección MDM de este artículo para ver el OMA-URI que se usará para esta regla de ejemplo. Para guides de regla de reducción de superficie expuesta a [ataques, consulte Descripciones por regla](attack-surface-reduction-rules-reference.md#per-rule-descriptions) en el tema: Reglas de reducción de superficie expuesta a ataques.
   - En **Tipo de datos**, seleccione **Cadena**.
   - En **Valor**, escriba o pegue el valor GUID, el \= signo y el valor De estado sin espacios (_GUID=StateValue_). Donde:

     - 0 : Deshabilitar (Deshabilitar la regla ASR)
     - 1: Bloquear (habilitar la regla ASR)
     - 2 : Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)
     - 6 : Advertir (Habilitar la regla ASR, pero permitir que el usuario final omita el bloque)

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem05-add-row-oma-uri.png" alt-text="Configuración del URI de OMA en el portal del centro de administración de Microsoft Endpoint Manager" lightbox="images/mem05-add-row-oma-uri.png":::

6. Seleccione **Guardar**. **Agregar fila** se cierra. En **Personalizado**, seleccione **Siguiente**. En el paso **3 Etiquetas de ámbito**, las etiquetas de ámbito son opcionales. Realiza una de las siguientes acciones:

   - Seleccione **Seleccionar etiquetas de ámbito**, seleccione la etiqueta de ámbito (opcional) y, a continuación, seleccione **Siguiente**.
   - O bien, seleccione **Siguiente.**

7. En **el paso 4 Asignaciones**, en **Grupos incluidos**, para los grupos a los que desea aplicar esta regla, seleccione una de las opciones siguientes:

   - **Agregar grupos**
   - **Agregar todos los usuarios**
   - **Agregar todos los dispositivos**

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem06-4-assignments.png" alt-text="Las asignaciones en el portal del centro de administración de Microsoft Endpoint Manager" lightbox="images/mem06-4-assignments.png":::

8. En **Grupos excluidos**, seleccione los grupos que quiera excluir de esta regla y, a continuación, seleccione **Siguiente**.

9. En el paso **5 Reglas de aplicabilidad** para la configuración siguiente, haga lo siguiente:

   - En **Regla**, seleccione **Asignar perfil si** o **No asignar perfil si**
   - En **Propiedad**, seleccione la propiedad a la que desea que se aplique esta regla.
   - En **Valor**, escriba el valor o el intervalo de valores aplicables.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/mem07-5-applicability-rules.png" alt-text="Las reglas de aplicabilidad del portal del centro de administración de Microsoft Endpoint Manager" lightbox="images/mem07-5-applicability-rules.png":::

10. Seleccione **Siguiente**. En el paso **6 Revisar y crear**, revise la configuración y la información que ha seleccionado y escrito y, a continuación, seleccione **Crear**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/mem08-6-review-create.png" alt-text="La opción Revisar y crear en el portal del Centro de administración de Microsoft Endpoint Manager" lightbox="images/mem08-6-review-create.png":::

    > [!NOTE]
    > Las reglas están activas y están activas en cuestión de minutos.

> [!NOTE]
> Control de conflictos:
>
> Si asigna dos directivas ASR diferentes a un dispositivo, la forma en que se controla el conflicto son las reglas a las que se asignan estados diferentes, no hay ninguna administración de conflictos en su lugar y el resultado es un error.
>
> Las reglas no conflictivas no producirán un error y la regla se aplicará correctamente. El resultado es que se aplica la primera regla y las reglas posteriores no conflictivas se combinan en la directiva.

### <a name="mdm"></a>MDM

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) para habilitar y establecer individualmente el modo para cada regla.

A continuación se muestra un ejemplo de referencia que usa valores GUID para la [referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md).

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=1|d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|d3e037e1-3eb8-44c8-a917-57927947596d=1|5beb7efe-fd9a-4556-801d-275e5ffc04cc=0|be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=1`

Los valores para habilitar (bloquear), deshabilitar, advertir o habilitar en modo de auditoría son:

- 0 : Deshabilitar (Deshabilitar la regla ASR)
- 1: Bloquear (habilitar la regla ASR)
- 2 : Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)
- 6 : advertir (habilitar la regla ASR, pero permitir que el usuario final omita el bloque). El modo de advertencia está disponible para la mayoría de las reglas de ASR.

Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) para agregar exclusiones.

Ejemplo:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Asegúrese de escribir valores de OMA-URI sin espacios.

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. En Microsoft Endpoint Configuration Manager, vaya a **Activos y cumplimiento** \> **Endpoint Protection** \> **Protección contra vulnerabilidades de seguridad de Windows Defender**.

2. Seleccione **Inicio** \> **Crear directiva de protección contra vulnerabilidades**.

3. Escriba un nombre y una descripción, seleccione **Reducción de superficie expuesta a ataques** y seleccione **Siguiente**.

4. Elija qué reglas bloquearán o auditarán las acciones y seleccione **Siguiente**.

5. Revise la configuración y seleccione **Siguiente** para crear la directiva.

6. Una vez creada la directiva, seleccione **Cerrar**.

### <a name="group-policy"></a>Directiva de grupo

> [!WARNING]
> Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de directiva de grupo en conflicto al iniciarse.

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol para **Windows componentes** \> **Antivirus de Microsoft Defender** \> **Protección contra vulnerabilidades de seguridad de Microsoft Defender** \> **reducción de la superficie expuesta a ataques**.

4. Seleccione **Configurar reglas de reducción de superficie expuesta a ataques** y seleccione **Habilitado**. A continuación, puede establecer el estado individual de cada regla en la sección de opciones. Seleccione **Mostrar...** y escriba el identificador de regla en la columna **Nombre** del valor y el estado elegido en la columna **Valor** de la siguiente manera:

   - 0 : Deshabilitar (Deshabilitar la regla ASR)
   - 1: Bloquear (habilitar la regla ASR)
   - 2 : Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)
   - 6 : Advertir (Habilitar la regla ASR, pero permitir que el usuario final omita el bloque)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Reglas de ASR en directiva de grupo" lightbox="images/asr-rules-gp.png":::

5. Para excluir archivos y carpetas de reglas de ASR, seleccione la opción **Excluir archivos y rutas de acceso de reglas de reducción de superficie expuesta a ataques** y establezca la opción **en Habilitado**. Seleccione **Mostrar** y escriba cada archivo o carpeta en la columna **Nombre de valor** . Escriba **0** en la columna **Valor** de cada elemento.

   > [!WARNING]
   > No use comillas, ya que no se admiten para la columna **Nombre de valor** ni para la columna **Valor** .

### <a name="powershell"></a>PowerShell

> [!WARNING]
> Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de PowerShell en conflicto durante el inicio. Para permitir que los usuarios definan el valor mediante PowerShell, use la opción "Definido por el usuario" para la regla en la plataforma de administración.
> "Definido por el usuario" permite a un usuario administrador local configurar la regla.
> La opción Definida por el usuario se muestra en la ilustración siguiente.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-user-defined.png" alt-text="La opción Habilitar para la seguridad de credenciales" lightbox="images/asr-user-defined.png":::

1. Escriba **powershell** en el menú Inicio, haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.

2. Escriba uno de los siguientes cmdlets. (Consulte Referencia de [reglas de reducción de superficie](attack-surface-reduction-rules-reference.md) expuesta a ataques para obtener más detalles, como el identificador de regla).

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Para habilitar las reglas de ASR en modo de auditoría, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Para habilitar las reglas de ASR en modo de advertencia, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    Para habilitar el abuso de bloques ASR de controladores firmados vulnerables explotados, use el siguiente cmdlet:

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    Para desactivar las reglas de ASR, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > Debe especificar el estado individualmente para cada regla, pero puede combinar reglas y estados en una lista separada por comas.
    >
    > En el ejemplo siguiente, se habilitarán las dos primeras reglas, la tercera se deshabilitará y la cuarta se habilitará en modo de auditoría:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    También puede usar el `Add-MpPreference` verbo de PowerShell para agregar nuevas reglas a la lista existente.

    > [!WARNING]
    > `Set-MpPreference` sobrescribirá siempre el conjunto de reglas existente. Si desea agregar al conjunto existente, use `Add-MpPreference` en su lugar.
    > Puede obtener una lista de reglas y su estado actual mediante `Get-MpPreference`.

3. Para excluir archivos y carpetas de reglas de ASR, use el siguiente cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Continúe usando `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` para agregar más archivos y carpetas a la lista.

    > [!IMPORTANT]
    > Use `Add-MpPreference` para anexar o agregar aplicaciones a la lista. El uso del `Set-MpPreference` cmdlet sobrescribirá la lista existente.

## <a name="related-articles"></a>Artículos relacionados

- [Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md)
- [Evaluación de la reducción de la superficie expuesta a ataques](evaluate-attack-surface-reduction.md)
- [Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction.md)
