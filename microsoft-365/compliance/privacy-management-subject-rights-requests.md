---
title: Administrar solicitudes de derechos de sujeto en administración de privacidad de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: La solución de solicitud de derechos de sujeto en administración de privacidad de Microsoft le ayuda a encontrar datos personales y colaborar en la revisión del contenido y la creación de informes.
ms.openlocfilehash: b266708c97ee4b81af6ba61dfa6716c57ff6026e
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419783"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>Administrar solicitudes de derechos de sujeto en la administración de privacidad (versión preliminar)

En este artículo: obtenga información sobre cómo usar la solución de solicitud de derechos de sujeto para buscar datos **personales** en su **entorno,** colaborar en revisiones, crear informes y **automatizar** tareas clave.

## <a name="purpose-of-subject-rights-requests"></a>Finalidad de las solicitudes de derechos del sujeto

La administración de privacidad proporciona potentes capacidades de solicitudes de derechos de sujeto para ayudarle a administrar las solicitudes de personas que buscan administrar sus datos personales dentro de su organización. Estas solicitudes a veces también se conocen como solicitudes de interesados (DSR), solicitudes de acceso de interesados (DSARs) o solicitudes de derechos de consumidor. La administración de privacidad permite al personal responsable de cumplir las solicitudes de derechos del sujeto identificar fácilmente a los interesados y encontrar su información personal entre los datos de su organización en Exchange, SharePoint, OneDrive y Teams.

La administración de privacidad es única capaz de ayudarle a priorizar los elementos que deben revisarse dentro de los datos que recopila para estas solicitudes. La solución es consciente Microsoft Information Protection etiquetas de confidencialidad, que indican contenido potencialmente confidencial y pueden necesitar una revisión especial, y marca los elementos con estas etiquetas. Para obtener más información acerca de las etiquetas de confidencialidad, [vea Learn about sensitivity labels](sensitivity-labels.md). Además, la administración de privacidad puede detectar y marcar los elementos que contienen los datos de varias personas, donde es posible que tenga que redactar contenido antes de suministrarlo al interesado.

Una vez recopilados y evaluados los datos, puede seleccionar los elementos más relevantes que se incluirán en sus informes y exportaciones, y colaborar de forma segura con otros miembros del equipo para mover las solicitudes hacia su finalización.

## <a name="get-started-with-subject-rights-requests"></a>Introducción a las solicitudes de derechos de sujeto

La administración de privacidad proporciona un centro central para que los administradores de privacidad puedan controlar las solicitudes de derechos de sujeto que su organización ha recibido.

Para empezar a controlar un nuevo caso de solicitud o para trabajar en una solicitud en curso, visite la página principal Solicitudes de derechos **del** sujeto. Proporciona una introducción visual a los casos que el equipo ha creado dentro de la administración de privacidad, su estado (activo, cerrado o vencido) y los tipos de solicitud y una lista filtrable de todas las solicitudes. Esta página también es donde puede ir para abrir una nueva solicitud.

Para ver detalles sobre los casos abiertos, seleccione cualquier solicitud de la lista y elija **Ir a los detalles de la solicitud.** Para obtener más información, vea [Review and take action on requests](#review-and-take-action-on-requests).

Para abrir una nueva solicitud, vea [Create a request](#create-a-request).

## <a name="create-a-request"></a>Crear una solicitud

Los administradores de administración de derechos de sujeto pueden usar el asistente de administración de privacidad para crear solicitudes. El asistente le guiará a través del proceso de búsqueda de datos personales sobre un interesado y el cumplimiento de su solicitud.

Los cuatro pasos principales incluyen los siguientes.

### <a name="identify-the-data-subject"></a>Identificar al interesado

Proporcione el nombre del sujeto que realizó la solicitud y especifique su relación con su empresa.

### <a name="select-the-request-type"></a>Seleccionar el tipo de solicitud

Elija un tipo de solicitud en función de lo que el interesado desea que haga con sus datos. Si su solicitud se relaciona con un reglamento de privacidad de datos específico, también puede seleccionarlo en una lista proporcionada para agregar más contexto. Establecer una fecha límite (requerida) hará que sea fácil ordenar las solicitudes que se acercan o vencidas y resolverlas en tiempo y forma. Los tipos de solicitud incluyen:

- **Access:** proporciona un resumen de la información personal del interesado en poder de su organización en Microsoft 365.
- **Export:** proporciona un resumen y una exportación de la información personal del interesado, tal como se recopila y se anota durante la revisión.
- **Lista etiquetada para seguimiento:** genera un resumen de archivos que pueden requerir acciones adicionales fuera de la administración de privacidad. Un escenario de ejemplo puede ser si necesita facilitar la eliminación de la información personal del interesado según su solicitud.

### <a name="confirm-the-request-name"></a>Confirmar el nombre de la solicitud

Este paso le permite confirmar el nombre de esta solicitud y agregar una descripción opcional para su referencia.

### <a name="review-and-finish"></a>Revisar y finalizar

Un resumen de lo que ha escrito durante los pasos anteriores. Cualquier campo se puede editar antes de seleccionar **Crear solicitud**.

En este nivel, algunas propiedades se pueden editar después de crear la solicitud, incluida la fecha límite, el nombre de la solicitud y la descripción, pero las propiedades clave como la identidad del asunto no se pueden cambiar. Para editar una solicitud existente, buscala en la lista de solicitudes de la página Solicitudes de derechos del sujeto y usa la **acción Editar detalles de solicitud.**

## <a name="review-and-take-action-on-requests"></a>Revisar y tomar medidas en las solicitudes

Una vez abierta una solicitud, la administración de privacidad empezará a buscar Microsoft 365 datos para encontrar datos sobre su asunto. Para ver los resultados iniciales, seleccione esa solicitud en la lista y elija **Ir a los detalles de la solicitud.** Aquí puede obtener más información sobre las propiedades de la solicitud, los resultados de búsqueda y el estado de la solicitud. Esta página también se convertirá en el centro para trabajar y colaborar en la administración de los archivos encontrados, la creación de informes y exportaciones y la finalización de la solicitud.

Los iconos de esta página incluyen:

- **Detalles:** los detalles básicos sobre la solicitud, incluida la fecha límite y la fecha de solicitud, su descripción y el reglamento de privacidad relacionado.
- **Progreso:** escala de tiempo que indica los pasos completados y las tareas pendientes de finalizar.
- **Resumen de estimación de datos:** información general sobre los datos evaluados en la búsqueda. Para obtener más información sobre esta información, vea Ver y editar consultas de búsqueda.
- **Elementos** prioritarios para revisar: si procede, se mostrará información sobre los elementos importantes que la administración de privacidad ha detectado por usted, incluida la información confidencial que ya lleva una etiqueta de confidencialidad de Microsoft, o los elementos con datos sobre varias personas que pueden requerir una redacción. Los elementos de prioridad se pueden encontrar en Datos recopilados mediante el filtrado por la columna "Tipos de prioridad".

### <a name="monitor-progress-and-complete-requests"></a>Supervisar el progreso y completar las solicitudes

Las solicitudes de derechos de sujeto pasan por varias fases en el camino a la finalización. Algunas fases progresan automáticamente a medida que la administración de privacidad realiza su evaluación de datos y otras avanzan cuando los derechos del sujeto solicitan a los administradores y colaboradores que completen pasos esenciales como revisar, seleccionar y redactar archivos.

Dado que es posible que las solicitudes deban trabajarse con el tiempo o con varios colaboradores, la administración de privacidad proporciona actualizaciones continuas sobre el estado de una solicitud y guía sobre los siguientes pasos a seguir. Estas actualizaciones se pueden ver en la página de información general de la solicitud de derechos del sujeto. Las fases de progreso incluyen lo siguiente.

#### <a name="data-estimate"></a>Estimación de datos

La estimación de datos es la fase inicial de la evaluación de datos. Después de crear una solicitud, la administración de privacidad identifica cuántos elementos de los datos de la organización incluyen posibles coincidencias con el interesado y toma nota de dónde están estos elementos en Microsoft 365. Una vez realizada la estimación de datos, puede obtener una vista previa de los resultados y revisar los detalles de la consulta de búsqueda original. Si desea editar la consulta de búsqueda, vea las instrucciones en [Ver y editar consultas de búsqueda](#view-and-edit-search-queries). Si los resultados iniciales son satisfactorios, puede continuar con la recuperación **de datos**.

- Se pueden recuperar hasta 10 000 elementos individuales de cualquier búsqueda. Los archivos asociados con un elemento que coincida (por ejemplo, datos adjuntos de archivos en un correo electrónico) pueden contar para el total. Si la búsqueda supera el umbral de recuento de archivos, intente revisar la búsqueda para refinar su ámbito. Vea la [sección Ver y editar consultas de búsqueda](#view-and-edit-search-queries) para obtener más información. No podrá editar la consulta de búsqueda una vez que inicie la fase de recuperación de datos.

#### <a name="retrieve-data"></a>Recuperar datos

Esta fase indica que la administración de privacidad está en proceso de recuperar los datos. Una vez completado, se avanzará automáticamente para revisar **los datos**.

#### <a name="review-data"></a>Revisar datos

En esta fase, los colaboradores deben revisar los resultados en la pestaña Datos recopilados. Entre los pasos esenciales se incluyen:

- Elija si desea incluir los elementos identificados en los resúmenes o exportaciones. Si no es necesaria una coincidencia notificada en el informe o exportación, seleccione la opción "Excluir". Si el contenido parece ser un falso positivo, puedes elegir "No coincidir" para excluir el archivo de los informes finales y marcar el elemento como algo que no debería haber sido recogido por la solicitud. Para establecer el estado de un elemento, use el menú de acción (puntos suspensivos verticales) junto a su nombre y seleccione la opción que desee. Si se le pide, agregue una nota de referencia interna para explicar su decisión. Las notas son necesarias al excluir archivos.
- Use la **opción Aplicar etiquetas** para ayudarle a identificar los elementos que necesitan atención. Las etiquetas disponibles incluyen opciones proporcionadas por el sistema, por ejemplo, etiquetar un elemento para seguimiento y pueden incluir etiquetas personalizadas según se define en Configuración.
- Use **Anotación para** crear marcas o redacciones en línea en un archivo seleccionado. Por ejemplo, si necesita incluir un archivo para una persona que también  contiene la información personal de otros, puede usar la redacción área (debajo del botón Dibujo de la barra de comandos) para cerrar toda la información que no pertenezca a la persona que realizó la solicitud. Una vez completadas las ediciones, seleccione Incluir para agregar el archivo redactado a la solicitud. Tenga en cuenta que la anotación crea una copia del archivo, de modo que no se altere nada en el archivo original y permanezca en su ubicación original. La copia se almacena en el blob de Azure y permanecerá durante el período de retención de datos indicado. Para obtener más información, vea [Retención de datos a](#data-retention) continuación.
- Para revisar las notas de un elemento, selecciónelo y vaya a la pestaña Notas del archivo. También puede usar la opción Agregar nota de archivo para crear un nuevo comentario. Para revisar o agregar notas en un nivel de caso general, vaya a la pestaña Notas principal anterior y use **Agregar nota de caso**. Estas notas serán visibles para los usuarios que trabajen en la solicitud, pero no se incluirán en el informe final ni se compartirán con el interesado.

Cuando se hayan revisado todos los elementos y se hayan establecido sus estados, seleccione **Completar** revisión para abrir un panel de sobrevía donde puede revisar un resumen de los datos y agregar las notas relevantes. Estas notas son para el mantenimiento de registros internos y no se comparten con el interesado. Seleccione Completar revisión de nuevo para pasar a la siguiente fase. Los resúmenes de sus decisiones se proporcionan más adelante en la pestaña Informes.

#### <a name="generate-reports"></a>Genere informes

Esta fase indica que se están generando los informes. Una vez completados, se pueden encontrar en la **pestaña** Informes. Los archivos terminados aquí se pueden exportar para su entrega al interesado que realizó la solicitud.

#### <a name="close-the-request"></a>Cerrar la solicitud

Cuando haya realizado las acciones necesarias para resolver la solicitud de derechos del sujeto, elija **Cerrar la solicitud**. Esto crea el informe final, que se cifrará y estará disponible en la **pestaña** Informes. Esto puede tardar un tiempo en función del número de archivos de la solicitud.

### <a name="view-and-edit-search-queries"></a>Ver y editar consultas de búsqueda

Para ver información detallada sobre la búsqueda de datos detrás de una solicitud de derechos de sujeto, seleccione **Ver** detalles de consulta de búsqueda en la tarjeta de resumen de estimación de datos. Se abre un panel que resume la consulta y muestra más detalles sobre lo que se encontró.

Aquí tendrá la opción obtener una vista **previa** de los resultados de la búsqueda para ver qué tipo de contenido se devolverá para esta consulta. Si determina que desea cambiar las propiedades de esta búsqueda y no ha iniciado la fase Recuperar datos, puede usar la opción Editar consulta **de** búsqueda. Este asistente ofrece la capacidad de cambiar o agregar propiedades para la identificación del interesado, los filtros y condiciones de búsqueda y las ubicaciones en las que buscar datos (incluidos Exchange, SharePoint, OneDrive o Teams). Usa estas opciones para alcanzar el nivel de especificidad deseado. Puede revisar la versión final de la nueva consulta antes de presionar **Guardar**.

Cuando termine de editar la consulta de búsqueda, se ejecutará una nueva búsqueda para reemplazar los resultados de búsqueda anteriores. Esto restablece el estado de la sección Progreso al primer paso, **Estimación de datos.** La nueva búsqueda puede tardar hasta 60 minutos en completarse. Una vez hecho esto, verá los resultados actualizados en la página de detalles de la solicitud.

### <a name="data-retention"></a>Retención de datos

Los informes generados a través de esta herramienta y los datos asociados, como los archivos anotados guardados en Azure, se almacenan durante un período de tiempo especificado. Esta duración se define a nivel global a través de **Configuración** en la sección **Períodos** de retención de datos, que le permiten elegir entre 30 y 90 días. Para obtener más información, vea [Introducción a la administración de privacidad.](privacy-management-setup.md)

## <a name="collaborate-on-requests-with-teams"></a>Colaborar en solicitudes con Teams

La administración de privacidad admite la colaboración Microsoft Teams para permitir que el grupo colabore en solicitudes de derechos de sujeto. Al crear una nueva solicitud, se crea automáticamente un canal de Teams y se asocia a la solicitud de forma predeterminada. Aquí puede analizar la solicitud y compartir de forma segura la entrada y las contribuciones a medida que avanza hacia su finalización. Para unirse a la conversación, abra la solicitud y use la **opción Chat with collaborators.** Esto abrirá Microsoft Teams y lo colocará en el canal General del sitio de grupo de la solicitud de derechos de sujeto.

Para revisar la lista de colaboradores activos que pueden ver y contribuir a su sitio de grupo, dentro de su solicitud de derechos de asunto, abra la **pestaña Colaboradores.** Para agregar usuarios adicionales para colaborar en esta solicitud, seleccione la opción Agregar un colaborador.

Para cambiar el comportamiento predeterminado de generar sitios Teams al crear una solicitud de derechos de sujeto, seleccione el engranaje **Configuración** **Teams** en la esquina superior derecha de la página de solicitud de derechos del sujeto y seleccione una colaboración para modificar la configuración.

También puede usar  la opción Compartir en la parte superior derecha dentro de una solicitud de derechos de sujeto para hacer que las personas entren a través de Teams o correo electrónico, o para copiar el vínculo a la página en la administración de privacidad. Compartir a través de Teams le permitirá seleccionar un sitio de Teams existente disponible para su cuenta y seleccionar un canal específico dentro de ese sitio donde se publique el vínculo a este caso junto con cualquier mensaje que proporcione.

## <a name="automate-subject-rights-request-tasks"></a>Automatizar tareas de solicitud de derechos de sujeto

Microsoft Power Automate es un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Al habilitar los flujos Power Automate para la administración de privacidad, puede automatizar tareas importantes para casos y usuarios. Para obtener más información sobre Power Automate, visite su [sitio de documentación](/power-automate/getting-started).

Los clientes con Microsoft 365 que incluyan la administración de privacidad no necesitan otras licencias de Power Automate para usar las plantillas de administración de privacidad Power Automate privacidad recomendadas. Estas plantillas se pueden personalizar para admitir su organización y cubrir los escenarios principales de administración de privacidad. Si elige usar características de Power Automate premium en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, puede que necesite más licencias de Power Automate.

Las siguientes Power Automate se incluyen en la administración de privacidad:

- **Cree un registro para casos de administración** de privacidad en ServiceNow: esta plantilla es para las organizaciones que desean usar su solución ServiceNow para realizar un seguimiento de los casos de solicitud de derechos de sujeto. Se le pedirá que escriba los detalles de la instancia de ServiceNow. Una vez conectado a la instancia, los administradores de solicitudes de derechos de sujeto podrán crear un registro para el caso en ServiceNow y personalizar lo que la plantilla rellenará en campos seleccionados si es necesario. Para obtener más información sobre el conector, vea la página de referencia [de ServiceNow Connector](/connectors/service-now/).
- **Crear un aviso de calendario:** esta plantilla es para establecer avisos de fecha de vencimiento en el calendario de Outlook para solicitudes de derechos de sujeto. La herramienta rellenará determinados detalles de las propiedades de la solicitud, como el nombre de la solicitud y su fecha de vencimiento. Puede agregar detalles descriptivos, especificar destinatarios y ajustar otras configuraciones avanzadas.

### <a name="create-a-new-power-automate-flow-from-a-template"></a>Crear un nuevo flujo Power Automate de una plantilla

Para empezar, abra la solicitud de derechos de sujeto con la que desea trabajar, seleccione **Automatizar** y, a continuación, seleccione **Administrar Power Automate flujos**. Se abre el panel desplegable Flujos. Use la opción Nuevo y elija la plantilla que desea usar de las opciones disponibles. Desde aquí, sigue las indicaciones para completar la configuración.

Después de guardar una instancia de la plantilla, debe ejecutarla desde la página de detalles de la solicitud de derechos de sujeto para que la instancia de flujo tenga el contexto y el identificador adecuados. Abra la solicitud, vuelva al menú **Automatizar,** seleccione la plantilla y seleccione **Ejecutar flujo**. Puede ver las actividades anteriores seleccionando **Ver actividad de ejecución de flujo**.

### <a name="share-a-power-automate-flow"></a>Compartir un flujo Power Automate de datos

Al compartir un Power Automate, puede agregar otro propietario y permitirle editar, actualizar y eliminar el flujo. Todos los propietarios también pueden tener acceso al historial de ejecución y agregar o quitar otros propietarios. Para compartir un flujo, abra la solicitud de derechos de sujeto con la que desea trabajar, seleccione **Automatizar** y, a continuación, seleccione **Administrar Power Automate flujos**. En este panel puede seleccionar un flujo existente y, a continuación, usar la opción Compartir para agregar un usuario o un grupo.

Este panel también le ofrece la opción de administrar las conexiones incrustadas a los servicios que se usan en el Power Automate flujo. Cambiar esta configuración puede afectar a la capacidad de ejecutar el flujo.

### <a name="edit-or-delete-power-automate-flow"></a>Editar o eliminar Power Automate flujo

Para ajustar los detalles de un flujo Power Automate, abra la solicitud de derechos del sujeto, seleccione **Automatizar** y seleccione Administrar **Power Automate flujos**. En este panel, puede seleccionar un flujo existente para ver detalles. Use Editar en cualquier sección para cambiar las propiedades y, a continuación, guardar.

Para quitar el flujo por completo, use la **opción** Eliminar. Quitará el flujo de todos los propietarios y lo desinstalará para todos los usuarios. Las instancias de flujo anteriores seguirán en ejecución para evitar la pérdida de datos. Puedes confirmar tu elección antes de que la eliminación sea definitiva.

## <a name="data-matching"></a>Coincidencia de datos

Con la coincidencia de datos, las organizaciones pueden habilitar la solución de administración de privacidad para identificar a los interesados en función de los valores de datos proporcionados exactamente. Esto puede ayudar a aumentar la precisión de la localización del contenido del interesado tanto para el personal interno como para los usuarios externos con los que interactúa. También simplifica la necesidad de proporcionar campos manualmente durante la creación de solicitudes de derechos de sujeto y proporciona contexto dentro de las solicitudes de derechos del sujeto y para el icono Información general que muestra los elementos con más contenido del interesado. Para obtener más información sobre esa vista, vea [Buscar y visualizar los datos](privacy-management-data-profile.md#items-with-the-most-data-subject-content).

Para usar la característica de coincidencia de datos, deberá ser miembro del grupo de roles De administración de privacidad. Seleccione el icono de engranaje de configuración de la parte superior derecha de la página de solicitudes de derechos del sujeto principal y seleccione **Coincidencia de datos**. A partir de aquí, deberá definir el esquema de datos personales y proporcionar una carga de datos personales como se muestra a continuación. Ten en cuenta que puedes agregar elementos y puedes eliminar los elementos que agregues a través de la interfaz de usuario. Sin embargo, no puedes modificar un elemento en su lugar desde la interfaz de usuario en este momento.

### <a name="prepare-for-data-import"></a>Preparar la importación de datos

Antes de definir el esquema o cargar datos, deberá identificar el origen de la información del interesado. El formato de archivo requerido es .csv, que puede leer una aplicación como Microsoft Excel. Estructura esta exportación para que los encabezados de columna aparezcan en la primera fila. Estos encabezados deben incluir los nombres de los atributos del esquema de datos personales. Compruebe el formato de los datos en cada campo. Si alguno de los datos contiene comas, envuelve estos valores entre comillas dobles para asegurarse de que no se analizarán en campos independientes.

### <a name="define-the-personal-data-schema"></a>Definir el esquema de datos personales

El esquema de datos personales describirá los atributos de los interesados. Upload este esquema en la primera pestaña del área de configuración de coincidencia de datos. Los archivos necesarios incluyen un archivo XML **de esquema de datos** personales y un archivo XML del paquete **de** reglas.

#### <a name="personal-data-schema-xml"></a>XML de esquema de datos personales

El archivo de esquema de datos personales es un archivo XML que definirá los nombres de columna que se esperan.

- Asigne a este archivo de *esquemapdm.xml*.
- Defina cada nombre de columna con la etiqueta Nombre de campo como se muestra en el ejemplo siguiente.
- Use searchable = "true" para los campos que desea que se puedan buscar, hasta un máximo de cinco campos. Al menos uno de los nombres de campo debe poder buscarse. Sintaxis de ejemplo: `\<Field name="" searchable=""/>` .
- El esquema de datos personales tiene una sección de etiqueta DataStore. Se deben asignar cuatro campos obligatorios a los nombres de los campos: primaryKeyField, upnField, firstNameField, lastNameField.

Por ejemplo, el siguiente archivo XML define un esquema de ejemplo, con cinco campos especificados como buscables: PatientID, MRN, SSN, Teléfono y DOB. PrimaryKeyField se asigna a PatientID, upnField se asigna a MRN, firstNameField se asigna a FirstName y lastNameField se asigna a LastName.

Puede copiar, modificar y usar nuestro ejemplo.

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>XML del paquete de reglas

Al configurar el paquete de reglas, asegúrese de hacer referencia correctamente al archivo de esquema de datos personales creado anteriormente: pdm.xml. En el siguiente código XML del paquete de reglas de ejemplo, se deben personalizar los siguientes campos para crear el tipo confidencial de coincidencia de datos:

- **Id. rulePack**  &  **Id. de PrivacyMatch:** use New-GUID para generar un GUID.
- **Almacén de datos:** este campo especifica el almacén de datos de búsqueda de coincidencia de datos personales que se va a usar. Proporcione el nombre datastore definido de un esquema de datos personales configurado.
- **idMatch:** este campo apunta al elemento principal de la coincidencia de datos personales.
  - **Matches:** especifica el campo que se usará en la búsqueda exacta. Proporcione un nombre de campo que se puede buscar desde el esquema de datos personales.
  - **Clasificación:** este campo especifica la coincidencia de tipo confidencial que desencadena la búsqueda de coincidencia de datos personales. Puede especificar el nombre o el GUID de una clasificación personalizada o integrada existente. Para evitar problemas de rendimiento, si usa un tipo de información confidencial personalizado como elemento Classification en la coincidencia de datos personales, no use un tipo de información confidencial personalizado que coincida con un gran porcentaje de contenido (como "cualquier número" o "cualquier palabra de cinco letras"). Se recomienda agregar palabras clave de compatibilidad o incluir formato en la definición del tipo de información confidencial de clasificación personalizada.
- **Match:** este campo apunta a pruebas adicionales encontradas cerca de idMatch.
  - **Matches:** proporcione cualquier nombre de campo en el esquema de datos personales de DataStore.
- **Recurso:** esta sección especifica el nombre y la descripción del tipo confidencial en varias configuraciones regionales.
  - **idRef:** proporcione guid para el identificador ExactMatch.
  - **Nombre & descripciones:** personalizar según sea necesario.

En el siguiente ejemplo XML del paquete de reglas, estamos haciendo referencia pdm.xml archivo de ejemplo del paso anterior que crea el XML del esquema de datos personales:

- **Almacén de datos:** el nombre dataStore hace referencia al archivo de esquema que creamos anteriormente: dataStore = "PatientRecords".
- **idMatch:** el valor idMatch hace referencia a un campo que se puede buscar que aparece en el archivo pdm.xml que creamos anteriormente: idMatch matches = "SSN".
  - **Clasificación:** el valor de clasificación hace referencia a un tipo de información confidencial existente o personalizada: classification = "U.S. Social Security Number (SSN)". (En este caso, usamos el tipo de información confidencial existente del número de la seguridad social de Estados Unidos).

Cree un paquete de regla en formato XML (con codificación Unicode), como en el siguiente código de ejemplo. Puede copiar, modificar y usar este ejemplo.

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>Upload datos personales
Después de definir el esquema de datos personales, puede realizar la carga de datos **personales** en la segunda pestaña de la página de configuración de coincidencia de datos. Al seleccionar **Agregar**, elija el esquema personal que definió en el primer paso y, a continuación, cargue el archivo que contiene los datos personales.

Puede cargar estos datos personales eligiendo un archivo local o suministrando una dirección URL de SAS a una ubicación Microsoft Azure Storage que contenga el archivo de datos personales.
Si ha preparado un archivo como primer paso de este proceso que se ajusta al esquema creado, puede usar ese archivo para la carga.
