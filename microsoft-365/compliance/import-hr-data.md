---
title: Configurar un conector para importar datos de RR.HH.
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
description: Los administradores pueden configurar un conector de datos para importar datos de empleados del sistema de recursos humanos (HR) de su organización a Microsoft 365. Esto le permite usar datos de recursos humanos en directivas de administración de riesgos internos para ayudarle a detectar actividad de usuarios específicos que pueden representar una amenaza interna para su organización.
ms.openlocfilehash: eb11eb5790ca9c585db8bbb95b41747a72e5c8f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911380"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Configurar un conector para importar datos de RR.HH.

Puede configurar un conector de datos en el centro de cumplimiento de Microsoft 365 para importar datos de recursos humanos (RRHH) relacionados con eventos como la dimisión de un usuario o un cambio en el nivel de trabajo de un usuario. A continuación, la solución de administración de riesgos [insider](insider-risk-management.md) puede usar los datos de recursos humanos para generar indicadores de riesgo que puedan ayudarle a identificar posibles actividades malintencionadas o robo de datos por parte de los usuarios de su organización.

La configuración de un conector para datos de recursos humanos que las directivas de administración de riesgos internas pueden usar para generar indicadores de riesgo consiste en crear un archivo CSV que contenga los datos de recursos humanos, crear una aplicación en Azure Active Directory que se use para la autenticación, crear un conector de datos de RECURSOS humanos en el centro de cumplimiento de Microsoft 365 y, a continuación, ejecutar un script (de forma programada) que ingieren los datos de RECURSOS humanos en archivos CSV a la nube de Microsoft para que esté disponible para la solución de administración de riesgos internas.

## <a name="before-you-begin"></a>Antes de empezar

- Determine qué escenarios y datos de recursos humanos se importarán a Microsoft 365. Esto le ayudará a determinar cuántos archivos CSV y conectores de RECURSOS necesitará crear y cómo generar y estructurar los archivos CSV. Los datos de recursos humanos que importa están determinados por las directivas de administración de riesgos internas que desea implementar. Para obtener más información, consulte Step 1.

- Determine cómo recuperar o exportar los datos del sistema de recursos humanos de la organización (y de forma regular) y agregarlos a los archivos CSV que cree en el paso 1. El script que ejecute en el paso 4 cargará los datos de RECURSOS humanos de los archivos CSV en la nube de Microsoft.

- Al usuario que crea el conector de recursos humanos en el paso 3 se le debe asignar el rol De importación de buzones de Exchange Online. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un nuevo grupo de roles, asignar el rol Exportar importación de buzones y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- El script de ejemplo que ejecute en el paso 4 cargará los datos de recursos humanos en la nube de Microsoft para que puedan ser usados por la solución de administración de riesgos insider. Este script de ejemplo no se admite en ningún servicio o programa de soporte técnico estándar de Microsoft. El script de ejemplo aparece "TAL CUAL", sin garantía de ningún tipo. Además, Microsoft no se hace responsable de cualquier garantía implícita, incluyendo, de manera enunciativa pero no limitativa, cualquier garantía implícita de comercialización o de calidad para cualquier propósito. Cualquier riesgo resultante del uso o rendimiento del script y la documentación de ejemplo será únicamente responsabilidad suya. En ningún caso Microsoft, sus autores o cualquier persona involucrada en su creación, producción o entrega de los scripts será responsable de cualquier daño (incluidos, de manera enunciativa pero no limitativa, daños por pérdidas de beneficios de una empresa, interrupción de la actividad de una empresa, pérdidas de información de una empresa, o cualquier otro daño pecuniario), incluso si Microsoft supiera de la posibilidad de tales daños.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Paso 1: Preparar un archivo CSV con los datos de recursos humanos

El primer paso es crear un archivo CSV que contenga los datos de recursos humanos que el conector importará a Microsoft 365. La solución de riesgo insider usará estos datos para generar indicadores de riesgo potenciales. Los datos de los siguientes escenarios de recursos humanos se pueden importar a Microsoft 365:

- Dimisión de los empleados. Información sobre los usuarios que han dejado la organización.

- Cambios en el nivel de trabajo. Información sobre los cambios en el nivel de trabajo para los usuarios, como promociones y degradaciones.

- Revisiones de rendimiento. Información sobre el rendimiento del usuario.

- Planes de mejora del rendimiento. Información sobre los planes de mejora de rendimiento para los usuarios.

El tipo de datos de recursos humanos que se importarán depende de la directiva de administración de riesgos insider y de la plantilla de directiva correspondiente que desee implementar. En la tabla siguiente se muestra qué tipo de datos de RECURSOS humanos es necesario para cada plantilla de directiva:

|  Plantilla de directiva |  Tipo de datos HR |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Robo de datos por parte de los usuarios que abandonan la organización                   | Dimisiones de empleados                                                 |
| Filtraciones de datos generales                              | No aplicable                                                        |
| Filtraciones de datos por parte de usuarios prioritarios                    | No aplicable                                                        |
| Filtraciones de datos por parte de usuarios inconformes                 | Cambios en el nivel de trabajo, revisiones de rendimiento, planes de mejora del rendimiento |
| Infracciones generales de la directiva de seguridad              | No aplicable                                                        |
| Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización   | Dimisiones de empleados                                                 |
| Infracciones de la directiva de seguridad por parte de los usuarios prioritarios    | No aplicable                                                        |
| Infracciones de la directiva de seguridad por parte de usuarios inconformes | Cambios en el nivel de trabajo, revisiones de rendimiento, planes de mejora del rendimiento |
| Lenguaje ofensivo en el correo electrónico                     | No aplicable                                                        |

Para obtener más información acerca de las plantillas de directiva para la administración de riesgos de [insider,](insider-risk-management-policies.md#policy-templates)vea Insider risk management policies .

Para cada escenario de recursos humanos, deberá proporcionar los datos de RECURSOS humanos correspondientes en uno o varios archivos CSV. Más adelante en esta sección se describe el número de archivos CSV que se usarán para la implementación de la administración de riesgos de insider.

Después de crear el archivo CSV con los datos de RECURSOS humanos necesarios, guárdalo en el equipo local en el que ejecute el script en el paso 4. También debe implementar una estrategia de actualización para asegurarse de que el archivo CSV siempre contenga la información más actualizada para que, independientemente de lo que ejecute el script, los datos de RECURSOS humanos más actuales se carguen en la nube de Microsoft y sean accesibles para la solución de administración de riesgos de insider.

> [!IMPORTANT]
> Los nombres de columna que se describen en las secciones siguientes no son parámetros obligatorios, sino solo ejemplos. Puede usar cualquier nombre de columna en los archivos CSV. Sin embargo, los nombres de  columna que use en un archivo CSV deben asignarse al tipo de datos al crear el conector de RECURSOS humanos en el paso 3. Tenga en cuenta también que los archivos CSV de ejemplo de las secciones siguientes se muestran en la vista Bloc de notas. Es mucho más fácil ver y editar archivos CSV en Microsoft Excel.

En las secciones siguientes se describen los datos CSV necesarios para cada escenario de recursos humanos.

### <a name="csv-file-for-employee-resignation-data"></a>Archivo CSV para datos de dimisión de empleados

Este es un ejemplo de un archivo CSV para datos de dimisión de empleados.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

En la tabla siguiente se describe cada columna del archivo CSV para los datos de renuncia de los empleados.

|  Columna   |   Descripción |
|:------------|:----------------|
|**EmailAddress**| Especifica la dirección de correo electrónico (UPN) del usuario terminado.|
| **ResignationDate** | Especifica la fecha en que el empleo del usuario se finalizó oficialmente en su organización. Por ejemplo, esta puede ser la fecha en la que el usuario dio su aviso sobre la salida de la organización. Esta fecha puede ser diferente de la fecha del último día de trabajo de la persona. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **LastWorkingDate** | Especifica el último día de trabajo para el usuario terminado. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

### <a name="csv-file-for-job-level-changes-data"></a>Archivo CSV para los datos de cambios de nivel de trabajo

Este es un ejemplo de un archivo CSV para los datos de cambios en el nivel de trabajo.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

En la tabla siguiente se describen cada columna del archivo CSV para los datos de cambios en el nivel de trabajo.

|  Columna | Descripción |
|:--------- |:------------- |
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en que se cambió oficialmente el nivel de trabajo del usuario. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica los comentarios que el evaluador ha proporcionado sobre el cambio de nivel de trabajo. Puede especificar un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **OldLevel**| Especifica el nivel de trabajo del usuario antes de cambiarlo. Se trata de un parámetro de texto libre y puede contener taxonomía jerárquica para su organización. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **NewLevel**| Especifica el nivel de trabajo del usuario después de cambiarlo. Se trata de un parámetro de texto libre y puede contener taxonomía jerárquica para su organización. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>Archivo CSV para datos de revisión de rendimiento

Este es un ejemplo de un archivo CSV para datos de rendimiento.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

En la tabla siguiente se describe cada columna del archivo CSV para los datos de revisión de rendimiento.

|  Columna | Descripción |
|:----------|:--------------|
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en que se informó oficialmente al usuario sobre el resultado de su revisión de rendimiento. Esta puede ser la fecha en la que finalizó el ciclo de revisión de rendimiento. Use el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica los comentarios que el evaluador ha proporcionado al usuario para la revisión de rendimiento. Se trata de un parámetro de texto con un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
| **Clasificación**| Especifica la clasificación proporcionada para la revisión de rendimiento. Se trata de un parámetro de texto y puede contener cualquier texto de forma libre que su organización use para reconocer la evaluación. Por ejemplo, "3 Expectativas cumplidas" o "2 Por debajo de la media". Se trata de un parámetro de texto con un límite de 25 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>Archivo CSV para datos del plan de mejora de rendimiento

Este es un ejemplo de un archivo CSV para los datos de los datos del plan de mejora de rendimiento.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

En la tabla siguiente se describe cada columna del archivo CSV para los datos de revisión de rendimiento.

|  Columna |  Descripción |
|:----------|:---------------|
| **EmailAddress**  | Especifica la dirección de correo electrónico del usuario (UPN).|
| **EffectiveDate** | Especifica la fecha en la que se informó oficialmente al usuario sobre su plan de mejora del rendimiento. Debe usar el siguiente formato de fecha: , que es el formato de fecha y hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentarios**| Especifica los comentarios que el evaluador ha proporcionado sobre el plan de mejora del rendimiento. Se trata de un parámetro de texto con un límite de 200 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV. |
| **Clasificación**| Especifica cualquier clasificación u otra información relacionada con la revisión de rendimiento. plan de mejora del rendimiento. Se trata de un parámetro de texto y puede contener cualquier texto de formulario libre que su organización use para reconocer la evaluación. Por ejemplo, "3 Expectativas cumplidas" o "2 Por debajo de la media". Se trata de un parámetro de texto con un límite de 25 caracteres. Este parámetro es opcional. No tiene que incluirlo en el archivo CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinación del número de archivos CSV que se usarán para los datos de RECURSOS HUMANOS

En el paso 3, puede elegir crear conectores independientes para cada tipo de datos hr o puede elegir crear un conector único para todos los tipos de datos. Puede usar archivos CSV independientes que contengan datos para un escenario de recursos humanos (como los ejemplos de los archivos CSV descritos en las secciones anteriores). Como alternativa, puede usar un único archivo CSV que contenga datos para dos o más escenarios de recursos humanos. Estas son algunas directrices que le ayudarán a determinar cuántos archivos CSV usar para los datos de recursos humanos.

- Si la directiva de administración de riesgos de insider que desea implementar requiere varios tipos de datos de recursos humanos, considere la posibilidad de usar un único archivo CSV que contenga todos los tipos de datos necesarios.

- El método para generar o recopilar los datos de recursos humanos puede determinar el número de archivos CSV. Por ejemplo, si los distintos tipos de datos de RECURSOS humanos usados para configurar un conector de RECURSOS humanos se encuentran en un único sistema de recursos humanos de la organización, es posible que pueda exportar los datos a un solo archivo CSV. Pero si los datos se distribuyen en distintos sistemas de recursos humanos, puede ser más fácil exportar datos a diferentes archivos CSV. Por ejemplo, los datos de dimisión de empleados pueden encontrarse en un sistema de recursos humanos diferente al de los datos de revisión de rendimiento o nivel de trabajo. En este caso, puede ser más fácil tener archivos CSV independientes en lugar de tener que combinar manualmente los datos en un único archivo CSV. Por lo tanto, la forma en que recupera o exporta datos de sus sistemas de recursos humanos puede determinar cómo el número de archivos CSV que necesitará.

- Como regla general, el número de conectores de RECURSOS humanos que necesitará crear viene determinado por los tipos de datos de un archivo CSV. Por ejemplo, si un archivo CSV contiene todos los tipos de datos necesarios para admitir la implementación de la administración de riesgos de insider, solo necesita un conector de recursos humanos. Pero si tiene dos archivos CSV independientes que contienen un solo tipo de datos, tendrá que crear dos conectores de RECURSOS. Una excepción a esto es que si agrega una columna **HRScenario** a un archivo CSV (vea la sección siguiente), puede configurar un único conector de RECURSOS que pueda procesar diferentes archivos CSV.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configuración de un único archivo CSV para varios tipos de datos de RRHH

Puede agregar varios tipos de datos de RRHH a un único archivo CSV. Esto es útil si la solución de administración de riesgos insider que está implementando requiere varios tipos de datos de RECURSOS humanos o si los tipos de datos se encuentran en un único sistema de RECURSOS humanos de la organización. Tener menos archivos CSV siempre le permite tener menos conectores de RECURSOS humanos para crear y administrar.

Estos son los requisitos para configurar un archivo CSV con varios tipos de datos:

- Debe agregar las columnas necesarias (y opcionales si las usa) para cada tipo de datos y el nombre de columna correspondiente en la fila de encabezado. Si un tipo de datos no corresponde a una columna, puede dejar el valor en blanco.

- Para usar un archivo CSV con varios tipos de datos de recursos humanos, el conector de recursos humanos debe saber qué filas del archivo CSV contienen los datos de HR de tipo. Esto se logra agregando una columna **HRScenario adicional** al archivo CSV. Los valores de esta columna identifican el tipo de datos de recursos humanos de cada fila. Por ejemplo, los valores que corresponden a los cuatro escenarios de recursos humanos pueden ser \` Resignation \` , Job level \` \` change, Performance review y Performance \` improvement plan \` \` \` .

- Si tiene varios archivos CSV que contienen una columna HRScenario**, asegúrese de que cada archivo usa el mismo nombre de columna y los mismos valores que identifican los escenarios de RECURSOS específicos.

En el ejemplo siguiente se muestra un archivo CSV que contiene la **columna HRScenario.** Los valores de la columna HRScenario identifican el tipo de datos de la fila correspondiente.

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
> Puede usar cualquier nombre para la columna que identifique el tipo de datos hr porque asignará el nombre de la columna en el archivo CSV como la columna que identifica el tipo de datos de RECURSOS humanos al configurar el conector en el paso 3. También asignará los valores usados para la columna de tipo de datos al configurar el conector.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Agregar la columna HRScenario a un archivo CSV que contiene un único tipo de datos

En función de los sistemas de recursos humanos de la organización y de cómo exportará los datos de RECURSOS humanos al archivo CSV, es posible que tenga que crear varios archivos CSV que contengan un único tipo de datos de RECURSOS. En este caso, todavía puede crear un único conector de RECURSOS para importar datos de diferentes archivos CSV. Para ello, solo tendrá que agregar una columna HRScenario al archivo CSV y especificar el tipo de datos hr. A continuación, puede ejecutar el script para cada archivo CSV, pero usar el mismo identificador de trabajo para el conector. Vea [el paso 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Paso 2: Crear una aplicación en Azure Active Directory

El siguiente paso es crear y registrar una nueva aplicación en Azure Active Directory (Azure AD). La aplicación corresponderá al conector de recursos humanos que creas en el paso 3. La creación de esta aplicación permitirá a Azure AD autenticar el conector de RECURSOS humanos cuando se ejecute e intente acceder a su organización. Esta aplicación también se usará para autenticar el script que se ejecuta en el paso 4 para cargar los datos de recursos humanos en la nube de Microsoft. Durante la creación de esta aplicación de Azure AD, asegúrese de guardar la siguiente información. Estos valores se usarán en los pasos 3 y 4.

- Id. de aplicación de Azure AD (también denominado *id. de aplicación* o *id. de cliente)*

- Secreto de aplicación de Azure AD (también denominado *secreto de cliente)*

- Identificador de inquilino (también denominado *id. de directorio)*

Para obtener instrucciones paso a paso para crear una aplicación en Azure AD, consulte [Register an application with the Plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>Paso 3: Crear el conector de RECURSOS HUMANOS

El siguiente paso es crear un conector de recursos humanos en el centro Microsoft 365 cumplimiento. Después de ejecutar el script en el paso 4, el conector de RECURSOS humanos que cree ingerirá los datos de RECURSOS humanos del archivo CSV a su Microsoft 365 organización. Antes de crear un conector, asegúrese de que tiene una lista de los escenarios de recursos humanos y los nombres de columna CSV correspondientes para cada uno de ellos. Debe asignar los datos necesarios para cada escenario a los nombres de columna reales del archivo CSV al configurar el conector. Como alternativa, puede cargar un archivo CSV de ejemplo al configurar el conector y el asistente le ayudará a asignar el nombre de las columnas a los tipos de datos necesarios.

Después de completar este paso, asegúrese de copiar el identificador de trabajo que se genera al crear el conector. Usará el identificador de trabajo al ejecutar el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** en la navegación izquierda.

2. En la **página Conectores de datos** en **HR,** haga clic **en Ver**.

3. En la **página Hr Custom,** haga clic **en Agregar conector**.

4. En la **página Configurar la conexión,** haga lo siguiente y, a continuación, haga clic **en Siguiente**:

   1. Escriba o pegue el identificador de aplicación de Azure AD para la aplicación de Azure que creó en el paso 2.

   1. Escriba un nombre para el conector de RECURSOS HUMANOS.

5. En la página Escenarios de recursos humanos, seleccione uno o varios escenarios de recursos humanos para los que desea importar datos y, a continuación, haga clic en **Siguiente**.

6. En la página método de asignación de archivos, seleccione una de las siguientes opciones y, a continuación, haga clic en **Siguiente**.

   - **Upload un archivo de ejemplo**. Si selecciona esta opción, haga clic Upload **archivo de ejemplo** para cargar el archivo CSV que preparó en el paso 1. Esta opción permite seleccionar rápidamente los nombres de columna en el archivo CSV de una lista desplegable para asignarlos a los tipos de datos de los escenarios de RECURSOS humanos que seleccionó anteriormente.

   O

   - **Proporcione manualmente los detalles de asignación**. Si selecciona esta opción, debe escribir el nombre de las columnas del archivo CSV para asignarlas a los tipos de datos de los escenarios de RECURSOS humanos que seleccionó anteriormente.

7. En la página Detalles de asignación de archivos, realice una de las siguientes acciones, en función de si cargó un archivo CSV de ejemplo y de si está configurando el conector para un único escenario de recursos humanos o para varios escenarios. Si ha cargado un archivo de ejemplo, no tiene que escribir los nombres de columna. Los eliges en una lista desplegable.

    - Si seleccionó un único escenario de RECURSOS humanos en el paso anterior, escriba los nombres de encabezado de columna (también denominados *parámetros)* del archivo CSV que creó en el paso 1 en cada uno de los cuadros correspondientes. Los nombres de columna que escriba no distinguen mayúsculas de minúsculas, pero asegúrese de incluir espacios si los nombres de columna del archivo CSV incluyen espacios. Como se ha explicado anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de parámetro del archivo CSV. Por ejemplo, la siguiente captura de pantalla muestra los nombres de los parámetros del archivo CSV de ejemplo para el escenario de recursos humanos de renuncia de empleados que se muestra en el paso 1.

    - Si seleccionó varios tipos de datos en el paso anterior, deberá escribir el nombre de columna de identificador que identificará el tipo de datos de RECURSOS humanos en el archivo CSV. Después de escribir el nombre de columna de identificador, escriba el valor que identifica este tipo de datos de recursos humanos y escriba los nombres de encabezado de columna para los tipos de datos seleccionados a partir de los archivos CSV que creó en el paso 1 en cada uno de los cuadros adecuados para cada tipo de datos seleccionado. Como se ha explicado anteriormente, los nombres que escriba en estos cuadros deben coincidir con los nombres de columna del archivo CSV.

8. En la **página Revisar,** revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

   Se muestra una página de estado que confirma que se creó el conector. Esta página contiene dos cosas importantes que debe completar el siguiente paso para ejecutar el script de ejemplo para cargar los datos de RECURSOS humanos.

   ![Página de revisión con identificador de trabajo y vínculo a github para script de ejemplo](../media/HRConnector_Confirmation.png)

   1. **Id. de trabajo.** Necesitará este identificador de trabajo para ejecutar el script en el paso siguiente. Puede copiarlo desde esta página o desde la página desplegable del conector.

   1. **Vínculo al script de ejemplo.** Haga clic **en el** vínculo aquí para ir al sitio GitHub para obtener acceso al script de ejemplo (el vínculo abre una nueva ventana). Mantenga esta ventana abierta para poder copiar el script en el paso 4. Como alternativa, puede marcar el destino o copiar la dirección URL para que pueda tener acceso de nuevo al ejecutar el script. Este vínculo también está disponible en la página desplegable del conector.

9. Haga clic en **Listo**.

   El nuevo conector se muestra en la lista de la **pestaña Conectores.**

10. Haga clic en el conector de RECURSOS que acaba de crear para mostrar la página desplegable, que contiene propiedades y otra información sobre el conector.

   ![Página desplegable para el nuevo conector de RECURSOS HUMANOS](../media/HRConnectorWizard7.png)

Si aún no lo ha hecho, puede copiar los valores del identificador de aplicación **de Azure** y el identificador de trabajo **de conector**. Los necesitará para ejecutar el script en el paso siguiente. También puede descargar el script desde la página desplegable (o descargarlo mediante el vínculo en el paso siguiente).

También puede hacer clic en **Editar** para cambiar el identificador de aplicación de Azure o los nombres de encabezado de columna que definió en la página **Asignación de** archivos.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Paso 4: Ejecutar el script de ejemplo para cargar los datos de recursos humanos

El último paso para configurar un conector de recursos humanos es ejecutar un script de ejemplo que cargará los datos de RECURSOS humanos en el archivo CSV (que creó en el paso 1) en la nube de Microsoft. En concreto, el script carga los datos en el conector de recursos humanos. Después de ejecutar el script, el conector de RECURSOS humanos que creó en el paso 3 importa los datos de recursos humanos a la organización de Microsoft 365 a la que pueden tener acceso otras herramientas de cumplimiento, como la solución de administración de riesgos Insider. Después de ejecutar el script, considere la posibilidad de programar una tarea para ejecutarla automáticamente diariamente para que los datos de terminación de empleados más actuales se carguen en la nube de Microsoft. Vea [Programar el script para que se ejecute automáticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vaya a la ventana que dejó abierta desde el paso anterior para obtener acceso al sitio GitHub con el script de ejemplo. Como alternativa, abra el sitio marcador o use la dirección URL que copió.

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

   | Parámetro | Descripción |
   |:-----|:-----|:-----|
   |`tenantId`|Este es el identificador de la Microsoft 365 que obtuvo en el paso 2. También puede obtener el identificador de  inquilino de su organización en la hoja Información general del Centro de administración de Azure AD. Esto se usa para identificar la organización.|
   |`appId` |Este es el identificador de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 2. Azure AD lo usa para la autenticación cuando el script intenta obtener acceso a su Microsoft 365 organización. | 
   |`appSecret`|Este es el secreto de aplicación de Azure AD para la aplicación que creó en Azure AD en el paso 2. También se usa para la autenticación.|
   |`jobId`|Este es el identificador de trabajo para el conector de RRHH que creó en el paso 3. Esto se usa para asociar los datos de recursos humanos que se cargan en la nube de Microsoft con el conector de recursos humanos.|
   |`csvFilePath`|Esta es la ruta de acceso de archivo del archivo CSV (almacenado en el mismo sistema que el script) que creó en el paso 1. Intente evitar espacios en la ruta de acceso del archivo; de lo contrario, use comillas simples.|
   |||

   Este es un ejemplo de la sintaxis del script del conector de RECURSOS humanos con valores reales para cada parámetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Si la carga se realiza correctamente, el script muestra **el Upload correcto.**

   > [!NOTE]
   > Si tiene problemas para ejecutar el comando anterior debido a las directivas de ejecución, vea [Acerca](/powershell/module/microsoft.powershell.core/about/about_execution_policies) de las directivas de ejecución y [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) para obtener instrucciones sobre cómo establecer directivas de ejecución.

## <a name="step-5-monitor-the-hr-connector"></a>Paso 5: Supervisar el conector de RRHH

Después de crear el conector de recursos humanos y ejecutar el script para cargar los datos de recursos humanos, puede ver el conector y el estado de carga en el centro de Microsoft 365 cumplimiento. Si programa el script para que se ejecute automáticamente de forma regular, también puede ver el estado actual después de la última vez que se ejecutó el script.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector de RECURSOS para mostrar la página desplegable. Esta página contiene las propiedades y la información sobre el conector.

   ![Página desplegable del conector de RECURSOS con propiedades y estado](../media/HRConnectorFlyout1.png)

3. En **Progreso,** haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene información sobre cada vez que se ejecuta el script y carga los datos del archivo CSV en la nube de Microsoft. 

   ![El archivo de registro del conector de RECURSOS muestra las filas de números del archivo CSV que se cargaron](../media/HRConnectorLogFile.png)

   El `RecordsSaved` campo indica el número de filas del archivo CSV que se cargó. Por ejemplo, si el archivo CSV contiene cuatro filas, el valor de los campos es 4, si el script cargó correctamente todas las filas `RecordsSaved` del archivo CSV.

Si no ha ejecutado el script en el paso 4, se muestra un vínculo para descargar el script en **Last import**. Puede descargar el script y, a continuación, seguir los pasos para ejecutar el script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Paso 6: Programar el script para que se ejecute automáticamente

Para asegurarse de que los últimos datos de recursos humanos de su organización están disponibles para herramientas como la solución de administración de riesgos insider, se recomienda programar el script para que se ejecute automáticamente de forma periódica, como una vez al día. Esto también requiere que actualice los datos de recursos humanos del archivo CSV con una programación similar (si no es la misma) para que contenga la información más reciente sobre los empleados que abandonan la organización. El objetivo es cargar los datos de RECURSOS humanos más actuales para que el conector de recursos humanos pueda estar disponible para la solución de administración de riesgos de insider.

Puedes usar la aplicación Programador de tareas en Windows para ejecutar automáticamente el script todos los días.

1. En el equipo local, haga clic en Windows **botón Inicio** y, a continuación, escriba Programador **de tareas**.

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

## <a name="existing-hr-connectors"></a>Conectores de RECURSOS existentes

El 20 de julio de 2020, lanzamos escenarios adicionales compatibles con conectores de recursos humanos. Estos son los escenarios de recursos humanos que se describen anteriormente en este artículo. Cualquier conector de RECURSOS humanos creado antes de esta fecha solo admite el escenario de dimisión de empleados. Si creó un conector de recursos humanos antes del 20 de julio de 2020, lo hemos migrado para que siga migrando los datos de recursos humanos a la nube de Microsoft. No tiene que hacer nada para mantener esta funcionalidad. Puede seguir usando el conector sin interrupciones.

Si desea implementar escenarios de recursos humanos adicionales, cree un nuevo conector de recursos humanos y configúrelo para los escenarios de RECURSOS adicionales que se publicaron. También tendrás que crear uno o varios archivos CSV nuevos que contengan los datos para admitir los escenarios de recursos humanos adicionales. Después de crear un nuevo conector de recursos humanos, ejecute el script con el identificador de trabajo del nuevo conector y los archivos CSV con los datos de los escenarios de RECURSOS adicionales.