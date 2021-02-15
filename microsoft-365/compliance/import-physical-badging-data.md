---
title: Configurar un conector para importar datos de daños físicos
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
description: Los administradores pueden configurar un conector de datos para importar datos desde el sistema de administración física de su organización a Microsoft 365. Esto le permite usar estos datos en directivas de administración de riesgos internos para ayudarle a detectar el acceso a sus edificios físicos por parte de usuarios específicos que puedan indicar una posible amenaza interna para su organización.
ms.openlocfilehash: 7e745b42d0df79f5c39f9fa02cb1b63f164ec2a5
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620136"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurar un conector para importar datos de daños físicos (versión preliminar)

Puede configurar un conector de datos en el Centro de cumplimiento de Microsoft 365 para importar datos de error físicos, como los eventos de acceso físico sin procesar de los empleados o cualquier alarma de acceso físico generada por el sistema de gobierno de su organización. Algunos ejemplos de puntos de acceso físicos son una entrada a un edificio o una entrada a la sala de servidores o al centro de datos. La solución de administración de riesgos interno de [](insider-risk-management.md) Microsoft 365 puede usar los datos de daños físicos para ayudar a proteger su organización contra actividad malintencionada o robo de datos dentro de su organización.

La configuración de un conector de error físico consta de las siguientes tareas:

- Crear una aplicación en Azure Active Directory (Azure AD) para tener acceso a un punto de conexión de API que acepte una carga JSON que contenga datos de error físicos.

- Crear la carga JSON con un esquema definido por el conector de datos con problemas físicos.

- Crear un conector de datos con problemas físicos en el Centro de cumplimiento de Microsoft 365.

- Ejecutar un script para insertar los datos de daños físicos en el punto de conexión de la API.

- Opcionalmente, la programación del script para que se ejecute automáticamente para importar datos de daños físicos actualmente.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar el conector

- El usuario que crea el conector de inasignación física en el paso 3 debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Debe determinar cómo recuperar o exportar los datos del sistema de protección física de su organización (diariamente) y crear un archivo JSON que se describe en el paso 2. El script que ejecute en el paso 4 insertará los datos del archivo JSON en el punto de conexión de la API.

- El script de ejemplo que se ejecuta en el paso 4 inserta los datos de daños físicos del archivo JSON en la API del conector para que puedan ser usados por la solución de administración de riesgos de Insider. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación se corresponderá con el conector de daños físicos que cree en el paso 3. La creación de esta aplicación permitirá que Azure AD autentique la solicitud de inserción de la carga JSON que contiene datos de daños físicos. Durante la creación de esta aplicación de Azure AD, asegúrate de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- Id. de aplicación de Azure AD (también denominado id. *de aplicación* o *id. de cliente)*

- Secreto de aplicación de Azure AD (también denominado secreto *de cliente)*

- Id. de inquilino (también denominado *id. de directorio)*

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, vea Registrar una aplicación [con la plataforma de identidad de Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Paso 2: Preparar un archivo JSON con datos de error físicos

El siguiente paso es crear un archivo JSON que contenga información sobre los datos de acceso físico de los empleados. Como se explica en la sección antes de comenzar, deberá determinar cómo generar este archivo JSON desde el sistema de configuración física de la organización.

El archivo JSON debe cumplir con la definición de esquema requerida por el conector. A continuación se descripciones de las propiedades de esquema necesarias para el archivo JSON:

| Propiedad | Descripción | Tipo de datos |
|:-----------|:--------------|:------------|
|UserId|Un empleado puede tener varias identidades digitales en todos los sistemas. La entrada debe tener el identificador de Azure AD ya resuelto por el sistema de origen. |UPN o dirección de correo electrónico|
|AssetId|Identificador de referencia del activo físico o punto de acceso físico.| Cadena alfanumérica|
|AssetName|Nombre descriptivo del activo físico o punto de acceso físico.|Cadena alfanumérica|
|EventTime|Marca de tiempo de acceso.|Fecha y hora, en formato UTC|
|AccessStatus|Valor de `Success` o `Failed`| Cadena|
|||

Este es un ejemplo de un archivo JSON que se ajusta al esquema requerido:

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
También puede descargar la siguiente definición de esquema para el archivo JSON desde el asistente cuando cree el conector de badging físico en el paso 3.

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

## <a name="step-3-create-the-physical-badging-connector"></a>Paso 3: Crear el conector de error físico

El siguiente paso es crear un conector de inefi miento físico en el Centro de cumplimiento de Microsoft 365. Después de ejecutar el script en el paso 4, el archivo JSON que creó en el paso 3 se procesará y se insertará en el punto de conexión de la API que configuró en el paso 1. En este paso, asegúrese de copiar el JobId que se genera al crear el conector. Usará el JobId cuando ejecute el script.

1. Vaya a conectores de datos y, a continuación, [https://compliance.microsoft.com](https://compliance.microsoft.com/) haga clic en **Conectores** de datos en el panel de navegación izquierdo.

2. En la **página Conectores de** datos, en Configuración **física,** haga clic en **Ver**.

3. En la **página Problemas físicos,** haga clic **en Agregar conector.**

4. En la **página Credenciales de autenticación,** haga lo siguiente y, a continuación, haga clic **en Siguiente:**
  
   1. Escriba o pegue el identificador de la aplicación de Azure AD para la aplicación de Azure que creó en el paso 1.
  
   2. Descargue el esquema de ejemplo de la referencia para crear el archivo JSON.
  
   3. Escriba un nombre único para el conector de badging físico.

5. En la **página Revisar,** revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

6. Se muestra una página de estado que confirma que se creó el conector. Esta página también contiene el identificador de trabajo. Puede copiar el identificador de trabajo desde esta página o desde la página desplegable del conector. Necesita este identificador de trabajo al ejecutar el script.

   La página de estado también contiene un vínculo al script. Consulte este script para comprender cómo publicar el archivo JSON en el punto de conexión de la API.

7. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la **pestaña Conectores.**

8. Haga clic en el conector de bloqueo físico que acaba de crear para mostrar la página desplegable, que contiene propiedades y otra información sobre el conector.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Paso 4: Ejecutar el script para publicar el archivo JSON que contiene datos de error físicos

El siguiente paso en la configuración de un conector de badging físico es ejecutar un script que insertará los datos de incoación de datos físicos en el archivo JSON (que creó en el paso 2) en el punto de conexión de la API que creó en el paso 1. Proporcionamos un script de ejemplo para su referencia y puede elegir usarlo o crear su propio script para publicar el archivo JSON en el punto de conexión de la API.

Después de ejecutar el script, el archivo JSON que contiene los datos de daños físicos se inserta en la organización de Microsoft 365, donde la solución de administración de riesgos de Insider puede acceder a él. Se recomienda publicar datos de daños físicos diariamente. Para ello, automatiza el proceso para generar el archivo JSON todos los días desde el sistema de protección física y, a continuación, programa el script para insertar los datos.

> [!NOTE]
> El número máximo de registros en el archivo JSON que puede procesar la API es de 50 000 registros.

1. Vaya a este [sitio de GitHub](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) para obtener acceso al script de ejemplo.

2. Haga clic en **el botón** Sin procesar para mostrar el script en la vista de texto

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo para su organización, si es necesario.

5. Guarde el archivo de texto como un Windows PowerShell de script mediante un sufijo de nombre de archivo de .ps1; por ejemplo, PhysicalBadging.ps1.

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para insertar los datos de daños físicos en el archivo JSON en la nube de Microsoft; por ejemplo:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   En la tabla siguiente se describen los parámetros que se deben usar con este script y sus valores necesarios. La información obtenida en los pasos anteriores se usa en los valores de estos parámetros.

   | Parámetro | Descripción |
   |:-------------|:--------------|
   |tenantId | Este es el identificador de su organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el tenantId de su organización en la hoja **Información** general del Centro de administración de Azure AD. Esto se usa para identificar la organización. |
   |appId | Este es el identificador de aplicación de Azure AD para la aplicación que creaste en Azure AD en el paso 1. Azure AD lo usa para la autenticación cuando el script intenta obtener acceso a su organización de Microsoft 365.                    |
   |appSecret | Este es el secreto de aplicación de Azure AD para la aplicación que creaste en Azure AD en el paso 1. También se usa para la autenticación.                                                        |
   |jobId | Este es el id. de trabajo para el conector de badging físico que creó en el paso 3. Esto se usa para asociar los datos de daños físicos que se insertan en la nube de Microsoft con el conector de mala administración física.              |
   |JsonFilePath | Esta es la ruta de acceso del archivo en el equipo local (el que está usando para ejecutar el script) para el archivo JSON que creó en el paso 2. Este archivo debe seguir el esquema de ejemplo descrito en el paso 3.|
   |||

   Este es un ejemplo de la sintaxis del script del conector de error físico que usa valores reales para cada parámetro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Si la carga se realiza correctamente, el script muestra el **mensaje Cargar correctamente.**

   Si tiene varios archivos JSON, debe ejecutar el script para cada archivo.

> [!NOTE]
> También puede optar por insertar los datos de daños físicos en el punto de conexión de la API mediante métodos que no ejecuten el script anterior. Por ejemplo, este es un ejemplo para usar Postman para insertar los datos en el punto de conexión de la API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Paso 5: Supervisar el conector de error físico

Después de crear el conector de carga física e insertar los datos de los problemas físicos, puede ver el conector y el estado de carga en el Centro de cumplimiento de Microsoft 365. Si programa el script para que se ejecute automáticamente de forma periódica, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de bloqueo físico para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

   ![Página desplegable de estado para conector de bloqueo físico](..\media\PhysicalBadgingStatusFlyout.png)

3. En **Última importación,** haga clic en el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV en la nube de Microsoft.

   ![El archivo de registro del conector de error físico muestra las filas de número del archivo JSON que se cargaron](..\media\PhysicalBadgingConnectorLogFile.png)

   El **campo RecordsSaved** indica el número de filas del archivo CSV cargado. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los campos **RecordsSaved** es 4, si el script cargó correctamente todas las filas del archivo CSV.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Última importación.** Puede descargar el script y, a continuación, seguir los pasos del paso 4 para ejecutarlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los últimos datos de daños físicos de su organización están disponibles para herramientas como la solución de administración de riesgos de Insider, le recomendamos que programe el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de daños físicos a un archivo JSON con una programación similar (si no es la misma) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar los datos de daños físicos más actuales para que el conector de administración de riesgos físicos pueda hacer que esté disponible para la solución de administración de riesgos de Insider.

Puedes usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script cada día.

1. En el equipo local, haga clic en el botón **Inicio** de Windows y, a continuación, escriba **Programador de tareas.**

2. Haz clic en **la aplicación Programador** de tareas para abrirla.

3. En la **sección Acciones,** haga clic **en Crear tarea.**

4. En la **pestaña General,** escriba un nombre descriptivo para la tarea programada; por ejemplo, **script de conector de badging físico.** También puede agregar una descripción opcional.

5. En **Opciones de seguridad,** haga lo siguiente:

   1. Determine si debe ejecutar el script solo cuando haya iniciado sesión en el equipo o cuando haya iniciado sesión o no.

   2. Asegúrate de que la **casilla Ejecutar con los privilegios más altos** esté activada.

6. Seleccione la **pestaña Desencadenadores,** **haga** clic en Nuevo y, a continuación, haga lo siguiente:

   1. En **Configuración,** seleccione la **opción Diaria** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script lo hará todos los días a la misma hora especificada.

   2. En **Configuración avanzada,** asegúrese de que la **casilla** Habilitada esté activada.

   3. Haga clic en **Aceptar**.

7. Seleccione la **pestaña Acciones,** haga clic **en** Nuevo y, a continuación, haga lo siguiente:

   ![Configuración de la acción para crear una nueva tarea programada para el script del conector de badging físico](..\media\SchedulePhysicalBadgingScript1.png)

   1. En la **lista** desplegable Acción, asegúrese de que **la opción Iniciar un programa** está seleccionada.

   2. En el **cuadro Programa/script,** haga clic en Examinar y vaya a la siguiente ubicación y selecciónelo para que la ruta de acceso se muestre en el cuadro: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe. 

   3. En el **cuadro Agregar argumentos (opcional),** pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo, .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. En el **cuadro Iniciar en (opcional),** pegue la ubicación de la carpeta del script que ejecutó en el paso 4. Por ejemplo, C:\Users\contosoadmin\Desktop\Scripts.

   5. Haga **clic en** Aceptar para guardar la configuración de la nueva acción.

8. En la **ventana Crear tarea,** haga clic en **Aceptar** para guardar la tarea programada. Es posible que se te pida que escribas las credenciales de tu cuenta de usuario.

   La nueva tarea se muestra en la Biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la Biblioteca del Programador de tareas](..\media\SchedulePhysicalBadgingScript2.png)

Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

También puede comprobar la última vez que el script se ejecutó en la página desplegable del conector de bloqueo físico correspondiente en el centro de cumplimiento.
