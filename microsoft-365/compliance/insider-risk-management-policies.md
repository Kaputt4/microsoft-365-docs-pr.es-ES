---
title: Directivas de administración de riesgos de Insider
description: Obtenga información sobre las directivas de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: e135ceec2ac4abcd0bfd5183fb19089a97dc4bb4
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043301"
---
# <a name="insider-risk-management-policies"></a>Directivas de administración de riesgos de Insider

Las directivas de administración de riesgos de Insider determinan qué empleados están en el ámbito y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de la organización, o bien definir grupos o usuarios individuales para la administración en una directiva. Las directivas admiten las prioridades de contenido para centrarse en las condiciones de la Directiva en varios o distintos equipos de Microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Mediante el uso de plantillas, incluyen indicadores de riesgos específicos y la cantidad de peso que tienen asignada dentro de una directiva, que determinan con eficacia el peso de cada desencadenador de alertas de la Directiva. Las ventanas de directivas permiten definir el intervalo de tiempo para aplicar la Directiva a las actividades de alerta y se usan para determinar la duración de la Directiva una vez activada. El límite máximo de directivas es cinco directivas activas al mismo tiempo. Sin embargo, puede configurar directivas adicionales y activar y desactivar directivas según sea necesario.

## <a name="policy-dashboard"></a>Panel de directivas

El **Panel de directivas** permite ver rápidamente las directivas de la organización y el estado actual de las alertas asociadas a cada Directiva.

- **Nombre de directiva**: nombre asignado a la Directiva en el Asistente para directivas.
- **Alertas activas**: el número de alertas activas para cada Directiva.
- **Alertas confirmadas**: número total de alertas que se produjeron en casos de la Directiva en los últimos 365 días.
- **Acciones realizadas en las alertas**: el número total de alertas que se han confirmado o desechado durante los últimos 365 días.
- **Eficacia**de la Directiva: el porcentaje determinado por las alertas confirmadas totales dividido por las acciones totales realizadas en las alertas (que es la suma de las alertas que se confirmaron o despasón durante el año anterior).
- **Active**: el estado del caso, ya sea *sí* o *no*.

![Panel de directivas de administración de riesgos de Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de administración de riesgos de internación son condiciones de directiva predefinidas que definen los tipos de indicadores de riesgo supervisados por una directiva. Cada Directiva debe tener una plantilla asignada en el Asistente para la creación de directivas antes de que se cree la Directiva. Al crear una nueva Directiva de riesgos de Insider, tendrás que elegir una de las siguientes plantillas.

### <a name="departing-employee-data-theft"></a>Robo de datos del empleado

Cuando los empleados dejan la organización, hay indicadores de riesgos específicos normalmente asociados con el robo de datos al abandonar a los empleados. Esta plantilla de directiva da prioridad a estos indicadores y se centra en la detección y las alertas de este área de riesgos. El robo de datos por parte de los empleados puede incluir la descarga de archivos desde SharePoint Online, la copia de archivos en dispositivos portátiles como unidades USB, la impresión de archivos y la copia de datos a servicios de almacenamiento y de mensajería en la nube personal, cerca de las fechas de retirada y de finalización del empleo. Esta plantilla prioriza los indicadores de riesgos relacionados con estas actividades y el modo en que se relacionan con el estado de empleo de los empleados.

>[!IMPORTANT]
>Cuando use esta plantilla, debe configurar un conector de Microsoft 365 de RRHH para importar periódicamente la información de fecha de retirada y de cancelación para los empleados de su organización. Consulte el tema de [importación de datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso sobre la configuración del conector de 365 de RRHH de Microsoft para su organización.

### <a name="data-leaks"></a>Pérdidas de datos

La protección de datos y la prevención de pérdidas de datos es un reto constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por empleados, dispositivos y servicios. Los empleados están capacitados para crear, almacenar y compartir información a través de servicios y dispositivos que hacen que la administración de pérdidas de datos sea cada vez más compleja y difícil. Las pérdidas de datos pueden incluir el reuso compartido accidental de información fuera de la organización o el robo de datos con malas intenciones. Esta plantilla da prioridad a la detección en tiempo real de descargas de datos sospechosas de SharePoint Online, uso compartido de archivos y carpetas, copiando archivos en dispositivos portátiles, como unidades USB, archivos de impresión y copiando datos en servicios de almacenamiento y mensajería en la nube personal.

>[!IMPORTANT]
>Al usar esta plantilla, debe configurar al menos una directiva de prevención de pérdida de datos (DLP) para definir la información confidencial de su organización. Consulte el tema [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para la organización.

### <a name="offensive-language-in-email"></a>Lenguaje ofensivo en el correo electrónico

La detección y la realización de acciones para evitar el comportamiento ofensivo y abusivo es un componente crítico de evitar el riesgo. Los clasificadores de idiomas ofensivos integrados en Microsoft 365 pueden analizar los mensajes de correo electrónico enviados desde buzones de Exchange online en su organización para diferentes tipos de problemas de cumplimiento. Estos clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el idioma en el correo electrónico que probablemente infrinja las directivas de Antiacoso. Use esta plantilla para crear rápidamente una directiva que use estos clasificadores para detectar automáticamente el contenido de los mensajes de correo electrónico que puedan considerarse abusivos u ofensivos. La administración de riesgos de Insiders usa clasificadores que exploran mensajes de correo electrónico enviados según los términos del idioma inglés y que se recomiendan en lenguaje ofensivo.

## <a name="policy-settings"></a>Configuración de directivas

La configuración de los riesgos de Insider se aplica a todas las directivas de administración de riesgos de Insider, independientemente de la plantilla que elija al crear una directiva. La configuración se configura con el control de **configuración de riesgos de Insider** ubicado en la parte superior de todas las pestañas de administración de riesgos de Insider. Esta configuración controla la privacidad, los indicadores, las ventanas de supervisión y las detecciones inteligentes.

### <a name="privacy"></a>Privacidad

La protección de la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en la investigación de datos y análisis de revisiones de alertas de riesgo de Insider. Para los usuarios con coincidencias de directivas de riesgos de Insider, puede elegir una de las siguientes opciones:

- **Mostrar anonimizan versiones de nombres de**usuario: los nombres de usuario son anonimizan para evitar que los administradores, investigadores de datos y revisores vean quiénes están asociados a las alertas de directiva. Por ejemplo, un usuario de "el período de gracia de Taylor" aparecería con un Pseudonym aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de administración de riesgos de Insider. La elección de esta opción anonymizes todos los usuarios con coincidencias de directivas actuales y pasadas y se aplica a todas las directivas. Cuando se selecciona esta opción, la información de Perfil de usuario en la alerta de riesgo de Insider y los detalles de casos no estarán disponibles. Sin embargo, los nombres de usuario se muestran cuando se agregan nuevos usuarios a directivas existentes o cuando se asignan usuarios a nuevas directivas. Si decide desactivar esta opción, los nombres de usuario se mostrarán para todos los usuarios que tengan coincidencias de directivas actuales o pasadas.
- **No mostrar anonimizan versiones de nombres de usuario**: los nombres de usuario se muestran en todas las coincidencias de directivas actuales y pasadas para alertas y casos. La información del perfil de usuario (el nombre, el cargo, el alias y la organización o departamento) se muestra al usuario para todos los casos y alertas de administración de riesgos del Insider.

### <a name="indicators"></a>Indicadores

Plantillas de directivas de riesgos de Insider definen el tipo de actividades de riesgo que desea detectar e investigar. Cada plantilla de Directiva se basa en indicadores específicos que se corresponden con las tareas y las actividades de riesgo específicas que las directivas desencadenan cuando los usuarios realizan actividades relacionadas con estos indicadores. En algunos casos, es posible que quiera limitar los indicadores que se aplican a las directivas de riesgo de Insider de su organización. Puede desactivar los indicadores para áreas específicas si los deshabilita en todas las directivas de riesgo de Insider.

Para definir los indicadores que están habilitados en todas las directivas, vaya a > **indicadores** de **configuración de riesgos de Insider**y seleccione uno o más indicadores. Los indicadores seleccionados en la página de configuración de **indicadores** no se pueden configurar individualmente al crear o editar una directiva de riesgos del Insider en el Asistente para directivas.

>[!IMPORTANT]
>Para recibir alertas de actividad arriesgada definida en las directivas, debe seleccionar uno o más indicadores antes de configurar una directiva de riesgo de Insiders.

### <a name="policy-timeframes"></a>Plazos de la Directiva

Los plazos de la Directiva permiten definir períodos de revisión pasados y futuros que se desencadenan después de las coincidencias de directivas basadas en eventos y actividades para las plantillas de directiva de administración de riesgos de Insider. Según la plantilla de directiva que elija, estarán disponibles los siguientes intervalos de tiempo de la Directiva:

- **Ventana activación**: disponible para todas las plantillas de Directiva, la *ventana de activación* es el número de días definido que la ventana activa **después** de un evento desencadenante. La ventana se activa durante 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido la *ventana de activación* en 30 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa la *ventana de activación* y la Directiva está activa para ese usuario durante 30 días después de que se haya producido el evento desencadenante.
- **Detección de actividad pasada**: disponible para todas las plantillas de Directiva, la *detección de actividad anterior* es el número de días definidos que la ventana activa **antes** de un evento desencadenante. La ventana se activa de 0 a 180 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido la *detección de actividad pasada* en 90 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa la *detección de actividad pasada* y la Directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.

### <a name="intelligent-detections"></a>Detecciones inteligentes

La configuración de detección inteligente ayuda a refinar cómo se procesan las detecciones de actividades de riesgo para las alertas. En determinadas circunstancias, es posible que necesite definir tipos de archivo para omitir o desea aplicar un nivel de detección para los archivos a fin de definir una barra mínima para las alertas. Al usar directivas de lenguaje ofensivo, es posible que deba aumentar o disminuir la sensibilidad de la detección para controlar la cantidad de coincidencias de directivas de informes. Use estas opciones para controlar las exclusiones de tipo de archivo, los límites del volumen de archivo y la sensibilidad de detección de idioma ofensivo.

#### <a name="anomaly-detections"></a>Detecciones de anomalías

Las detecciones anómalas incluyen la configuración de las exclusiones de tipo de archivo y los límites del volumen de archivo.

- **Exclusiones de tipo de archivo**: para excluir tipos de archivo específicos de toda la coincidencia de directivas de administración de riesgos de Insider, escriba extensiones de tipo de archivo separadas por comas. Por ejemplo, para excluir determinados tipos de archivos de música de las coincidencias de directivas, puede escribir *AAC, MP3, WAV, WMA* en el campo **exclusiones de tipo de archivo** . Todas las directivas de administración de riesgos de Insider omitirán los archivos con estas extensiones.
- **Límite de corte del volumen del archivo**: para definir un nivel de archivo mínimo antes de notificar las alertas de actividad en las directivas de riesgo de Insider, escriba el número de archivos. Por ejemplo, escribiría ' 10 ' si no desea generar alertas de riesgo de Insider cuando un usuario descarga 10 archivos o menos, incluso si las directivas consideran que esta actividad es una anomalía.

#### <a name="offensive-language-detections"></a>Detecciones de idiomas ofensivos

Para ajustar la confidencialidad del clasificador de idioma ofensivo para las directivas que usan el *idioma ofensivo en* la plantilla de correo electrónico, elija una de las siguientes opciones:

- **Bajo**: el nivel de confidencialidad más bajo con el intervalo más amplio para la detección de un idioma y una opinión ofensivos. La probabilidad de falsos positivos para la coincidencia de idiomas ofensivos es elevada.
- **Media**: el nivel de confidencialidad de nivel medio con un intervalo equilibrado para la sumisión y el lenguaje ofensivo de detección. La probabilidad de falsos positivos para la coincidencia de lenguaje ofensivo es la media.
- **Alta**: el nivel de confidencialidad más alto con un intervalo estrecho para la detección de lenguaje ofensivo y su opinión. La probabilidad de falsos positivos para la coincidencia de lenguaje ofensivo es baja.

## <a name="create-a-new-policy"></a>Crear una nueva directiva

Para crear una nueva Directiva de administración de riesgos de Insider, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para crear una nueva Directiva:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. Seleccione **crear Directiva** para abrir el Asistente para directivas
3. En la página **asigne un nombre a la Directiva y elija una plantilla** , complete los campos siguientes:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la Directiva.
    - **Descripción (opcional)**: escriba una descripción para la Directiva.
    - **Elegir plantilla de directiva (obligatorio)**: Seleccione una de las [plantillas de directiva](insider-risk-management-policies.md#policy-templates) para definir los tipos de indicadores de riesgo que se supervisan mediante la Directiva.

    >[!IMPORTANT]
    >Si selecciona la plantilla de *fugas de datos* , tendrá que configurar al menos una directiva DLP que asignará más adelante en el asistente. Si selecciona la plantilla de *robo de datos de empleado* de la que se descargan, tendrá que configurar el conector de recursos humanos para que use las características de detección de señal completa de la plantilla de directiva.

4. Seleccione **siguiente** para continuar.
5. En la página **elegir usuarios y grupos** , seleccione **elegir usuarios o grupos** para definir qué usuarios se incluyen en la Directiva o seleccione **todos los usuarios y grupos con correo habilitado** . Seleccione **siguiente** para continuar.
6. En la página **especificar el contenido que va a priorizar (opcional)** , puede asignar una calificación de riesgo mayor a la actividad detectada en función de dónde se encuentre el contenido relacionado, de la información confidencial que se incluye y de las etiquetas de confidencialidad que se aplican:
    - Sitios de SharePoint: seleccione **elegir sitios de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de información confidencial: seleccione **elegir tipos de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - Etiquetas de confidencialidad: seleccione **elegir etiquetas de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
7. Seleccione **siguiente** para continuar.
8. En la **Página indicadores de alerta** , verá los indicadores que ha definido en la página**indicadores** de configuración > de **riesgos de Insider**. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
9. En la página **seleccionar ventana de supervisión** , verá las condiciones de la [ventana de supervisión](insider-risk-management-policies.md#policy-timeframes) para la Directiva que ha configurado en la configuración de los riesgos de Insider. Si ha seleccionado la plantilla de directiva de *robo de datos de empleado* de cancelación, puede seleccionar la casilla comprobar la *interrupción posterior* a la actividad para detectar la actividad después de la fecha de finalización importada desde el conector de 365 de RRHH de Microsoft.
10. Seleccione **siguiente** para continuar.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para crear y activar la Directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos de Insider existente, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para administrar una directiva existente:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea administrar.
3. En la página Detalles de la Directiva, seleccione **Editar Directiva** .
4. En el Asistente para directivas, no puede editar los campos siguientes:
    - **Name**: el nombre descriptivo de la Directiva.
    - **Seleccione Guía**: la plantilla que se usa para definir los tipos de indicadores de riesgo supervisados por la Directiva.
5. Escriba una nueva descripción para la Directiva en el campo **Descripción** . Seleccione **siguiente** para continuar.
6. En la página **elegir usuarios y grupos** , seleccione **elegir usuarios o grupos** para definir qué usuarios se incluyen en la Directiva o seleccione **todos los usuarios y grupos con correo habilitado** . Seleccione **siguiente** para continuar.
7. En la página **especificar el contenido que va a priorizar (opcional)** , actualice los orígenes para priorizar las actividades de usuario arriesgadas:
    - Sitios de SharePoint: seleccione **elegir sitios de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de información confidencial: seleccione **elegir tipos de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - Etiquetas de confidencialidad: seleccione **elegir etiquetas de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
8. Seleccione **siguiente** para continuar.
9. En la **Página indicadores de alerta** , verá los indicadores que ha definido en la página**indicadores** de configuración > de **riesgos de Insider**. Si seleccionó la plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** .
10. En la página **seleccionar ventana de supervisión** , verá las condiciones de la [ventana de supervisión](insider-risk-management-policies.md#policy-timeframes) para la Directiva que ha configurado en la configuración de los riesgos de Insider. Si ha seleccionado la plantilla de directiva de *robo de datos de empleado* de cancelación, puede seleccionar la casilla comprobar la *interrupción posterior* a la actividad para detectar la actividad después de la fecha de finalización importada desde el conector de 365 de RRHH de Microsoft.
11. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para actualizar y activar los cambios en la Directiva.

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva no se eliminan las alertas activas o archivadas generadas desde la Directiva.

Para eliminar una directiva de administración de riesgos de Insider existente, siga estos pasos:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea administrar.
3. Seleccione **eliminar** en la barra de herramientas del panel.
4. En el cuadro de diálogo **eliminar** , seleccione **sí** para eliminar la Directiva o seleccione **Cancelar** para cerrar el cuadro de diálogo.
