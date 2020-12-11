---
title: Configurar un conector para importar datos de distintivos físicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de datos para importar datos del sistema de distintivos físico de la organización a Microsoft 365. Esto le permite usar estos datos en directivas de administración de riesgos de Insider para ayudarle a detectar el acceso a sus edificios físicos por parte de usuarios específicos que pueden indicar una posible amenaza interna para su organización.
ms.openlocfilehash: 7e745b42d0df79f5c39f9fa02cb1b63f164ec2a5
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620136"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurar un conector para importar datos físicos de distintivos (versión preliminar)

Puede configurar un conector de datos en el centro de cumplimiento de Microsoft 365 para importar datos de distintivos físicos, como los eventos de acceso físico sin procesar del empleado o las alarmas de acceso físico generadas por el sistema de distintivos de la organización. Algunos ejemplos de puntos de acceso físico son una entrada a un edificio o una entrada a una sala de servidores o a un centro de datos. La [solución de administración de riesgos de Insider](insider-risk-management.md) de Microsoft 365 puede usar los datos de distintivos físicos para ayudar a proteger a su organización de la actividad malintencionada o del robo de datos dentro de la organización.

La configuración de un conector de distintivos físico consta de las siguientes tareas:

- Creación de una aplicación en Azure Active Directory (Azure AD) para acceder a un punto de conexión de API que acepta una carga JSON que contiene datos de distintivos físicos.

- Crear la carga JSON con un esquema definido por el conector de datos físico distintivos.

- Creación de un conector de datos físico distintivos en el centro de cumplimiento de Microsoft 365.

- Ejecutar un script para insertar los datos de distintivos físicos en el punto de conexión de la API.

- De manera opcional, la programación de la secuencia de comandos para que se ejecute automáticamente para importar los datos de distintivos físicos actualmente.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar el conector

- El usuario que crea el conector de distintivos físico en el paso 3 debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

- Debe determinar cómo recuperar o exportar los datos del sistema de distintivos físico de la organización (cada día) y crear un archivo JSON que se describe en el paso 2. El script que ejecutó en el paso 4 hará que los datos del archivo JSON se inserten en el punto de conexión de la API.

- El script de ejemplo que ejecutó en el paso 4 inserta los datos de distintivos físicos desde un archivo JSON en la API del conector para que pueda ser usado por la solución de administración de riesgos de Insider. Este script de ejemplo no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantías de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

El primer paso consiste en crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación se corresponderá con el conector físico de distintivos que ha creado en el paso 3. La creación de esta aplicación permitirá que Azure AD autentique la solicitud de inserción de la carga útil de JSON que contiene datos de distintivos físicos. Durante la creación de esta aplicación de Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- IDENTIFICADOR de la aplicación de Azure AD (también denominado identificador de *aplicación* o *identificador de cliente*)

- Secreto de la aplicación de Azure AD (también denominado *secreto de cliente*)

- Identificador de inquilino (también denominado *identificador de directorio*)

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, vea [registrar una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Paso 2: preparar un archivo JSON con datos de distintivos físicos

El paso siguiente es crear un archivo JSON que contenga información sobre los datos de acceso físico de los empleados. Como se explica en la sección antes de empezar, debe determinar cómo generar este archivo JSON desde el sistema de distintivos físico de la organización.

El archivo JSON debe cumplir con la definición de esquema que necesita el conector. Estas son las descripciones de las propiedades de esquema necesarias para el archivo JSON:

| Propiedad | Descripción | Tipo de datos |
|:-----------|:--------------|:------------|
|UserId|Un empleado puede tener varias identidades digitales en todos los sistemas. La entrada debe tener el identificador de Azure AD ya resuelto por el sistema de origen. |Dirección de correo electrónico o UPN|
|AssetId|IDENTIFICADOR de referencia del activo físico o del punto de acceso físico.| Cadena alfanumérica|
|AssetName|El nombre descriptivo del activo físico o del punto de acceso físico.|Cadena alfanumérica|
|EventTime|Marca de tiempo de acceso.|Fecha y hora en formato UTC|
|AccessStatus|Valor de `Success` o `Failed`| Cadena|
|||

A continuación, se muestra un ejemplo de un archivo JSON que se ajusta al esquema necesario:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
También puede descargar la siguiente definición de esquema para el archivo JSON desde el asistente cuando cree el conector distintivos físico en el paso 3.

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Paso 3: crear el conector de distintivos físico

El siguiente paso es crear un conector de distintivos físico en el centro de cumplimiento de Microsoft 365. Después de ejecutar el script en el paso 4, el archivo JSON que creó en el paso 3 se procesará y se insertará en el punto de conexión de la API que configuró en el paso 1. En este paso, asegúrese de copiar el JobId que se genera al crear el conector. Debe usar el JobId al ejecutar el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** , en **distintivos físicos**, haga clic en **Ver**.

3. En la página **distintivos física** , haga clic en **Agregar conector**.

4. En la página **credenciales de autenticación** , realice lo siguiente y, a continuación, haga clic en **siguiente**:
  
   1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que ha creado en el paso 1.
  
   2. Descargue el esquema de ejemplo para su referencia para crear el archivo JSON.
  
   3. Escriba un nombre único para el conector de distintivos físico.

5. En la página **revisión** , revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

6. Se muestra una página de estado que confirma que se ha creado el conector. Esta página también contiene el identificador de trabajo. Puede copiar el identificador de trabajo de esta página o de la página de control flotante para el conector. Necesita este identificador de trabajo al ejecutar el script.

   La página de estado también contiene un vínculo a la secuencia de comandos. Consulte este script para saber cómo exponer el archivo JSON en el punto de conexión de la API.

7. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la ficha **conectores** .

8. Haga clic en el conector físico de distintivos que acaba de crear para mostrar la página de flotante, que contiene propiedades y otra información sobre el conector.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Paso 4: ejecutar el script para publicar el archivo JSON que contiene datos de distintivos físicos

El siguiente paso para configurar un conector de distintivos físico es ejecutar un script que insertará los datos de distintivos físicos en el archivo JSON (que creó en el paso 2) en el punto de conexión de la API que creó en el paso 1. Se proporciona un script de ejemplo para la referencia y puede elegir usarla o crear su propio script para publicar el archivo JSON en el punto de conexión de la API.

Después de ejecutar el script, el archivo JSON que contiene los datos de distintivos físicos se inserta en su organización de Microsoft 365 donde la solución de administración de riesgos de Insider puede obtener acceso a él. Le recomendamos que publique datos de distintivos físicos diariamente. Para ello, puede automatizar el proceso para generar el archivo JSON todos los días desde el sistema de distintivos físico y, a continuación, programar el script para insertar los datos.

> [!NOTE]
> El número máximo de registros en el archivo JSON que puede procesar la API es de 50.000 registros.

1. Vaya a [este sitio de github](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) para acceder al script de ejemplo.

2. Haga clic en el botón **sin procesar** para mostrar el script en la vista de texto

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo para su organización, si es necesario.

5. Guarde el archivo de texto como un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de. ps1; por ejemplo, PhysicalBadging.ps1.

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para insertar los datos de distintivos físicos en el archivo JSON en la nube de Microsoft; por ejemplo:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   En la tabla siguiente se describen los parámetros que se deben usar con este script y los valores necesarios. La información que ha obtenido en los pasos anteriores se usa en los valores de estos parámetros.

   | Parámetro | Descripción |
   |:-------------|:--------------|
   |tenantId | Este es el identificador de la organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el tenantId de su organización en la hoja de **información general** del centro de administración de Azure ad. Se usa para identificar la organización. |
   |appId | Este es el identificador de la aplicación de Azure AD para la aplicación que ha creado en Azure AD en el paso 1. Esto lo usa Azure AD para la autenticación cuando el script intenta obtener acceso a la organización de 365 de Microsoft.                    |
   |appSecret | Este es el secreto de la aplicación de Azure AD para la aplicación que ha creado en Azure AD en el paso 1. También se usa para la autenticación.                                                        |
   |jobId | Se trata del identificador de trabajo para el conector de distintivos físico que ha creado en el paso 3. Se usa para asociar los datos de distintivos físicos que se insertan en la nube de Microsoft con el conector de distintivos físico.              |
   |JsonFilePath | Esta es la ruta de acceso al archivo en el equipo local (la que está usando para ejecutar el script) para el archivo JSON que creó en el paso 2. Este archivo debe seguir el esquema de ejemplo descrito en el paso 3.|
   |||

   Este es un ejemplo de la sintaxis del script de conector de distintivos físico con los valores reales para cada parámetro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Si la carga se realiza correctamente, el script muestra el mensaje de **carga correcta** .

   Si tiene varios archivos JSON, tiene que ejecutar el script para cada archivo.

> [!NOTE]
> También puede optar por insertar los datos de distintivos físicos en el extremo de la API mediante métodos que no sean ejecutar el script anterior. Por ejemplo, aquí se muestra un ejemplo de uso de Postman para insertar los datos en el punto de conexión de la API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Paso 5: supervisar el conector de distintivos físico

Después de crear el conector de distintivos físico y de insertar los datos de distintivos físicos, puede ver el conector y el estado de carga en el centro de cumplimiento de Microsoft 365. Si programa la secuencia de comandos para que se ejecute automáticamente periódicamente, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector de distintivos físico para mostrar la página de flotante. Esta página contiene las propiedades y la información sobre el conector.

   ![Página de control flotante de estado para conector de distintivos físico](..\media\PhysicalBadgingStatusFlyout.png)

3. En **última importación**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV a la nube de Microsoft.

   ![El archivo de registro del conector de distintivos físico muestra las filas de número del archivo JSON que se cargó](..\media\PhysicalBadgingConnectorLogFile.png)

   El campo **RecordsSaved** indica el número de filas del archivo CSV que se han cargado. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los campos **RecordsSaved** es 4, si el script cargó correctamente todas las filas en el archivo CSV.

Si no ha ejecutado el script en el paso 4, en la **última importación** se muestra un vínculo para descargar el script. Puede descargar el script y, a continuación, seguir los pasos del paso 4 para ejecutarlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Opcional Paso 6: programar el script para que se ejecute automáticamente

Para asegurarse de que los datos de distintivos físicos más recientes de su organización están disponibles para herramientas como la solución de administración de riesgos de Insider, le recomendamos que programe el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de distintivos físicos a archivo JSON en un programa similar (si no es el mismo) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar los datos de distintivos físicos más actuales para que el conector de distintivos físico pueda ponerlos a disposición de la solución de administración de riesgos de Insider.

Puede usar la aplicación programador de tareas de Windows para ejecutar el script de forma automática cada día.

1. En el equipo local, haga clic en el botón **Inicio** de Windows y, a continuación, escriba **programador de tareas**.

2. Haga clic en la aplicación **programador de tareas** para abrirla.

3. En la sección **acciones** , haga clic en **crear tarea**.

4. En la pestaña **General** , escriba un nombre descriptivo para la tarea programada; por ejemplo, el **script de conector de distintivos físico**. También puede Agregar una descripción opcional.

5. En **Opciones de seguridad**, haga lo siguiente:

   1. Determine si desea ejecutar el script solo cuando haya iniciado sesión en el equipo o ejecutarlo cuando haya iniciado sesión o no.

   2. Asegúrese de que la casilla **ejecutar con los privilegios más altos** está seleccionada.

6. Seleccione la pestaña **desencadenadores** , haga clic en **nuevo** y, a continuación, realice las siguientes acciones:

   1. En **configuración**, seleccione la opción **diariamente** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script será cada día a la misma hora especificada.

   2. En **Configuración avanzada**, asegúrese de que esté activada la casilla de verificación **habilitado** .

   3. Haga clic en **Aceptar**.

7. Seleccione la pestaña **acciones** , haga clic en **nueva** y, a continuación, realice las siguientes acciones:

   ![Configuración de la acción para crear una nueva tarea programada para el script de conector de distintivos físico](..\media\SchedulePhysicalBadgingScript1.png)

   1. En la lista desplegable **acción** , asegúrese de que está seleccionado **iniciar un programa** .

   2. En el cuadro **programa/script** , haga clic en **examinar**, vaya a la siguiente ubicación y selecciónela para mostrar la ruta de acceso en el cuadro: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. En el cuadro **Agregar argumentos (opcional)** , pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo, .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-FABA-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. En el cuadro **iniciar en (opcional)** , pegue la ubicación de la carpeta del script que ejecutó en el paso 4. Por ejemplo, C:\Users\contosoadmin\Desktop\Scripts.

   5. Haga clic en **Aceptar** para guardar la configuración de la nueva acción.

8. En la ventana **crear tarea** , haga clic en **Aceptar** para guardar la tarea programada. Es posible que se le pida que escriba sus credenciales de cuenta de usuario.

   La nueva tarea se muestra en la biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la biblioteca del programador de tareas](..\media\SchedulePhysicalBadgingScript2.png)

Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

También puede comprobar la última vez que se ejecutó el script en la página de flotante del conector de distintivos físico correspondiente en el centro de cumplimiento.
