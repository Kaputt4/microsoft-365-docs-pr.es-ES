---
title: Configuración de un conector para importar datos genéricos de auditoría sanitaria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de datos para importar datos de registros médicos electrónicos (EHR) de su sistema sanitario a Microsoft 365. Esto le permite usar los datos de EHR en directivas de administración de riesgos internos para ayudarle a detectar la actividad de acceso no autorizado a los datos de los pacientes por parte de los empleados.
ms.openlocfilehash: b1745d8f91253132748fe08d724386d2e6633a4c
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64993170"
---
# <a name="set-up-a-connector-to-import-healthcare-ehr-audit-data-preview"></a>Configuración de un conector para importar datos de auditoría de EHR de atención sanitaria (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede configurar un conector de datos en el portal de cumplimiento de Microsoft Purview para importar datos de auditoría para la actividad del usuario en el sistema de Registros electrónicos de atención sanitaria (EHR) de su organización. Los datos de auditoría del sistema ehr sanitario incluyen datos para eventos relacionados con el acceso a los registros de salud de un paciente. La [solución de administración de riesgos](insider-risk-management.md) internos de Microsoft 365 puede usar los datos de auditoría de EHR de atención sanitaria para ayudar a proteger su organización frente al acceso no autorizado a la información de los pacientes.

La configuración de un conector de Healthcare consta de las siguientes tareas:

- Crear una aplicación en Azure Active Directory (Azure AD) para acceder a un punto de conexión de API que acepta un archivo de texto separado por tabulaciones que contiene datos de auditoría de EHR de atención sanitaria.

- Crear un archivo de texto con todos los campos necesarios tal como se define en el esquema del conector.

- Creación de una instancia del conector de Healthcare en el portal de cumplimiento.

- Ejecución de un script para insertar datos de auditoría de EHR de atención sanitaria en el punto de conexión de API.

- Opcionalmente, programar el script para que se ejecute automáticamente para importar los datos de auditoría.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar el conector

- Al usuario que crea el conector de Healthcare en el paso 3 se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Debe determinar cómo recuperar o exportar los datos del sistema de EHR sanitario de su organización (a diario) y crear un archivo de texto que se describe en el paso 2. El script que ejecute en el paso 4 insertará los datos del archivo de texto en el punto de conexión de API.

- El script de ejemplo que se ejecuta en el paso 4 inserta los datos de auditoría de EHR de atención sanitaria desde el archivo de texto a la API del conector para que la solución de administración de riesgos internos pueda usarla. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación se corresponderá con el conector de Healthcare que cree en el paso 3. La creación de esta aplicación permite Azure AD autenticar la solicitud de inserción para el archivo de texto que contiene datos de auditoría de EHR de atención sanitaria. Durante la creación de esta aplicación Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- Azure AD identificador de aplicación (también denominado *id. de aplicación* o *id. de cliente*)

- Azure AD secreto de aplicación (también denominado *secreto de cliente*)

- Id. de inquilino (también denominado *id. de directorio*)

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, consulte [Registro de una aplicación con el Plataforma de identidad de Microsoft](\azure\active-directory\develop\quickstart-register-app).

## <a name="step-2-prepare-a-text-file-with-healthcare-ehr-auditing-data"></a>Paso 2: Preparación de un archivo de texto con datos de auditoría de EHR de atención sanitaria

El siguiente paso es crear un archivo de texto que contenga información sobre el acceso de los empleados a los registros de salud de los pacientes en el sistema ehr sanitario de su organización. Como se ha explicado anteriormente, debe determinar cómo generar este archivo de texto a partir de su sistema de EHR sanitario. El flujo de trabajo del conector de Healthcare requiere un archivo de texto con valores separados por tabulaciones para asignar esos datos en el archivo de texto con el esquema de conector necesario. El formato de archivo admitido es un archivo de texto separado por comas (.csv), canalización (.psv) o tabulación (.tsv).

> [!NOTE]
> El tamaño máximo del archivo de texto que contiene los datos de auditoría es de 3 GB. El número máximo de filas es de 5 millones. Además, asegúrese de incluir solo los datos de auditoría pertinentes de su sistema de EHR sanitario.

En la tabla siguiente se enumeran los campos necesarios para habilitar escenarios de administración de riesgos internos. Un subconjunto de estos campos es obligatorio. Estos campos se resaltan con un asterisco (*). Si falta alguno de los campos obligatorios en el archivo de texto, el archivo no se validará y no se importarán los datos del archivo.

|Field|Categoría|
|:----|:----------|
| Nombre del evento de tiempo *<br/>de* creación<br/>Id. de estación de trabajo<br/>Sección de eventos<br/>Categoría del evento |Estos campos se usan para identificar eventos de actividad de acceso en el sistema de EHR de atención sanitaria.|
| Id. de reg del paciente<br/>Nombre *<br/>del pacienteNombre del segundo pacienteNombre <br/>del paciente* <br/>Línea 1 de dirección del paciente* <br/>Línea 2 de dirección del paciente<br/>Ciudad del paciente* <br/>Código postal del paciente*  <br/>Estado del paciente <br/>País del paciente <br/>Departamento de pacientes              | Estos campos se usan para identificar la información del perfil del paciente.|
| Motivo de acceso restringido*<br/> Comentario de acceso restringido | Estos campos se usan para identificar el acceso a registros restringidos.|
| Dirección de correo electrónico (UPN) o SamAccountName*<br/>Nombre de usuario del empleado <br/> Id. de empleado <br/> Apellidos <sup>del empleado 1</sup> <br/> Nombre del empleado <sup>1</sup> | Estos campos se usan para identificar la información del perfil de empleado para la coincidencia de direcciones y nombres necesaria para determinar el acceso a los registros de familia, vecino o empleado. |
|||

> [!NOTE] 
> <sup>1</sup> Es posible que este campo no esté disponible de forma predeterminada en el sistema de EHR sanitario. Debe configurar la exportación para asegurarse de que el archivo de texto contiene este campo.

## <a name="step-3-create-the-healthcare-connector"></a>Paso 3: Creación del conector de Healthcare

El siguiente paso es crear un conector de Healthcare en el portal de cumplimiento. Después de ejecutar el script en el paso 4, el archivo de texto que creó en el paso 2 se procesará e insertará en el punto de conexión de API que configuró en el paso 1. En este paso, asegúrese de copiar el JobId que se genera al crear el conector. Usará jobid al ejecutar el script.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la pestaña **Información general**, haga clic en **Atención sanitaria (versión preliminar).**

3. En la página **Healthcare (versión preliminar),** haga clic en **Agregar conector**.

4. Acepte los términos de servicio.

5. En la página **Credenciales de autenticación** , haga lo siguiente y, a continuación, haga clic en **Siguiente**:

    1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que creó en el paso 1.

    2. Escriba un nombre para el conector de atención sanitaria.

6. En la página **Método de asignación** de archivos, seleccione una de las siguientes opciones y, a continuación, haga clic en **Siguiente**.

   - **Upload un archivo de ejemplo**. Si selecciona esta opción, haga clic en **Upload archivo de ejemplo** para cargar el archivo que preparó en el paso 2. Esta opción le permite seleccionar rápidamente los nombres de columna en el archivo de texto de una lista desplegable para asignar las columnas al esquema necesario para el conector de atención sanitaria. 

    O bien:

   - **Proporcione manualmente los detalles de la asignación**. Si selecciona esta opción, debe escribir el nombre de las columnas en el archivo de texto para asignar las columnas al esquema necesario para el conector de atención sanitaria.

7. En la página **Detalles de asignación** de archivos, realice una de las siguientes acciones, en función de si cargó un archivo de ejemplo o no en el paso anterior:

   - Use las listas desplegables para asignar las columnas del archivo de ejemplo a cada campo necesario para el conector de atención sanitaria.

    O bien:

   - Para cada campo, escriba el nombre de columna del archivo que preparó en el paso 2 que corresponde al campo del conector de atención sanitaria.

8. En la página **Revisar** , revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

   Se muestra una página de estado que confirma que se creó el conector. Esta página contiene dos cosas importantes que necesita para completar el siguiente paso para ejecutar el script de ejemplo para cargar los datos de auditoría de EHR de atención sanitaria.

    - **Id. de trabajo.** Necesitará este identificador de trabajo para ejecutar el script en el paso siguiente. Puede copiarlo desde esta página o desde la página de control flotante del conector.

    - **Vínculo a script de ejemplo.** Haga clic en el vínculo **aquí** para ir al sitio GitHub para acceder al script de ejemplo (el vínculo abre una nueva ventana). Mantenga esta ventana abierta para que pueda copiar el script en el paso 4. Como alternativa, puede marcar el destino o copiar la dirección URL para poder acceder a ella de nuevo al ejecutar el script. Este vínculo también está disponible en la página de control flotante del conector.

9. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la pestaña **Conectores** .

10. Haga clic en el conector de Healthcare que acaba de crear para mostrar la página de control flotante, que contiene propiedades y otra información sobre el conector.

Si aún no lo ha hecho, puede copiar los valores del **identificador de App de Azure** y el **identificador del trabajo del conector**. Necesitará estos para ejecutar el script en el paso siguiente. También puede descargar el script desde la página de control flotante (o descargarlo mediante el vínculo del paso siguiente).

También puede hacer clic en **Editar** para cambiar el identificador de App de Azure o los nombres de encabezado de columna que definió en la página **Asignación de** archivos.

## <a name="step-4-run-the-sample-script-to-upload-your-healthcare-ehr-auditing-data"></a>Paso 4: Ejecución del script de ejemplo para cargar los datos de auditoría de EHR de atención sanitaria

El último paso para configurar un conector de Healthcare es ejecutar un script de ejemplo que cargará los datos de auditoría de EHR de atención sanitaria en el archivo de texto (que creó en el paso 1) en la nube de Microsoft. En concreto, el script carga los datos en el conector de Healthcare. Después de ejecutar el script, el conector de Healthcare que creó en el paso 3 importa los datos de auditoría de EHR de atención sanitaria a la organización de Microsoft 365 a la que pueden acceder otras herramientas de cumplimiento, como la solución de administración de riesgos Insider. Después de ejecutar el script, considere la posibilidad de programar una tarea para ejecutarla automáticamente diariamente para que los datos de terminación de empleados más actuales se carguen en la nube de Microsoft. Consulte [(Opcional) Paso 6: Programar el script para que se ejecute automáticamente](#optional-step-6-schedule-the-script-to-run-automatically).

> [!NOTE]
> Como se indicó anteriormente, el tamaño máximo del archivo de texto que contiene los datos de auditoría es de 3 GB. El número máximo de filas es de 5 millones. El script que ejecute en este paso tardará entre 30 y 40 minutos en importar los datos de auditoría de archivos de texto grandes. Además, el script dividirá archivos de texto grandes en bloques más pequeños de 100 000 filas y, a continuación, importará esos bloques secuencialmente.

1. Vaya a la ventana que dejó abierta desde el paso anterior para acceder al sitio GitHub con el script de ejemplo. Como alternativa, abra el sitio marcado o use la dirección URL que copió. También puede acceder al script [aquí](https://github.com/microsoft/m365-compliance-connector-sample-scripts/blob/main/sample_script.ps1).

2. Haga clic en el botón **Sin formato** para mostrar el script en la vista de texto.

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo de su organización, si es necesario.

5. Guarde el archivo de texto como un archivo de script Windows PowerShell usando un sufijo de nombre de archivo de `.ps1`; por ejemplo, `HealthcareConnector.ps1`.

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para cargar los datos de auditoría sanitaria en el archivo de texto en la nube de Microsoft; por ejemplo:

   ```powershell
   .\HealthcareConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -filePath '<filePath>'
   ```

En la tabla siguiente se describen los parámetros que se usarán con este script y sus valores necesarios. La información obtenida en los pasos anteriores se usa en los valores de estos parámetros.

|Parámetro  |Descripción|
|:----------|:----------|
|tenantId|Este es el identificador de la organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el identificador de inquilino de su organización en la hoja **Información general** del centro de administración de Azure AD. Esto se usa para identificar su organización.|
|appId|Este es el identificador de aplicación Azure AD de la aplicación que creó en Azure AD en el paso 1. Esto lo usa Azure AD para la autenticación cuando el script intenta acceder a la organización Microsoft 365.|
|appSecret|Este es el secreto de aplicación Azure AD de la aplicación que creó en Azure AD en el paso 1. Esto también se usa para la autenticación.|
|jobId|Este es el identificador de trabajo del conector de Healthcare que creó en el paso 3. Esto se usa para asociar los datos de auditoría de EHR de atención sanitaria que se cargan en la nube de Microsoft con el conector healthcare.|
|Filepath|Esta es la ruta de acceso del archivo de texto (almacenado en el mismo sistema que el script) que creó en el paso 2. Intente evitar espacios en la ruta de acceso del archivo; de lo contrario, use comillas simples.|
|||

Este es un ejemplo de la sintaxis del script del conector de Healthcare mediante valores reales para cada parámetro:

```powershell
.\HealthcareConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -filePath 'C:\Users\contosoadmin\Desktop\Data\healthcare_audit_records.csv'
```

Si la carga se realiza correctamente, el script muestra el **mensaje Upload Correcto**.

> [!NOTE]
> Si tiene problemas para ejecutar el comando anterior debido a las directivas de ejecución, consulte [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies) y [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) para obtener instrucciones sobre cómo establecer directivas de ejecución.

## <a name="step-5-monitor-the-healthcare-connector"></a>Paso 5: Supervisión del conector sanitario

Después de crear el conector de Healthcare e insertar los datos de auditoría de EHR, puede ver el conector y cargar el estado en el portal de cumplimiento. Si programa el script para que se ejecute automáticamente de forma periódica, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector de Healthcare para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Última importación**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo de texto en la nube de Microsoft.

    El `RecordsSaved` campo indica el número de filas del archivo de texto que se cargó. Por ejemplo, si el archivo de texto contiene cuatro filas, el valor de los `RecordsSaved` campos es 4, si el script cargó correctamente todas las filas del archivo de texto.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Última importación**. Puede descargar el script y, a continuación, seguir los pasos para ejecutar el script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los datos de auditoría más recientes del sistema ehr sanitario están disponibles para herramientas como la solución de administración de riesgos internos, se recomienda programar el script para que se ejecute automáticamente diariamente. Esto también requiere que actualice los datos de auditoría de EHR en el mismo archivo de texto en una programación similar (si no es la misma) para que contenga la información más reciente sobre las actividades de acceso de los registros de pacientes por parte de los empleados. El objetivo es cargar los datos de auditoría más actuales para que el conector healthcare pueda ponerlos a disposición de la solución de administración de riesgos internos.

Puede usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script todos los días.

1. En el equipo local, haga clic en el botón **inicio** Windows y escriba **Programador de tareas**.

2. Haga clic en la aplicación **Programador de tareas** para abrirla.

3. En la sección **Acciones** , haga clic en **Crear tarea**.

4. En la pestaña **General** , escriba un nombre descriptivo para la tarea programada; por ejemplo, **script del conector de Healthcare**. También puede agregar una descripción opcional.

5. En **Opciones de seguridad**, haga lo siguiente:

    1. Determine si debe ejecutar el script solo cuando haya iniciado sesión en el equipo o ejecutarlo cuando haya iniciado sesión o no.

    2. Asegúrese de que está activada **la casilla Ejecutar con los privilegios más altos** .

6. Seleccione la pestaña **Desencadenadores** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

    1. En **Configuración**, seleccione la opción **Diario** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script se ejecutará todos los días a la misma hora especificada.

    2. En **Configuración avanzada**, asegúrese de que la casilla **Habilitado** está seleccionada.

    3. Haga clic en **Aceptar**.

7. Seleccione la pestaña **Acciones** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

   ![Configuración de acción para crear una nueva tarea programada para el script del conector de atención sanitaria.](../media/GenericHealthCareConnectorScheduleTask1.png)

    1. En la lista desplegable **Acción** , asegúrese de que **iniciar un programa** está seleccionado.

    2. En el cuadro **Programa o script** , haga clic en **Examinar**, vaya a la siguiente ubicación y selecciónela para que la ruta de acceso se muestre en el cuadro: C:.0.exe.

    3. En el cuadro **Agregar argumentos (opcional),** pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo: `.\HealthcareConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -filePath "C:\Healthcare\audit\records.txt"`

    4. En el cuadro **Iniciar en (opcional),** pegue la ubicación de carpeta del script que ejecutó en el paso 4. Por ejemplo, C:\Healthcare\audit.

    5. Haga clic en **Aceptar** para guardar la configuración de la nueva acción.

8. En la ventana **Crear tarea** , haga clic en **Aceptar** para guardar la tarea programada. Es posible que se le pida que escriba las credenciales de la cuenta de usuario.

   La nueva tarea se muestra en la biblioteca del programador de tareas.

   ![La nueva tarea para el script del conector de atención sanitaria se muestra en la biblioteca del programador de tareas.](../media/HealthcareConnectorTaskSchedulerLibrary.png)

   Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

   También puede comprobar la última vez que el script se ejecutó en la página de control flotante del conector de Healthcare correspondiente en el centro de cumplimiento.
