---
title: Establecer preferencias para Microsoft Defender para punto de conexión en Linux
ms.reviewer: ''
description: Describe cómo configurar Microsoft Defender para punto de conexión en Linux en empresas.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 2bc051baa8d2ac6df9e29f1679402e63c2774cac
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679316"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Establecer preferencias para Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> Este tema contiene instrucciones sobre cómo establecer preferencias para Defender para punto de conexión en Linux en entornos empresariales. Si está interesado en configurar el producto en un dispositivo desde la línea de comandos, consulte [Recursos](linux-resources.md#configure-from-the-command-line).

En entornos empresariales, Defender para punto de conexión en Linux se puede administrar a través de un perfil de configuración. Este perfil se implementa desde la herramienta de administración que prefiera. Las preferencias administradas por la empresa tienen prioridad sobre las establecidas localmente en el dispositivo. Es decir, los usuarios de la empresa no pueden cambiar las preferencias establecidas a través de este perfil de configuración.

En este artículo se describe la estructura de este perfil (incluido un perfil recomendado que puede usar para empezar) e instrucciones sobre cómo implementar el perfil.

## <a name="configuration-profile-structure"></a>Estructura del perfil de configuración

El perfil de configuración es un archivo .json que consta de entradas identificadas por una clave (que denota el nombre de la preferencia), seguidas de un valor, que depende de la naturaleza de la preferencia. Los valores pueden ser simples, como un valor numérico o complejos, como una lista anidada de preferencias.

Normalmente, usaría una herramienta de administración de configuración para insertar un archivo con el nombre ```mdatp_managed.json``` en la ubicación ```/etc/opt/microsoft/mdatp/managed/```.

El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para subáreas del producto, que se explican con más detalle en las secciones siguientes.

### <a name="antivirus-engine-preferences"></a>Preferencias del motor antivirus

La sección *antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus del producto.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|antivirusEngine|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comentarios**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

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

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|enforcementLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|real_time (valor predeterminado) <p> on_demand <p> Pasiva|
|**Comentarios**|Disponible en Defender para punto de conexión, versión 101.10.72 o posterior.|
|


#### <a name="enabledisable-behavior-monitoring"></a>Habilitar o deshabilitar la supervisión del comportamiento 

Determina si la funcionalidad de bloqueo y supervisión del comportamiento está habilitada en el dispositivo o no. Para mejorar la eficacia de la protección de seguridad, se recomienda mantener activada esta característica.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|behaviorMonitoring|
|**Tipo de datos**|Cadena|
|**Posibles valores**|disabled (valor predeterminado) <p> habilitado |
|**Comments**|Disponible en Defender para punto de conexión, versión 101.45.00 o posterior.|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>Ejecución de un examen después de actualizar las definiciones

Especifica si se debe iniciar un examen del proceso después de que se descarguen nuevas actualizaciones de inteligencia de seguridad en el dispositivo. Al habilitar esta configuración, se desencadenará un examen antivirus en los procesos en ejecución del dispositivo.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanAfterDefinitionUpdate|
|**Tipo de datos**|Booleano|
|**Posibles valores**|true (valor predeterminado) <p> false|
|**Comentarios**|Disponible en Defender para punto de conexión, versión 101.45.00 o posterior.|
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
|**Comentarios**|Disponible en Microsoft Defender para punto de conexión versión 101.45.00 o posterior.|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>Grado de paralelismo para los exámenes a petición

Especifica el grado de paralelismo para los exámenes a petición. Esto corresponde al número de subprocesos utilizados para realizar el examen y afecta al uso de la CPU, así como a la duración del examen a petición.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|maximumOnDemandScanThreads|
|**Tipo de datos**|Entero|
|**Posibles valores**|2 (valor predeterminado). Los valores permitidos son enteros entre 1 y 64.|
|**Comments**|Disponible en Microsoft Defender para punto de conexión versión 101.45.00 o posterior.|
|||
  

#### <a name="exclusion-merge-policy"></a>Directiva de combinación de exclusión

Especifica la directiva de combinación para exclusiones. Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario (`merge`) o solo exclusiones definidas por el administrador (`admin_only`). Esta configuración se puede usar para impedir que los usuarios locales definan sus propias exclusiones.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|exclusionesMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comentarios**|Disponible en La versión 100.83.73 o posterior de Defender para punto de conexión.|
|

#### <a name="scan-exclusions"></a>Exclusiones de análisis

Entidades que se han excluido del examen. Las exclusiones se pueden especificar mediante rutas de acceso completas, extensiones o nombres de archivo.
(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|Exclusiones|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
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

Se usa para excluir contenido del examen por ruta de acceso completa del archivo.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|ruta de acceso|
|**Tipo de datos**|Cadena|
|**Posibles valores**|rutas de acceso válidas|
|**Comentarios**|Aplicable solo si *$type* está *excluidoPath*|
|

##### <a name="path-type-file--directory"></a>Tipo de ruta de acceso (archivo o directorio)

Indica si la propiedad *path* hace referencia a un archivo o directorio.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|isDirectory|
|**Tipo de datos**|Booleano|
|**Posibles valores**|false (predeterminado) <p> true|
|**Comentarios**|Aplicable solo si *$type* está *excluidoPath*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>Extensión de archivo excluida del examen

Se usa para excluir contenido del examen por extensión de archivo.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|Extensión|
|**Tipo de datos**|Cadena|
|**Posibles valores**|extensiones de archivo válidas|
|**Comentarios**|Solo se aplica si *$type* es *excludedFileExtension*|
|

##### <a name="process-excluded-from-the-scan"></a>Proceso excluido del examen*

Especifica un proceso para el que toda la actividad de archivo se excluye del examen. El proceso se puede especificar por su nombre (por ejemplo, `cat`) o por la ruta de acceso completa (por ejemplo, `/bin/cat`).

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|name|
|**Tipo de datos**|Cadena|
|**Posibles valores**|cualquier cadena|
|**Comentarios**|Aplicable solo si *$type* es *excludedFileName*|
|

#### <a name="allowed-threats"></a>Amenazas permitidas

Lista de amenazas (identificadas por su nombre) que no están bloqueadas por el producto y que, en su lugar, pueden ejecutarse.

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
|**Posibles valores**|allow (impide que los usuarios permitan amenazas) <p> restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)|
|**Comments**|Disponible en La versión 100.83.73 o posterior de Defender para punto de conexión.|
|

#### <a name="threat-type-settings"></a>Configuración del tipo de amenaza

La preferencia *threatTypeSettings* en el motor antivirus se usa para controlar cómo el producto controla determinados tipos de amenazas.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|threatTypeSettings|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

##### <a name="threat-type"></a>Tipo de amenaza

Tipo de amenaza para la que está configurado el comportamiento.

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

- **Auditoría**: el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.
- **Bloquear**: el dispositivo está protegido contra este tipo de amenaza y se le notifica en la consola de seguridad.
- **Desactivado**: el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|valor|
|**Tipo de datos**|Cadena|
|**Posibles valores**|audit (valor predeterminado) <p> Bloquear <p> desactivado|
|

#### <a name="threat-type-settings-merge-policy"></a>Directiva de combinación de configuración de tipos de amenazas

Especifica la directiva de combinación para la configuración del tipo de amenaza. Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario (`merge`) o solo una configuración definida por el administrador (`admin_only`). Esta configuración se puede usar para impedir que los usuarios locales definan su propia configuración para distintos tipos de amenazas.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|threatTypeSettingsMergePolicy|
|**Tipo de datos**|Cadena|
|**Posibles valores**|merge (valor predeterminado) <p> admin_only|
|**Comentarios**|Disponible en La versión 100.83.73 o posterior de Defender para punto de conexión.|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>Retención del historial de exámenes antivirus (en días)

Especifique el número de días que los resultados se conservan en el historial de exámenes del dispositivo. Los resultados del examen antiguos se quitan del historial. Archivos en cuarentena antiguos que también se quitan del disco.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanResultsRetentionDays|
|**Tipo de datos**|Cadena|
|**Posibles valores**|90 (valor predeterminado). Los valores permitidos van de 1 día a 180 días.|
|**Comentarios**|Disponible en Defender para punto de conexión, versión 101.04.76 o posterior.|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de elementos en el historial de examen del antivirus

Especifique el número máximo de entradas que se conservarán en el historial de exámenes. Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones antivirus.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|scanHistoryMaximumItems|
|**Tipo de datos**|Cadena|
|**Posibles valores**|10000 (valor predeterminado). Los valores permitidos van de 5000 elementos a 15000 elementos.|
|**Comentarios**|Disponible en Defender para punto de conexión, versión 101.04.76 o posterior.|
|

### <a name="cloud-delivered-protection-preferences"></a>Preferencias de protección entregadas en la nube

La entrada *cloudService* del perfil de configuración se usa para configurar la característica de protección controlada por la nube del producto.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|cloudService|
|**Tipo de datos**|Diccionario (preferencia anidada)|
|**Comments**|Consulte las secciones siguientes para obtener una descripción del contenido del diccionario.|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitación o deshabilitación de la protección entregada en la nube

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

Los datos de diagnóstico se usan para mantener Defender para punto de conexión seguro y actualizado, detectar, diagnosticar y corregir problemas, y también realizar mejoras en el producto. Esta configuración determina el nivel de diagnóstico enviado por el producto a Microsoft.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|diagnosticLevel|
|**Tipo de datos**|Cadena|
|**Posibles valores**|opcional (valor predeterminado) <p> necesario|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar o deshabilitar envíos de ejemplo automáticos

Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft. Hay tres niveles para controlar el envío de muestras:

- **Ninguno**: no se envían muestras sospechosas a Microsoft.
- **Caja fuerte**: solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII). Este es el valor predeterminado para esta configuración.
- **Todos:** todos los ejemplos sospechosos se envían a Microsoft.

<br>

****

|Descripción|Valor|
|---|---|
|**Clave**|automaticSampleSubmissionConsent|
|**Tipo de datos**|Cadena|
|**Posibles valores**|ninguno <p> safe (valor predeterminado) <p> todo|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitación o deshabilitación de actualizaciones automáticas de inteligencia de seguridad

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

Para empezar, se recomienda el siguiente perfil de configuración para su empresa para aprovechar todas las características de protección que proporciona Defender para punto de conexión.

El siguiente perfil de configuración:

- Habilitación de la protección en tiempo real (RTP)
- Especifique cómo se controlan los siguientes tipos de amenazas:
  - **Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas
  - **Las bombas de archivo** (archivo con una alta tasa de compresión) se auditan en los registros de productos.
- Habilitación de actualizaciones automáticas de inteligencia de seguridad
- Habilitar la protección proporcionada en la nube
- Habilitación del envío automático de ejemplos en el `safe` nivel
- Habilitación de la supervisión del comportamiento

### <a name="sample-profile"></a>Perfil de ejemplo

```JSON
{
   "antivirusEngine":{
      "enforcementLevel":"real_time",
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
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Ejemplo de perfil de configuración completa

El siguiente perfil de configuración contiene entradas para todas las opciones descritas en este documento y se puede usar para escenarios más avanzados en los que quiera tener más control sobre el producto.

### <a name="full-profile"></a>Perfil completo

```JSON
{
   "antivirusEngine":{
      "enforcementLevel":"real_time",
      "scanAfterDefinitionUpdate":true,
      "scanArchives":true,
      "maximumOnDemandScanThreads":2,
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
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="add-tag-or-group-id-to-the-configuration-profile"></a>Adición de una etiqueta o un identificador de grupo al perfil de configuración

Al ejecutar el `mdatp health` comando por primera vez, el valor de la etiqueta y el identificador de grupo estarán en blanco. Para agregar una etiqueta o un identificador de grupo al `mdatp_managed.json` archivo, siga estos pasos:
  
  1. Abra el perfil de configuración desde la ruta de acceso `/etc/opt/microsoft/mdatp/managed/mdatp_managed.json`.
  2. Vaya a la parte inferior del archivo, donde se encuentra el `cloudService` bloque.
  3. Agregue la etiqueta o el identificador de grupo necesarios como ejemplo siguiente al final del corchete de cierre para `cloudService`.

  ```JSON
    },
    "cloudService": {
      "enabled": true,
      "diagnosticLevel": "optional",
      "automaticSampleSubmissionConsent": "safe",
      "automaticDefinitionUpdateEnabled": true,
      "proxy": "http://proxy.server:port/"
  },
  "edr": {
    "groupIds":"GroupIdExample",
    "tags": [
              {
              "key": "GROUP",
              "value": "Tag"
              }
            ]
        }
  }
  ```

  > [!NOTE]
  > No olvide agregar la coma después del corchete de cierre al final del `cloudService` bloque. Además, asegúrese de que hay dos corchetes de cierre después de agregar tag o bloque de id. de grupo (consulte el ejemplo anterior). En este momento, el único nombre de clave admitido para las etiquetas es `GROUP`. 
  
## <a name="configuration-profile-validation"></a>Validación del perfil de configuración

El perfil de configuración debe ser un archivo con formato JSON válido. Hay varias herramientas que se pueden usar para comprobarlo. Por ejemplo, si ha `python` instalado en el dispositivo:

```bash
python -m json.tool mdatp_managed.json
```

Si el json tiene un formato correcto, el comando anterior lo devuelve al terminal y devuelve un código de salida de `0`. De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1`.

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Comprobación de que el archivo mdatp_managed.json funciona según lo previsto

Para comprobar que /etc/opt/microsoft/mdatp/managed/mdatp_managed.json funciona correctamente, debería ver "[managed]" junto a esta configuración:

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Para que el archivo mdatp_managed.json surta efecto, no es necesario reiniciar el `mdatp` demonio.

## <a name="configuration-profile-deployment"></a>Implementación del perfil de configuración

Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la herramienta de administración que usa la empresa. Defender para punto de conexión en Linux lee la configuración administrada del archivo */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* .
