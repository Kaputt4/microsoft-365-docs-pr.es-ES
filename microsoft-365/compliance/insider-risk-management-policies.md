---
title: Directivas de administración de riesgos internos
description: Obtenga más información sobre las directivas de administración de riesgos internos en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 23c2ed180606e61820c6e736e472aef0ae4933a5
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445690"
---
# <a name="insider-risk-management-policies"></a>Directivas de administración de riesgos internos

Las directivas de administración de riesgos internos determinan qué usuarios deben estar dentro del ámbito de búsqueda y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de su organización o definir usuarios o grupos individuales para su administración en una directiva. Las directivas son compatibles con las prioridades de contenido para centrar las condiciones de las directivas en varios o determinados Microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Mediante el uso de plantillas, puede seleccionar indicadores de riesgo específicos y personalizar los umbrales de los eventos para los indicadores de directivas, personalizando eficazmente las puntuaciones de riesgo y el nivel y la frecuencia de las alertas. Además, los impulsores de la puntuación de riesgo y las detecciones de anomalías ayudan a identificar la actividad del usuario que es de mayor importancia o más inusual. Las ventanas de la directiva permiten definir el marco temporal para aplicar la directiva a las actividades de alerta y se usan para determinar la duración de la directiva una vez activada.

Vea el vídeo sobre la [configuración de las directivas de administración de riesgos internos](https://www.youtube.com/watch?v=kudK5ajZTUo) para obtener una visión general de cómo las directivas creadas con las plantillas de directivas integradas pueden ayudarle a tomar rápidamente medidas sobre los posibles riesgos.

## <a name="policy-dashboard"></a>Panel de directivas

El **Panel de control de la directiva** le permite ver rápidamente las directivas de su organización, el estado de las mismas, agregar manualmente usuarios a las directivas y ver el estado de las alertas asociadas a cada directiva.

- **Nombre de la directiva**: el nombre asignado a la directiva en el asistente de directivas educativas.
- **Estado**: el estado de cada directiva. Muestra el número de advertencias y recomendaciones de las directivas, o un estado *Correcto* para las directivas sin problemas.  Puede hacer clic en la directiva para ver los detalles del estado para cualquier advertencia o recomendación.
- **Alertas activas**: el número de alertas activas para cada directiva.
- **Alertas confirmadas**: el número total de alertas que generaron casos de la directiva en los últimos 365 días.
- **Acciones realizadas en alertas**: el número total de alertas que se confirmaron o descartaron durante los últimos 365 días.
- **Efectividad de la alerta de la directiva**: el porcentaje determinado por el total de alertas confirmadas dividido entre el total de acciones realizadas en alertas (que es la suma de alertas que se confirmaron o descartaron durante el año pasado).

![Panel de directiva de administración de riesgos internos](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Recomendaciones de directivas a partir de los análisis (versión preliminar)

Los análisis de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar.

Para obtener más información sobre los análisis de riesgos internos y las recomendaciones de directivas, vea [Configuración de la administración de riesgos internos: Análisis (versión preliminar)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de administración de riesgos internos son condiciones predefinidas de la directiva que definen los tipos de indicadores de riesgo y el modelo de puntuación de riesgos que usa la directiva. Cada directiva debe tener una plantilla asignada en el asistente de creación de directivas antes de que se cree la directiva. La administración de riesgos internos admite hasta cinco directivas para cada plantilla de directivas. Cuando se crea una nueva directiva de riesgos internos con el asistente de directivas, se elige una de las siguientes plantillas de directivas:

### <a name="data-theft-by-departing-users"></a>Robo de datos por parte de los usuarios que abandonan la organización

Cuando los usuarios abandonan su organización, existen indicadores de riesgo específicos que suelen asociarse al robo de datos por parte de los usuarios que abandonan la organización. Esta plantilla de directiva utiliza los indicadores de filtración para la puntuación del riesgo y se centra en la detección y las alertas en esta área de riesgo. El robo de datos por parte de los usuarios que abandonan la organización puede incluir la descarga de archivos de SharePoint Online, la impresión de archivos y la copia de datos en servicios personales de mensajería y almacenamiento en la nube cerca de sus fechas de renuncia y finalización del empleo. Al usar el conector de recursos humanos de Microsoft 365 o la opción de supervisar automáticamente la eliminación de cuentas de usuario en Azure Active Directory para su organización, esta plantilla comienza a puntuar los indicadores de riesgo relacionados con estas actividades y cómo se correlacionan con el estado de empleo del usuario.

>[!IMPORTANT]
>Al usar esta plantilla, puede configurar un conector de recursos humanos de Microsoft 365 para importar periódicamente la información de las fechas de renuncia y finalización de los usuarios de su organización. Vea el artículo [Importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de recursos humanos de Microsoft 365 para su organización. Si decide no usar el conector de recursos humanos, debe seleccionar la opción Cuenta de usuario eliminada de Azure AD al configurar los eventos desencadenantes en el asistente de directivas.

### <a name="general-data-leaks"></a>Filtraciones de datos generales

La protección de los datos y la prevención de las filtraciones es un reto constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por los usuarios, los dispositivos y los servicios. Los usuarios tienen la posibilidad de crear, almacenar y compartir información a través de servicios y dispositivos que hacen que la administración de las filtraciones de datos sea cada vez más compleja y difícil. Las filtraciones de datos pueden incluir la divulgación accidental de información fuera de su organización o el robo de datos con fines malintencionados. Con una directiva de prevención de pérdida de datos (DLP) asignada o el evento desencadenante incorporado, esta plantilla comienza a marcar las detecciones en tiempo real de descargas de datos sospechosas de SharePoint Online, el uso compartido de archivos y carpetas, la impresión de archivos y la copia de datos en servicios personales de mensajería y almacenamiento en la nube.

Al usar una plantilla de *Filtración de datos*, puede asignar una directiva DLP para activar indicadores en la directiva de riesgo interno para alertas de alta gravedad en su organización. Cada vez que una regla de directiva DLP genera una alerta de alta gravedad que se agrega al registro de auditoría de Office 365, las directivas de riesgo interno creadas con esta plantilla examinan automáticamente la alerta de DLP de alta gravedad. Si la alerta contiene un usuario dentro del ámbito definido en la directiva de riesgo interno, la alerta es procesada por la directiva de riesgo interno como una nueva alerta y se le asigna una gravedad de riesgo interno y una puntuación de riesgo. Esta directiva le permite evaluar esta alerta en contexto con otras actividades incluidas en el caso. Si no elige una directiva DLP, debe seleccionar el evento desencadenante incorporado.

#### <a name="data-leaks-policy-guidelines"></a>Directrices de la directiva sobre filtración de datos

Al crear o modificar las directivas DLP para usarlas con las directivas de administración de riesgos internos, tenga en cuenta las siguientes directrices:

- Establezca prioridad a los eventos de filtración de datos y sea selectivo a la hora de asignar la configuración de los **Informes de incidentes** a *Alto* cuando configure las reglas en sus directivas DLP. Por ejemplo, enviar por correo electrónico documentos confidenciales a un competidor conocido debería ser un evento de filtración de nivel de alerta *Alto*. La sobreasignación del nivel *Alto* en la configuración de los **Informes de incidentes** en otras reglas de directivas DLP puede aumentar el ruido en el flujo de trabajo de las alertas de administración de riesgos internos y dificultar la evaluación adecuada de estas alertas por parte de los investigadores y analistas de datos. Por ejemplo, la asignación de niveles de alerta *Alto* a las actividades de denegación de acceso en las directivas DLP hace que sea más difícil evaluar los comportamientos y actividades de los usuarios de riesgo.
- Asegúrese de comprender y configurar correctamente los usuarios dentro del ámbito de aplicación tanto en la DLP como en las directivas de administración de riesgos internos. Solo los usuarios definidos como dentro del ámbito de las directivas de administración de riesgos internos usando la plantilla de **Filtración de datos** tendrán alertas de directivas DLP de alta gravedad procesadas. Además, únicamente los usuarios definidos como dentro del ámbito de una regla para una alerta DLP de alta gravedad serán examinados por la directiva de administración de riesgos internos para su consideración. Es importante que no configure, sin saberlo, a los usuarios dentro del ámbito de búsqueda tanto en su DLP como en las directivas de riesgo interno de manera conflictiva.

     Por ejemplo, si sus reglas de directiva DLP se limitan a los usuarios del equipo de ventas y la directiva de riesgo interno creada a partir de la plantilla de **Filtración de datos** ha definido a todos los usuarios como dentro del ámbito de búsqueda, la directiva de riesgo interno solo procesará realmente las alertas de DLP de alta gravedad para los usuarios del equipo de ventas. La directiva de riesgo interno no recibirá ninguna alerta de DLP de alta prioridad para que los usuarios procesen las alertas que no están definidas en las reglas de DLP en este ejemplo. Por el contrario, si su directiva de administración de riesgos internos creada a partir de las plantillas de **Filtración de datos** tiene un ámbito solo para los usuarios del equipo de ventas y la directiva DLP asignada tiene un ámbito para todos los usuarios, la directiva de riesgos internos solo procesará las alertas de DLP de alta gravedad para los miembros del equipo de ventas. La directiva de administración de riesgos internos ignorará las alertas de DLP de alta gravedad para todos los usuarios que no pertenezcan al equipo de ventas.

- Asegúrese de que la configuración de la regla de **Informes de incidentes** en la directiva DLP usada para esta plantilla de administración de riesgos internos esté configurada para alertas de nivel de gravedad *Alto*. El nivel de gravedad *Alto* es el de los eventos desencadenantes y las alertas de administración de riesgos internos no se generarán a partir de las reglas de las directivas DLP con el campo **Informes de incidentes** configurado en *Bajo* o *Medio*.

    ![Configuración de alertas de la directiva DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Al crear una nueva directiva DLP usando las plantillas incorporadas, tendrá que seleccionar la opción **Crear o personalizar reglas DLP avanzadas** para configurar el ajuste de **Informes de incidentes** para el nivel de gravedad *Alto*.

Cada directiva de administración de riesgos internos creada a partir de la plantilla de **Filtración de datos** solo puede tener asignada una directiva DLP. Considere la posibilidad de crear una directiva DLP dedicada que combine las diferentes actividades que desea detectar y que actúe como evento desencadenante de las directivas de riesgo interno que usan la plantilla de **Filtración de datos**.

Vea el artículo [Crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso para configurar las directivas DLP para su organización.

### <a name="data-leaks-by-priority-users-preview"></a>Filtración de datos por parte de usuarios prioritarios (versión preliminar)

La protección de los datos y la prevención de las filtraciones de datos para los usuarios de su organización puede depender de su posición, del nivel de acceso a la información confidencial o del historial de riesgos. Las filtraciones de datos pueden incluir la divulgación accidental de información altamente confidencial fuera de su organización o el robo de datos con fines malintencionados. Con una directiva de Prevención de Pérdida de Datos (DLP) asignada, esta plantilla comienza a puntuar las detecciones de actividad sospechosa en tiempo real y da lugar a una mayor probabilidad de alertas de riesgo interno y alertas con niveles de gravedad más altos. Los usuarios prioritarios se definen en [grupos de usuarios prioritarios](insider-risk-management-settings.md#priority-user-groups-preview) configurados en el área de configuración de la administración de riesgos internos.

Al igual que con la **Plantilla de filtración de datos general**, debe asignar una directiva DLP para activar indicadores en la directiva de riesgo interno para alertas de alta gravedad en su organización. Siga las directrices de la directiva sobre filtración de datos indicadas anteriormente cuando cree una directiva utilizando esta plantilla. Además, tendrá que asignar a la directiva los grupos de usuarios prioritarios creados en **Administración de riesgos internos** > **Configuración** > **Grupos de usuarios prioritarios**.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Filtraciones de datos por parte de usuarios inconformes (versión preliminar)

Cuando los usuarios experimentan factores de estrés laboral, pueden sentirse inconformes, lo que puede aumentar las posibilidades de que se produzcan actividades de riesgo interno. Esta plantilla comienza a puntuar la actividad del usuario cuando se identifica un indicador asociado al descontento. Algunos ejemplos son las notificaciones de mejora del rendimiento, las revisiones de bajo rendimiento o los cambios de estado del trabajo. Las filtraciones de datos de usuarios inconformes pueden incluir la descarga de archivos de SharePoint Online y la copia de datos en servicios personales de mensajería en la nube y de almacenamiento cerca de eventos de estrés laboral.

Cuando se utiliza esta plantilla, también se debe configurar un conector de recursos humanos de Microsoft 365 para importar periódicamente las notificaciones de mejora del rendimiento, el estado de la revisión del rendimiento deficiente o la información de cambio de nivel de trabajo de los usuarios de su organización. Vea el artículo [Importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de recursos humanos de Microsoft 365 para su organización.

### <a name="general-security-policy-violations-preview"></a>Infracciones generales de la directiva de seguridad (versión preliminar)

En muchas organizaciones, los usuarios tienen permiso para instalar software en sus dispositivos o para modificar la configuración de los mismos para ayudarles con sus tareas. Ya sea de forma involuntaria o con fines malintencionados, los usuarios pueden instalar software malintencionado o deshabilitar características de seguridad importantes que ayudan a proteger la información de su dispositivo o de sus recursos de red. Esta plantilla de directiva usa alertas de seguridad de ATP de Microsoft Defender para empezar a puntuar estas actividades y centrar la detección y las alertas en esta área de riesgo. Use esta plantilla para proporcionar información sobre las infracciones de la directiva de seguridad en escenarios en los que los usuarios pueden tener un historial de infracciones de la directiva de seguridad que puede ser un indicador de riesgo interno.

Deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización (versión preliminar)

Los usuarios que abandonan la organización, ya sea en términos positivos o negativos, pueden suponer un mayor riesgo de infracción de la directiva de seguridad. Para ayudar a protegerse contra las infracciones de seguridad involuntarias o malintencionadas de los usuarios que abandonan la organización, esta plantilla de directiva usa las alertas de Defender para punto de conexión para proporcionar información sobre las actividades relacionadas con la seguridad. Estas actividades incluyen la instalación por parte del usuario de software malintencionado u otras aplicaciones potencialmente dañinas y la desactivación de las funciones de seguridad de sus dispositivos. Al usar el [conector de recursos humanos de Microsoft 365](import-hr-data.md) o la opción de supervisar automáticamente la eliminación de cuentas de usuario en Azure Active Directory para su organización, esta plantilla comienza a puntuar los indicadores de riesgo relacionados con estas actividades de seguridad y cómo se correlacionan con el estado de empleo del usuario.

Deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Infracciones de la directiva de seguridad por parte de los usuarios prioritarios (versión preliminar)

La protección contra las infracciones de seguridad de los usuarios de su organización puede depender de su posición, nivel de acceso a la información confidencial o historial de riesgos. Dado que las infracciones de seguridad por parte de los usuarios prioritarios pueden tener un impacto significativo en las áreas críticas de su organización, esta plantilla de directiva comienza a puntuar estos indicadores y usa las alertas de Microsoft Defender para punto de conexión para proporcionar información sobre las actividades relacionadas con la seguridad de estos usuarios. Estas actividades pueden incluir que los usuarios prioritarios instalen software malintencionado u otras aplicaciones potencialmente dañinas y desactiven las funciones de seguridad de sus dispositivos. Los usuarios prioritarios se definen en grupos de usuarios prioritarios configurados en el área de configuración de la administración de riesgos internos.

Deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Además, tendrá que asignar a la directiva los grupos de usuarios prioritarios creados en **Administración de riesgos internos** > **Configuración** > **Grupos de usuarios prioritarios**.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Infracciones de la directiva de seguridad por parte de usuarios inconformes (versión preliminar)

Los usuarios que experimentan factores de estrés laboral pueden correr un mayor riesgo de infringir las directivas de seguridad de forma involuntaria o malintencionada. Estos factores de estrés pueden incluir la asignación al usuario de un plan de mejora del rendimiento, un estado de revisión de bajo rendimiento o la degradación de su puesto actual. Esta plantilla de directiva comienza a puntuar el riesgo en base a estos indicadores y a las actividades asociadas a estos eventos para estos usuarios.

Cuando se utiliza esta plantilla, también se debe configurar un conector de recursos humanos de Microsoft 365 para importar periódicamente las notificaciones de mejora del rendimiento, el estado de la revisión del rendimiento deficiente o la información de cambio de nivel de trabajo de los usuarios de su organización. Vea el artículo [Importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de recursos humanos de Microsoft 365 para su organización.

También deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Requisitos previos de la plantilla de directiva y eventos desencadenantes

Dependiendo de la plantilla que elija para una directiva de administración de riesgos internos, los eventos desencadenantes y los requisitos previos de la directiva varían. Los eventos desencadenantes son requisitos previos que determinan si un usuario está activo para una directiva de administración de riesgos internos. Si un usuario se agrega a una directiva de administración de riesgos internos pero no tiene un evento desencadenante, la actividad del usuario no se evalúa por la directiva a menos que se agregue manualmente en el panel Usuarios. Los requisitos previos de la directiva son elementos necesarios para que la directiva reciba las señales o actividades necesarias para evaluar el riesgo.

La siguiente tabla enumera los eventos desencadenantes y los requisitos previos para las directivas creadas a partir de cada plantilla de directivas de administración de riesgos internos:

| **Plantilla de directiva** | **Desencadenar eventos para directivas** | **Requisitos previos** |
| :------------------ | :--------------------------------- | :---------------- |
| Robo de datos por parte de los usuarios que abandonan la organización | Indicador de la fecha de renuncia o finalización del conector de recursos humanos | (opcional) Conector de recursos humanos de Microsoft 365 configurado para los indicadores de fecha de finalización y renuncia o integración de Azure Active Directory habilitada |
| Filtraciones de datos generales | Actividad de la directiva de filtración de datos que crea una alerta de gravedad alta | (opcional) Directiva DLP configurada para alertas de alta gravedad o evento desencadenante de filtración de datos incorporado |
| Filtraciones de datos por parte de usuarios prioritarios | La actividad de la directiva de filtración de datos que crea una alerta de *Alta gravedad* o desencadena un evento de filtración incorporado | (opcional) Directiva DLP configurada para alertas de alta gravedad <br><br> Grupos de usuarios prioritarios configurados en la configuración de riesgo interno |
| Filtraciones de datos por parte de usuarios inconformes | Indicadores de mejora del rendimiento, bajo rendimiento o cambio de nivel de trabajo del conector de recursos humanos | Conector de recursos humanos de Microsoft 365 configurado para los indicadores de inconformidad |
| Infracciones generales de la directiva de seguridad | Evasión defensiva de los controles de seguridad o del software no deseado detectado por ATP de Microsoft Defender | Suscripción activa a ATP de Microsoft Defender <br><br> Integración de ATP de Microsoft Defender con el Centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización | Indicadores de la fecha de renuncia o finalización del contrato desde el conector de recursos humanos o la eliminación de la cuenta de Azure Active Directory | (opcional) Conector de recursos humanos de Microsoft 365 configurado para los indicadores de fecha de finalización y renuncia. <br><br> Suscripción activa a ATP de Microsoft Defender <br><br> Integración de ATP de Microsoft Defender con el Centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de la directiva de seguridad por parte de los usuarios prioritarios | Evasión defensiva de los controles de seguridad o del software no deseado detectado por ATP de Microsoft Defender | Suscripción activa a ATP de Microsoft Defender <br><br> Integración de ATP de Microsoft Defender con el Centro de cumplimiento de Microsoft 365 configurado <br><br> Grupos de usuarios prioritarios configurados en la configuración de riesgo interno |
| Infracciones de la directiva de seguridad por parte de un usuario inconforme | Indicadores de mejora del rendimiento, bajo rendimiento o cambio de nivel de trabajo del conector de recursos humanos | Conector de recursos humanos de Microsoft 365 configurado para los indicadores de inconformidad <br><br> Suscripción activa a ATP de Microsoft Defender <br><br> Integración de ATP de Microsoft Defender con el Centro de cumplimiento de Microsoft 365 configurado |

## <a name="prioritize-content-in-policies"></a>Priorizar los contenidos en las directivas

Las directivas de administración de riesgos internos permiten especificar una mayor prioridad para los contenidos en función de dónde se almacenan o cómo se clasifican. Especificar el contenido como prioritario aumenta la puntuación de riesgo de cualquier actividad asociada, lo que a su vez aumenta la posibilidad de generar una alerta de alta gravedad. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial incorporados o personalizados o se haya especificado como prioridad en la directiva.

Por ejemplo, su organización tiene un sitio de SharePoint dedicado a un proyecto altamente confidencial. Las filtraciones de información en este sitio de SharePoint podrían comprometer el proyecto y tendrían un impacto significativo en su éxito. Al priorizar este sitio de SharePoint en una directiva de filtración de datos, las puntuaciones de riesgo para las actividades puntuadas se incrementan automáticamente. Esta priorización aumenta la probabilidad de que estas actividades generen una alerta de riesgo interno y eleva el nivel de gravedad de la alerta.

Cuando se crea una directiva de administración de riesgos internos en el asistente de directivas, se puede elegir entre las siguientes prioridades:

- **Sitios de SharePoint**: cualquier actividad asociada a todos los tipos de archivo en sitios de SharePoint definidos se asigna una mayor puntuación de riesgo. 
- **Tipos de información confidencial**: cualquier actividad asociada a un contenido que contenga [tipos de información confidencial](sensitive-information-type-entity-definitions.md) se le asigna una puntuación de riesgo más alta.
- **Etiquetas de confidencialidad**: a cualquier actividad asociada a un contenido que tenga aplicadas [etiquetas de confidencialidad](sensitivity-labels.md) específicas se le asigna una puntuación de riesgo más alta.

## <a name="sequence-detection-preview"></a>Detección de secuencias (versión preliminar)

Las actividades de riesgo pueden no producirse como eventos aislados. Estos riesgos suelen formar parte de una secuencia más amplia de eventos. Una secuencia es un grupo de dos o más actividades del usuario realizadas una tras otra que podrían sugerir un riesgo elevado. La identificación de estas actividades relacionadas es una parte importante de la evaluación del riesgo global. Cuando la detección de secuencias está activada para las directivas de robo o filtración de datos, los conocimientos de las actividades de información de secuencias se muestran en la pestaña **Actividad del usuario** dentro de un caso de administración de riesgos internos. Las siguientes plantillas de directivas admiten la detección de secuencias:

- Robo de datos por parte de los usuarios que abandonan la organización
- Filtraciones de datos generales
- Filtraciones de datos por parte de usuarios prioritarios
- Filtraciones de datos por parte de usuarios inconformes

Estas directivas de administración de riesgos internos pueden usar indicadores específicos y el orden en que ocurren para detectar cada paso en una secuencia de riesgo. Los nombres de los archivos se usan cuando se asignan las actividades a través de una secuencia. Estos riesgos se organizan en cuatro principales categorías de actividad:

- **Colección**: estas señales de categoría se centran en las actividades de descarga de los usuarios de la directiva dentro del ámbito de búsqueda. Un ejemplo de actividad en esta categoría sería la descarga de archivos de los sitios de SharePoint.
- **Filtración**: estas señales de categoría se centran en las actividades de uso compartido o extracción a fuentes internas y externas por parte de los usuarios de la directiva dentro del ámbito de búsqueda. Un ejemplo de actividad en esta categoría sería el envío de correos electrónicos con archivos adjuntos de su organización a destinatarios externos.
- **Ofuscación**: estas señales de categoría se centran en el enmascaramiento de las actividades de riesgo por parte de los usuarios de la directiva dentro del ámbito de búsqueda. Un ejemplo de actividad en esta categoría sería renombrar archivos en un dispositivo.
- **Limpieza**: estas señales de categoría se centran en las actividades de eliminación por parte de los usuarios de la directiva dentro del ámbito de búsqueda. Una actividad de ejemplo en esta categoría eliminaría archivos de un dispositivo.

>[!NOTE]
>La detección de secuencias utiliza los indicadores habilitados en la configuración global para la administración de riesgos internos y los indicadores seleccionados en una directiva. Si no se seleccionan los indicadores adecuados, la detección de la secuencia no funcionará.

Puede personalizar la configuración de umbral individual para cada tipo de detección de secuencia cuando se configure en la directiva. Esta configuración de umbral ajusta las alertas según el volumen de archivos asociados con la secuencia.

Para obtener más información sobre la administración de la detección de secuencias en la vista de la **Actividad del usuario**, vea [Casos de administración de riesgos internos: actividad de los usuarios](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Detección de filtración acumulada (versión preliminar)

Los indicadores de riesgo interno ayudan a identificar niveles inusuales de actividades de riesgo cuando se evalúan diariamente para los usuarios que están dentro del ámbito de búsqueda de las directivas de riesgo interno. La detección de filtración acumulada usa modelos de aprendizaje automático para ayudarle a identificar cuándo las actividades de filtración de los usuarios superan los promedios de la organización cuando se miden a lo largo del tiempo y en varios tipos de actividades de filtración. Los analistas e investigadores de administración de riesgos internos pueden utilizar los conocimientos de detección de filtración acumulada para ayudar a identificar las actividades de filtración que no suelen generar alertas, pero que están por encima de lo que es típico para su organización. Algunos ejemplos pueden ser que los usuarios que abandonan la organización filtren lentamente los datos durante varios días, o que los usuarios compartan repetidamente los datos a través de múltiples canales más de lo habitual para el uso compartido de datos de su organización.

La detección de filtración acumulada está activada de forma predeterminada cuando se utilizan las siguientes plantillas de directivas:

- Robo de datos por parte de los usuarios que abandonan la organización
- Filtraciones de datos generales
- Filtraciones de datos por parte de usuarios prioritarios
- Filtraciones de datos por parte de usuarios inconformes

>[!NOTE]
>La detección de filtración acumulada utiliza los indicadores de filtración activados en la configuración global para la administración de riesgos internos y los indicadores de filtración seleccionados en una directiva. Como tal, la detección de filtración acumulada solo se evalúa para los indicadores de filtración necesarios seleccionados.

Cuando la detección de filtración acumulada está activada para las directivas de robo o filtración de datos, la información de las actividades de filtración acumulada se muestra en la pestaña **Actividad del usuario** dentro de un caso de administración de riesgos internos.

Para obtener más información sobre la administración de las actividades de los usuarios, vea los [Casos de administración de riesgos internos: actividades de los usuarios](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Estado de la directiva (versión preliminar)

El estado de la directiva le permite conocer los posibles problemas de sus directivas de administración de riesgos internos. La columna de Estado en la pestaña de Directivas puede alertarle de los problemas de las directivas que pueden impedir que se informe de la actividad del usuario o de por qué el número de alertas de actividad es inusual. El estado de la directiva también puede confirmar que la directiva está en buen estado y no necesita atención o cambios de configuración.

Si hay problemas con una directiva, el estado de la misma muestra advertencias de notificación y recomendaciones para ayudarle a tomar medidas para resolver los problemas de la directiva. Estas notificaciones pueden ayudarle a resolver los siguientes problemas:

- Directivas con configuración incompleta. Estos problemas pueden incluir la falta de usuarios o grupos en la directiva o otros pasos de configuración de la directiva incompletos.
- Directivas con problemas de configuración de indicadores. Los indicadores son una parte importante de cada directiva. Si no se configuran los indicadores, o si se seleccionan muy pocos, la directiva puede no evaluar las actividades de riesgo como se espera.
- Los activadores de directivas no funcionan, o los requisitos de activación de directivas no están bien configurados. La funcionalidad de la directiva puede depender de otros servicios o requisitos de configuración para detectar eficazmente los eventos desencadenantes para activar la asignación de la puntuación de riesgo a los usuarios en la directiva. Estas dependencias pueden incluir problemas con la configuración del conector, el uso compartido de alertas de ATP de Microsoft Defender o la configuración de la directiva de prevención de pérdida de datos.
- Los límites de volumen se acercan o superan los límites. Las directivas de administración de riesgos internos usan numerosos servicios y puntos de conexión de Microsoft 365 para agregar señales de actividad de riesgo. Dependiendo del número de usuarios en sus directivas, los límites de volumen pueden retrasar la identificación y notificación de las actividades de riesgo. Obtenga más información sobre estos límites en la sección Límites de la plantilla de directiva de este artículo.

Para ver rápidamente el estado de la directiva, navegue por la pestaña Directiva y la columna Estado. Aquí verá las siguientes opciones de estado de la directiva para cada directiva:

- Buen estado: no se han detectado problemas con la directiva.
- Recomendaciones: hay algunos problemas con la directiva que pueden impedir que ésta funcione como se espera.
- Advertencias: hay problemas con la directiva que le impedirán identificar las actividades de riesgo.

Para obtener más detalles sobre cualquier recomendación o advertencia, seleccione una directiva en la pestaña **Directiva** para abrir la tarjeta de detalles de la misma. En la sección de notificaciones de la tarjeta de datos se mostrará más información sobre las recomendaciones y advertencias, incluidas las directrices sobre cómo resolver estos problemas.

![Estado de directiva de administración de riesgos internos](../media/insider-risk-policy-health.png)

Use la siguiente tabla para obtener más información sobre las recomendaciones y las notificaciones de advertencia, así como sobre las acciones a realizar para resolver posibles problemas.

|**Mensajes de notificación**|**Plantillas de directiva**|**Causas / Probar esta acción para corregir**|
|:------------------------|:-------------------|:---------------------------|
| La directiva no está asignando puntuaciones de riesgo a la actividad | Todas las plantillas de directiva | Es posible que desee revisar el ámbito de búsqueda de la directiva y la configuración de los eventos desencadenantes para que la directiva pueda asignar puntuaciones de riesgo a la actividad <br><br> 1. Revise los usuarios seleccionados para la directiva. Si tiene pocos usuarios seleccionados, es posible que desee seleccionar usuarios adicionales. <br> 2. Si está usando un conector de recursos humanos, compruebe que su conector de recursos humanos está enviando los datos correctos. <br> 3. Si está usando una directiva DLP como evento desencadenante, compruebe la configuración de su directiva DLP para asegurarse de que está configurada para ser usada en esta directiva. <br> 4. Para las directivas de infracción de seguridad, revise el estado de evaluación de prioridades de alertas de ATP de Microsoft Defender seleccionado en Configuración de riesgos internos > Detecciones inteligentes. Confirme que el filtro de alerta no es demasiado estrecho. |
| La directiva no ha generado ninguna alerta | Todas las plantillas de directiva | Es posible que desee revisar la configuración de su directiva para que esté analizando la puntuación de la actividad que le interesa. <br><br> 1. Confirme que ha seleccionado los indicadores que desea puntuar. Cuantos más indicadores se seleccionen, más actividades se asignarán a las puntuaciones de riesgo. <br> 2. Revisar la personalización del umbral para la directiva. Si los umbrales seleccionados no se alinean con la tolerancia al riesgo de su organización, ajuste las selecciones para que se creen alertas basadas en sus umbrales preferidos. <br> 3. Revise los usuarios y grupos seleccionados para la directiva. Confirme que ha seleccionado todos los usuarios y grupos aplicables. <br> 4. Para las directivas de infracción de seguridad, confirme que ha seleccionado el estado de evaluación de prioridades de alertas que desea puntuar para las alertas de ATP de Microsoft Defender en Detecciones inteligentes en la configuración.|
| No hay usuarios ni grupos incluidos en esta directiva | Todas las plantillas de directiva | Los usuarios o grupos no están asignados a la directiva. <br><br> Edite su directiva y seleccione los usuarios o grupos para la misma. |
| No se han seleccionado indicadores para esta directiva. | Todas las plantillas de directiva | Los indicadores no han sido seleccionados para la directiva <br><br> Edite su directiva y seleccione los indicadores adecuados para la misma. |
| Esta directiva no incluye a ningún grupo de usuarios prioritarios | - Filtraciones de datos por parte de usuarios prioritarios <br> - Infracciones de directiva de seguridad por usuario prioritario | Los grupos de usuarios prioritarios no están asignados a la directiva. <br><br> Configure grupos de usuarios prioritarios en las configuraciones de administración de riesgos internos y asigne grupos de usuarios prioritarios a la directiva. |
| No se ha seleccionado ningún evento desencadenante para esta directiva | Todas las plantillas de directiva | No se ha configurado un evento desencadenante para la directiva <br><br> Las puntuaciones de riesgo no se asignarán a las actividades de los usuarios hasta que se edite la directiva y se seleccione un evento desencadenante. |
| El conector de recursos humanos no está configurado o no funciona como se esperaba | - Robo de datos por parte del usuario que abandona la organización <br> - Infracciones de la directiva de seguridad por parte del usuario que abandona la organización <br> - Filtraciones de datos por parte de usuarios inconformes <br> - Infracciones de la directiva de seguridad por parte de usuarios inconformes | Hay un problema con el conector de recursos humanos. <br><br> 1. Si está utilizando un conector de recursos humanos, compruebe que su conector de recursos humanos está enviando datos correctos <br><br> O <br><br> 2. Seleccione el evento desencadenante de la cuenta Azure AD eliminada. |
| No hay dispositivos incorporados | - Robo de datos por parte de los usuarios que abandonan la organización <br> - Filtración de datos generales <br> - Filtraciones de datos por parte de usuarios inconformes <br> - Filtraciones de datos por parte de usuarios prioritarios | Los indicadores de dispositivos están seleccionados pero no hay ningún dispositivo incorporado a Microsoft 365 <br><br> Compruebe si los dispositivos están incorporados y cumplen los requisitos. |
| El conector de recursos humanos no ha cargado datos recientemente | - Robo de datos por parte del usuario que abandona la organización <br> - Infracciones de la directiva de seguridad por parte del usuario que abandona la organización <br> - Filtraciones de datos por parte de usuarios inconformes <br> - Infracciones de la directiva de seguridad por parte de usuarios inconformes | El conector de recursos humanos no ha importado datos en más de 7 días. <br><br> Compruebe que su conector de recursos humanos está configurado correctamente y que envía datos. |
| No podemos comprobar el estado de su conector de recursos humanos en este momento, vuelva a comprobarlo más tarde | - Robo de datos por parte del usuario que abandona la organización <br> - Infracciones de la directiva de seguridad por parte del usuario que abandona la organización <br> - Filtraciones de datos por parte de usuarios inconformes <br> - Infracciones de la directiva de seguridad por parte de usuarios inconformes | La solución de administración de riesgos internos no puede comprobar el estado de su conector de recursos humanos. <br><br> Compruebe que su conector de recursos humanos está configurado correctamente y envía datos, o vuelva a comprobar el estado de la directiva.  |
| La directiva DLP no está seleccionada como evento desencadenante | - Filtraciones de datos generales <br> - Filtraciones de datos por parte de usuarios prioritarios | Una directiva DLP no se ha seleccionado como un evento de desencadenador o la directiva DLP seleccionada se ha eliminado. <br><br> Edite la directiva y seleccione una directiva DLP activa o "El usuario realiza una actividad de filtración" como evento desencadenante en la configuración de la directiva. |
| La directiva DLP usada en esta directiva de riesgos internos está desactivada | - Filtraciones de datos generales <br> - Filtraciones de datos por parte de usuarios prioritarios | La directiva DLP usada en esta directiva está desactivada. <br><br> 1. Activar la directiva DLP asignada a esta directiva. <br><br> O <br><br> 2. Edite esta directiva y seleccione una nueva directiva DLP o "El usuario realiza una actividad de filtración" como evento desencadenante en la configuración de la directiva. |
| La directiva DLP no cumple con los requisitos | - Filtraciones de datos generales <br> - Filtraciones de datos por parte de usuarios prioritarios | Las directivas DLP usadas como eventos desencadenantes deben ser configuradas para generar alertas de alta gravedad. <br><br>  1. Edite su directiva DLP para asignar las alertas aplicables como de *Alta gravedad*. <br><br> O <br><br> 2. Edite esta directiva y seleccione *El usuario realiza una actividad de filtración* como evento desencadenante. |
| Su organización no tiene una suscripción a ATP de Microsoft Defender | - Infracciones generales de la directiva de seguridad <br> - Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización <br> - Infracciones de la directiva de seguridad por parte de usuarios inconformes <br> - Infracciones de directiva de seguridad por usuario prioritario | No se ha detectado una suscripción activa a ATP de Microsoft Defender para su organización. <br><br> Hasta que se agregue una suscripción a ATP de Microsoft Defender, estas directiva no asignarán puntuaciones de riesgo a la actividad de los usuarios. |
| Las alertas de ATP de Microsoft Defender no se comparten con el centro de cumplimiento | - Infracciones generales de la directiva de seguridad <br> - Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización <br> - Infracciones de la directiva de seguridad por parte de usuarios inconformes <br> - Infracciones de directiva de seguridad por usuario prioritario | Las alertas de ATP de Microsoft Defender no se comparten con el centro de cumplimiento. <br><br> Configurar el uso compartido de las alertas de ATP de Microsoft Defender. |
| Se está acercando al límite máximo de usuarios puntuados activamente para esta plantilla de directiva. | Todas las plantillas de directiva | Cada plantilla de directiva tiene un número máximo de usuarios dentro del ámbito de búsqueda. Vea los detalles de la sección de límites de la plantilla. <br><br> Revise los usuarios en la pestaña Usuarios y quite los usuarios que ya no necesiten ser puntuados. |

## <a name="policy-template-limits"></a>Límites del modelo de directiva

Las plantillas de directivas de administración de riesgos internos usan límites para administrar el volumen y la tasa de procesamiento de las actividades de riesgo de los usuarios dentro del ámbito de búsqueda y cómo este proceso se integra con los servicios de apoyo de Microsoft 365. Cada plantilla de directiva tiene un número máximo de usuarios a los que se pueden asignar activamente puntuaciones de riesgo para la directiva que puede soportar y procesar e informar eficazmente de las actividades de riesgo. Los usuarios dentro del ámbito de búsqueda son usuarios con eventos desencadenantes para la directiva.

El límite de cada directiva se calcula en función del número total de usuarios únicos que reciben puntuaciones de riesgo por tipo de plantilla de directiva. Si el número de usuarios para un tipo de plantilla de directiva se acerca o supera el límite de usuarios, el rendimiento de la directiva se verá reducido. Para ver el número actual de usuarios de una directiva, vaya a la pestaña Directiva y a la columna Usuarios en el ámbito de búsqueda. Puede tener hasta cinco directivas para cualquier plantilla de directiva. Estos límites máximos se aplican a los usuarios en todas las directivas que utilizan una plantilla de directiva determinada.

Use la siguiente tabla para determinar el número máximo de usuarios dentro del ámbito de búsqueda que admite cada plantilla de directiva:

|**Plantilla de directiva**|**Máximo de usuarios actuales en el ámbito de aplicación**|
|:------------------|:--------------------------------|
| Filtración de datos generales | 15 000 |
| Filtración de datos por usuarios inconformes | 7 500 |
| Filtración de datos por parte de usuarios prioritarios | 1 000  |
| Robo de datos por parte de los usuarios que abandonan la organización | 20 000 |
| Infracciones generales de la directiva de seguridad | 1 000  |
| Infracciones de directiva de seguridad por usuarios prioritarios | 1 000  |
| Infracciones de la directiva de seguridad por parte de los usuarios que abandonan la organización | 15 000 |
| Infracciones de la directiva de seguridad por parte de usuarios inconformes | 7 500 |

## <a name="create-a-new-policy"></a>Crear una nueva directiva

Para crear una nueva directiva de administración de riesgos internos, usará el asistente de directivas en la solución de **Administración de riesgos internos** en el Centro de cumplimiento de Microsoft 365.

Siga los siguientes pasos para crear una nueva directiva:

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. Seleccione **Crear directiva** para abrir el asistente de directivas.
3. En la página **Plantilla de directiva**, elija una categoría de directiva y luego seleccione la plantilla para la nueva directiva. Estas plantillas están compuestas por condiciones y señales que definen las actividades de riesgo que desea detectar e investigar. Revise los requisitos previos de la plantilla, los eventos desencadenantes y las actividades detectadas para confirmar que esta plantilla de directiva se ajusta a sus necesidades.

    >[!IMPORTANT]
    >Algunas plantillas de directivas tienen requisitos previos que deben configurarse para que la directiva genere las alertas relevantes. Si no ha configurado los requisitos previos de la directiva aplicable, vea el **Paso 4** anterior.

4. Seleccione **Siguiente** para continuar.
5. En la página **Nombre y descripción**, siga los siguientes campos:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la directiva. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional)**: escriba una descripción para la directiva.

6. Seleccione **Siguiente** para continuar.
7. En la página **Usuarios y grupos**, seleccione **Incluir todos los usuarios y grupos** o **Incluir usuarios y grupos específicos** para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios; seleccione **Agregar o editar grupos de usuarios prioritarios**. Si se selecciona **Incluir a todos los usuarios y grupos**, se buscarán los eventos desencadenantes de todos los usuarios y grupos de su organización para empezar a asignar puntuaciones de riesgo para la directiva. Seleccionar **Incluir usuarios y grupos específicos** permite definir qué usuarios y grupos se asignan a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la página **Contenido a priorizar**, puede asignar (si es necesario) las fuentes a priorizar, lo que aumenta la posibilidad de generar una alerta de alta gravedad para estas fuentes. Seleccione una de las siguientes opciones:

    - **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad, y/o tipos de información confidencial como contenido prioritario**. Al seleccionar esta opción se habilitarán las páginas de detalles del asistente para configurar estos canales.
    - **No deseo especificar el contenido prioritario en este momento (podrá hacerlo una vez que se haya creado la directiva)**. Al seleccionar esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si ha seleccionado **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario** en el paso anterior, verá las páginas de detalles de los *sitios de SharePoint*, *Tipos de información confidencial* y *Etiquetas de confidencialidad*. Use estas páginas detalladas para definir el SharePoint, los tipos de información confidencial y las etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar tipo de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"Número de cuenta bancaria de EE. UU."* y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiquetas de confidencialidad** y seleccionar las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto"*.

12. Seleccione **Siguiente** para continuar.
13. En la página **Indicadores y eventos desencadenantes**, verá los [indicadores](insider-risk-management-settings.md#indicators)que ha definido como disponibles en la página **Configuración de riesgos internos** > **Indicadores**. Si ha seleccionado una plantilla de *Filtración de datos* al principio del asistente, deberá seleccionar una directiva DLP de la lista desplegable de **directivas DLP** para activar los indicadores de activación de la directiva o seleccionar el evento desencadenante incorporado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, tendrá que seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Habilitar indicadores** del asistente o seleccionar los indicadores en la página **Administración de riesgos internos** > **Configuración** > **Indicadores de directiva**.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración del umbral de la directiva predeterminada para estos indicadores, desactive la opción **Usar umbrales predeterminados recomendados por Microsoft** y escriba los valores del umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* o *Dispositivo*, seleccione los **Impulsores de la puntuación de riesgo** según corresponda. Los impulsores de la puntuación de riesgo solo se aplican a los indicadores seleccionados.
    - Si ha seleccionado una plantilla de directiva de *Robo de datos* o *Filtración de datos*, seleccione uno o más métodos de **Detección de Secuencia** y un método de **Detección de filtración acumulada** para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la página **Umbrales de los indicadores**, seleccione la opción de usar los umbrales de los indicadores predeterminados o de especificar umbrales personalizados para los indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la página **Revisión**, revise la configuración que ha elegido para la directiva y cualquier sugerencia o advertencia sobre sus selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de la directiva o seleccione **Enviar** para crear y activar la directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos internos existente, utilizará el asistente de directivas en la solución de **Administración de riesgos internos** en el Centro de cumplimiento de Microsoft 365.

Siga los siguientes pasos para administrar una directiva existente:

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. En el panel de directivas, seleccione la directiva que desea administrar.
3. En la página de detalles de la directiva, seleccione **Editar directiva**
4. En el asistente de directivas, no se puede editar lo siguiente:
    - **Plantilla de la directiva**: la plantilla utilizada para definir los tipos de indicadores de riesgo supervisados por la directiva.
    - **Nombre**: el nombre amigable para la directiva.
5. En la página **Nombre y descripción**, actualice la descripción de la directiva en el campo **Descripción**.
6. Seleccione **Siguiente** para continuar.
7. En la página **Usuarios y grupos**, seleccione **Incluir todos los usuarios y grupos** o **Incluir usuarios y grupos específicos** para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios; seleccione **Agregar o editar grupos de usuarios prioritarios**. Si se selecciona **Incluir a todos los usuarios y grupos**, se buscarán los eventos desencadenantes de todos los usuarios y grupos de su organización para empezar a asignar puntuaciones de riesgo para la directiva. Seleccionar **Incluir usuarios y grupos específicos** permite definir qué usuarios y grupos se asignan a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la página **Contenido a priorizar**, puede asignar (si es necesario) las fuentes a priorizar, lo que aumenta la posibilidad de generar una alerta de alta gravedad para estas fuentes. Seleccione una de las siguientes opciones:

    - **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad, y/o tipos de información confidencial como contenido prioritario**. Al seleccionar esta opción se habilitarán las páginas de detalles del asistente para configurar estos canales.
    - **No deseo especificar el contenido prioritario en este momento (podrá hacerlo una vez que se haya creado la directiva)**. Al seleccionar esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si ha seleccionado **Deseo especificar sitios de SharePoint, etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario** en el paso anterior, verá las páginas de detalles de los *sitios de SharePoint*, *Tipos de información confidencial* y *Etiquetas de confidencialidad*. Use estas páginas detalladas para definir el SharePoint, los tipos de información confidencial y las etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar tipo de información confidencial** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"Número de cuenta bancaria de EE. UU."* y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiquetas de confidencialidad** y seleccionar las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto"*.

12. Seleccione **Siguiente** para continuar.
13. En la página **Indicadores y eventos desencadenantes**, verá los [indicadores](insider-risk-management-settings.md#indicators)que ha definido como disponibles en la página **Configuración de riesgos internos** > **Indicadores**. Si ha seleccionado una plantilla de *Filtración de datos* al principio del asistente, deberá seleccionar una directiva DLP de la lista desplegable de **directivas DLP** para activar los indicadores de activación de la directiva o seleccionar el evento desencadenante incorporado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, tendrá que seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Habilitar indicadores** del asistente o seleccionar los indicadores en la página **Administración de riesgos internos** > **Configuración** > **Indicadores de directiva**.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración del umbral de la directiva predeterminada para estos indicadores, desactive la opción **Usar umbrales predeterminados recomendados por Microsoft** y escriba los valores del umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* o *Dispositivo*, seleccione los **Impulsores de la puntuación de riesgo** según corresponda. Los impulsores de la puntuación de riesgo solo se aplican a los indicadores seleccionados.
    - Si ha seleccionado una plantilla de directiva de *Robo de datos* o *Filtración de datos*, seleccione uno o más métodos de **Detección de Secuencia** y un método de **Detección de filtración acumulada** para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la página **Umbrales de los indicadores**, seleccione la opción de usar los umbrales de los indicadores predeterminados o de especificar umbrales personalizados para los indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la página **Revisión**, revise la configuración que ha elegido para la directiva y cualquier sugerencia o advertencia sobre sus selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de la directiva o seleccione **Enviar** para crear y activar la directiva.

## <a name="copy-a-policy"></a>Copiar una directiva

Es posible que tenga que crear una nueva directiva que sea similar a una directiva existente pero que solo necesite unos pocos cambios de configuración. En lugar de crear una nueva directiva desde cero, puede copiar una directiva existente y luego modificar las áreas que deben actualizarse en la nueva directiva.

Siga los siguientes pasos para copiar una directiva existente:

1. En Centro de cumplimiento de Microsoft 365, vaya Administración de riesgos internos y seleccione la pestaña Directivas.
2. En el panel de directivas, seleccione la directiva que desea copiar.
3. En la página de detalles de la directiva, seleccione Copiar.
4. En el asistente de directivas, asigne un nombre a la nueva directiva y actualice la configuración de la misma según sea necesario.

## <a name="immediately-start-scoring-user-activity"></a>Iniciar inmediatamente la puntuación de la actividad de los usuarios

Puede haber escenarios en los que necesite comenzar inmediatamente a asignar puntuaciones de riesgo a los usuarios con directivas de riesgo interno fuera del flujo de trabajo de eventos desencadenantes de la administración de riesgos internos. Use **Iniciar actividad de puntuación para usuarios** en la pestaña **Directivas** para agregar manualmente un usuario (o usuarios) a una o más directivas de riesgo interno durante una cantidad de tiempo específica, para comenzar inmediatamente a asignar puntuaciones de riesgo a su actividad, y para omitir el requisito de que un usuario tenga un indicador desencadenante (como una coincidencia de directivas DLP). También puede agregar una razón para agregar el usuario a la directiva, que aparecerá en la escala de tiempo de la actividad de los usuarios. Los usuarios agregados manualmente a las directivas se muestran en el panel de **Usuarios** y se crean alertas si la actividad cumple con los umbrales de alerta de las directivas.

Algunos escenarios en los que puede querer empezar inmediatamente a puntuar las actividades de los usuarios:

- Cuando los usuarios se identifican con las preocupaciones de riesgo y desea iniciar inmediatamente la asignación de puntuaciones de riesgo a su actividad para una o varias de sus directivas
- Cuando hay un incidente que puede requerir que inicie inmediatamente la asignación de puntuaciones de riesgo a la actividad de los usuarios involucrados para una o varias de las directivas
- Cuando aún no ha configurado su conector de recursos humanos, pero desea iniciar la asignación de puntuaciones de riesgo a actividades de usuario para eventos de recursos humanos cargando un archivo .csv para los usuarios

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel de **Usuarios**. Las actividades de los 90 días anteriores de estos usuarios pueden tardar hasta 24 horas en aparecer. Para ver las actividades de los usuarios agregados manualmente, vaya a la pestaña **Usuarios** y seleccione el usuario en el panel **Usuarios** y abra la pestaña **Actividad del usuario** en el panel de detalles.

Para iniciar manualmente la actividad de puntuación de los usuarios en una o más directivas de administración de riesgos internos, siga los siguientes pasos:

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. En el panel de directivas, seleccione la directiva o directivas a las que desea agregar usuarios.
3. Seleccione **Iniciar la actividad de puntuación para los usuarios**.
4. En el campo **Razón del panel** y luego en el panel **Agregar usuarios a múltiples directivas**, agregue una razón para agregar los usuarios.
5. En el campo **Esto debe durar (elija entre 5 y 30 días)**, defina el número de días para puntuar la actividad del usuario para la directiva a la que se agrega
6. Para buscar usuarios en su Active Directory, use el campo **Buscar usuario para agregar a las directivas**. Escriba el nombre del usuario que desea agregar a las directivas. Seleccione el nombre del usuario y repita esta acción para asignar usuarios adicionales a las directivas. La lista de usuarios que ha seleccionado aparece en la sección de usuarios del panel Agregar usuarios a múltiples directivas.
7. Para importar una lista de usuarios que desea agregar a las directivas, seleccione **Importar** para importar un archivo .csv (valores separados por comas). El archivo debe tener el siguiente formato y debe enumerar los nombres de los usuarios principales en el archivo:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Seleccione Agregar usuarios a las directivas para aceptar los cambios y agregar usuarios a las directivas o seleccione Cancelar para descartar los cambios y cerrar el diálogo.

## <a name="stop-scoring-users-in-a-policy"></a>Dejar de puntuar a los usuarios en una directiva

Para dejar de puntuar a los usuarios en una directiva, vea el artículo [Usuarios de la administración de riesgos internos: quitar usuarios de la asignación dentro del ámbito de búsqueda de las directivas](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies).

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva no elimina las alertas activas o archivadas generadas a partir de la misma.

Para eliminar una directiva de administración de riesgos internos existente, siga estos pasos:

1. En [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya **Administración de riesgos internos** y seleccione la pestaña **Directivas**.
2. En el panel de directivas, seleccione la directiva que desea eliminar.
3. Seleccione **Eliminar** la barra de herramientas del panel.
4. En el cuadro de dialogo **Eliminar**, seleccione **Sí** para eliminar la directiva o **Cancelar** para cerrarlo.
