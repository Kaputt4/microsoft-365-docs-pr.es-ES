---
title: Establecer preferencias para Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe cómo configurar Microsoft Defender para Endpoint en Linux en empresas.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 9620fd5209bb72617cf41b6b9aff48f39d607b61
ms.sourcegitcommit: a15ea6bc8f60895e791a08a5a88d346c6581ea38
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2021
ms.locfileid: "61144996"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Establecer preferencias para Microsoft Defender para endpoint en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> Este tema contiene instrucciones sobre cómo establecer las preferencias de Defender para Endpoint en Linux en entornos empresariales. Si estás interesado en configurar el producto en un dispositivo desde la línea de comandos, consulta [Recursos](linux-resources.md#configure-from-the-command-line).

En entornos empresariales, Defender para Endpoint en Linux se puede administrar a través de un perfil de configuración. Este perfil se implementa desde la herramienta de administración que prefiera. Las preferencias administradas por la empresa tienen prioridad sobre las establecidas localmente en el dispositivo. En otras palabras, los usuarios de su empresa no pueden cambiar las preferencias que se establecen a través de este perfil de configuración.

En este artículo se describe la estructura de este perfil (incluido un perfil recomendado que puede usar para empezar) e instrucciones sobre cómo implementar el perfil.

## <a name="configuration-profile-structure"></a>Estructura de perfiles de configuración

El perfil de configuración es un archivo .json que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia. Los valores pueden ser simples, como un valor numérico o complejos, como una lista anidada de preferencias.

Normalmente, se usa una herramienta de administración de configuración para insertar un archivo con el nombre ```mdatp_managed.json``` en la ubicación ```/etc/opt/microsoft/mdatp/managed/``` .

El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas del producto, que se explican con más detalle en las secciones siguientes.

### <a name="antivirus-engine-preferences"></a>Preferencias del motor antivirus

La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus del producto.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|antivirusEngine|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

#### <a name="enable--disable-real-time-protection"></a>Habilitar o deshabilitar la protección en tiempo real

Determina si la protección en tiempo real (archivos de examen a medida que se accede a ellos) está habilitada.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|enableRealTimeProtection|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|

#### <a name="enable--disable-passive-mode"></a>Habilitar o deshabilitar el modo pasivo

Determina si el motor antivirus se ejecuta en modo pasivo o no. En modo pasivo:

- La protección en tiempo real está desactivada.
- El examen a petición está activado.
- La corrección automática de amenazas está desactivada.
- Las actualizaciones de inteligencia de seguridad están activadas.
- El icono del menú Estado está oculto.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|passiveMode|
|**Tipo de datos**|Booleano|
|**Posibles valores**|false (predeterminado) <p> true|
|**Comments**|Disponible en Defender para endpoint versión 100.67.60 o posterior.|
|


#### <a name="enabledisable-behavior-monitoring"></a>Habilitar o deshabilitar la supervisión del comportamiento 

Determina si la funcionalidad de bloqueo y supervisión de comportamiento está habilitada en el dispositivo o no.Para mejorar la eficacia de la protección de seguridad, se recomienda mantener activada esta característica.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|behaviorMonitoring|
|**Tipo de datos**|Cadena|
|**Posibles valores**|deshabilitado <p> habilitado (predeterminado)|
|**Comments**|Disponible en Defender para endpoint versión 101.45.00 o posterior.|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>Ejecutar un examen después de actualizar las definiciones

Especifica si se debe iniciar un examen de proceso después de que se descarguen nuevas actualizaciones de inteligencia de seguridad en el dispositivo. Al habilitar esta configuración, se desencadenará un examen antivirus en los procesos en ejecución del dispositivo.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanAfterDefinitionUpdate|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|**Comments**|Disponible en Defender para endpoint versión 101.45.00 o posterior.|
|

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>Examinar archivos (solo exámenes antivirus a petición)

Especifica si se deben examinar los archivos durante los exámenes antivirus a petición.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanArchives|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|**Comments**|Disponible en Microsoft Defender para endpoint versión 101.45.00 o posterior.|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>Grado de paralelismo para exámenes a petición

Especifica el grado de paralelismo de los exámenes a petición. Esto corresponde al número de subprocesos usados para realizar el examen y afecta al uso de la CPU, así como a la duración del examen a petición.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|maximumOnDemandScanThreads|
|**Tipo de datos**|Entero|
|**Posibles valores**|2 (valor predeterminado). Los valores permitidos son enteros entre 1 y 64.|
|**Comments**|Disponible en Microsoft Defender para endpoint versión 101.45.00 o posterior.|
|||
  

#### <a name="exclusion-merge-policy"></a>Directiva de combinación de exclusión

Especifica la directiva de combinación para exclusiones. Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ). Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|exclusionsMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comments**|Disponible en Defender para endpoint versión 100.83.73 o posterior.|
|

#### <a name="scan-exclusions"></a>Exclusiones de análisis

Entidades que se han excluido del examen. Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.
(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|exclusiones|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

##### <a name="type-of-exclusion"></a>Tipo de exclusión

Especifica el tipo de contenido excluido del examen.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|$type|
|**Tipo de datos**|Cadena|
|**Posibles valores**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|

##### <a name="path-to-excluded-content"></a>Ruta de acceso al contenido excluido

Se usa para excluir contenido del examen por ruta de acceso de archivo completa.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|path|
|**Tipo de datos**|Cadena|
|**Posibles valores**|rutas de acceso válidas|
|**Comments**|Aplicable solo *si $type* *se excluyePath*|
|

##### <a name="path-type-file--directory"></a>Tipo de ruta de acceso (archivo/directorio)

Indica si la *propiedad path* hace referencia a un archivo o directorio.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|isDirectory|
|**Tipo de datos**|Booleano|
|**Posibles valores**|false (predeterminado) <p> true|
|**Comments**|Aplicable solo *si $type* *se excluyePath*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>Extensión de archivo excluida del examen

Se usa para excluir contenido del examen por extensión de archivo.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|extensión|
|**Tipo de datos**|Cadena|
|**Posibles valores**|extensiones de archivo válidas|
|**Comments**|Aplicable solo *si $type* *se excluyeFileExtension*|
|

##### <a name="process-excluded-from-the-scan"></a>Proceso excluido del examen*

Especifica un proceso para el que se excluye toda la actividad de archivo del examen. El proceso se puede especificar por su nombre (por ejemplo, ) o la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|name|
|**Tipo de datos**|Cadena|
|**Posibles valores**|cualquier cadena|
|**Comments**|Aplicable solo *si $type* *se excluyeFileName*|
|

#### <a name="allowed-threats"></a>Amenazas permitidas

Lista de amenazas (identificadas por su nombre) que no están bloqueadas por el producto y que en su lugar pueden ejecutarse.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|allowedThreats|
|**Tipo de datos**|Matriz de cadenas|
|

#### <a name="disallowed-threat-actions"></a>Acciones de amenazas no permitidas

Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas. Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|disallowedThreatActions|
|**Tipo de datos**|Matriz de cadenas|
|**Posibles valores**|permitir (restringe a los usuarios permitir amenazas) <p> restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)|
|**Comments**|Disponible en Defender para endpoint versión 100.83.73 o posterior.|
|

#### <a name="threat-type-settings"></a>Configuración del tipo de amenaza

La *preferencia threatTypeSettings* en el motor antivirus se usa para controlar cómo el producto controla determinados tipos de amenazas.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|threatTypeSettings|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

##### <a name="threat-type"></a>Tipo de amenaza

Tipo de amenaza para la que se configura el comportamiento.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|clave|
|**Tipo de datos**|Cadena|
|**Posibles valores**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>Acción que puede realizar

Acción que se debe realizar al encontrarse con una amenaza del tipo especificado en la sección anterior. Puede ser:

- **Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.
- **Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la consola de seguridad.
- **Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|valor|
|**Tipo de datos**|Cadena|
|**Posibles valores**|auditoría (valor predeterminado) <p> bloque <p> off|
|

#### <a name="threat-type-settings-merge-policy"></a>Directiva de combinación de configuración de tipo de amenaza

Especifica la directiva de combinación para la configuración del tipo de amenaza. Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ). Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|threatTypeSettingsMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comments**|Disponible en Defender para endpoint versión 100.83.73 o posterior.|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>Retención del historial de examen antivirus (en días)

Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo. Los resultados del examen antiguos se quitan del historial. Archivos antiguos en cuarentena que también se quitan del disco.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanResultsRetentionDays|
|**Tipo de datos**|Cadena|
|**Posibles valores**|90 (valor predeterminado). Los valores permitidos van de 1 día a 180 días.|
|**Comments**|Disponible en Defender para endpoint versión 101.04.76 o posterior.|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de elementos en el historial de examen antivirus

Especifique el número máximo de entradas que se deben conservar en el historial de examen. Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanHistoryMaximumItems|
|**Tipo de datos**|Cadena|
|**Posibles valores**|10000 (valor predeterminado). Los valores permitidos van de 5000 elementos a 15000 elementos.|
|**Comments**|Disponible en Defender para endpoint versión 101.04.76 o posterior.|
|

### <a name="cloud-delivered-protection-preferences"></a>Preferencias de protección entregadas en la nube

La *entrada cloudService* en el perfil de configuración se usa para configurar la característica de protección controlada por la nube del producto.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|cloudService|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Vea las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitar o deshabilitar la protección de entrega en la nube

Determina si la protección entregada en la nube está habilitada en el dispositivo o no. Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|habilitado|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|

#### <a name="diagnostic-collection-level"></a>Nivel de recopilación de diagnóstico

Los datos de diagnóstico se usan para mantener Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto. Esta configuración determina el nivel de diagnóstico enviado por el producto a Microsoft.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|diagnosticLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|opcional (predeterminado) <p> necesario|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar o deshabilitar envíos de ejemplo automáticos

Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft. Existen tres niveles para controlar el envío de muestra:

- **Ninguno:** no se envían muestras sospechosas a Microsoft.
- **Caja fuerte:** solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII). Este es el valor predeterminado para esta configuración.
- **All**: todas las muestras sospechosas se envían a Microsoft.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|automaticSampleSubmissionConsent|
|**Tipo de datos**|Cadena|
|**Posibles valores**|ninguno <p> safe (valor predeterminado) <p> all|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad

Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|automaticDefinitionUpdateEnabled|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|

## <a name="recommended-configuration-profile"></a>Perfil de configuración recomendado

Para empezar, recomendamos el siguiente perfil de configuración para que la empresa aproveche todas las características de protección que proporciona Defender for Endpoint.

El siguiente perfil de configuración será:

- Habilitar la protección en tiempo real (RTP)
- Especifique cómo se controlan los siguientes tipos de amenazas:
  - **Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas
  - **Las bomba de archivo** (archivo con una tasa de compresión alta) se auditan en los registros del producto
- Habilitar actualizaciones automáticas de inteligencia de seguridad
- Habilitar la protección proporcionada en la nube
- Habilitar el envío automático de muestra en `safe` el nivel
- Habilitar la supervisión del comportamiento

### <a name="sample-profile"></a>Perfil de ejemplo

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Ejemplo de perfil de configuración completa

El siguiente perfil de configuración contiene entradas para todas las opciones descritas en este documento y se puede usar para escenarios más avanzados en los que desea tener más control sobre el producto.

### <a name="full-profile"></a>Perfil completo

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enableRealTimeProtection":true,
      "scanAfterDefinitionUpdate":true,
      "scanArchives":true,
      "maximumOnDemandScanThreads":2,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "<EXAMPLE DO NOT USE>EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Validación de perfiles de configuración

El perfil de configuración debe ser un archivo con formato JSON válido. Hay varias herramientas que se pueden usar para comprobar esto. Por ejemplo, si has `python` instalado en el dispositivo:

```bash
python -m json.tool mdatp_managed.json
```

Si el JSON está bien formado, el comando anterior lo devuelve al Terminal y devuelve un código de salida de `0` . De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Comprobar que el archivo mdatp_managed.json funciona de la forma esperada

Para comprobar que el /etc/opt/microsoft/mdatp/managed/mdatp_managed.json funciona correctamente, debería ver "[administrado]" junto a esta configuración:

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Para que mdatp_managed.json entre en vigor, no es necesario reiniciar el wdavdaemon.

## <a name="configuration-profile-deployment"></a>Implementación de perfiles de configuración

Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la herramienta de administración que usa su empresa. Defender para Endpoint en Linux lee la configuración administrada del archivo */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*
