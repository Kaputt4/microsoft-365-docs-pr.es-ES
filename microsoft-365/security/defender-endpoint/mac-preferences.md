---
title: Establecer preferencias para Microsoft Defender para punto de conexión en Mac
description: Configure Microsoft Defender para punto de conexión en Mac en organizaciones empresariales.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 64b6db32974a7755c46ff4cd87eea87512d8bfc5
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683305"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>Establecer las preferencias para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> Este artículo contiene instrucciones sobre cómo establecer preferencias para Microsoft Defender para punto de conexión en macOS en organizaciones empresariales. Para configurar Microsoft Defender para punto de conexión en macOS mediante la interfaz de línea de comandos, consulte [Recursos](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Resumen

En las organizaciones empresariales, Microsoft Defender para punto de conexión en macOS se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración. Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo. Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para los usuarios sin permisos administrativos.

En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar a trabajar y se proporcionan instrucciones sobre cómo implementar el perfil.

## <a name="configuration-profile-structure"></a>Estructura del perfil de configuración

El perfil de configuración es un archivo *.plist* que consta de entradas identificadas por una clave (que denota el nombre de la preferencia), seguidas de un valor, que depende de la naturaleza de la preferencia. Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.

> [!CAUTION]
>El diseño del perfil de configuración depende de la consola de administración que esté usando. Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF y Intune.

El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para subáreas de Microsoft Defender para punto de conexión, que se explican con más detalle en las secciones siguientes.

### <a name="antivirus-engine-preferences"></a>Preferencias del motor antivirus

La sección *antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para punto de conexión.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|antivirusEngine|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

#### <a name="enforcement-level-for-antivirus-engine"></a>Nivel de cumplimiento para el motor antivirus

Especifica la preferencia de cumplimiento del motor antivirus. Hay tres valores para establecer el nivel de cumplimiento:

- En tiempo real (`real_time`): la protección en tiempo real (examinar archivos a medida que se accede a ellos) está habilitada.
- A petición (`on_demand`): los archivos se examinan solo a petición. En esto:
  - La protección en tiempo real está desactivada.
- Pasivo (`passive`): ejecuta el motor antivirus en modo pasivo. En esto:
  - La protección en tiempo real está desactivada.
  - El examen a petición está activado.
  - La corrección automática de amenazas está desactivada.
  - Las actualizaciones de inteligencia de seguridad están activadas.
  - El icono del menú Estado está oculto.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|enforcementLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|real_time (valor predeterminado) <p> on_demand <p> Pasiva|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.10.72 o posterior.|
|||

#### <a name="configure-file-hash-computation-feature"></a>Configuración de la característica de cálculo de hash de archivos

Habilita o deshabilita la característica de cálculo hash de archivos. Cuando esta característica está habilitada, Defender para punto de conexión calculará los hashes de los archivos que examina. Tenga en cuenta que la habilitación de esta característica podría afectar al rendimiento del dispositivo. Para obtener más información, consulte: [Crear indicadores para archivos](indicator-file.md).

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|enableFileHashComputation|
|**Tipo de datos**|Cadena|
|**Posibles valores**|disabled (valor predeterminado) <p> habilitado|
|**Comentarios**|Disponible en La versión 101.73.77 o posterior de Defender para punto de conexión.|

#### <a name="run-a-scan-after-definitions-are-updated"></a>Ejecución de un examen después de actualizar las definiciones

Especifica si se debe iniciar un examen del proceso después de que se descarguen nuevas actualizaciones de inteligencia de seguridad en el dispositivo. Al habilitar esta configuración, se desencadenará un examen antivirus en los procesos en ejecución del dispositivo.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|scanAfterDefinitionUpdate|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.41.10 o posterior.|
|||

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>Examinar archivos (solo exámenes antivirus a petición)

Especifica si se deben examinar los archivos durante los exámenes antivirus a petición.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|scanArchives|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.41.10 o posterior.|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>Grado de paralelismo para los exámenes a petición

Especifica el grado de paralelismo para los exámenes a petición. Esto corresponde al número de subprocesos utilizados para realizar el examen y afecta al uso de la CPU, así como a la duración del examen a petición.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|maximumOnDemandScanThreads|
|**Tipo de datos**|Entero|
|**Posibles valores**|2 (valor predeterminado). Los valores permitidos son enteros entre 1 y 64.|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.41.10 o posterior.|
|||

#### <a name="exclusion-merge-policy"></a>Directiva de combinación de exclusión

Especifique la directiva de combinación para las exclusiones. Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario (`merge`) o solo exclusiones definidas por el administrador (`admin_only`). Esta configuración se puede usar para impedir que los usuarios locales definan sus propias exclusiones.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|exclusionesMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 100.83.73 o posterior.|
|||

#### <a name="scan-exclusions"></a>Exclusiones de análisis

Especifique las entidades excluidas del análisis. Las exclusiones se pueden especificar mediante rutas de acceso completas, extensiones o nombres de archivo.
(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Exclusiones|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

##### <a name="type-of-exclusion"></a>Tipo de exclusión

Especifique el contenido excluido del análisis por tipo.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|$type|
|**Tipo de datos**|Cadena|
|**Posibles valores**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|||

##### <a name="path-to-excluded-content"></a>Ruta de acceso al contenido excluido

Especifique el contenido excluido del examen por la ruta de acceso completa del archivo.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|ruta de acceso|
|**Tipo de datos**|Cadena|
|**Posibles valores**|rutas de acceso válidas|
|**Comentarios**|Aplicable solo si *$type* está *excluidoPath*|
|||

## <a name="supported-exclusion-types"></a>Tipos de exclusión admitidos

En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para punto de conexión en Mac.

<br>

****

|Exclusión|Definición|Ejemplos|
|---|---|---|
|Extensión de archivo|Todos los archivos con la extensión, en cualquier lugar del dispositivo|`.test`|
|Archivo|Un archivo específico identificado por la ruta de acceso completa|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`|
|Folder|Todos los archivos de la carpeta especificada (de forma recursiva)|`/var/log/` <p> `/var/*/`|
|Proceso|Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él|`/bin/cat` <p> `cat` <p> `c?t`|
||||

> [!IMPORTANT]
> Las rutas de acceso anteriores deben ser vínculos duros, no vínculos simbólicos, para que se excluyan correctamente. Puede comprobar si una ruta de acceso es un vínculo simbólico mediante la ejecución de `file <path-name>`.

Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:

<br>

****

|Carácter comodín|Descripción|Ejemplo|Coincidencias|No coincide|
|---|---|---|---|---|
|\*|Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este carácter comodín dentro de una ruta de acceso, solo sustituirá una carpeta).|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`|
|?|Coincide con cualquier carácter único|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`|
||||||

### <a name="path-type-file--directory"></a>Tipo de ruta de acceso (archivo o directorio)

Indique si la propiedad *path* hace referencia a un archivo o directorio.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|isDirectory|
|**Tipo de datos**|Booleano|
|**Posibles valores**|false (predeterminado) <p> true|
|**Comentarios**|Aplicable solo si *$type* está *excluidoPath*|
|||

### <a name="file-extension-excluded-from-the-scan"></a>Extensión de archivo excluida del examen

Especifique el contenido excluido del análisis por extensión de archivo.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Extensión|
|**Tipo de datos**|Cadena|
|**Posibles valores**|extensiones de archivo válidas|
|**Comentarios**|Solo se aplica si *$type* es *excludedFileExtension*|
|||

### <a name="process-excluded-from-the-scan"></a>Proceso excluido del examen

Especifique un proceso para el que se excluya toda la actividad de archivo del examen. El proceso se puede especificar por su nombre (por ejemplo, `cat`) o por la ruta de acceso completa (por ejemplo, `/bin/cat`).

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|name|
|**Tipo de datos**|Cadena|
|**Posibles valores**|cualquier cadena|
|**Comentarios**|Aplicable solo si *$type* es *excludedFileName*|
|||

#### <a name="allowed-threats"></a>Amenazas permitidas

Especifique amenazas por nombre que Defender para punto de conexión no bloquee en Mac. Estas amenazas podrán ejecutarse.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|allowedThreats|
|**Tipo de datos**|Matriz de cadenas|
|||

#### <a name="disallowed-threat-actions"></a>Acciones de amenazas no permitidas

Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas. Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|disallowedThreatActions|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|allow (impide que los usuarios permitan amenazas) <p> restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 100.83.73 o posterior.|
|||

#### <a name="threat-type-settings"></a>Configuración del tipo de amenaza

Especifique cómo se controlan determinados tipos de amenazas Microsoft Defender para punto de conexión en macOS.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|threatTypeSettings|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

##### <a name="threat-type"></a>Tipo de amenaza

Especifique los tipos de amenaza.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|clave|
|**Tipo de datos**|Cadena|
|**Posibles valores**|potentially_unwanted_application <p> archive_bomb|
|||

##### <a name="action-to-take"></a>Acción que puede realizar

Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior. Seleccione una de las opciones siguientes:

- **Auditoría**: el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.
- **Bloquear**: el dispositivo está protegido contra este tipo de amenaza y se le notifica en la interfaz de usuario y en la consola de seguridad.
- **Desactivado**: el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|valor|
|**Tipo de datos**|Cadena|
|**Posibles valores**|audit (valor predeterminado) <p> Bloquear <p> desactivado|
|||

#### <a name="threat-type-settings-merge-policy"></a>Directiva de combinación de configuración de tipos de amenazas

Especifique la directiva de combinación para la configuración del tipo de amenaza. Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario (`merge`) o solo una configuración definida por el administrador (`admin_only`). Esta configuración se puede usar para impedir que los usuarios locales definan su propia configuración para distintos tipos de amenazas.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|threatTypeSettingsMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 100.83.73 o posterior.|
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Retención del historial de exámenes antivirus (en días)

Especifique el número de días que los resultados se conservan en el historial de exámenes del dispositivo. Los resultados del examen antiguos se quitan del historial. Archivos en cuarentena antiguos que también se quitan del disco.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|scanResultsRetentionDays|
|**Tipo de datos**|Cadena|
|**Posibles valores**|90 (valor predeterminado). Los valores permitidos van de 1 día a 180 días.|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.07.23 o posterior.|
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de elementos en el historial de examen del antivirus

Especifique el número máximo de entradas que se conservarán en el historial de exámenes. Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones antivirus.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|scanHistoryMaximumItems|
|**Tipo de datos**|Cadena|
|**Posibles valores**|10000 (valor predeterminado). Los valores permitidos van de 5000 elementos a 15000 elementos.|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.07.23 o posterior.|
|||

### <a name="cloud-delivered-protection-preferences"></a>Preferencias de protección entregadas en la nube

Configure las características de protección controlada por la nube de Microsoft Defender para punto de conexión en macOS.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|cloudService|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitación o deshabilitación de la protección entregada en la nube

Especifique si se va a habilitar la protección entregada en la nube del dispositivo o no. Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|habilitado|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|||

#### <a name="diagnostic-collection-level"></a>Nivel de recopilación de diagnóstico

Los datos de diagnóstico se usan para mantener Microsoft Defender para punto de conexión seguros y actualizados, detectar, diagnosticar y corregir problemas, y también realizar mejoras en el producto. Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para punto de conexión a Microsoft.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|diagnosticLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|opcional (valor predeterminado) <p> necesario|
|||

#### <a name="configure-cloud-block-level"></a>Configuración del nivel de bloque en la nube

Esta configuración determina el grado de agresividad de Defender para punto de conexión al bloquear y examinar archivos sospechosos. Si esta configuración está activada, Defender para punto de conexión será más agresivo al identificar archivos sospechosos que bloquear y examinar; De lo contrario, será menos agresivo y, por lo tanto, bloqueará y examinará con menos frecuencia. Hay cinco valores para establecer el nivel de bloque en la nube:

- Normal (`normal`): el nivel de bloqueo predeterminado.
- Moderado (`moderate`): solo proporciona veredicto para las detecciones de alta confianza.
- Alto (`high`): bloquea agresivamente los archivos desconocidos al tiempo que optimiza el rendimiento (mayor posibilidad de bloquear archivos no dañinos).
- High Plus (`high_plus`): bloquea agresivamente los archivos desconocidos y aplica medidas de protección adicionales (podrían afectar al rendimiento del dispositivo cliente).
- Tolerancia cero (`zero_tolerance`): bloquea todos los programas desconocidos.

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|cloudBlockLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|normal (valor predeterminado) <p> Moderado <p> Alto <p> high_plus <p> zero_tolerance|
|**Comentarios**|Disponible en Defender para punto de conexión, versión 101.56.62 o posterior.|

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar o deshabilitar envíos de ejemplo automáticos

Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft. Se le pedirá si es probable que el archivo enviado contenga información personal.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|automaticSampleSubmission|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitación o deshabilitación de actualizaciones automáticas de inteligencia de seguridad

Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:

<br>

****

|Sección|Valor|
|---|---|
|**Clave**|automaticDefinitionUpdateEnabled|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|||

### <a name="user-interface-preferences"></a>Preferencias de la interfaz de usuario

Administre las preferencias de la interfaz de usuario de Microsoft Defender para punto de conexión en macOS.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|userInterface|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

#### <a name="show--hide-status-menu-icon"></a>Icono del menú Mostrar u ocultar estado

Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|hideStatusMenuIcon|
|**Tipo de datos**|Booleano|
|**Posibles valores**|false (predeterminado) <p> true|
|||

#### <a name="show--hide-option-to-send-feedback"></a>Opción Mostrar u ocultar para enviar comentarios

Especifique si los usuarios pueden enviar comentarios a Microsoft si van a `Help` > `Send Feedback`.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|userInitiatedFeedback|
|**Tipo de datos**|Cadena|
|**Posibles valores**|enabled (valor predeterminado) <p> deshabilitado|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.19.61 o posterior.|
|||



#### <a name="control-sign-in-to-consumer-version-of-microsoft-defender"></a>Controlar el inicio de sesión en la versión de consumidor de Microsoft Defender

Especifique si los usuarios pueden iniciar sesión en la versión de consumidor de Microsoft Defender.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|consumerExperience|
|**Tipo de datos**|Cadena|
|**Posibles valores**|enabled (valor predeterminado) <p> deshabilitado|
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.60.18 o posterior.|
|||


### <a name="endpoint-detection-and-response-preferences"></a>Preferencias de respuesta y detección de puntos de conexión

Administre las preferencias del componente de detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para punto de conexión en macOS.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|Edr|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

#### <a name="device-tags"></a>Etiquetas de dispositivo

Especifique un nombre de etiqueta y su valor.

- La etiqueta GROUP etiqueta el dispositivo con el valor especificado. La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|tags|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|||

##### <a name="type-of-tag"></a>Tipo de etiqueta

Especifica el tipo de etiqueta

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|clave|
|**Tipo de datos**|Cadena|
|**Posibles valores**|`GROUP`|
|||

##### <a name="value-of-tag"></a>Valor de la etiqueta

Especifica el valor de tag

<br>

****

|Sección|Valor|
|---|---|
|**Dominio**|`com.microsoft.wdav`|
|**Clave**|valor|
|**Tipo de datos**|Cadena|
|**Posibles valores**|cualquier cadena|
|||

> [!IMPORTANT]
>
> - Solo se puede establecer un valor por tipo de etiqueta.
> - El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.

## <a name="recommended-configuration-profile"></a>Perfil de configuración recomendado

Para empezar, se recomienda la siguiente configuración para que su empresa aproveche todas las características de protección que Microsoft Defender para punto de conexión proporciona.

El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que se podría cargar en el perfil de configuración de configuración personalizada):

- Habilitación de la protección en tiempo real (RTP)
- Especifique cómo se controlan los siguientes tipos de amenazas:
  - **Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas
  - **Las bombas de archivo** (archivo con una alta tasa de compresión) se auditan para Microsoft Defender para punto de conexión registros
- Habilitación de actualizaciones automáticas de inteligencia de seguridad
- Habilitar la protección proporcionada en la nube
- Habilitación del envío automático de ejemplos

### <a name="property-list-for-jamf-recommended-configuration-profile"></a>Lista de propiedades para el perfil de configuración recomendado de JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-recommended-profile"></a>Intune perfil recomendado

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enforcementLevel</key>
                    <string>real_time</string>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Ejemplo de perfil de configuración completa

Las plantillas siguientes contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que quiera tener más control sobre Microsoft Defender para punto de conexión en macOS.

### <a name="property-list-for-jamf-full-configuration-profile"></a>Lista de propiedades para el perfil de configuración completo de JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
        <key>scanAfterDefinitionUpdate</key>
        <true/>
        <key>scanArchives</key>
        <true/>
        <key>maximumOnDemandScanThreads</key>
        <integer>2</integer>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-full-profile"></a>Intune perfil completo

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enforcementLevel</key>
                    <string>real_time</string>
                    <key>scanAfterDefinitionUpdate</key>
                    <true/>
                    <key>scanArchives</key>
                    <true/>
                    <key>maximumOnDemandScanThreads</key>
                    <integer>1</integer>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="property-list-validation"></a>Validación de la lista de propiedades

La lista de propiedades debe ser un archivo *.plist* válido. Esto se puede comprobar mediante la ejecución de:

```bash
plutil -lint com.microsoft.wdav.plist
```

```Output
com.microsoft.wdav.plist: OK
```

Si el archivo tiene un formato correcto, el comando anterior genera `OK` y devuelve un código de salida de `0`. De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1`.

## <a name="configuration-profile-deployment"></a>Implementación del perfil de configuración

Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa la empresa. En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil mediante JAMF y Intune.

### <a name="jamf-deployment"></a>Implementación de JAMF

En la consola de JAMF, abra **Perfiles de configuración** de **equipos**\>, vaya al perfil de configuración que desea usar y, a continuación, seleccione **Configuración personalizada**. Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *archivo .plist* generado anteriormente.

> [!CAUTION]
> Debe especificar el dominio de preferencias correcto (`com.microsoft.wdav`); de lo contrario, las preferencias no serán reconocidas por Microsoft Defender para punto de conexión.

### <a name="intune-deployment"></a>Implementación de Intune

1. Abra **Administrar** \> **configuración del dispositivo**. Seleccione **Administrar** \> **perfiles** \> **Crear perfil**.

2. Elija un nombre para el perfil. Cambie **Platform=macOS** a **Profile type=Custom**. Seleccione Configurar.

3. Guarde el archivo .plist generado anteriormente como `com.microsoft.wdav.xml`.

4. Escriba `com.microsoft.wdav` como **el nombre del perfil de configuración personalizado**.

5. Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo. (Este archivo se creó en el paso 3).

6. Seleccione **Aceptar**.

7. Seleccione **Administrar** \> **asignaciones**. En la pestaña **Incluir** , seleccione **Asignar a todos los usuarios & Todos los dispositivos**.

> [!CAUTION]
> Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, estas preferencias no serán reconocidas por Microsoft Defender para punto de conexión.

## <a name="resources"></a>Recursos

- [Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
