---
title: Configuración de un conector para importar datos físicos incorrectos
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
description: Los administradores pueden configurar un conector de datos para importar datos del sistema de badging físico de su organización a Microsoft 365. Esto le permite usar estos datos en directivas de administración de riesgos internos para ayudarle a detectar el acceso a los edificios físicos por parte de usuarios específicos que pueden indicar una posible amenaza interna para su organización.
ms.openlocfilehash: 96017d6477f914c799fecbe834abdac22917bfaa
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077972"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurar un conector para importar datos físicos incorrectos (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede configurar un conector de datos en el portal de cumplimiento de Microsoft Purview para importar datos físicos incorrectos, como los eventos de acceso físico sin procesar de los empleados o las alarmas de acceso físico generadas por el sistema de badging de su organización. Algunos ejemplos de puntos de acceso físicos son una entrada a un edificio o una entrada a la sala de servidores o al centro de datos. La [solución de administración de riesgos](insider-risk-management.md) internos de Microsoft 365 puede usar los datos de falsificación física para ayudar a proteger su organización frente a actividades malintencionadas o robo de datos dentro de la organización.

La configuración de un conector de badging físico consta de las siguientes tareas:

- Creación de una aplicación en Azure Active Directory (Azure AD) para acceder a un punto de conexión de API que acepta una carga JSON que contiene datos físicos incorrectos.

- Creación de la carga JSON con un esquema definido por el conector de datos de badging físico.

- Creación de un conector de datos de badging físico en el portal de cumplimiento.

- Ejecución de un script para insertar los datos físicos incorrectos en el punto de conexión de API.

- Opcionalmente, puede programar el script para que se ejecute automáticamente para importar datos de errores físicos actualmente.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar el conector

- Al usuario que crea el conector de badging físico en el paso 3 se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

   > [!NOTE]
   > Actualmente, el rol administrador del conector de datos no se admite en los entornos de administración GCC Alto y DoD de la Administración pública de EE. UU. Por lo tanto, al usuario que crea el conector de RR. HH. en GCC entornos High y DoD se le debe asignar el rol Exportación de importación de buzones en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol Exportar importación de buzón y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [Crear grupos de roles](/Exchange/permissions-exo/role-groups#create-role-groups) o [Modificar grupos de roles](/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo "Administrar grupos de roles en Exchange Online".

- Debe determinar cómo recuperar o exportar los datos del sistema físico de la organización (a diario) y crear un archivo JSON que se describe en el paso 2. El script que ejecute en el paso 4 insertará los datos del archivo JSON en el punto de conexión de API.

- El script de ejemplo que se ejecuta en el paso 4 inserta los datos físicos incorrectos del archivo JSON en la API del conector para que la solución de administración de riesgos internos pueda usarla. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

- Este conector está disponible en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación se corresponderá con el conector de badging físico que cree en el paso 3. La creación de esta aplicación permitirá que Azure AD autentique la solicitud de inserción para la carga json que contiene datos físicos incorrectos. Durante la creación de esta aplicación Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- Azure AD identificador de aplicación (también denominado *id. de aplicación* o *id. de cliente*)

- Azure AD secreto de aplicación (también denominado *secreto de cliente*)

- Id. de inquilino (también denominado *id. de directorio*)

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, consulte [Registro de una aplicación con el Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Paso 2: Preparación de un archivo JSON con datos físicos incorrectos

El siguiente paso consiste en crear un archivo JSON que contenga información sobre los datos de acceso físico de los empleados. Como se explica en la sección antes de comenzar, tendrá que determinar cómo generar este archivo JSON a partir del sistema de badging físico de su organización.

El archivo JSON debe cumplir la definición de esquema requerida por el conector. Estas son descripciones de las propiedades de esquema necesarias para el archivo JSON:

|Propiedad|Descripción|Tipo de datos|
|---|---|---|
|UserId|Un empleado puede tener varias identidades digitales en todos los sistemas. La entrada debe tener el identificador de Azure AD ya resuelto por el sistema de origen.|UPN o dirección de correo electrónico|
|AssetId|Identificador de referencia del recurso físico o punto de acceso físico.|Cadena alfanumérica|
|AssetName|Nombre descriptivo del recurso físico o punto de acceso físico.|Cadena alfanumérica|
|EventTime|Marca de tiempo de acceso.|Fecha y hora, en formato UTC|
|AccessStatus|Valor de `Success` o `Failed`|Cadena|
|||

Este es un ejemplo de un archivo JSON que se ajusta al esquema necesario:

```json
[
    {
        "UserId":"sarad@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed"
    },
    {
        "UserId":"pilarp@contoso.com",
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",
        "AccessStatus":"Success"
    }
]
```

También puede descargar la siguiente definición de esquema para el archivo JSON desde el asistente al crear el conector de errores físicos en el paso 3.

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

## <a name="step-3-create-the-physical-badging-connector"></a>Paso 3: Creación del conector de badging físico

El siguiente paso consiste en crear un conector de badging físico en el portal de cumplimiento. Después de ejecutar el script en el paso 4, el archivo JSON que creó en el paso 3 se procesará e insertará en el punto de conexión de API que configuró en el paso 1. En este paso, asegúrese de copiar el JobId que se genera al crear el conector. Usará jobid al ejecutar el script.

1. Vaya al portal de cumplimiento y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**Conectores de datos**</a>.

2. En la página **Conectores de datos** , en **Errores físicos**, haga clic en **Ver**.

3. En la página **Badging físico** , haga clic en **Agregar conector**.

4. En la página **Credenciales de autenticación** , haga lo siguiente y, a continuación, haga clic en **Siguiente**:

   1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que creó en el paso 1.

   2. Descargue el esquema de ejemplo de la referencia para crear el archivo JSON.

   3. Escriba un nombre único para el conector de badging físico.

5. En la página **Revisar** , revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

6. Se muestra una página de estado que confirma que se creó el conector. Esta página también contiene el identificador del trabajo. Puede copiar el identificador de trabajo desde esta página o desde la página de control flotante del conector. Necesita este identificador de trabajo al ejecutar el script.

   La página de estado también contiene un vínculo al script. Consulte este script para comprender cómo publicar el archivo JSON en el punto de conexión de API.

7. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la pestaña **Conectores** .

8. Haga clic en el conector de badging físico que acaba de crear para mostrar la página de control flotante, que contiene propiedades y otra información sobre el conector.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Paso 4: Ejecutar el script para publicar el archivo JSON que contiene datos físicos incorrectos

El siguiente paso para configurar un conector físico incorrecto es ejecutar un script que insertará los datos físicos incorrectos en el archivo JSON (que creó en el paso 2) en el punto de conexión de API que creó en el paso 1. Proporcionamos un script de ejemplo para la referencia y puede optar por usarlo o crear su propio script para publicar el archivo JSON en el punto de conexión de API.

Después de ejecutar el script, el archivo JSON que contiene los datos físicos incorrectos se inserta en la organización Microsoft 365 a la que puede acceder la solución de administración de riesgos internos. Se recomienda publicar datos físicos incorrectos diariamente. Para ello, automatice el proceso para generar el archivo JSON todos los días a partir del sistema físico incorrecto y, a continuación, programe el script para insertar los datos.

> [!NOTE]
> El número máximo de registros en el archivo JSON que puede procesar la API es de 50 000 registros.

1. Vaya a [este sitio de GitHub](https://github.com/microsoft/m365-physical-badging-connector-sample-scripts/blob/master/push_physical_badging_records.ps1) para acceder al script de ejemplo.

2. Haga clic en el botón **Sin formato** para mostrar el script en la vista de texto.

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo de su organización, si es necesario.

5. Guarde el archivo de texto como un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de .ps1; por ejemplo, PhysicalBadging.ps1.

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para insertar los datos físicos incorrectos en el archivo JSON en la nube de Microsoft; por ejemplo:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   En la tabla siguiente se describen los parámetros que se usarán con este script y sus valores necesarios. La información obtenida en los pasos anteriores se usa en los valores de estos parámetros.

   |Parámetro|Descripción|
   |---|---|
   |tenantId|Este es el identificador de la organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el tenantId de su organización en la hoja **Información general** del centro de administración de Azure AD. Esto se usa para identificar su organización.|
   |appId|Este es el identificador de aplicación Azure AD de la aplicación que creó en Azure AD en el paso 1. Esto lo usa Azure AD para la autenticación cuando el script intenta acceder a la organización Microsoft 365.|
   |appSecret|Este es el secreto de aplicación Azure AD de la aplicación que creó en Azure AD en el paso 1. Esto también se usa para la autenticación.|
   |jobId|Este es el id. de trabajo del conector de badging físico que creó en el paso 3. Esto se usa para asociar los datos físicos incorrectos que se insertan en la nube de Microsoft con el conector de badging físico.|
   |JsonFilePath|Esta es la ruta de acceso del archivo en el equipo local (la que se usa para ejecutar el script) del archivo JSON que creó en el paso 2. Este archivo debe seguir el esquema de ejemplo descrito en el paso 3.|
   |||

   Este es un ejemplo de la sintaxis del script del conector de badging físico mediante valores reales para cada parámetro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -jsonFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Si la carga se realiza correctamente, el script muestra el **mensaje Upload Correcto**.

   Si tiene varios archivos JSON, debe ejecutar el script para cada archivo.

> [!NOTE]
> También puede optar por insertar los datos físicos incorrectos en el punto de conexión de API mediante métodos distintos de ejecutar el script anterior. Por ejemplo, este es un ejemplo para usar Postman para insertar los datos en el punto de conexión de API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Paso 5: Supervisión del conector de badging físico

Después de crear el conector de badging físico e insertar los datos físicos incorrectos, puede ver el conector y cargar el estado en el portal de cumplimiento. Si programa el script para que se ejecute automáticamente de forma periódica, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya al portal de cumplimiento y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**Conectores de datos**</a>.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector de badging físico para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

   ![Página de control flotante de estado para el conector de badging físico.](..\media\PhysicalBadgingStatusFlyout.png)

3. En **Última importación**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo JSON en la nube de Microsoft.

   ![El archivo de registro del conector de badging físico muestra el número de objetos del archivo JSON que se cargaron.](..\media\PhysicalBadgingConnectorLogFile.png)

   El campo **RecordsSaved** indica el número de objetos en el archivo JSON que se cargó. Por ejemplo, si el archivo JSON contiene cuatro objetos, el valor de los campos **RecordsSaved** es 4, si el script cargó correctamente todos los objetos del archivo JSON.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Última importación**. Puede descargar el script y, a continuación, seguir los pasos del paso 4 para ejecutarlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los últimos datos físicos incorrectos de su organización están disponibles para herramientas como la solución de administración de riesgos internos, se recomienda programar el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos físicos incorrectos al archivo JSON en una programación similar (si no es la misma) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar losdatoss físicos más actuales para que el conector de badging físico pueda ponerlos a disposición de la solución de administración de riesgos internos.

Puede usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script todos los días.

1. En el equipo local, haga clic en el botón **inicio** Windows y escriba **Programador de tareas**.

2. Haga clic en la aplicación **Programador de tareas** para abrirla.

3. En la sección **Acciones** , haga clic en **Crear tarea**.

4. En la pestaña **General** , escriba un nombre descriptivo para la tarea programada; por ejemplo, script del **conector de badging físico**. También puede agregar una descripción opcional.

5. En **Opciones de seguridad**, haga lo siguiente:

   1. Determine si debe ejecutar el script solo cuando haya iniciado sesión en el equipo o ejecutarlo cuando haya iniciado sesión o no.

   2. Asegúrese de que está activada **la casilla Ejecutar con los privilegios más altos** .

6. Seleccione la pestaña **Desencadenadores** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

   1. En **Configuración**, seleccione la opción **Diario** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script se ejecutará todos los días a la misma hora especificada.

   2. En **Configuración avanzada**, asegúrese de que la casilla **Habilitado** está seleccionada.

   3. Haga clic en **Aceptar**.

7. Seleccione la pestaña **Acciones** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

   ![Configuración de acciones para crear una nueva tarea programada para el script del conector de errores físicos.](..\media\SchedulePhysicalBadgingScript1.png)

   1. En la lista desplegable **Acción** , asegúrese de que **iniciar un programa** está seleccionado.

   2. En el cuadro **Programa o script** , haga clic en **Examinar**, vaya a la siguiente ubicación y selecciónela para que la ruta de acceso se muestre en el cuadro: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. En el cuadro **Agregar argumentos (opcional),** pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo, .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json"

   4. En el cuadro **Iniciar en (opcional),** pegue la ubicación de carpeta del script que ejecutó en el paso 4. Por ejemplo, C:\Users\contosoadmin\Desktop\Scripts.

   5. Haga clic en **Aceptar** para guardar la configuración de la nueva acción.

8. En la ventana **Crear tarea** , haga clic en **Aceptar** para guardar la tarea programada. Es posible que se le pida que escriba las credenciales de la cuenta de usuario.

   La nueva tarea se muestra en la biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la biblioteca del programador de tareas.](..\media\SchedulePhysicalBadgingScript2.png)

Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

También puede comprobar la última vez que el script se ejecutó en la página de control flotante del conector de badging físico correspondiente en el centro de cumplimiento.
