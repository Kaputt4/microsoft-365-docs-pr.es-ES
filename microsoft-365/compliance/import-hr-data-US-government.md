---
title: Configurar un conector para importar datos de recursos humanos a la nube de Us Government
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
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores de la nube del Gobierno de Estados Unidos pueden configurar un conector de datos para importar datos de empleados del sistema de recursos humanos (HR) de su organización a Microsoft 365. Esto le permite usar datos de recursos humanos en directivas de administración de riesgos internos para ayudarle a detectar actividad de usuarios específicos que pueden representar una amenaza interna para su organización.
ms.openlocfilehash: 16d6d72d557744e30d41795d5f8c8a17db81c6a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905932"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Configurar un conector para importar datos de recursos humanos en US Government

Puede configurar un conector de datos en el Centro de cumplimiento de Microsoft 365 para importar datos de recursos humanos (RRHH) a su organización gubernamental de Estados Unidos. Los datos relacionados con recursos humanos incluyen la fecha en que un empleado envió su renuncia y la fecha del último día del empleado. A continuación, las soluciones de protección de la información de Microsoft pueden usar estos datos de recursos humanos, como la solución de administración de riesgos [insider,](insider-risk-management.md)para ayudar a proteger su organización contra actividades malintencionadas o robo de datos dentro de su organización. La configuración de un conector de RECURSOS humanos consiste en crear una aplicación en Azure Active Directory que se usa para la autenticación por conector, crear un archivo de asignación CSV que contenga los datos de recursos humanos, crear un conector de datos en el centro de cumplimiento y, a continuación, ejecutar un script (de forma programada) que ingieren los datos de RECURSOS humanos en el archivo CSV a la nube de Microsoft. A continuación, la herramienta de administración de riesgos insider usa el conector de datos para obtener acceso a los datos de RECURSOS humanos que se importaron a su organización de Microsoft 365 US Government.

## <a name="before-you-begin"></a>Antes de empezar

- Al usuario que crea el conector de RECURSOS humanos en el paso 3 se le debe asignar el rol De importación de buzones de exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol Exportar importación de buzones y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Deberá determinar cómo recuperar o exportar los datos del sistema de recursos humanos de su organización (de forma regular) y agregarlos al archivo CSV que se describe en el paso 2. El script que ejecute en el paso 4 cargará los datos de RECURSOS humanos del archivo CSV en la nube de Microsoft.

- El script de ejemplo que ejecute en el paso 4 cargará datos de RECURSOS humanos en la nube de Microsoft para que puedan ser usados por otras herramientas de Microsoft, como la solución de administración de riesgos insider. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

El primer paso es crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación corresponderá al conector de recursos humanos que creas en el paso 3. La creación de esta aplicación permitirá a Azure AD autenticar el conector de RECURSOS humanos cuando se ejecute e intente acceder a su organización. Esta aplicación también se usará para autenticar el script que se ejecuta en el paso 4 para cargar los datos de recursos humanos en la nube de Microsoft. Durante la creación de esta aplicación de Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- Id. de aplicación de Azure AD (también denominado *id. de aplicación* o *id. de cliente)*

- Secreto de aplicación de Azure AD (también denominado *secreto de cliente)*

- Identificador de inquilino (también denominado *id. de directorio)*

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, vea [Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Paso 2: Preparar un archivo CSV con los datos de recursos humanos

El siguiente paso es crear un archivo CSV que contenga información sobre los empleados que han dejado la organización. Como se explica en la sección Antes de empezar, deberá determinar cómo generar este archivo CSV desde el sistema de recursos humanos de la organización. En el siguiente ejemplo se muestra un archivo CSV completado (abierto en el Bloc de notas) que contiene los tres parámetros requeridos (columnas). Es mucho más fácil editar el archivo CSV en Microsoft Excel.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

La primera fila, o fila de encabezado, del archivo CSV enumera los nombres de columna necesarios. El nombre usado en cada encabezado de columna lo tiene usted (los del ejemplo anterior son sugerencias). Sin embargo, los mismos nombres de  columna que usa en el archivo CSV deben especificarse al crear el conector de RECURSOS humanos en el paso 3. No incluya espacios en los nombres de columna.

En la tabla siguiente se describe cada columna del archivo CSV:

| Nombre de columna | Description |
|:-----|:-----|
| **EmailAddress** <br/> |Especifica la dirección de correo electrónico del empleado terminado.|
| **TerminationDate** <br/> |Especifica la fecha en que el empleo de la persona terminó oficialmente en su organización. Por ejemplo, esta puede ser la fecha en la que el empleado dio su aviso sobre la salida de la organización. Esta fecha puede ser diferente de la fecha del último día de trabajo de la persona. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|**LastWorkingDate**|Especifica el último día de trabajo del empleado terminado. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

Después de crear el archivo CSV con los datos de RECURSOS humanos necesarios, guárdalo en el mismo sistema que el script que se ejecuta en el paso 4. Asegúrese de implementar una estrategia de actualización para que el archivo CSV siempre contenga la información más actual. Al hacerlo, se garantiza que, independientemente de lo que ejecute el script, los datos de terminación de empleados más actuales se carguen en la nube de Microsoft.

## <a name="step-3-create-the-hr-connector"></a>Paso 3: Crear el conector de RECURSOS HUMANOS

El siguiente paso es crear un conector de RRHH en el Centro de cumplimiento de Microsoft 365. Después de ejecutar el script en el paso 4, el conector de RECURSOS humanos que cree ingerirá los datos de RECURSOS humanos del archivo CSV a su organización de Microsoft 365. En este paso, asegúrese de copiar el identificador de trabajo que se genera al crear el conector. Usará el identificador de trabajo al ejecutar el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Conectores de datos** en la navegación izquierda.

2. En la **página Conectores de datos** en **HR,** haga clic **en Ver**.

3. En la **página HR,** haga clic **en Agregar conector**.

4. En la **página Credenciales de autenticación,** haga lo siguiente y, a continuación, haga clic **en Siguiente**:

   1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que creó en el paso 1.

   1. Escriba un nombre para el conector de RECURSOS HUMANOS.

5. En la **página** Asignación de archivos, escriba los nombres de los tres encabezados de columna (también denominados *parámetros)* del archivo CSV que creó en el paso 2 en cada uno de los cuadros correspondientes. Los nombres no distinguen mayúsculas de minúsculas. Como se ha explicado anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de parámetro del archivo CSV. Por ejemplo, la siguiente captura de pantalla muestra los nombres de los parámetros del ejemplo del archivo CSV de ejemplo que se muestra en el paso 2.

   ![Los nombres de encabezado de columna coinciden con los del archivo CSV](../media/HRConnectorWizard3.png)

6. En la **página Revisar,** revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

   Se muestra una página de estado que confirma que se creó el conector. Esta página contiene dos cosas importantes que debe completar el siguiente paso para ejecutar el script de ejemplo para cargar los datos de RECURSOS humanos.

   ![Página de revisión con identificador de trabajo y vínculo a github para script de ejemplo](../media/HRConnector_Confirmation.png)

   1. **Id. de trabajo.** Necesitará este identificador de trabajo para ejecutar el script en el paso siguiente. Puede copiarlo desde esta página o desde la página desplegable del conector.
   
   1. **Vínculo al script de ejemplo.** Haga clic **en el** vínculo aquí para ir al sitio de GitHub para obtener acceso al script de ejemplo (el vínculo abre una nueva ventana). Mantenga esta ventana abierta para poder copiar el script en el paso 4. Como alternativa, puede marcar el destino o copiar la dirección URL para que pueda tener acceso a él de nuevo en el paso 4. Este vínculo también está disponible en la página desplegable del conector.

7. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la **pestaña Conectores.** 

8. Haga clic en el conector de RECURSOS que acaba de crear para mostrar la página desplegable, que contiene propiedades y otra información sobre el conector.

   ![Página desplegable para el nuevo conector de RECURSOS HUMANOS](../media/HRConnectorWizard7.png)

   Si aún no lo ha hecho, puede copiar los valores del identificador de aplicación **de Azure** y el identificador de trabajo **de conector**. Los necesitará para ejecutar el script en el paso siguiente. También puede descargar el script desde la página desplegable (o descargarlo mediante el vínculo en el paso siguiente).

   También puede hacer clic en **Editar** para cambiar el identificador de aplicación de Azure o los nombres de encabezado de columna que definió en la página **Asignación de** archivos.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Paso 4: Ejecutar el script de ejemplo para cargar los datos de recursos humanos

El último paso para configurar un conector de recursos humanos es ejecutar un script de ejemplo que cargará los datos de RECURSOS humanos en el archivo CSV (que creó en el paso 2) en la nube de Microsoft. En concreto, el script carga los datos en el conector de recursos humanos. Después de ejecutar el script, el conector de RECURSOS humanos que creó en el paso 3 importa los datos de RECURSOS humanos a su organización de Microsoft 365, a la que pueden acceder otras herramientas de cumplimiento, como la solución de administración de riesgos Insider. Después de ejecutar el script, considere la posibilidad de programar una tarea para ejecutarla automáticamente diariamente para que los datos de terminación de empleados más actuales se carguen en la nube de Microsoft. Vea [Programar el script para que se ejecute automáticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vaya a la ventana que dejó abierta desde el paso anterior para obtener acceso al sitio de GitHub con el script de ejemplo. Como alternativa, abra el sitio marcador o use la dirección URL que copió.

2. Haga clic en **el botón** Sin procesar para mostrar el script en la vista de texto.

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo de la organización, si es necesario.

5. Guarde el archivo de texto como un archivo Windows PowerShell script mediante un sufijo de nombre de `.ps1` archivo de ; por ejemplo, `HRConnector.ps1` .

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para cargar los datos de RECURSOS humanos del archivo CSV en la nube de Microsoft; por ejemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   En la tabla siguiente se describen los parámetros que se deben usar con este script y sus valores necesarios. La información obtenida en los pasos anteriores se usa en los valores de estos parámetros.

   | Parámetro | Description |
   |:-----|:-----|:-----|
   |`tenantId`|Identificador de la organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el identificador de  inquilino de su organización en la hoja Información general del Centro de administración de Azure AD. Esto se usa para identificar la organización.|
   |`appId` |Identificador de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 1. Azure AD lo usa para la autenticación cuando el script intenta tener acceso a su organización de Microsoft 365. |
   |`appSecret`|El secreto de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 1. También se usa para la autenticación.|
   |`jobId`|Identificador de trabajo para el conector de recursos humanos que creó en el paso 3. Esto se usa para asociar los datos de recursos humanos que se cargan en la nube de Microsoft con el conector de recursos humanos.|
   |`csvFilePath`|Ruta de acceso del archivo CSV (almacenado en el mismo sistema que el script) que creó en el paso 2. Intente evitar espacios en la ruta de acceso del archivo; de lo contrario, use comillas simples.|
   |||
   
   Este es un ejemplo de la sintaxis del script del conector de RECURSOS humanos con valores reales para cada parámetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Si la carga se realiza correctamente, el script muestra el **mensaje Cargar correctamente.**

   > [!NOTE]
   > Si tiene problemas para ejecutar el comando anterior debido a las directivas de ejecución, vea [Acerca](/powershell/module/microsoft.powershell.core/about/about_execution_policies) de las directivas de ejecución y [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) para obtener instrucciones sobre cómo establecer directivas de ejecución.

## <a name="step-5-monitor-the-hr-connector"></a>Paso 5: Supervisar el conector de RRHH

Después de crear el conector de RECURSOS humanos y ejecutar el script para cargar los datos de recursos humanos, puede ver el conector y el estado de carga en el Centro de cumplimiento de Microsoft 365. Si programa el script para que se ejecute automáticamente de forma regular, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de RECURSOS para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

   ![Página desplegable del conector de RECURSOS con propiedades y estado](../media/HRConnectorFlyout1.png)

3. En **Progreso,** haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV en la nube de Microsoft. 

   ![El archivo de registro del conector de RECURSOS muestra las filas de números del archivo CSV que se cargaron](../media/HRConnectorLogFile.png)

   El `RecordsSaved` campo indica el número de filas del archivo CSV que se cargó. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los campos es 4, si el script cargó correctamente todas las filas `RecordsSaved` del archivo CSV.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Last import**. Puede descargar el script y, a continuación, seguir los pasos del paso 4 para ejecutarlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los últimos datos de recursos humanos de su organización están disponibles para herramientas como la solución de administración de riesgos insider, se recomienda programar el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de recursos humanos del archivo CSV con una programación similar (si no es la misma) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar los datos de RECURSOS humanos más actuales para que el conector de recursos humanos pueda estar disponible para la solución de administración de riesgos de insider.

Puedes usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script todos los días.

1. En el equipo local, haga clic en el **botón** Inicio de Windows y, a continuación, escriba Programador **de tareas**.

2. Haz clic **en la aplicación Programador de** tareas para abrirlo.

3. En la **sección Acciones,** haga clic **en Crear tarea**.

4. En la **ficha General,** escriba un nombre descriptivo para la tarea programada; por ejemplo, **Script de conector de RECURSOS HUMANOS**. También puede agregar una descripción opcional.

5. En **Opciones de seguridad,** haga lo siguiente:

   1. Determine si se debe ejecutar el script solo cuando haya iniciado sesión en el equipo o cuando haya iniciado sesión o no.
   
   1. Asegúrese de que la **casilla Ejecutar con los privilegios más altos** está activada.

6. Seleccione la **pestaña Desencadenadores,** haga clic **en Nuevo** y, a continuación, haga lo siguiente:

   1. En **Configuración**, seleccione la **opción Diario** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script lo hará todos los días a la misma hora especificada.
   
   1. En **Configuración avanzada,** asegúrese de que la **casilla Habilitado** está activada.
   
   1. Haga clic en **Aceptar**.

7. Seleccione la **pestaña Acciones,** haga clic **en Nuevo** y, a continuación, haga lo siguiente:

   ![Configuración de la acción para crear una nueva tarea programada para el script del conector de RECURSOS HUMANOS](../media/HRConnectorScheduleTask1.png)

   1. En la **lista** desplegable Acción, asegúrese de que está seleccionado **Iniciar un** programa.

   1. En el **cuadro Programa/script,** haga clic en **Examinar** y vaya a la siguiente ubicación y selecciónelo para que la ruta de acceso se muestre en el cuadro: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. En el **cuadro Agregar argumentos (opcional),** pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. En el **cuadro Inicio en (opcional),** pegue la ubicación de carpeta del script que ejecutó en el paso 4. Por ejemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Haga **clic en** Aceptar para guardar la configuración de la nueva acción.

8. En la **ventana Crear tarea,** haga clic en **Aceptar** para guardar la tarea programada. Es posible que se te pida que escribas las credenciales de tu cuenta de usuario.

   La nueva tarea se muestra en la Biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la Biblioteca del programador de tareas](../media/HRConnectorTaskSchedulerLibrary.png)

   Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

   También puede comprobar la última vez que se ejecutó el script en la página desplegable del conector de RECURSOS correspondiente en el centro de cumplimiento.