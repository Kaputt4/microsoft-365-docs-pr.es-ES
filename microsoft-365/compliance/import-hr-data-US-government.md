---
title: Configuración de un conector para importar datos de RR. HH. a la nube del Gobierno de EE. UU.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
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
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores de la nube del Gobierno de EE. UU. pueden configurar un conector de datos para importar datos de empleados desde el sistema de recursos humanos (RR. HH.) de su organización a Microsoft 365. Esto le permite usar datos de RR. HH. en directivas de administración de riesgos internos para ayudarle a detectar la actividad de usuarios específicos que pueden suponer una amenaza interna para su organización.
ms.openlocfilehash: f8a8c302b226951631ab2bdd70a2f7cadf2e4657
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67826454"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Configuración de un conector para importar datos de RR. HH. en el Gobierno de EE. UU.

Puede configurar un conector de datos en el portal de cumplimiento Microsoft Purview para importar datos de recursos humanos (RR. HH.) a su organización del Gobierno de EE. UU. Los datos relacionados con RR. HH. incluyen la fecha en que un empleado presentó su renuncia y la fecha del último día del empleado. A continuación, las soluciones de protección de la información de Microsoft pueden usar estos datos de RR. HH., como la [solución de administración de riesgos internos](insider-risk-management.md), para ayudar a proteger su organización frente a actividades malintencionadas o robo de datos dentro de su organización. La configuración de un conector de RR. HH. consiste en crear una aplicación en Azure Active Directory que se usa para la autenticación mediante el conector, crear un archivo de asignación CSV que contenga los datos de RR. HH., crear un conector de datos en el centro de cumplimiento y, a continuación, ejecutar un script (de forma programada) que ingiera los datos de RR. HH. en el archivo CSV en la nube de Microsoft. A continuación, la herramienta de administración de riesgos internos usa el conector de datos para acceder a los datos de RR. HH. que se importaron a su organización de Microsoft 365 US Government.

## <a name="before-you-begin"></a>Antes de empezar

- Al usuario que crea el conector de RR. HH. en el paso 3 se le debe asignar el rol Administración conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

   > [!NOTE]
   > El rol de Administración del conector de datos no se admite actualmente en los entornos GCC High y DoD del Gobierno de EE. UU. Por lo tanto, al usuario que crea el conector de RR. HH. en entornos de GCC High y DoD se le debe asignar el rol Exportación de importación de buzones en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol Exportar importación de buzón y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [Crear grupos de roles](/Exchange/permissions-exo/role-groups#create-role-groups) o [Modificar grupos de roles](/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo "Administrar grupos de roles en Exchange Online".

- Tendrá que determinar cómo recuperar o exportar los datos del sistema de RR. HH. de su organización (de forma periódica) y agregarlos al archivo CSV que se describe en el paso 2. El script que ejecute en el paso 4 cargará los datos de RR. HH. en el archivo CSV en la nube de Microsoft.

- El script de ejemplo que ejecute en el paso 4 cargará datos de RR. HH. en la nube de Microsoft para que puedan usarlos otras herramientas de Microsoft, como la solución de administración de riesgos internos. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Creación de una aplicación en Azure Active Directory

El primer paso consiste en crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación se corresponderá con el conector de RR. HH. que cree en el paso 3. La creación de esta aplicación permitirá que Azure AD autentique el conector de RR. HH. cuando se ejecute e intente acceder a su organización. Esta aplicación también se usará para autenticar el script que se ejecuta en el paso 4 para cargar los datos de RR. HH. en la nube de Microsoft. Durante la creación de esta aplicación de Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en pasos posteriores.

- Identificador de aplicación de Azure AD (también denominado *id. de aplicación* o *id. de cliente*)

- Secreto de aplicación de Azure AD (también denominado *secreto de cliente*)

- Id. de inquilino (también denominado *id. de directorio*)

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, consulte [Registro de una aplicación con el Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Paso 2: Preparación de un archivo CSV con los datos de RR. HH.

El siguiente paso es crear un archivo CSV que contenga información sobre los empleados que han abandonado la organización. Como se explica en la sección Antes de comenzar, deberá determinar cómo generar este archivo CSV desde el sistema de RR. HH. de la organización. En el ejemplo siguiente se muestra un archivo CSV completado (abierto en el Panel de notas) que contiene los tres parámetros necesarios (columnas). Es mucho más fácil editar el archivo CSV en Microsoft Excel.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

La primera fila, o fila de encabezado, del archivo CSV enumera los nombres de columna necesarios. El nombre usado en cada encabezado de columna depende de usted (los del ejemplo anterior son sugerencias). Sin embargo, se *deben* especificar los mismos nombres de columna que se usan en el archivo CSV al crear el conector de RR. HH. en el paso 3. No incluya espacios en los nombres de columna.

En la tabla siguiente se describe cada columna del archivo CSV:

| Nombre de columna | Descripción |
|:-----|:-----|
| **EmailAddress** <br/> |Especifica la dirección de correo electrónico del empleado terminado.|
| **TerminationDate** <br/> |Especifica la fecha en que se finalizó oficialmente el empleo de la persona en su organización. Por ejemplo, esta puede ser la fecha en que el empleado dio su aviso sobre la salida de la organización. Esta fecha puede ser diferente de la fecha del último día de trabajo de la persona. Use el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|**LastWorkingDate**|Especifica el último día de trabajo para el empleado terminado. Use el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`, que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

Después de crear el archivo CSV con los datos de RR. HH. necesarios, almacénelo en el mismo sistema que el script que se ejecuta en el paso 4. Asegúrese de implementar una estrategia de actualización para que el archivo CSV contenga siempre la información más reciente. Al hacerlo, se garantiza que, sea cual sea el script que ejecute, los datos de terminación de empleados más actuales se carguen en la nube de Microsoft.

## <a name="step-3-create-the-hr-connector"></a>Paso 3: Creación del conector de RR. HH.

El siguiente paso es crear un conector de RR. HH. en el portal de cumplimiento. Después de ejecutar el script en el paso 4, el conector de RR. HH. que cree ingerirá los datos de RR. HH. del archivo CSV en la organización de Microsoft 365. En este paso, asegúrese de copiar el identificador de trabajo que se genera al crear el conector. Usará el identificador de trabajo al ejecutar el script.

1. Vaya al portal de cumplimiento y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**La página Conectores de datos**</a>.

2. En la página **Conectores de datos** en **RR. HH.**, haga clic en **Ver**.

3. En la página **RR. HH.** , haga clic en **Agregar conector**.

4. En la página **Credenciales de autenticación** , haga lo siguiente y, a continuación, haga clic en **Siguiente**:

   1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que creó en el paso 1.

   1. Escriba un nombre para el conector de RR. HH.

5. En la página **Asignación** de archivos, escriba los nombres de los tres encabezados de columna (también *denominados parámetros*) del archivo CSV que creó en el paso 2 en cada uno de los cuadros adecuados. Los nombres no distinguen mayúsculas de minúsculas. Como se explicó anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de parámetro del archivo CSV. Por ejemplo, en la captura de pantalla siguiente se muestran los nombres de parámetros del ejemplo en el archivo CSV de ejemplo que se muestra en el paso 2.

   ![Los nombres de encabezado de columna coinciden con los del archivo CSV.](../media/HRConnectorWizard3.png)

6. En la página **Revisar** , revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

   Se muestra una página de estado que confirma que se creó el conector. Esta página contiene dos cosas importantes que necesita para completar el siguiente paso para ejecutar el script de ejemplo para cargar los datos de RR. HH.

   ![Página de revisión con el identificador de trabajo y vínculo a GitHub para obtener un script de ejemplo.](../media/HRConnector_Confirmation.png)

   1. **Id. de trabajo.** Necesitará este identificador de trabajo para ejecutar el script en el paso siguiente. Puede copiarlo desde esta página o desde la página de control flotante del conector.
   
   1. **Vínculo a script de ejemplo.** Haga clic en el vínculo **aquí** para ir al sitio de GitHub para acceder al script de ejemplo (el vínculo abre una nueva ventana). Mantenga esta ventana abierta para que pueda copiar el script en el paso 4. Como alternativa, puede marcar el destino o copiar la dirección URL para poder acceder a ella de nuevo en el paso 4. Este vínculo también está disponible en la página de control flotante del conector.

7. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la pestaña **Conectores** . 

8. Haga clic en el conector de RR. HH. que acaba de crear para mostrar la página de control flotante, que contiene propiedades y otra información sobre el conector.

   ![Página de control flotante para el nuevo conector de RR. HH.](../media/HRConnectorWizard7.png)

   Si aún no lo ha hecho, puede copiar los valores del **identificador de App de Azure** y el **identificador del trabajo del conector**. Necesitará estos para ejecutar el script en el paso siguiente. También puede descargar el script desde la página de control flotante (o descargarlo mediante el vínculo del paso siguiente).

   También puede hacer clic en **Editar** para cambiar el identificador de App de Azure o los nombres de encabezado de columna que definió en la página **Asignación de** archivos.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Paso 4: Ejecución del script de ejemplo para cargar los datos de RR. HH.

El último paso para configurar un conector de RR. HH. es ejecutar un script de ejemplo que cargará los datos de RR. HH. en el archivo CSV (que creó en el paso 2) en la nube de Microsoft. En concreto, el script carga los datos en el conector de RR. HH. Después de ejecutar el script, el conector de RR. HH. que creó en el paso 3 importa los datos de RR. HH. a la organización de Microsoft 365, donde se puede acceder a ellos mediante otras herramientas de cumplimiento, como la solución de administración de riesgos Insider. Después de ejecutar el script, considere la posibilidad de programar una tarea para ejecutarla automáticamente diariamente para que los datos de terminación de empleados más actuales se carguen en la nube de Microsoft. Consulte [Programación del script para que se ejecute automáticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vaya a la ventana que dejó abierta desde el paso anterior para acceder al sitio de GitHub con el script de ejemplo. Como alternativa, abra el sitio marcado o use la dirección URL que copió.

2. Haga clic en el botón **Sin formato** para mostrar el script en la vista de texto.

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo de su organización, si es necesario.

5. Guarde el archivo de texto como un archivo de script Windows PowerShell usando un sufijo de nombre de archivo de `.ps1`; por ejemplo, `HRConnector.ps1`.

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para cargar los datos de RR. HH. en el archivo CSV en la nube de Microsoft; por ejemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   En la tabla siguiente se describen los parámetros que se usarán con este script y sus valores necesarios. La información obtenida en los pasos anteriores se usa en los valores de estos parámetros.

   | Parámetro | Descripción |
   |:-----|:-----|:-----|
   |`tenantId`|Identificador de la organización de Microsoft 365 que obtuvo en el paso 1. También puede obtener el identificador de inquilino de su organización en la hoja **Información general** del Centro de administración de Azure AD. Esto se usa para identificar su organización.|
   |`appId` |Identificador de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 1. Azure AD lo usa para la autenticación cuando el script intenta acceder a la organización de Microsoft 365. |
   |`appSecret`|Secreto de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 1. Esto también se usa para la autenticación.|
   |`jobId`|Identificador de trabajo para el conector de RR. HH. que creó en el paso 3. Esto se usa para asociar los datos de RR. HH. que se cargan en la nube de Microsoft con el conector de RR. HH.|
   |`csvFilePath`|Ruta de acceso del archivo CSV (almacenada en el mismo sistema que el script) que creó en el paso 2. Intente evitar espacios en la ruta de acceso del archivo; de lo contrario, use comillas simples.|
   |||
   
   Este es un ejemplo de la sintaxis del script del conector de RR. HH. mediante valores reales para cada parámetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Si la carga se realiza correctamente, el script muestra el mensaje **Cargar correctamente** .

   > [!NOTE]
   > Si tiene problemas para ejecutar el comando anterior debido a las directivas de ejecución, consulte [Acerca de las directivas de ejecución](/powershell/module/microsoft.powershell.core/about/about_execution_policies) y [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) para obtener instrucciones sobre cómo establecer directivas de ejecución.

## <a name="step-5-monitor-the-hr-connector"></a>Paso 5: Supervisión del conector de RR. HH.

Después de crear el conector de RR. HH. y ejecutar el script para cargar los datos de RR. HH., puede ver el conector y cargar el estado en el portal de cumplimiento. Si programa el script para que se ejecute automáticamente de forma periódica, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya al portal de cumplimiento y seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**Conectores de datos**</a>.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector de RR. HH. para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

   ![Página de control flotante del conector de RR. HH. con propiedades y estado.](../media/HRConnectorFlyout1.png)

3. En **Progreso**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV en la nube de Microsoft. 

   ![El archivo de registro del conector de RR. HH. muestra el número de filas del archivo CSV que se cargaron.](../media/HRConnectorLogFile.png)

   El `RecordsSaved` campo indica el número de filas del archivo CSV que se cargó. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los `RecordsSaved` campos es 4, si el script cargó correctamente todas las filas del archivo CSV.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Última importación**. Puede descargar el script y, a continuación, seguir los pasos del paso 4 para ejecutarlo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los datos de RR. HH. más recientes de su organización están disponibles para herramientas como la solución de administración de riesgos internos, se recomienda programar el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de RR. HH. en el archivo CSV en una programación similar (si no es la misma) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar los datos de RR. HH. más actuales para que el conector de RR. HH. pueda ponerlos a disposición de la solución de administración de riesgos internos.

Puede usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script todos los días.

1. En el equipo local, haga clic en el botón **Inicio** de Windows y escriba **Programador de tareas**.

2. Haga clic en la aplicación **Programador de tareas** para abrirla.

3. En la sección **Acciones** , haga clic en **Crear tarea**.

4. En la pestaña **General** , escriba un nombre descriptivo para la tarea programada; por ejemplo, **script del conector de RR. HH**. También puede agregar una descripción opcional.

5. En **Opciones de seguridad**, haga lo siguiente:

   1. Determine si debe ejecutar el script solo cuando haya iniciado sesión en el equipo o ejecutarlo cuando haya iniciado sesión o no.
   
   1. Asegúrese de que está activada **la casilla Ejecutar con los privilegios más altos** .

6. Seleccione la pestaña **Desencadenadores** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

   1. En **Configuración**, seleccione la opción **Diario** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script se ejecutará todos los días a la misma hora especificada.
   
   1. En **Configuración avanzada**, asegúrese de que la casilla **Habilitado** está seleccionada.
   
   1. Haga clic en **Aceptar**.

7. Seleccione la pestaña **Acciones** , haga clic en **Nuevo** y, a continuación, haga lo siguiente:

   ![Configuración de acción para crear una nueva tarea programada para el script del conector de RR. HH.](../media/HRConnectorScheduleTask1.png)

   1. En la lista desplegable **Acción** , asegúrese de que **iniciar un programa** está seleccionado.

   1. En el cuadro **Programa o script** , haga clic en **Examinar**, vaya a la siguiente ubicación y selecciónela para que la ruta de acceso se muestre en el cuadro : `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`.

   1. En el cuadro **Agregar argumentos (opcional),** pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. En el cuadro **Iniciar en (opcional),** pegue la ubicación de carpeta del script que ejecutó en el paso 4. Por ejemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Haga clic en **Aceptar** para guardar la configuración de la nueva acción.

8. En la ventana **Crear tarea** , haga clic en **Aceptar** para guardar la tarea programada. Es posible que se le pida que escriba las credenciales de la cuenta de usuario.

   La nueva tarea se muestra en la biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la biblioteca del programador de tareas.](../media/HRConnectorTaskSchedulerLibrary.png)

   Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

   También puede comprobar la última vez que el script se ejecutó en la página de control flotante del conector de RR. HH. correspondiente en el centro de cumplimiento.