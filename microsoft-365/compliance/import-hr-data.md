---
title: Configurar un conector para importar datos de RR.HH.
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de datos para importar los datos de los empleados desde el sistema de recursos humanos de la organización (HR) a Microsoft 365. Esto le permite usar datos de recursos humanos en las directivas de administración de riesgos de Insider para ayudarle a detectar la actividad de usuarios específicos que pueden suponer una amenaza interna para su organización.
ms.openlocfilehash: 0febd13003cdcb80867bd7f5b91ac482a463895a
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527592"
---
# <a name="set-up-a-connector-to-import-hr-data-preview"></a>Configurar un conector para importar datos de recursos humanos (versión preliminar)

Puede configurar un conector de datos en el centro de cumplimiento de Microsoft 365 para importar los datos de recursos humanos relacionados con eventos como la retirada de un usuario o un cambio en el nivel de trabajo de un usuario. A continuación, la [solución de administración de riesgos de Insiders](insider-risk-management.md) puede usar estos datos de recursos humanos para generar indicadores de riesgos que pueden ayudarle a identificar posibles robos de datos o actividad dañina por parte de los usuarios de la organización.

Configurar un conector para los datos de recursos humanos que las directivas de administración de riesgos de Insider pueden usar para generar indicadores de riesgo consiste en crear un archivo CSV que contenga los datos de recursos humanos, crear una aplicación en Azure Active Directory que se usa para la autenticación, crear un conector de datos de recursos humanos en el centro de cumplimiento de Microsoft 365 y, a continuación, ejecutar un script (en una base programada) que recopile los datos de recursos humanos en archivos CSV a la nube de Microsoft para que esté disponible para el Insider solución de administración de riesgos.

## <a name="before-you-begin"></a>Antes de empezar

- Determine los escenarios y datos de recursos humanos para importar a Microsoft 365. Esto le ayudará a determinar cuántos archivos CSV y conectores de recursos humanos tendrá que crear y cómo generar y estructurar los archivos. CSV. Los datos de recursos humanos que importe se determinan según las directivas de administración de riesgos de Insider que desea implementar. Para obtener más información, consulte el paso 1.

- Determine cómo recuperar o exportar los datos del sistema de RRHH de su organización (y de forma regular) y agregarlos a los archivos. CSV que se crean en el paso 1. El script que ejecutó en el paso 4 cargará los datos de recursos humanos en los archivos CSV en la nube de Microsoft.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Microsoft 365 y, a continuación, acepte la solicitud. Debe completar este paso para poder crear correctamente el conector de recursos humanos en el paso 3.

- El usuario que crea el conector de recursos humanos en el paso 3 debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

- El script de ejemplo que ejecutó en el paso 4 cargará los datos de recursos humanos en la nube de Microsoft para que la solución de administración de riesgos de Insider pueda usarlos. Este script de ejemplo no es compatible con ningún servicio o programa de soporte estándar de Microsoft. El script de ejemplo se proporciona tal cual sin garantías de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Todo el riesgo derivado del uso o el rendimiento de la secuencia de comandos de muestra y la documentación se conservan con usted. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Paso 1: preparar un archivo CSV con los datos de recursos humanos

El primer paso consiste en crear un archivo CSV que contenga los datos de recursos humanos que el conector va a importar a Microsoft 365. Esta solución de riesgo de Insider usará estos datos para generar posibles indicadores de riesgo. Los datos de los siguientes escenarios de RRHH pueden importarse a Microsoft 365:

- Retirada de empleados. Información sobre los usuarios que han abandonado la organización.

- Cambios en el nivel de trabajo. Información acerca de los cambios en el nivel de trabajo para los usuarios, como promociones y disminuciones de nivel.

- Revisiones de rendimiento. Información sobre el rendimiento del usuario.

- Planes de mejora del rendimiento. Información acerca de los planes de mejora del rendimiento para los usuarios.

El tipo de datos de recursos humanos que se va a importar depende de la Directiva de administración de riesgos de Insider y de la plantilla de directiva correspondiente que desea implementar. En la tabla siguiente se muestra qué tipo de datos de HR es necesario para cada plantilla de directiva:

| **Plantilla de directiva**| **Tipo de datos HR**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Robo de datos al pertenecer a los usuarios                   | Remesas de empleado                                                 |
| Pérdidas de datos generales                              | No aplicable                                                        |
| Pérdidas de datos por usuarios con prioridad                    | No aplicable                                                        |
| Pérdidas de datos por usuarios descontentos                 | Cambios en el nivel de trabajo, revisiones de rendimiento, planes de mejora del rendimiento |
| Infracciones de directivas de seguridad generales              | No aplicable                                                        |
| Infracciones de directivas de seguridad mediante la desactivación de usuarios   | Remesas de empleado                                                 |
| Infracciones de directivas de seguridad por usuarios con prioridad    | No aplicable                                                        |
| Violaciones de directivas de seguridad por usuarios descontentos | Cambios en el nivel de trabajo, revisiones de rendimiento, planes de mejora del rendimiento |
| Lenguaje ofensivo en el correo electrónico                     | No aplicable                                                        |

Para más información sobre las plantillas de directiva para la administración de riesgos de Insider, vea [directivas de administración de riesgos de Insider](insider-risk-management-policies.md#policy-templates).

Para cada escenario de recursos humanos, deberá proporcionar los datos de recursos humanos correspondientes en uno o más archivos CSV. El número de archivos CSV que se deben usar para la implementación de la administración de riesgos de Insider se describe más adelante en esta sección.

Después de crear el archivo CSV con los datos de HR necesarios, almacénelo en el equipo local en el que ejecute el script en el paso 4. También debe implementar una estrategia de actualización para asegurarse de que el archivo CSV siempre contiene la información más actual para que cualquier cosa que ejecute el script, los datos de recursos humanos más actuales se carguen en la nube de Microsoft y sean accesibles para la solución de administración de riesgos de Insider.

> [!IMPORTANT]
> Los nombres de columna que se describen en las siguientes secciones no son parámetros obligatorios, sino solo ejemplos. Puede usar cualquier nombre de columna en los archivos. CSV. Sin embargo, los nombres de columna que usa en un archivo CSV *deben* estar asignados al tipo de datos al crear el conector de recursos humanos en el paso 3. Además, tenga en cuenta que los archivos CSV de ejemplo de las siguientes secciones se muestran en la vista del Bloc de notas. Es mucho más fácil ver y editar archivos CSV en Microsoft Excel.

En las secciones siguientes se describen los datos de CSV necesarios para cada escenario de recursos humanos.

### <a name="csv-file-for-employee-resignation-data"></a>Archivo CSV para los datos de retirada de empleados

Este es un ejemplo de un archivo CSV para los datos de retirada de empleados.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

En la tabla siguiente se describe cada una de las columnas del archivo CSV para los datos de retirada de empleados.

| **Columna**  |  **Descripción**|
|:------------|:----------------|
|**EmailAddress**| Especifica la dirección de correo electrónico (UPN) del usuario que ha finalizado.|
| **ResignationDate** | Especifica la fecha en la que el usuario terminó oficialmente su empleo en la organización. Por ejemplo, puede ser la fecha en la que el usuario ha dado su aviso sobre cómo dejar la organización. Esta fecha puede ser distinta a la fecha del último día de trabajo de la persona. Debe usar el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **LastWorkingDate** | Especifica el último día de trabajo del usuario que ha finalizado. Debe usar el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

### <a name="csv-file-for-job-level-changes-data"></a>Datos del archivo CSV para cambios en el nivel de trabajo

A continuación, se muestra un ejemplo de un archivo CSV para los datos de cambios de nivel de trabajo.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

En la tabla siguiente se describe cada una de las columnas del archivo CSV para los datos de cambios en el nivel de trabajo.

| **Columna**|**Descripción**|
|:--------- |:------------- |
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en que se cambió oficialmente el nivel de trabajo del usuario. Debe usar el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica las notas que el evaluador ha proporcionado sobre el cambio de nivel de trabajo. Se trata de un parámetro de texto con un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **OldLevel**| Especifica el nivel de trabajo del usuario antes de que se modificara. Este es un parámetro de texto libre y puede contener una taxonomía jerárquica para su organización. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **NewLevel**| Especifica el nivel de trabajo del usuario después de que se modificó. Este es un parámetro de texto libre y puede contener una taxonomía jerárquica para su organización. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>Archivo CSV para datos de revisión de rendimiento

Este es un ejemplo de un archivo CSV para los datos de rendimiento.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

En la tabla siguiente se describe cada una de las columnas del archivo CSV para los datos de revisión de rendimiento.

| **Columna**|**Descripción**|
|:----------|:--------------|
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en la que se informará oficialmente al usuario sobre el resultado de la revisión del rendimiento. Puede ser la fecha en la que finalizó el ciclo de revisión del rendimiento. Debe usar el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica cualquier comentario que el evaluador haya proporcionado al usuario para que la revise el rendimiento. Se trata de un parámetro de texto con un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **Rating**| Especifica la clasificación proporcionada para la revisión del rendimiento. Es un parámetro de texto y puede contener cualquier texto de forma libre que la organización use para reconocer la evaluación. Por ejemplo, "3 cumplieron las expectativas" o "2 por debajo de la media". Es un parámetro de texto con un límite de 25 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>Archivo CSV para datos del plan de mejora del rendimiento

Este es un ejemplo de un archivo CSV para los datos de los datos del plan de mejora del rendimiento.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

En la tabla siguiente se describe cada una de las columnas del archivo CSV para los datos de revisión de rendimiento.

| **Columna**| **Descripción**|
|:----------|:---------------|
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en la que se informará oficialmente al usuario sobre su plan de mejora del rendimiento. Debe usar el siguiente formato de fecha: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que es el [formato de fecha y hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica cualquier comentario que el evaluador haya proporcionado sobre el plan de mejora del rendimiento. Se trata de un parámetro de texto con un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV. |
| **Rating**| Especifica cualquier clasificación u otra información relacionada con la revisión del rendimiento. Plan de mejora del rendimiento. Es un parámetro de texto y puede contener cualquier texto de forma libre que la organización use para reconocer la evaluación. Por ejemplo, "3 cumplieron las expectativas" o "2 por debajo de la media". Es un parámetro de texto con un límite de 25 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinación del número de archivos CSV que se deben usar para los datos de recursos humanos

En el paso 3, puede optar por crear conectores independientes para cada tipo de datos HR o puede elegir crear un conector único para todos los tipos de datos. Puede usar archivos. CSV independientes que contengan datos para un escenario de recursos humanos (como los ejemplos de los archivos CSV descritos en las secciones anteriores). Como alternativa, puede usar un único archivo CSV que contenga datos para dos o más escenarios de recursos humanos. Estas son algunas instrucciones que le ayudarán a determinar cuántos archivos CSV usar para los datos de recursos humanos.

- Si la Directiva de administración de riesgos de Insider que desea implementar requiere varios tipos de datos de recursos humanos, considere la posibilidad de usar un único archivo CSV que contenga todos los tipos de datos necesarios.

- El método para generar o recopilar los datos de recursos humanos puede determinar el número de archivos CSV. Por ejemplo, si los diferentes tipos de datos de recursos humanos usados para configurar un conector de recursos humanos se encuentran en un solo sistema de RRHH en su organización, es posible que pueda exportar los datos a un único archivo CSV. Pero si los datos se distribuyen entre diferentes sistemas de recursos humanos, es posible que sea más fácil exportar datos a archivos. CSV diferentes. Por ejemplo, los datos de retirada de empleados pueden estar ubicados en un sistema de recursos humanos diferente al nivel de trabajo o datos de revisión de rendimiento. En este caso, es posible que sea más fácil tener archivos CSV independientes en lugar de tener que combinar manualmente los datos en un único archivo CSV. Por lo tanto, la forma de recuperar o exportar datos de sus sistemas de recursos humanos puede determinar el número de archivos CSV que necesitará.

- Como regla general, el número de conectores de recursos humanos que necesita crear está determinado por los tipos de datos en un archivo CSV. Por ejemplo, si un archivo CSV contiene todos los tipos de datos necesarios para admitir la implementación de administración de riesgos de Insider, solo necesitará un conector de RRHH. Pero si tiene dos archivos. CSV independientes que contienen un solo tipo de datos, tendrá que crear dos conectores de recursos humanos. Una excepción a esto es que si agrega una columna **HRScenario** a un archivo CSV (consulte la siguiente sección), puede configurar un único conector de RRHH que puede procesar archivos. csv diferentes.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configuración de un único archivo CSV para varios tipos de datos de recursos humanos

Puede agregar varios tipos de datos de recursos humanos a un único archivo CSV. Esto es útil si la solución de administración de riesgos de Insider que está implementando requiere varios tipos de datos de recursos humanos o si los tipos de datos se encuentran en un solo sistema de RRHH en su organización. La necesidad de tener menos archivos CSV siempre le permite crear y administrar menos conectores de recursos humanos.

Estos son los requisitos para configurar un archivo CSV con varios tipos de datos:

- Debe agregar las columnas necesarias (y opcionales si las usa) para cada tipo de datos y el nombre de columna correspondiente en la fila de encabezado. Si un tipo de datos no corresponde a una columna, puede dejar el valor en blanco.

- Para usar un archivo CSV con varios tipos de datos de recursos humanos, el conector de recursos humanos debe saber qué filas del archivo CSV contienen datos de RR. Esto se consigue agregando una columna **HRScenario** adicional al archivo CSV. Los valores de esta columna identifican el tipo de datos de recursos humanos en cada fila. Por ejemplo, los valores que corresponden a los cuatro escenarios de recursos humanos podrían ser la \` retirada, el cambio en el \` nivel del \` trabajo, la revisión del \` \` rendimiento y el plan de mejora del \` \` rendimiento \` .

- Si tiene varios archivos CSV que contienen una columna HRScenario * *, asegúrese de que cada archivo usa el mismo nombre de columna y los mismos valores que identifican los escenarios de recursos humanos específicos.

En el ejemplo siguiente se muestra un archivo CSV que contiene la columna **HRScenario** . Los valores de la columna HRScenario identifican el tipo de datos en la fila correspondiente.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> Puede usar cualquier nombre para la columna que identifica el tipo de datos HR porque asignará el nombre de la columna en el archivo CSV como la columna que identifica el tipo de datos HR cuando configure el conector en el paso 3. También asignará los valores usados para la columna tipo de datos cuando configure el conector.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Adición de la columna HRScenario a un archivo CSV que contiene un tipo de datos único

En función de los sistemas de RRHH de la organización y de cómo se exportan los datos de RRHH a un archivo CSV, es posible que tenga que crear varios archivos CSV que contengan un solo tipo de datos de RR. En este caso, todavía puede crear un único conector de recursos humanos para importar datos de archivos. CSV diferentes. Para ello, solo tiene que agregar una columna HRScenario al archivo CSV y especificar el tipo de datos HR. A continuación, puede ejecutar el script para cada archivo CSV, pero debe usar el mismo identificador de trabajo para el conector. Consulte el [paso 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Paso 2: crear una aplicación en Azure Active Directory

El siguiente paso es crear y registrar una nueva aplicación en Azure Active Directory (AAD). La aplicación se corresponderá con el conector de RRHH que cree en el paso 3. La creación de esta aplicación permitirá que AAD autentique el conector de RRHH cuando se ejecute e intente acceder a su organización. Esta aplicación también se usará para autenticar el script que ejecutó en el paso 4 para cargar los datos de recursos humanos en la nube de Microsoft. Durante la creación de esta aplicación de AAD, asegúrese de guardar la siguiente información. Estos valores se usarán en el paso 3 y en el paso 4.

- IDENTIFICADOR de la aplicación AAD (también denominado identificador de *aplicación* o identificador de *cliente*)

- Secreto de la aplicación AAD (también denominado *secreto de cliente*)

- Identificador de inquilino (también denominado *identificador de directorio*)

Para obtener instrucciones paso a paso para crear una aplicación en AAD, vea [registrar una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>Paso 3: crear el conector de recursos humanos

El siguiente paso es crear un conector de recursos humanos en el centro de cumplimiento de Microsoft 365. Después de ejecutar el script en el paso 4, el conector de recursos humanos que cree devolverá los datos de recursos humanos del archivo CSV a la organización de Microsoft 365. Antes de crear un conector, asegúrese de que dispone de una lista de los escenarios de recursos humanos y de los nombres de columna CSV correspondientes para cada uno de ellos. Debe asignar los datos necesarios para cada escenario a los nombres de columna reales del archivo CSV al configurar el conector. Como alternativa, puede cargar un archivo CSV de muestra al configurar el conector y el asistente le ayudará a asignar el nombre de las columnas a los tipos de datos requeridos.

Después de completar este paso, asegúrese de copiar el identificador de trabajo que se genera al crear el conector. Deberá usar el identificador de trabajo cuando ejecute el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos (vista previa)** , en **HR**, haga clic en **Ver**.

3. En la página **personalizada RH** , haga clic en **Agregar conector**.

4. En la página **configurar la conexión** , realice lo siguiente y, a continuación, haga clic en **siguiente**:

   a. Escriba o pegue el identificador de la aplicación de AAD para la aplicación de Azure que creó en el paso 2.

   b. Escriba un nombre para el conector de recursos humanos.

5. En la página escenarios de recursos humanos, seleccione uno o varios escenarios de RRHH para los que desea importar datos y, a continuación, haga clic en **siguiente**.

6. En la página método de asignación de archivos, seleccione una de las siguientes opciones y, a continuación, haga clic en **siguiente**.

   - **Cargar un archivo de muestra**. Si selecciona esta opción, haga clic en **Cargar archivo de ejemplo** para cargar el archivo CSV que preparó en el paso 1. Esta opción le permite seleccionar rápidamente los nombres de columna en el archivo CSV desde una lista desplegable para asignarlos a los tipos de datos para los escenarios de recursos humanos que seleccionó anteriormente.

   O

   - **Proporcione manualmente los detalles de la asignación**. Si selecciona esta opción, tiene que escribir el nombre de las columnas en el archivo CSV para asignarlas a los tipos de datos para los escenarios de RRHH que seleccionó anteriormente.

7. En la página Detalles de la asignación de archivos, realice una de las siguientes acciones, en función de si ha cargado un archivo CSV de muestra y si está configurando el conector para un solo escenario de RRHH o para varios escenarios. Si ha cargado un archivo de muestra, no es necesario que escriba los nombres de las columnas. Puede seleccionarlos de una lista desplegable.

    - Si seleccionó un solo escenario de RRHH en el paso anterior, escriba los nombres de encabezado de columna (también denominados *parámetros*) del archivo CSV que creó en el paso 1 en cada uno de los cuadros correspondientes. Los nombres de columna que escriba no distinguen entre mayúsculas y minúsculas, pero asegúrese de incluir espacios si los nombres de las columnas del archivo CSV incluyen espacios. Como se ha explicado anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de los parámetros en el archivo CSV. Por ejemplo, en la siguiente captura de pantalla se muestran los nombres de parámetro del archivo CSV de ejemplo para el escenario de retirada de recursos humanos del empleado que se muestra en el paso 1.

    - Si seleccionó varios tipos de datos en el paso anterior, debe escribir el nombre de la columna de identificador que identificará el tipo de datos HR en el archivo CSV. Después de escribir el nombre de columna de identificador, escriba el valor que identifica este tipo de datos de HR y escriba los nombres de los encabezados de columna de los tipos de datos seleccionados de los archivos. CSV que creó en el paso 1 en cada uno de los cuadros correspondientes para cada tipo de datos seleccionado. Como se ha explicado anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de columna en el archivo CSV.

8. En la página **revisión** , revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

   Se muestra una página de estado que confirma que se ha creado el conector. Esta página contiene dos cosas importantes que necesita para completar el siguiente paso para ejecutar el script de ejemplo para cargar los datos de recursos humanos.

   ![Página revisión con identificador de trabajo y vínculo a GitHub para obtener un script de ejemplo](../media/HRConnector_Confirmation.png)

   a. **IDENTIFICADOR de trabajo.** Necesitará este identificador de trabajo para ejecutar el script en el paso siguiente. Puede copiarlo desde esta página o desde la página de control flotante de los conectores.

   b. **Vínculo al script de ejemplo.** Haga clic en **este vínculo para** ir al sitio de Github y acceder al script de ejemplo (el vínculo abre una nueva ventana). Mantenga esta ventana abierta para poder copiar el script en el paso 4. Como alternativa, puede marcar el destino o copiar la dirección URL para que pueda tener acceso de nuevo al ejecutar el script. Este vínculo también está disponible en la página de control flotante de conectores.

9. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la ficha **conectores** .

10. Haga clic en el conector de recursos humanos que acaba de crear para mostrar la página de flotante, que contiene propiedades y otra información sobre el conector.

   ![Página de control flotante para nuevo conector de recursos humanos](../media/HRConnectorWizard7.png)

Si aún no lo ha hecho, puede copiar los valores del identificador de la **aplicación de Azure** y del identificador de trabajo del **conector**. Necesitará estos para ejecutar el script en el paso siguiente. También puede descargar el script de la página flotante (o descargarlo con el vínculo en el paso siguiente).

También puede hacer clic en **Editar** para cambiar el identificador de la aplicación de Azure o los nombres de encabezado de columna que ha definido en la página **asignación de archivos** .

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Paso 4: ejecutar el script de ejemplo para cargar los datos de recursos humanos

El último paso para configurar un conector de recursos humanos es ejecutar un script de ejemplo que cargará los datos de recursos humanos en el archivo CSV (que creó en el paso 1) a la nube de Microsoft. En concreto, la secuencia de comandos carga los datos en el conector de recursos humanos. Después de ejecutar el script, el conector de recursos humanos que creó en el paso 3 importa los datos de recursos humanos a su organización de Microsoft 365, donde puede tener acceso a ellos otras herramientas de cumplimiento, como la solución de administración de riesgos de Insider. Después de ejecutar el script, considere la posibilidad de programar una tarea para que se ejecute de forma automática diariamente, de modo que los datos de finalización de los empleados más actuales se carguen en la nube de Microsoft. Consulte [programar el script para que se ejecute automáticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vaya a la ventana que dejó abierta en el paso anterior para obtener acceso al sitio de GitHub con el script de ejemplo. Como alternativa, abra el sitio marcado o use la dirección URL que ha copiado.

2. Haga clic en el botón **sin procesar** para mostrar el script en la vista de texto.

3. Copie todas las líneas del script de ejemplo y guárdelas en un archivo de texto.

4. Modifique el script de ejemplo para su organización, si es necesario.

5. Guarde el archivo de texto como un archivo de script de Windows PowerShell mediante un sufijo de nombre de archivo de `.ps1` ; por ejemplo, `HRConnector.ps1` .

6. Abra un símbolo del sistema en el equipo local y vaya al directorio donde guardó el script.

7. Ejecute el siguiente comando para cargar los datos de recursos humanos en el archivo CSV a la nube de Microsoft; por ejemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   En la tabla siguiente se describen los parámetros que se deben usar con este script y los valores necesarios. La información que ha obtenido en los pasos anteriores se usa en los valores de estos parámetros.

   |**Parámetro**|**Descripción**
   |:-----|:-----|:-----|
   |`tenantId`|Este es el identificador de la organización de Microsoft 365 que obtuvo en el paso 2. También puede obtener el identificador de inquilino de su organización en la hoja de **información general** del centro de administración de Azure ad. Se usa para identificar la organización.|
   |`appId` |Este es el identificador de la aplicación de AAD para la aplicación que ha creado en Azure AD en el paso 2. Esto lo usa Azure AD para la autenticación cuando el script intenta obtener acceso a la organización de 365 de Microsoft. | 
   |`appSecret`|Este es el secreto de la aplicación de AAD para la aplicación que ha creado en Azure AD en el paso 2. También se usa para la autenticación.|
   |`jobId`|Se trata del identificador de trabajo para el conector de recursos humanos que creó en el paso 3. Se usa para asociar los datos de recursos humanos cargados en la nube de Microsoft con el conector de recursos humanos.|
   |`csvFilePath`|Esta es la ruta de acceso del archivo CSV (que se almacena en el mismo sistema que el script) que creó en el paso 1. Intente evitar espacios en la ruta de acceso al archivo; de lo contrario, use comillas simples.|
   |||

   A continuación, se muestra un ejemplo de la sintaxis del script del conector de recursos humanos con valores reales para cada parámetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Si la carga se realiza correctamente, el script muestra el mensaje de **carga correcta** .

## <a name="step-5-monitor-the-hr-connector"></a>Paso 5: supervisar el conector de recursos humanos

Después de crear el conector de recursos humanos y ejecutar el script para cargar los datos de recursos humanos, puede ver el conector y el estado de carga en el centro de cumplimiento de Microsoft 365. Si programa la secuencia de comandos para que se ejecute automáticamente periódicamente, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **conectores** y, a continuación, seleccione el conector de RRHH para mostrar la página de flotante, que contiene las propiedades y la información sobre el conector.

   ![Página de control flotante de conector de RRHH con propiedades y estado](../media/HRConnectorFlyout1.png)

3. En **curso**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV a la nube de Microsoft. 

   ![El archivo de registro del conector de recursos humanos muestra las filas de números del archivo CSV que se cargaron](../media/HRConnectorLogFile.png)

   El `RecordsSaved` campo indica el número de filas que se han cargado en el archivo CSV. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los `RecordsSaved` campos es 4, si el script cargó correctamente todas las filas en el archivo CSV.

Si no ha ejecutado el script en el paso 4, en la **última importación**se muestra un vínculo para descargar el script. Puede descargar el script y, a continuación, seguir los pasos para ejecutar el script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Opcional Paso 6: programar el script para que se ejecute automáticamente

Para asegurarse de que los datos de recursos humanos más recientes de su organización están disponibles para herramientas como la solución de administración de riesgos de Insider, le recomendamos que programe el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de recursos humanos en el archivo CSV en una programación similar, si no es la misma, para que contenga la información más reciente acerca de los empleados que dejan la organización. El objetivo es cargar los datos de recursos humanos más actuales para que el conector de recursos humanos pueda ponerlos a disposición de la solución de administración de riesgos de Insider.

Puede usar la aplicación programador de tareas de Windows para ejecutar el script de forma automática cada día.

1. En el equipo local, haga clic en el botón **Inicio** de Windows y, a continuación, escriba **programador de tareas**.

2. Haga clic en la aplicación **programador de tareas** para abrirla.

3. En la sección **acciones** , haga clic en **crear tarea**.

4. En la pestaña **General** , escriba un nombre descriptivo para la tarea programada; por ejemplo, **script de conector de recursos humanos**. También puede Agregar una descripción opcional.

5. En **Opciones de seguridad**, haga lo siguiente:

   a. Determine si desea ejecutar el script solo cuando haya iniciado sesión en el equipo o ejecutarlo cuando haya iniciado sesión o no.

   b. Asegúrese de que la casilla **ejecutar con los privilegios más altos** está seleccionada.

6. Seleccione la pestaña **desencadenadores** , haga clic en **nuevo**y, a continuación, realice las siguientes acciones:

   a. En **configuración**, seleccione la opción **diariamente** y, a continuación, elija una fecha y hora para ejecutar el script por primera vez. El script será cada día a la misma hora especificada.

   b. En **Configuración avanzada**, asegúrese de que esté activada la casilla de verificación **habilitado** .

   c. Haga clic en **Aceptar**.

7. Seleccione la pestaña **acciones** , haga clic en **nueva**y, a continuación, realice las siguientes acciones:

   ![Configuración de la acción para crear una nueva tarea programada para el script del conector de recursos humanos](../media/HRConnectorScheduleTask1.png)

   a. En la lista desplegable **acción** , asegúrese de que está seleccionado **iniciar un programa** .

   b. En el cuadro **programa/script** , haga clic en **examinar**, vaya a la siguiente ubicación y selecciónela para que la ruta de acceso aparezca en el cuadro: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   c. En el cuadro **Agregar argumentos (opcional)** , pegue el mismo comando de script que ejecutó en el paso 4. Por ejemplo: `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. En el cuadro **iniciar en (opcional)** , pegue la ubicación de la carpeta del script que ejecutó en el paso 4. Por ejemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   e. Haga clic en **Aceptar** para guardar la configuración de la nueva acción.

8. En la ventana **crear tarea** , haga clic en **Aceptar** para guardar la tarea programada. Es posible que se le pida que escriba sus credenciales de cuenta de usuario.

   La nueva tarea se muestra en la biblioteca del programador de tareas.

   ![La nueva tarea se muestra en la biblioteca del programador de tareas](../media/HRConnectorTaskSchedulerLibrary.png)

   Se muestra la última vez que se ejecutó el script y la próxima vez que está programado para ejecutarse. Puede hacer doble clic en la tarea para editarla.

   También puede comprobar la última vez que se ejecutó el script en la página flotante del conector HR correspondiente en el centro de cumplimiento.

## <a name="existing-hr-connectors"></a>Conectores de recursos humanos existentes

El 20 de julio de 2020, publicamos escenarios adicionales compatibles con los conectores de recursos humanos. Estos son los escenarios de recursos humanos que se han descrito anteriormente en este artículo. Los conectores de recursos humanos creados antes de esta fecha solo admiten el escenario de retirada de empleados. Si ha creado un conector de recursos humanos antes del 20 de julio de 2020, lo hemos migrado para que continúe migrando los datos de recursos humanos a la nube de Microsoft. No tiene que hacer nada para mantener esta funcionalidad. Puede seguir usando el conector sin interrupciones.

Si desea implementar escenarios de recursos humanos adicionales, cree un nuevo conector de recursos humanos y configúrelo para los escenarios de recursos humanos adicionales que se publicaron. También tendrá que crear uno o más archivos CSV nuevos que contengan los datos para admitir los escenarios de recursos humanos adicionales. Después de crear un nuevo conector de recursos humanos, ejecute el script con el identificador de trabajo del nuevo conector y los archivos. CSV con los datos de los escenarios de RRHH adicionales.
