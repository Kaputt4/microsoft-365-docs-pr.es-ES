---
title: Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo controlar falsos positivos o falsos negativos en Microsoft Defender para punto de conexión.
keywords: antivirus, excepción, exclusión, Microsoft Defender para punto de conexión, falso positivo, falso negativo, archivo bloqueado, dirección URL bloqueada
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.date: 12/02/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom:
- FPFN
- admindeeplinkDEFENDER
ms.openlocfilehash: d7477c2006acd04008e6cb56cb22261a4db4a92b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789933"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

En las soluciones de endpoint protection, un falso positivo es una entidad, como un archivo o un proceso, que se detectó e identificó como malintencionada, aunque la entidad no sea realmente una amenaza. Un falso negativo es una entidad que no se detectó como amenaza, aunque realmente sea malintencionada. Los falsos positivos o negativos pueden producirse con cualquier solución de protección contra amenazas, [incluidos los Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md).

:::image type="content" source="images/false-positives-overview.png" alt-text="Definición de falsos positivos y negativos en el portal de Microsoft Defender para punto de conexión" lightbox="images/false-positives-overview.png":::

Afortunadamente, se pueden realizar pasos para abordar y reducir este tipo de problemas. Si ve falsos positivos o negativos en [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender), las operaciones de seguridad pueden realizar pasos para solucionarlos mediante el siguiente proceso:

1. [Revisión y clasificación de alertas](#part-1-review-and-classify-alerts)
2. [Revisión de las acciones de corrección que se han realizado](#part-2-review-remediation-actions)
3. [Revisión y definición de exclusiones](#part-3-review-or-define-exclusions)
4. [Envío de una entidad para su análisis](#part-4-submit-a-file-for-analysis)
5. [Revisión y ajuste de la configuración de protección contra amenazas](#part-5-review-and-adjust-your-threat-protection-settings)

Puede obtener ayuda si sigue teniendo problemas con falsos positivos o negativos después de realizar las tareas descritas en este artículo. Consulte [¿Todavía necesita ayuda?](#still-need-help)

:::image type="content" source="images/false-positives-step-diagram.png" alt-text="Pasos para abordar falsos positivos y negativos" lightbox="images/false-positives-step-diagram.png":::

> [!NOTE]
> Este artículo está pensado como guía para los operadores de seguridad y los administradores de seguridad que usan [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md).

## <a name="part-1-review-and-classify-alerts"></a>Parte 1: Revisión y clasificación de alertas

Si ve una [alerta](alerts.md) que se desencadenó porque se detectó algo como malintencionado o sospechoso que no debería haber sido, puede suprimir la alerta para esa entidad. También puede suprimir las alertas que no son necesariamente falsos positivos, pero que no son importantes. Se recomienda clasificar también las alertas.

Administrar las alertas y clasificar los positivos verdaderos o falsos ayuda a entrenar la solución de protección contra amenazas y puede reducir el número de falsos positivos o falsos negativos a lo largo del tiempo. Realizar estos pasos también ayuda a reducir el ruido en el panel de operaciones de seguridad para que el equipo de seguridad pueda centrarse en los elementos de trabajo de mayor prioridad.

### <a name="determine-whether-an-alert-is-accurate"></a>Determinar si una alerta es precisa

Antes de clasificar o suprimir una alerta, determine si la alerta es precisa, un falso positivo o benigno.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Cola de alertas**.

3. Seleccione una alerta para obtener más detalles sobre la alerta. (Consulte [Revisión de alertas en Microsoft Defender para punto de conexión](review-alerts.md)).

4. En función del estado de la alerta, siga los pasos descritos en la tabla siguiente:

   |Estado de alerta|Qué hacer|
   |---|---|
   |La alerta es precisa|Asigne la alerta y, a continuación, [investigue más](investigate-alerts.md) .|
   |La alerta es un falso positivo|1. [Clasifique la alerta](#classify-an-alert) como un falso positivo.<br/><br/>2. [Suprima la alerta](#suppress-an-alert).<br/><br/>3. [Cree un indicador](#indicators-for-microsoft-defender-for-endpoint) para Microsoft Defender para punto de conexión.<br/><br/>4. [Envíe un archivo a Microsoft para su análisis](#part-4-submit-a-file-for-analysis).|
   |La alerta es precisa, pero benigna (no importante)|[Clasifique la alerta](#classify-an-alert) como un verdadero positivo y, a continuación, [suprima la alerta](#suppress-an-alert).|

### <a name="classify-an-alert"></a>Clasificación de una alerta

Las alertas se pueden clasificar como falsos positivos o verdaderos positivos en Microsoft 365 Defender. La clasificación de alertas ayuda a entrenar Microsoft Defender para punto de conexión para que, con el tiempo, vea más alertas verdaderas y menos alertas falsas.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Seleccione **Cola de alertas** y, a continuación, seleccione una alerta.

3. Para la alerta seleccionada, seleccione **Actions** **Manage alert (Administrar alerta).**\> Se abre un panel flotante.

4. En la sección **Administrar alerta** , seleccione **Alerta verdadera** o **Alerta falsa**. (Use **la alerta False** para clasificar un falso positivo).

> [!TIP]
> Para obtener más información sobre cómo suprimir alertas, vea [Administrar alertas de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/manage-alerts). Además, si su organización usa un servidor de administración de eventos e información de seguridad (SIEM), asegúrese de definir también allí una regla de supresión.

### <a name="suppress-an-alert"></a>Suprimir una alerta

Si tiene alertas que son falsos positivos o que son verdaderos positivos, pero para eventos que no son importantes, puede suprimir esas alertas en Microsoft 365 Defender. La supresión de alertas ayuda a reducir el ruido en el panel de operaciones de seguridad.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, seleccione **Cola de alertas**.

3. Seleccione una alerta que quiera suprimir para abrir su panel **Detalles** .

4. En el panel **Detalles** , elija los puntos suspensivos (**...**) y, a continuación, **Cree una regla de supresión**.

5. Especifique toda la configuración de la regla de supresión y, a continuación, elija **Guardar**.

> [!TIP]
> ¿Necesita ayuda con las reglas de supresión? Consulte [Suprimir una alerta y crear una nueva regla de supresión](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule).

## <a name="part-2-review-remediation-actions"></a>Parte 2: Revisar las acciones de corrección

[Las acciones de corrección](manage-auto-investigation.md#remediation-actions), como enviar un archivo a poner en cuarentena o detener un proceso, se realizan en entidades (como archivos) que se detectan como amenazas. Varios tipos de acciones de corrección se producen automáticamente mediante la investigación automatizada y Antivirus de Microsoft Defender:

- Poner en cuarentena un archivo
- Eliminación de una clave del Registro
- Eliminación de un proceso
- Detener un servicio
- Deshabilitar un controlador
- Eliminación de una tarea programada

Otras acciones, como iniciar un examen antivirus o recopilar un paquete de investigación, se producen manualmente o a través de [Live Response](live-response.md). Las acciones realizadas a través de Live Response no se pueden deshacer.

Después de revisar las alertas, el siguiente paso es [revisar las acciones de corrección](manage-auto-investigation.md). Si se realizaron acciones como resultado de falsos positivos, puede deshacer la mayoría de los tipos de acciones de corrección. En concreto, puede:

- [Restauración de un archivo en cuarentena desde el Centro de acciones](#restore-a-quarantined-file-from-the-action-center)
- [Deshacer varias acciones a la vez](#undo-multiple-actions-at-one-time)
- [Quite un archivo de la cuarentena en varios dispositivos](#remove-a-file-from-quarantine-across-multiple-devices). y
- [Restaurar archivo de la cuarentena](#restore-file-from-quarantine)

Cuando haya terminado de revisar y deshacer las acciones que se realizaron como resultado de falsos positivos, continúe con [la revisión o definición de exclusiones](#part-3-review-or-define-exclusions).

### <a name="review-completed-actions"></a>Revisar las acciones completadas

1. En el panel de navegación izquierdo del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, haga clic en **Centro de acciones**.

2. Seleccione la pestaña **Historial** para ver una lista de las acciones realizadas.

3. Seleccione un elemento para ver más detalles sobre la acción de corrección que se ha realizado.

### <a name="restore-a-quarantined-file-from-the-action-center"></a>Restauración de un archivo en cuarentena desde el Centro de acciones

1. En el panel de navegación izquierdo del portal de Microsoft 365 Defender, haga clic en **Centro de acciones**.

2. En la pestaña **Historial** , seleccione una acción que quiera deshacer.

3. En el panel flotante, seleccione **Deshacer**. Si la acción no se puede deshacer con este método, no verá un botón **Deshacer** . (Para obtener más información, consulte [Deshacer acciones completadas](manage-auto-investigation.md#undo-completed-actions)).

### <a name="undo-multiple-actions-at-one-time"></a>Deshacer varias acciones a la vez

1. En el panel de navegación izquierdo del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, haga clic en **Centro de acciones**.

2. En la pestaña **Historial** , seleccione las acciones que desea deshacer.

3. En el panel del lado derecho de la pantalla, seleccione **Deshacer**.

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>Eliminación de un archivo de la cuarentena en varios dispositivos

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/autoir-quarantine-file-1.png" alt-text="El archivo de cuarentena" lightbox="images/autoir-quarantine-file-1.png":::

1. En el panel de navegación izquierdo del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, haga clic en **Centro de acciones**.

2. En la pestaña **Historial** , seleccione un archivo que tenga el **archivo de cuarentena** Tipo de acción.

3. En el panel del lado derecho de la pantalla, seleccione **Aplicar a X más instancias de este archivo** y, a continuación, seleccione **Deshacer**.

### <a name="restore-file-from-quarantine"></a>Restaurar archivo de la cuarentena

Puede revertir y quitar un archivo de la cuarentena si ha determinado que está limpio después de una investigación. Ejecute el siguiente comando en cada dispositivo en el que se puso en cuarentena el archivo.

1. Abra un símbolo del sistema con privilegios elevados en el dispositivo:

   1. Vaya a **Inicio** y escriba _cmd_.
   2. Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.

2. Escriba el siguiente comando y presione **Entrar**:

    ```console
    "%ProgramFiles%\Windows Defender\MpCmdRun.exe" -Restore -Name EUS:Win32/CustomEnterpriseBlock -All
    ```

    > [!IMPORTANT]
    > En algunos escenarios, **ThreatName** puede aparecer como `EUS:Win32/CustomEnterpriseBlock!cl`. Defender para punto de conexión restaurará todos los archivos bloqueados personalizados que se pusieron en cuarentena en este dispositivo en los últimos 30 días.
    >
    > Es posible que un archivo que se puso en cuarentena como una posible amenaza de red no se pueda recuperar. Si un usuario intenta restaurar el archivo después de la cuarentena, es posible que no sea accesible. Esto puede deberse a que el sistema ya no tiene credenciales de red para acceder al archivo. Normalmente, esto es el resultado de un inicio de sesión temporal en un sistema o carpeta compartida y los tokens de acceso han expirado.

3. En el panel del lado derecho de la pantalla, seleccione **Aplicar a X más instancias de este archivo** y, a continuación, seleccione **Deshacer**.

## <a name="part-3-review-or-define-exclusions"></a>Parte 3: Revisión o definición de exclusiones

Una exclusión es una entidad, como un archivo o una dirección URL, que se especifica como una excepción a las acciones de corrección. La entidad excluida todavía se puede detectar, pero no se realizan acciones de corrección en esa entidad. Es decir, el archivo o el proceso detectados no se detendrán, se enviarán a cuarentena, se quitarán ni cambiarán por Microsoft Defender para punto de conexión.

Para definir exclusiones entre Microsoft Defender para punto de conexión, realice las tareas siguientes:

- [Definir exclusiones para Antivirus de Microsoft Defender](#exclusions-for-microsoft-defender-antivirus)
- [Crear indicadores de "permitir" para Microsoft Defender para punto de conexión](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Antivirus de Microsoft Defender exclusiones solo se aplican a la protección antivirus, no a otras funcionalidades de Microsoft Defender para punto de conexión. Para excluir archivos en general, use exclusiones para Antivirus de Microsoft Defender e [indicadores personalizados](/microsoft-365/security/defender-endpoint/manage-indicators) para Microsoft Defender para punto de conexión.

Los procedimientos de esta sección describen cómo definir exclusiones e indicadores.

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Exclusiones para Antivirus de Microsoft Defender

En general, no es necesario definir exclusiones para Antivirus de Microsoft Defender. Asegúrese de definir exclusiones con moderación y de que solo incluya los archivos, carpetas, procesos y archivos abiertos por procesos que dan lugar a falsos positivos. Además, asegúrese de revisar periódicamente las exclusiones definidas. Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para definir o editar las exclusiones de antivirus; sin embargo, puede usar otros métodos, como [directiva de grupo](/azure/active-directory-domain-services/manage-group-policy) (consulte [Administrar Microsoft Defender para punto de conexión](manage-mde-post-migration.md).

> [!TIP]
> ¿Necesita ayuda con las exclusiones de antivirus? Consulte [Configuración y validación de exclusiones para exámenes de Antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md).

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>Usar Microsoft Endpoint Manager para administrar exclusiones de antivirus (para directivas existentes)

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija **Antivirus de seguridad** \> de puntos de conexión y, a continuación, seleccione una directiva existente. (Si no tiene una directiva existente o quiere crear una nueva, vaya [al siguiente procedimiento](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).

3. Elija **Propiedades** y, junto a **Configuración**, elija **Editar**.

4. Expanda **Antivirus de Microsoft Defender Exclusiones** y especifique las exclusiones.

5. Elija **Revisar y guardar** y, a continuación, elija **Guardar**.

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>Uso de Microsoft Endpoint Manager para crear una nueva directiva antivirus con exclusiones

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija **Antivirus** \> de seguridad \> **de puntos de conexión** **y crear directiva**.

3. Seleccione una plataforma (como **Windows 10 y versiones posteriores**, **macOS** o **Windows 10 y Windows Server**).

4. En **Perfil**, seleccione **Antivirus de Microsoft Defender exclusiones** y, a continuación, elija **Crear**.

5. Especifique un nombre y una descripción para el perfil y, a continuación, elija **Siguiente**.

6. En la pestaña **Configuración** , especifique las exclusiones de antivirus y, a continuación, elija **Siguiente**.

7. En la pestaña **Etiquetas** de ámbito, si usa etiquetas de ámbito en su organización, especifique las etiquetas de ámbito para la directiva que va a crear. (Consulte [Etiquetas de ámbito](/mem/intune/fundamentals/scope-tags)).

8. En la pestaña **Asignaciones** , especifique los usuarios y grupos a los que se debe aplicar la directiva y, a continuación, elija **Siguiente**. (Si necesita ayuda con las asignaciones, consulte [Asignación de perfiles de usuario y dispositivo en Microsoft Intune](/mem/intune/configuration/device-profile-assign)).

9. En la pestaña **Revisar y crear** , revise la configuración y, a continuación, elija **Crear**.

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Indicadores de Microsoft Defender para punto de conexión

[Los indicadores](/microsoft-365/security/defender-endpoint/manage-indicators) (en concreto, los indicadores de riesgo o IOC) permiten al equipo de operaciones de seguridad definir la detección, prevención y exclusión de entidades. Por ejemplo, puede especificar determinados archivos que se omitirán de los exámenes y las acciones de corrección en Microsoft Defender para punto de conexión. O bien, se pueden usar indicadores para generar alertas para determinados archivos, direcciones IP o direcciones URL.

Para especificar entidades como exclusiones para Microsoft Defender para punto de conexión, cree indicadores "allow" para esas entidades. Estos indicadores de "permitir" en Microsoft Defender para punto de conexión se aplican a la [protección de próxima generación](microsoft-defender-antivirus-in-windows-10.md), [la detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) y la [investigación automatizada & corrección](/microsoft-365/security/defender-endpoint/automated-investigations).

Se pueden crear indicadores "Allow" para:

- [Files](#indicators-for-files)
- [Direcciones IP, direcciones URL y dominios](#indicators-for-ip-addresses-urls-or-domains)
- [Certificados de aplicación](#indicators-for-application-certificates)

:::image type="content" source="images/false-positives-indicators.png" alt-text="Tipos de indicador" lightbox="images/false-positives-indicators.png":::

#### <a name="indicators-for-files"></a>Indicadores de archivos

Al [crear un indicador "allow" para un archivo, como un ejecutable](/microsoft-365/security/defender-endpoint/indicator-file), ayuda a evitar que se bloqueen los archivos que usa la organización. Los archivos pueden incluir archivos ejecutables portátiles (PE), como `.exe` y `.dll` archivos.

Antes de crear indicadores para los archivos, asegúrese de que se cumplen los siguientes requisitos:

- Antivirus de Microsoft Defender está configurado con la protección basada en la nube habilitada (consulte [Administración de la protección basada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))
- La versión de cliente antimalware es 4.18.1901.x o posterior
- Los dispositivos ejecutan Windows 10, versión 1703 o posterior, o Windows 11; Windows Server 2016, o Windows Server 2019 o Windows Server 2022
- La [característica Bloquear o permitir está activada](/microsoft-365/security/defender-endpoint/advanced-features)

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>Indicadores de direcciones IP, direcciones URL o dominios

Al [crear un indicador "allow" para una dirección IP, una dirección URL o un dominio](/microsoft-365/security/defender-endpoint/indicator-ip-domain), ayuda a evitar que se bloqueen los sitios o las direcciones IP que usa la organización.

Antes de crear indicadores para direcciones IP, direcciones URL o dominios, asegúrese de que se cumplen los siguientes requisitos:

- La protección de red en Defender para punto de conexión está habilitada en modo de bloque (consulte [Habilitación de la protección de red](/microsoft-365/security/defender-endpoint/enable-network-protection))
- La versión de cliente antimalware es 4.18.1906.x o posterior
- Los dispositivos ejecutan Windows 10, versión 1709 o posterior, o Windows 11

Los indicadores de red personalizados se activan en el [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). Para más información, consulte [Características avanzadas](/microsoft-365/security/defender-endpoint/advanced-features).

#### <a name="indicators-for-application-certificates"></a>Indicadores de certificados de aplicación

Al [crear un indicador "allow" para un certificado de aplicación](/microsoft-365/security/defender-endpoint/indicator-certificates), ayuda a evitar que se bloqueen las aplicaciones, como las aplicaciones desarrolladas internamente, que la organización usa. `.CER` o `.PEM` se admiten extensiones de archivo.

Antes de crear indicadores para certificados de aplicación, asegúrese de que se cumplen los siguientes requisitos:

- Antivirus de Microsoft Defender está configurado con la protección basada en la nube habilitada (consulte [Administración de la protección basada en la nube](deploy-manage-report-microsoft-defender-antivirus.md)).
- La versión de cliente antimalware es 4.18.1901.x o posterior
- Los dispositivos ejecutan Windows 10, versión 1703 o posterior, o Windows 11; Windows Server 2016, o Windows Server 2019 o Windows Server 2022
- Las definiciones de protección contra virus y amenazas están actualizadas

> [!TIP]
> Al crear indicadores, puede definirlos uno por uno o importar varios elementos a la vez. Tenga en cuenta que hay un límite de 15 000 indicadores para un solo inquilino. Además, es posible que primero deba recopilar ciertos detalles, como la información hash de archivos. Asegúrese de revisar los requisitos previos antes de [crear indicadores](manage-indicators.md).

## <a name="part-4-submit-a-file-for-analysis"></a>Parte 4: Envío de un archivo para su análisis

Puede enviar entidades, como archivos y detecciones sin archivos, a Microsoft para su análisis. Los investigadores de seguridad de Microsoft analizan todos los envíos y sus resultados ayudan a informar Microsoft Defender para punto de conexión funcionalidades de protección contra amenazas. Al iniciar sesión en el sitio de envío, puede realizar un seguimiento de los envíos.

### <a name="submit-a-file-for-analysis"></a>Envío de un archivo para su análisis

Si tiene un archivo que se detectó erróneamente como malintencionado o se perdió, siga estos pasos para enviar el archivo para su análisis.

1. Revise las instrucciones aquí: [Enviar archivos para su análisis](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite el [sitio de envío de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission)y envíe sus archivos).

### <a name="submit-a-fileless-detection-for-analysis"></a>Envío de una detección sin archivos para su análisis

Si se detectó algo como malware en función del comportamiento y no tiene un archivo, puede enviar el `Mpsupport.cab` archivo para su análisis. Puede obtener el archivo *.cab* mediante la herramienta Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) en Windows 10 o Windows 11.

1. Vaya a y, a ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`continuación, ejecute `MpCmdRun.exe` como administrador.

2. Escriba `mpcmdrun.exe -GetFiles`y, a continuación, presione **Entrar**.

   Se genera un archivo .cab que contiene varios registros de diagnóstico. La ubicación del archivo se especifica en la salida del símbolo del sistema. De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.

3. Revise las instrucciones aquí: [Enviar archivos para su análisis](/windows/security/threat-protection/intelligence/submission-guide).

4. Visite el [sitio de envío de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission) (https://www.microsoft.com/wdsi/filesubmission)y envíe los archivos de .cab.

### <a name="what-happens-after-a-file-is-submitted"></a>¿Qué ocurre después de enviar un archivo?

Nuestros sistemas examinan inmediatamente su envío para proporcionarle la determinación más reciente incluso antes de que un analista empiece a controlar su caso. Es posible que un analista ya haya enviado y procesado un archivo. En esos casos, se determina rápidamente.

En el caso de los envíos que aún no se han procesado, se priorizan para el análisis como se indica a continuación:

- Los archivos frecuentes con el potencial de afectar a un gran número de equipos tienen una prioridad más alta.
- A los clientes autenticados, especialmente a los clientes [empresariales con identificadores de Software Assurance (SAID) válidos](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), se les da una prioridad más alta.
- Los envíos marcados como de alta prioridad por los titulares de SAID reciben atención inmediata.

Para comprobar si hay actualizaciones relacionadas con el envío, inicie sesión en el [sitio de envío de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission).

> [!TIP]
> Para obtener más información, consulte [Envío de archivos para su análisis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions).

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>Parte 5: Revisión y ajuste de la configuración de protección contra amenazas

Microsoft Defender para punto de conexión ofrece una amplia variedad de opciones, incluida la capacidad de ajustar la configuración para diversas características y funcionalidades. Si recibe numerosos falsos positivos, asegúrese de revisar la configuración de protección contra amenazas de su organización. Es posible que deba realizar algunos ajustes en:

- [Protección entregada en la nube](#cloud-delivered-protection)
- [Corrección para aplicaciones potencialmente no deseadas](#remediation-for-potentially-unwanted-applications)
- [Investigación y corrección automatizadas](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>Protección entregada en la nube

Compruebe el nivel de protección entregado en la nube para obtener Antivirus de Microsoft Defender. De forma predeterminada, la protección entregada en la nube se establece en **No configurado**, que corresponde a un nivel normal de protección para la mayoría de las organizaciones. Si la protección entregada en la nube se establece en **Tolerancia alta**, **alta** o **cero**, puede experimentar un mayor número de falsos positivos.

> [!TIP]
> Para más información sobre cómo configurar la protección entregada en la nube, consulte [Especificación del nivel de protección entregado en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).

Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para editar o establecer la configuración de protección proporcionada en la nube; sin embargo, puede usar otros métodos, como [directiva de grupo](/azure/active-directory-domain-services/manage-group-policy) (consulte [Administración de Microsoft Defender para punto de conexión](manage-mde-post-migration.md).

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>Use Microsoft Endpoint Manager para revisar y editar la configuración de protección entregada en la nube (para directivas existentes)

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija **Antivirus de seguridad** \> de puntos de conexión y, a continuación, seleccione una directiva existente. (Si no tiene una directiva existente o quiere crear una nueva, vaya [al siguiente procedimiento](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).

3. En **Administrar**, seleccione **Propiedades**. A continuación, junto a **Configuración,** elija **Editar**.

4. Expanda **Protección** en la nube y revise la configuración actual en la fila **Nivel de protección entregado** en la nube. Se recomienda establecer la protección de entrega en la nube en **No configurada**, lo que proporciona una protección sólida y, al mismo tiempo, reduce las posibilidades de obtener falsos positivos.

5. Elija **Revisar y guardar** y, a continuación, **Guardar**.

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>Use Microsoft Endpoint Manager para establecer la configuración de protección entregada en la nube (para una nueva directiva)

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija **Antivirus** \> de seguridad \> **de punto de conexión** **+ Crear directiva**.

3. En **Plataforma**, seleccione una opción y, a continuación, en **Perfil**, seleccione **Antivirus** o **Antivirus de Microsoft Defender** (la opción específica depende de lo que haya seleccionado para **Plataforma**). A continuación, elija **Crear**.

4. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción para la directiva. A continuación, elija **Siguiente**.

5. En la pestaña **Configuración** , expanda Protección en la **nube** y especifique los valores siguientes:

   - Establezca **Activar la protección entregada en la nube en** **Sí**.
   - Establezca **Nivel de protección proporcionada en la nube** en **Sin configurar**. (Este nivel proporciona un alto nivel de protección de forma predeterminada, a la vez que reduce las posibilidades de obtener falsos positivos).

6. En la pestaña **Etiquetas** de ámbito, si usa etiquetas de ámbito en su organización, especifique etiquetas de ámbito para la directiva. (Consulte [Etiquetas de ámbito](/mem/intune/fundamentals/scope-tags)).

7. En la pestaña **Asignaciones** , especifique los usuarios y grupos a los que se debe aplicar la directiva y, a continuación, elija **Siguiente**. (Si necesita ayuda con las asignaciones, consulte [Asignación de perfiles de usuario y dispositivo en Microsoft Intune](/mem/intune/configuration/device-profile-assign)).

8. En la pestaña **Revisar y crear** , revise la configuración y, a continuación, elija **Crear**.

### <a name="remediation-for-potentially-unwanted-applications"></a>Corrección para aplicaciones potencialmente no deseadas

Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que los dispositivos se ejecuten lentamente, muestren anuncios inesperados o instalen otro software que podría ser inesperado o no deseado. Algunos ejemplos de PUA son el software de publicidad, el software de agrupación y el software de evasión que se comporta de manera diferente con los productos de seguridad. Aunque PUA no se considera malware, algunos tipos de software son PUA en función de su comportamiento y reputación.

> [!TIP]
> Para obtener más información sobre PUA, consulte [Detección y bloqueo de aplicaciones potencialmente no deseadas](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).

En función de las aplicaciones que use su organización, es posible que obtenga falsos positivos como resultado de la configuración de protección de PUA. Si es necesario, considere la posibilidad de ejecutar la protección de PUA en modo de auditoría durante un tiempo o aplicar la protección pua a un subconjunto de dispositivos de la organización. La protección pua se puede configurar para el explorador Microsoft Edge y para Antivirus de Microsoft Defender.

Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para editar o establecer la configuración de protección de PUA; sin embargo, puede usar otros métodos, como [directiva de grupo](/azure/active-directory-domain-services/manage-group-policy) (consulte [Administrar Microsoft Defender para punto de conexión](manage-mde-post-migration.md).

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>Uso de Microsoft Endpoint Manager para editar la protección de PUA (para perfiles de configuración existentes)

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija Perfiles **de configuración de** **dispositivos** \> y, a continuación, seleccione una directiva existente. (Si no tiene una directiva existente o quiere crear una nueva, vaya [al siguiente procedimiento](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)).

3. En **Administrar**, elija **Propiedades** y, después, junto a **Configuración**, elija **Editar**.

4. En la pestaña **Configuración**, desplácese hacia abajo y expanda **Antivirus de Microsoft Defender**.

5. Establezca **Detectar aplicaciones potencialmente no deseadas** en **Auditar**. (Puede desactivarlo, pero mediante el modo de auditoría, podrá ver las detecciones).

6. Elija **Revisar y guardar** y, a continuación, elija **Guardar**.

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>Use Microsoft Endpoint Manager para establecer la protección pua (para un nuevo perfil de configuración)

1. Vaya al centro de administración de Microsoft Endpoint Manager (<https://endpoint.microsoft.com>) e inicie sesión.

2. Elija Perfiles **de configuración de** \> **dispositivos** \> **+ Crear perfil**.

3. En **Plataforma**, elija **Windows 10 y versiones posteriores** y, en **Perfil**, seleccione **Restricciones de dispositivos**.

4. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción para la directiva. A continuación, elija **Siguiente**.

5. En la pestaña **Configuración**, desplácese hacia abajo y expanda **Antivirus de Microsoft Defender**.

6. Establezca **Detectar aplicaciones potencialmente no deseadas** en **Auditar** y, a continuación, elija **Siguiente**. (Puede desactivar la protección pua, pero mediante el modo de auditoría, podrá ver las detecciones).

7. En la pestaña **Asignaciones** , especifique los usuarios y grupos a los que se debe aplicar la directiva y, a continuación, elija **Siguiente**. (Si necesita ayuda con las asignaciones, consulte [Asignación de perfiles de usuario y dispositivo en Microsoft Intune](/mem/intune/configuration/device-profile-assign)).

8. En la pestaña **Reglas de aplicabilidad** , especifique las ediciones o versiones del sistema operativo para incluir o excluir de la directiva. Por ejemplo, puede establecer la directiva para que se aplique a todos los dispositivos determinadas ediciones de Windows 10. A continuación, elija **Siguiente**.

9. En la pestaña **Revisar y crear** , revise la configuración y, a continuación, elija **Crear**.

### <a name="automated-investigation-and-remediation"></a>Investigación y corrección automatizadas

[Las funcionalidades de investigación y corrección automatizadas](automated-investigations.md) (AIR) están diseñadas para examinar alertas y tomar medidas inmediatas para resolver las infracciones. A medida que se desencadenan alertas y se ejecuta una investigación automatizada, se genera un veredicto para cada parte de la evidencia investigada. Los veredictos pueden ser *Malintencionados*, *Sospechosos* o *No se encuentran amenazas*.

En función [del nivel de automatización](/microsoft-365/security/defender-endpoint/automation-levels) establecido para su organización y otras configuraciones de seguridad, se realizan acciones de corrección en artefactos que se consideran *malintencionados* o *sospechosos*. En algunos casos, las acciones de corrección se producen automáticamente; en otros casos, las acciones de corrección se realizan manualmente o solo tras la aprobación del equipo de operaciones de seguridad.

- [Obtenga más información sobre los niveles de automatización](/microsoft-365/security/defender-endpoint/automation-levels); Y entonces
- [Configure las funcionalidades de AIR en Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).

> [!IMPORTANT]
> Se recomienda usar *la automatización completa* para la investigación y la corrección automatizadas. No desactive estas funcionalidades debido a un falso positivo. En su lugar, use [indicadores "allow" para definir excepciones](#indicators-for-microsoft-defender-for-endpoint) y mantenga la investigación y la corrección automatizadas establecidas para realizar acciones adecuadas automáticamente. Siguiendo [esta guía](automation-levels.md#levels-of-automation) ayuda a reducir el número de alertas que debe controlar el equipo de operaciones de seguridad.

## <a name="still-need-help"></a>¿Aún necesita ayuda?

Si ha trabajado en todos los pasos de este artículo y sigue necesitando ayuda, póngase en contacto con el soporte técnico.

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> e inicie sesión.

2. En la esquina superior derecha, seleccione el signo de interrogación (**?**) y, a continuación, seleccione **Soporte técnico de Microsoft**.

3. En la ventana **Asistente de soporte** técnico, describa el problema y envíe el mensaje. Desde allí, puede abrir una solicitud de servicio.

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md) 

## <a name="see-also"></a>Vea también

[Administrar Microsoft Defender para punto de conexión](manage-mde-post-migration.md)

[Introducción al portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
