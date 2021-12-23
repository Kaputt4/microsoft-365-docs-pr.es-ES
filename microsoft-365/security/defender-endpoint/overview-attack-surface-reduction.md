---
title: Comprender y usar la reducción de superficie de ataque
ms.reviewer: ''
description: Obtenga información sobre las capacidades de reducción de superficie de ataque de Microsoft Defender para endpoint.
keywords: asr, reducción de superficie de ataque, Microsoft Defender para endpoint, microsoft defender, antivirus, av, windows defender
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: asr
ms.topic: conceptual
ms.technology: mde
ms.date: 10/14/2021
ms.openlocfilehash: 05650ab36833f8ea633c9f314fd438cfd0275919
ms.sourcegitcommit: db62fce58867c7e5c8029b66966e792da3103b89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2021
ms.locfileid: "61598454"
---
# <a name="understand-and-use-attack-surface-reduction-capabilities"></a>Comprender y usar las capacidades de reducción de superficie de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Las superficies de ataque son todos los lugares donde su organización es vulnerable a ciberamenazas y ataques. Defender for Endpoint incluye varias funcionalidades para ayudar a reducir las superficies de ataque. Vea el siguiente vídeo para obtener más información sobre la reducción de superficie de ataque.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="configure-attack-surface-reduction-capabilities"></a>Configurar capacidades de reducción de superficie de ataques

Para configurar la reducción de superficie de ataque en el entorno, siga estos pasos:

1. [Habilitar el aislamiento basado en hardware para Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. Habilitar el control de aplicaciones.

   1. Revise las directivas base en Windows. Vea [Ejemplo de directivas base](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).
   2. Consulte la [Windows Defender de diseño del control de aplicaciones](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).
   3. Consulte [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).

3. [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md).

4. [Activar Protección de red](enable-network-protection.md).

5. [Habilitar protección contra vulnerabilidades](enable-exploit-protection.md)de seguridad .

6. [Implementar reglas de reducción de superficie de ataque](attack-surface-reduction-rules-deployment.md).

7. Configurar el firewall de red.

   1. Obtenga una introducción a [Windows Defender Firewall con seguridad avanzada.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
   2. Use la [Windows Defender de diseño del firewall para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) decidir cómo desea diseñar las directivas de firewall.
   3. Use la [Windows Defender de implementación de Firewall para](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) configurar el firewall de su organización con seguridad avanzada.

> [!TIP]
> En la mayoría de los casos, al configurar las capacidades de reducción de superficie de ataque, puedes elegir entre varios métodos:
>
> - Microsoft Endpoint Manager (que ahora incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)
> - Directiva de grupo
> - Cmdlets de PowerShell

## <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Probar la reducción de superficie de ataque en Microsoft Defender para endpoint

Como parte del equipo de seguridad de la organización, puedes configurar las capacidades de reducción de superficie de ataque para que se ejecuten en modo auditoría para ver cómo funcionarán. En el modo de auditoría, puede habilitar:

- Reglas de reducción de la superficie expuesta a ataques
- Protección contra vulnerabilidades de seguridad
- Protección de red
- Acceso controlado a carpetas en modo auditoría

El modo auditoría te permite ver un registro de lo *que hubiera* ocurrido si hubieras habilitado la característica.

Puedes habilitar el modo de auditoría al probar cómo funcionarán las características. Habilitar el modo de auditoría solo para pruebas ayuda a evitar que el modo de auditoría afecte a las aplicaciones de línea de negocio. También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos se producen durante un período de tiempo determinado.

Las características no bloquearán ni impedirán que se modifiquen aplicaciones, scripts o archivos. Sin embargo, el Windows de eventos registrará eventos como si las características estuvieran totalmente habilitadas. Con el modo de auditoría, puedes revisar el registro de eventos para ver qué efecto habría tenido la característica si se hubiera habilitado.

Para buscar las entradas auditadas, vaya a **Aplicaciones y servicios** de \> **Microsoft** \> **Windows** \> **Windows Defender** \> **Operativo**.

Usa Defender para endpoint para obtener más detalles para cada evento. Estos detalles son especialmente útiles para investigar reglas de reducción de superficie de ataque. El uso de la consola defender para endpoint te permite investigar problemas como parte de la escala de tiempo de alerta y [los escenarios de investigación.](investigate-alerts.md)

Puede habilitar el modo de auditoría mediante la directiva de grupo, PowerShell y los proveedores de servicios de configuración (CSP).

> [!TIP]
> También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.

| Opciones de auditoría | Cómo habilitar el modo de auditoría | Cómo ver eventos |
|---|---|---|
| La auditoría se aplica a todos los eventos | [Habilitar el acceso controlado a carpetas](enable-controlled-folders.md) | [Eventos de acceso controlado a carpetas](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer) |
| La auditoría se aplica a reglas individuales | [Paso 1: Probar reglas ASR con Auditoría](attack-surface-reduction-rules-deployment-phase-2.md#step-1-test-asr-rules-using-audit) | [Paso 2: Comprender la página de informes de reglas de reducción de superficie de ataque](attack-surface-reduction-rules-deployment-phase-2.md#step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal) |
| La auditoría se aplica a todos los eventos | [Habilitar la protección de red](enable-network-protection.md) | [Eventos de protección de red](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer) |
| La auditoría se aplica a mitigaciones individuales | [Habilitar la protección contra vulnerabilidades de seguridad](enable-exploit-protection.md) | [Eventos de protección contra vulnerabilidades](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer) |

## <a name="view-attack-surface-reduction-events"></a>Ver eventos de la reducción de la superficie expuesta a ataques

Revisa los eventos de reducción de superficie de ataque en el Visor de eventos para supervisar qué reglas o configuraciones funcionan. También puede determinar si alguna configuración es demasiado "ruidosa" o si afecta al flujo de trabajo diario.

Revisar los eventos es útil al evaluar las características. Puede habilitar el modo de auditoría para las características o la configuración y, a continuación, revisar lo que hubiera ocurrido si estuvieran totalmente habilitadas.

En esta sección se enumeran todos los eventos, su característica o configuración asociada, y se describe cómo crear vistas personalizadas para filtrar a eventos específicos.

Obtenga informes detallados sobre eventos, bloques y advertencias como parte de Seguridad de Windows si tiene una suscripción a E5 y usa [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md).

### <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Usar vistas personalizadas para revisar las capacidades de reducción de superficie de ataque

Cree vistas personalizadas en el Windows de eventos para ver solo eventos para funciones y configuraciones específicas. La forma más sencilla es importar una vista personalizada como un archivo XML. Puede copiar el XML directamente desde esta página.

También puede navegar manualmente hasta el área de eventos que corresponde a la característica.

#### <a name="import-an-existing-xml-custom-view"></a>Importar una vista personalizada XML existente

1. Cree un archivo .txt y copie el XML de la vista personalizada que desea usar en el .txt archivo. Haga esto para cada una de las vistas personalizadas que desee usar. Cambie el nombre de los archivos de la siguiente manera (asegúrese de cambiar el tipo de .txt a .xml):
    - Vista personalizada de eventos de acceso a carpetas *controladas:cfa-events.xml*
    - Vista personalizada de eventos de protección contra *vulnerabilidades:ep-events.xml*
    - Vista personalizada de eventos de reducción de superficie *de ataque:asr-events.xml*
    - Vista personalizada de eventos de *red/protección:np-events.xml*

2. Escriba **el visor de** eventos en el menú Inicio y abra el Visor de **eventos**.

3. Seleccionar **acción** \> **Importar vista personalizada...**

   > [!div class="mx-imgBorder"]
   > ![Animación resaltando Importar vista personalizada a la izquierda de la ventana Visor de par.](images/events-import.gif)

4. Navegue hasta donde extrajo el archivo XML para la vista personalizada que desee y selecciónelo.

5. Seleccione **Abrir**.

6. Creará una vista personalizada que filtra para mostrar solo los eventos relacionados con esa característica.

#### <a name="copy-the-xml-directly"></a>Copiar el XML directamente

1. Escriba **el visor** de eventos en el menú Inicio y abra el Windows de **eventos**.

2. En el panel izquierdo, en **Acciones,** seleccione **Crear vista personalizada...**

   > [!div class="mx-imgBorder"]
   > ![Animación que resalta la opción crear vista personalizada en la ventana Visor de eventos.](images/events-create.gif)

3. Vaya a la pestaña XML y seleccione **Editar consulta manualmente.** Verá una advertencia de que no puede editar  la consulta mediante la pestaña Filtro si usa la opción XML. Seleccione **Sí**.

4. Pegue el código XML de la característica desde la que desea filtrar los eventos en la sección XML.

5. Seleccione **Aceptar**. Especifique un nombre para el filtro. Esto crea una vista personalizada que filtra para mostrar solo los eventos relacionados con esa característica.

#### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML para eventos de regla de reducción de superficie de ataque

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-controlled-folder-access-events"></a>XML para eventos de acceso controlado a carpetas

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-exploit-protection-events"></a>XML para eventos de protección contra vulnerabilidades

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-network-protection-events"></a>XML para eventos de protección de red

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

### <a name="list-of-attack-surface-reduction-events"></a>Lista de eventos de reducción de superficie de ataque

Todos los eventos de reducción de superficie de ataque se encuentran en Registros de aplicaciones y **servicios > Microsoft > Windows** y, a continuación, la carpeta o el proveedor como se muestra en la tabla siguiente.

Puede tener acceso a estos eventos en Windows visor de eventos:

1. Abra el **menú Inicio** y escriba visor **de eventos** y, a continuación, seleccione el resultado del **Visor de** eventos.
2. Expanda Registros de aplicaciones y **servicios > Microsoft > Windows** y, a continuación, vaya a la carpeta que aparece en **Proveedor/origen** en la tabla siguiente.
3. Haga doble clic en el sub elemento para ver los eventos. Desplácese por los eventos para encontrar el que está buscando.

   ![Animación que se muestra con el Visor de eventos.](images/event-viewer.gif)

<br>

****

|Característica|Proveedor u origen|Id. de evento|Descripción|
|---|---|:---:|---|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|1|Auditoría de ACG|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|2|Aplicación de ACG|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|3|No permitir procesos secundarios de auditoría|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|4|No permitir procesos secundarios de bloqueo|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|5|Bloquear auditoría de imágenes de integridad baja|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|6 |Bloquear bloqueo de imágenes de integridad baja|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|7 |Bloquear auditoría de imágenes remota|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|8 |Bloquear bloqueo de imágenes remoto|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|9 |Deshabilitar auditoría de llamadas del sistema de Win32k|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|10|Deshabilitar bloqueo de llamadas del sistema de Win32k|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|11|Auditoría de protección de integridad de código|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|12 |Bloque de protección de integridad de código|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|13|Auditoría de EAF|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|14 |Aplicación de EAF|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|15 |Auditoría de EAF+|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|16|Aplicación de EAF+|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|17 |Auditoría de IAF|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|18 |Aplicación de IAF|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|19|Auditoría ROP StackPivot|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|20|Aplicación de ROP StackPivot|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)| 21|Auditoría ROP CallerCheck|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|22|Aplicación de ROP CallerCheck|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|23|Auditoría de ROP SimExec|
|Protección contra vulnerabilidades de seguridad|Security-Mitigations (modo kernel/modo de usuario)|24|Aplicación de ROP SimExec|
|Protección contra vulnerabilidades de seguridad|Diagnósticos WER|5|Bloque CFG|
|Protección contra vulnerabilidades de seguridad|Win32K (operativo)|260|Fuente que no es de confianza|
|Protección de red|Windows Defender (operativo)|5007|Evento cuando se cambia la configuración|
|Protección de red|Windows Defender (operativo)|1125|Evento cuando la protección de red se dispara en modo auditoría|
|Protección de red|Windows Defender (operativo)|1126|Evento cuando la protección de red se dispara en modo de bloqueo|
|Acceso controlado a carpetas|Windows Defender (operativo)|5007|Evento cuando se cambia la configuración|
|Acceso controlado a carpetas|Windows Defender (operativo)|1124|Evento de acceso a carpetas controladas auditadas|
|Acceso controlado a carpetas|Windows Defender (operativo)|1123|Evento de acceso a carpetas controladas bloqueadas|
|Acceso controlado a carpetas|Windows Defender (operativo)|1127|Evento de bloque de escritura del sector de acceso controlado a carpetas bloqueadas|
|Acceso controlado a carpetas|Windows Defender (operativo)|1128|Evento de bloque de escritura auditado del sector de acceso controlado a carpetas|
|Reducción de la superficie expuesta a ataques|Windows Defender (operativo)|5007|Evento cuando se cambia la configuración|
|Reducción de la superficie expuesta a ataques|Windows Defender (operativo)|1122|Evento cuando la regla se dispara en modo auditoría|
|Reducción de la superficie expuesta a ataques|Windows Defender (operativo)|1121|Evento cuando la regla se dispara en modo bloque|

>[!NOTE]
> Desde el punto de vista del usuario, las notificaciones del modo de advertencia ASR se realizan como una notificación Windows notificación del sistema para las reglas de reducción de superficie de ataque.
>
> En ASR, Network Protection solo proporciona los modos Audit y Block.

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>Recursos para obtener más información sobre la reducción de superficie de ataque

Como se mencionó en el vídeo, Defender for Endpoint incluye varias funcionalidades de reducción de superficie de ataque. Use los siguientes recursos para obtener más información:

| Artículo | Descripción |
|:---|:---|
| [Aislamiento basado en hardware](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | Proteger y mantener la integridad de un sistema cuando se inicia y mientras se ejecuta. Validar la integridad del sistema mediante la atestación local y remota. Use el aislamiento de contenedores Microsoft Edge para ayudar a proteger contra sitios web malintencionados. |
| [Control de la aplicación](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | Use el control de aplicaciones para que las aplicaciones deben ganar confianza para poder ejecutarse. |
| [Acceso controlado a carpetas](controlled-folders.md) | Ayudar a evitar que las aplicaciones malintencionadas o sospechosas (incluido el malware ransomware cifrado de archivos) realicen cambios en los archivos de las carpetas clave del sistema (requiere Antivirus de Microsoft Defender) |
| [Protección de red](network-protection.md) | Amplíe la protección al tráfico de red y la conectividad en los dispositivos de su organización. (Requiere Antivirus de Microsoft Defender) |
| [Protección contra vulnerabilidades de seguridad](exploit-protection.md) | Ayude a proteger los sistemas operativos y las aplicaciones que usa su organización para evitar que se aprovechen. La protección contra vulnerabilidades de seguridad también funciona con soluciones antivirus de terceros. |
| [Reglas de la reducción de la superficie expuesta a ataques](attack-surface-reduction.md) | Reduzca los puntos vulnerables (las superficies de ataque) en sus aplicaciones con reglas inteligentes que le ayudarán a detener el malware. (Requiere Antivirus de Microsoft Defender). |
| [Control de dispositivos](device-control-report.md) | Protege contra la pérdida de datos mediante la supervisión y el control de los medios usados en dispositivos, como el almacenamiento extraíble y las unidades USB, en la organización. |
