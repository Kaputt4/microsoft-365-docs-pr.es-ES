---
title: Directivas de administración de riesgos de Insider
description: Obtenga información sobre las directivas de administración de riesgos internas en Microsoft 365
keywords: Microsoft 365, administración de riesgos insider, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 96d265a7b909b439f960c951b10c84f4bc7a63b0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916834"
---
# <a name="insider-risk-management-policies"></a>Directivas de administración de riesgos de Insider

Las directivas de administración de riesgos de Insider determinan qué usuarios están en el ámbito y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de la organización o definir usuarios o grupos individuales para la administración en una directiva. Las directivas admiten prioridades de contenido para centrar las condiciones de directiva en varios o específicos sitios de Microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Con las plantillas, puede seleccionar indicadores de riesgo específicos y personalizar umbrales de eventos para los indicadores de directiva, personalizar eficazmente las puntuaciones de riesgo y el nivel y la frecuencia de las alertas. Además, los refuerzos de puntuación de riesgo y las detecciones de anomalías ayudan a identificar la actividad del usuario que es de mayor importancia o más inusual. Las ventanas de directiva permiten definir el período de tiempo para aplicar la directiva a las actividades de alerta y se usan para determinar la duración de la directiva una vez activada.

## <a name="policy-dashboard"></a>Panel de directivas

El **panel Directiva** permite ver rápidamente las directivas de su organización, el estado de la directiva, agregar manualmente usuarios a las directivas y ver el estado de las alertas asociadas a cada directiva.

- **Nombre de directiva:** el nombre asignado a la directiva en el asistente para directivas.
- **Estado:** el estado de mantenimiento de cada directiva. Muestra el número de advertencias y recomendaciones de directiva, o un estado *de Correcto* para directivas sin problemas.  Puede hacer clic en la directiva para ver los detalles del estado de mantenimiento para cualquier advertencia o recomendación.
- **Alertas activas:** número de alertas activas para cada directiva.
- **Alertas confirmadas:** número total de alertas que se han dado como resultado casos de la directiva en los últimos 365 días.
- **Acciones realizadas en alertas:** el número total de alertas que se confirmaron o descartaron durante los últimos 365 días.
- **Efectividad de** alertas de directiva: porcentaje determinado por el total de alertas confirmadas dividido por el total de acciones realizadas en alertas (que es la suma de alertas que se confirmaron o descartaron durante el año pasado).

![Panel de directivas de administración de riesgos insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Recomendaciones de directivas de análisis (versión preliminar)

El análisis de riesgos de Insider le permite realizar una evaluación de los posibles riesgos de insider en su organización sin configurar directivas de riesgo de insider. Esta evaluación puede ayudar a su organización a identificar posibles áreas de mayor riesgo para el usuario y ayudar a determinar el tipo y el ámbito de las directivas de administración de riesgos internas que puede considerar la configuración.

Para obtener más información sobre las recomendaciones de directiva y análisis de riesgos de insider, consulte Configuración de administración de riesgos de [Insider: Analytics (versión preliminar).](insider-risk-management-settings.md#analytics-preview)

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de administración de riesgos insider son condiciones de directiva predefinidas que definen los tipos de indicadores de riesgo y el modelo de puntuación de riesgos que usa la directiva. Cada directiva debe tener asignada una plantilla en el Asistente para la creación de directivas antes de crear la directiva. La administración de riesgos de Insider admite hasta cinco directivas para cada plantilla de directiva. Al crear una nueva directiva de riesgo de insider con el asistente para directivas, elegirá entre una de las siguientes plantillas de directiva:

### <a name="data-theft-by-departing-users"></a>Robo de datos por parte de los usuarios que salen

Cuando los usuarios abandonan la organización, hay indicadores de riesgo específicos que suelen asociarse con el robo de datos al salir de los usuarios. Esta plantilla de directiva usa indicadores de exfiltración para la puntuación de riesgos y se centra en la detección y alertas en esta área de riesgo. El robo de datos para los usuarios que salen puede incluir la descarga de archivos de SharePoint Online, la impresión de archivos y la copia de datos en servicios de almacenamiento y mensajería en la nube personales cerca de su renuncia de empleo y fechas de finalización. Al usar el conector de Recursos humanos de Microsoft 365 o la opción de supervisar automáticamente la eliminación de cuentas de usuario en Azure Active Directory para su organización, esta plantilla comienza a puntuar los indicadores de riesgo relacionados con estas actividades y cómo se correlacionan con el estado de empleo del usuario.

>[!IMPORTANT]
>Al usar esta plantilla, puede configurar un conector de RRHH de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización para los usuarios de la organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de Recursos humanos de Microsoft 365 para su organización. Si decide no usar el conector de recursos humanos, debe seleccionar la opción Cuenta de usuario eliminada de Azure AD al configurar eventos desencadenadores en el asistente para directivas.

### <a name="general-data-leaks"></a>Pérdidas de datos generales

Proteger los datos y evitar pérdidas de datos es un desafío constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por usuarios, dispositivos y servicios. Los usuarios tienen la capacidad de crear, almacenar y compartir información entre servicios y dispositivos que hacen que la administración de pérdidas de datos sea cada vez más compleja y difícil. Las pérdidas de datos pueden incluir el exceso accidental de información fuera de la organización o el robo de datos con intenciones malintencionadas. Con una directiva de prevención de pérdida de datos (DLP) asignada o el evento de activación integrado, esta plantilla comienza a puntuar detecciones en tiempo real de descargas sospechosas de datos de SharePoint Online, uso compartido de archivos y carpetas, impresión de archivos y copia de datos en servicios de almacenamiento y mensajería en la nube personales.

Al usar una plantilla de pérdida de datos, puede asignar una directiva DLP para desencadenar indicadores en la directiva de riesgo de información interna para *alertas* de alta gravedad en su organización. Cada vez que una regla de directiva DLP genera una alerta de alta gravedad al registro de auditoría de Office 365, las directivas de riesgo de insider creadas con esta plantilla examinan automáticamente la alerta DLP de alta gravedad. Si la alerta contiene un usuario dentro del ámbito definido en la directiva de riesgo insider, la directiva de riesgo insider procesa la alerta como una nueva alerta y se le asigna una gravedad de riesgo y una puntuación de riesgo de insider. Esta directiva le permite evaluar esta alerta en contexto con otras actividades incluidas en el caso. Si no elige una directiva DLP, debe seleccionar el evento de activación integrado.

#### <a name="data-leaks-policy-guidelines"></a>Directrices de directiva de pérdida de datos

Al crear o modificar directivas DLP para su uso con directivas de administración de riesgos internas, tenga en cuenta las siguientes directrices:

- Priorice los eventos de exfiltración  de datos y sea selectivo al asignar la configuración de informes de incidentes a *High* al configurar reglas en las directivas DLP. Por ejemplo, enviar por correo electrónico documentos confidenciales a un competidor conocido debe ser un *evento de* exfiltración de nivel de alerta alto. Asignar el nivel  alto en  la configuración de informes de incidentes en otras reglas de directiva DLP puede aumentar el ruido en el flujo de trabajo de alertas de administración de riesgos interno y dificultar que los investigadores y analistas de datos evalúen correctamente estas alertas. Por ejemplo, la asignación de niveles de *alerta* altos para acceder a actividades de denegación en directivas DLP hace que sea más difícil evaluar actividades y comportamientos de usuario realmente arriesgados.
- Asegúrese de comprender y configurar correctamente los usuarios del ámbito en las directivas de administración de riesgos de DLP e insider. Solo los usuarios definidos como en el ámbito de las directivas de administración de riesgos de insider con la plantilla Pérdida de datos tendrán **alertas** de directiva DLP de alta gravedad procesadas. Además, la directiva de administración de riesgos de insider examinará solo los usuarios definidos como en el ámbito de una regla para una alerta DLP de alta gravedad para su consideración. Es importante que no configure los usuarios en el ámbito, sin que se sepa, tanto en sus directivas de riesgo DLP como en las directivas de riesgo de insider de manera conflictiva.

     Por ejemplo, si las reglas de directiva DLP están en el ámbito de solo los usuarios del equipo de ventas y la directiva de riesgo de información interna creada a partir de la plantilla **Pérdidas** de datos ha definido a todos los usuarios como dentro del ámbito, la directiva de riesgo interno solo procesará realmente alertas DLP de alta gravedad para los usuarios del equipo de ventas. La directiva de riesgo insider no recibirá alertas DLP de alta prioridad para que los usuarios procese que no están definidos en las reglas DLP de este ejemplo. Por el contrario, si la directiva de administración de riesgos insider creada a partir de plantillas de pérdida de datos está ámbito solo para los usuarios del equipo de ventas y la directiva DLP asignada está en el ámbito de todos los usuarios, la directiva de riesgo insider solo procesará **alertas** DLP de alta gravedad para los miembros del equipo de ventas. La directiva de administración de riesgos de insider omitirá las alertas DLP de alta gravedad para todos los usuarios que no se encuentran en el equipo de ventas.

- Asegúrese de que la configuración **de** la regla Informes de incidentes en la directiva DLP usada para esta plantilla de administración de riesgos insider esté configurada para *alertas* de nivel de gravedad alta. El *nivel* de gravedad alta son los eventos desencadenamientos y las alertas de  administración de riesgos internas no se generarán a partir de reglas de directivas DLP con el campo Informes de incidentes establecido en *Bajo* o *Medio*.

    ![Configuración de alerta de directiva DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Al crear una nueva directiva DLP con las plantillas integradas, deberá seleccionar la opción  Crear o personalizar  reglas **dlp** avanzadas para configurar la configuración informes de incidentes para el nivel de gravedad alta.

Cada directiva de administración de riesgos insider creada a partir de la **plantilla Pérdida de** datos solo puede tener asignada una directiva DLP. Considere la posibilidad de crear una directiva DLP dedicada que combine las distintas actividades que desea detectar y actuar como eventos desencadenantes para las directivas de riesgo de insider que usan la **plantilla Pérdida de** datos.

Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización.

### <a name="data-leaks-by-priority-users-preview"></a>Pérdidas de datos por usuarios prioritarios (versión preliminar)

La protección de datos y la prevención de pérdidas de datos para los usuarios de su organización pueden depender de su posición, nivel de acceso a información confidencial o historial de riesgos. Las pérdidas de datos pueden incluir el exceso accidental de información altamente confidencial fuera de la organización o el robo de datos con intenciones malintencionadas. Con una directiva de prevención de pérdida de datos (DLP) asignada, esta plantilla comienza a puntuar detecciones en tiempo real de actividad sospechosa y da como resultado una mayor probabilidad de alertas y alertas de riesgo interno con niveles de gravedad más altos. Los usuarios prioritarios se definen en [grupos de usuarios prioritarios](insider-risk-management-settings.md#priority-user-groups-preview) configurados en el área de configuración de administración de riesgos de insider.

Al igual que con la **plantilla Pérdidas de** datos generales, debe asignar una directiva DLP para desencadenar indicadores en la directiva de riesgo interno para alertas de alta gravedad en su organización. Siga las directrices de directiva de pérdida de datos anteriores al crear una directiva con esta plantilla. Además, deberá asignar grupos de usuarios de prioridad creados en La configuración de administración de riesgos de **Insider** Grupos de usuarios  >    >  **prioritarios** a la directiva.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Pérdidas de datos por usuarios inconformes (versión preliminar)

Cuando los usuarios experimentan factores de estrés laborales, pueden resultar inconformes, lo que puede aumentar las posibilidades de actividad de riesgo interno. Esta plantilla comienza a puntuar la actividad del usuario cuando se identifica un indicador asociado con el descontento. Algunos ejemplos son las notificaciones de mejora del rendimiento, las revisiones de rendimiento deficientes o los cambios en el estado del nivel de trabajo. Las pérdidas de datos para usuarios inconformes pueden incluir la descarga de archivos de SharePoint Online y la copia de datos en servicios de almacenamiento y mensajería en la nube personales cerca de eventos de estrés laboral.

Al usar esta plantilla, también debe configurar un conector de RRHH de Microsoft 365 para importar periódicamente notificaciones de mejora del rendimiento, estado de revisión de rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de Recursos humanos de Microsoft 365 para su organización.

### <a name="general-security-policy-violations-preview"></a>Infracciones de directivas de seguridad generales (versión preliminar)

En muchas organizaciones, los usuarios tienen permiso para instalar software en sus dispositivos o para modificar la configuración del dispositivo para ayudar con sus tareas. Ya sea de forma involuntaria o con intenciones malintencionadas, los usuarios pueden instalar malware o deshabilitar características de seguridad importantes que ayudan a proteger la información en su dispositivo o en los recursos de red. Esta plantilla de directiva usa alertas de seguridad de Microsoft Defender para endpoint para empezar a puntuar estas actividades y detectar focos y alertas en esta área de riesgo. Use esta plantilla para proporcionar información sobre las infracciones de directivas de seguridad en escenarios en los que los usuarios pueden tener un historial de infracciones de directivas de seguridad que pueden ser un indicador del riesgo de insider.

Tendrás que configurar Microsoft Defender para endpoint en tu organización y habilitar Defender for Endpoint para la integración de la administración de riesgos de información interna en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender for Endpoint para la integración de la administración de riesgos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Infracciones de directivas de seguridad al salir de los usuarios (versión preliminar)

Los usuarios que salen, ya sean positivos o negativos, pueden ser riesgos más elevados para las infracciones de la directiva de seguridad. Para ayudar a proteger contra infracciones de seguridad inadvertidas o malintencionadas para los usuarios que salen, esta plantilla de directiva usa alertas de Defender para endpoints para proporcionar información sobre actividades relacionadas con la seguridad. Estas actividades incluyen que el usuario instale malware u otras aplicaciones potencialmente dañinas y deshabilite las características de seguridad en sus dispositivos. Al usar el conector de RRHH de [Microsoft 365](import-hr-data.md) o la opción de supervisar automáticamente la eliminación de cuentas de usuario en Azure Active Directory para su organización, esta plantilla comienza a puntuar los indicadores de riesgo relacionados con estas actividades de seguridad y cómo se correlacionan con el estado de empleo del usuario.

Tendrás que configurar Microsoft Defender para endpoint en tu organización y habilitar Defender for Endpoint para la integración de la administración de riesgos de información interna en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender for Endpoint para la integración de la administración de riesgos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Infracciones de directivas de seguridad por parte de usuarios prioritarios (versión preliminar)

La protección contra infracciones de seguridad para los usuarios de su organización puede depender de su posición, nivel de acceso a información confidencial o historial de riesgos. Dado que las infracciones de seguridad de los usuarios prioritarios pueden tener un impacto significativo en las áreas críticas de la organización, esta plantilla de directiva comienza a puntuar en estos indicadores y usa alertas de Microsoft Defender para puntos de conexión para proporcionar información sobre las actividades relacionadas con la seguridad de estos usuarios. Estas actividades pueden incluir los usuarios prioritarios que instalan malware u otras aplicaciones potencialmente dañinas y deshabilitan las características de seguridad en sus dispositivos. Los usuarios prioritarios se definen en grupos de usuarios prioritarios configurados en el área de configuración de administración de riesgos de insider.

Tendrás que configurar Microsoft Defender para endpoint en tu organización y habilitar Defender for Endpoint para la integración de la administración de riesgos de información interna en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender for Endpoint para la integración de la administración de riesgos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Además, deberá asignar grupos de usuarios de prioridad creados en La configuración de administración de riesgos de **Insider** Grupos de usuarios  >    >  **prioritarios** a la directiva.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Infracciones de directivas de seguridad por parte de usuarios inconformes (versión preliminar)

Los usuarios que experimentan factores de estrés laboral pueden tener un mayor riesgo de infracciones de directivas de seguridad inadvertidas o malintencionadas. Estos estresores pueden incluir el usuario que se coloca en un plan de mejora del rendimiento, el estado de la revisión de rendimiento deficiente o la degradación de su posición actual. Esta plantilla de directiva inicia la puntuación de riesgos en función de estos indicadores y actividades asociadas con estos eventos para estos usuarios.

Al usar esta plantilla, también debe configurar un conector de RRHH de Microsoft 365 para importar periódicamente notificaciones de mejora del rendimiento, estado de revisión de rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de Recursos humanos de Microsoft 365 para su organización.

También tendrás que configurar Microsoft Defender para endpoint en tu organización y habilitar Defender for Endpoint para la integración de la administración de riesgos insider en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender for Endpoint para la integración de la administración de riesgos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Requisitos previos de plantilla de directiva y eventos desencadenantes

Según la plantilla que elija para una directiva de administración de riesgos de insider, los eventos desencadenantes y los requisitos previos de la directiva varían. Los eventos desencadenantes son requisitos previos que determinan si un usuario está activo para una directiva de administración de riesgos de insider. Si un usuario se agrega a una directiva de administración de riesgos de insider pero no tiene un evento desencadenante, la directiva no evalúa la actividad del usuario a menos que se agregó manualmente en el panel Usuarios. Los requisitos previos de la directiva son elementos necesarios para que la directiva reciba las señales o actividades necesarias para evaluar el riesgo.

En la tabla siguiente se enumeran los eventos desencadenantes y los requisitos previos para las directivas creadas a partir de cada plantilla de directiva de administración de riesgos insider:

| **Plantilla de directiva** | **Desencadenar eventos para directivas** | **Requisitos previos** |
| :------------------ | :--------------------------------- | :---------------- |
| Robo de datos por parte de los usuarios que salen | Indicador de fecha de dimisión o finalización desde el conector de RECURSOS HUMANOS | (opcional) Conector de RRHH de Microsoft 365 configurado para indicadores de fecha de terminación y dimisión o integración de Azure Active Directory habilitada |
| Pérdidas de datos generales | Actividad de directiva de pérdida de datos que crea una alerta de gravedad alta | (opcional) Directiva DLP configurada para alertas de gravedad alta o evento de activación de exfiltración de datos integrado |
| Pérdidas de datos por usuarios prioritarios | Actividad de directiva de pérdida de datos que crea *una alerta de gravedad* alta o desencadenadores de eventos de exfiltración integrados | (opcional) Directiva DLP configurada para alertas de gravedad alta <br><br> Grupos de usuarios prioritarios configurados en la configuración de riesgos de insider |
| Pérdidas de datos de usuarios inconformes | Mejora del rendimiento, rendimiento deficiente o indicadores de cambio de nivel de trabajo desde el conector de RECURSOS HUMANOS | Conector de RRHH de Microsoft 365 configurado para indicadores de inconformidad |
| Infracciones de la directiva de seguridad general | Evasión defensivo de controles de seguridad o software no deseado detectado por Microsoft Defender para endpoint | Suscripción a Active Microsoft Defender para endpoint <br><br> Integración de Microsoft Defender para endpoints con el centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de directivas de seguridad por parte de los usuarios que salen | Indicadores de fecha de dimisión o finalización del conector de recursos humanos o la eliminación de cuentas de Azure Active Directory | (opcional) Conector de RRHH de Microsoft 365 configurado para indicadores de fecha de terminación y dimisión <br><br> Suscripción a Active Microsoft Defender para endpoint <br><br> Integración de Microsoft Defender para endpoints con el centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de directivas de seguridad por parte de usuarios prioritarios | Evasión defensivo de controles de seguridad o software no deseado detectado por Microsoft Defender para endpoint | Suscripción a Active Microsoft Defender para endpoint <br><br> Integración de Microsoft Defender para endpoints con el centro de cumplimiento de Microsoft 365 configurado <br><br> Grupos de usuarios prioritarios configurados en la configuración de riesgos de insider |
| Infracciones de directivas de seguridad por parte de un usuario inconforme | Mejora del rendimiento, rendimiento deficiente o indicadores de cambio de nivel de trabajo desde el conector de RECURSOS HUMANOS | Conector de RRHH de Microsoft 365 configurado para indicadores de inconformidad <br><br> Suscripción a Active Microsoft Defender para endpoint <br><br> Integración de Microsoft Defender para endpoints con el centro de cumplimiento de Microsoft 365 configurado |

## <a name="prioritize-content-in-policies"></a>Priorizar contenido en directivas

Las directivas de administración de riesgos de Insider admiten la especificación de una prioridad más alta para el contenido en función de dónde se almacene o cómo se clasifique. La especificación de contenido como prioridad aumenta la puntuación de riesgo de cualquier actividad asociada, lo que a su vez aumenta la probabilidad de generar una alerta de gravedad alta. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o que se haya especificado como prioridad en la directiva.

Por ejemplo, su organización tiene un sitio de SharePoint dedicado para un proyecto extremadamente confidencial. Las pérdidas de datos de información en este sitio de SharePoint podrían poner en peligro el proyecto y tendrían un impacto significativo en su éxito. Al priorizar este sitio de SharePoint en una directiva de pérdida de datos, se aumentan automáticamente las puntuaciones de riesgo para las actividades que califican. Esta priorización aumenta la probabilidad de que estas actividades generen una alerta de riesgo de información interna y aumenta el nivel de gravedad de la alerta.

Al crear una directiva de administración de riesgos insider en el asistente para directivas, puede elegir entre las siguientes prioridades:

- **Sitios de SharePoint:** a cualquier actividad asociada con todos los tipos de archivo de sitios de SharePoint definidos se le asigna una puntuación de riesgo más alta. 
- **Tipos de información confidencial:** a cualquier actividad asociada con contenido que [contenga](sensitive-information-type-entity-definitions.md) tipos de información confidencial se le asigna una puntuación de riesgo más alta.
- **Etiquetas de confidencialidad:** cualquier actividad asociada con el contenido que tenga etiquetas de confidencialidad [específicas](sensitivity-labels.md) aplicadas tiene asignada una puntuación de riesgo más alta.

## <a name="sequence-detection-preview"></a>Detección de secuencias (versión preliminar)

Es posible que las actividades de riesgo no se produzcan como eventos aislados. Estos riesgos suelen formar parte de una secuencia más grande de eventos. Una secuencia es un grupo de dos o más actividades de usuario realizadas una tras otra que pueden sugerir un riesgo elevado. La identificación de estas actividades relacionadas es una parte importante de la evaluación del riesgo general. Cuando la detección de secuencias está habilitada para directivas de robo de  datos o de pérdida de datos, los conocimientos de las actividades de información de secuencia se muestran en la pestaña Actividad del usuario dentro de un caso de administración de riesgos de insider. Las siguientes plantillas de directiva admiten la detección de secuencias:

- Robo de datos por parte de los usuarios que salen
- Pérdidas de datos generales
- Pérdidas de datos por usuarios prioritarios
- Pérdidas de datos de usuarios inconformes

Estas directivas de administración de riesgos internas pueden usar indicadores específicos y el orden en que se producen para detectar cada paso de una secuencia de riesgo. Los nombres de archivo se usan al asignar actividades en una secuencia. Estos riesgos se organizan en cuatro categorías principales de actividad:

- **Colección:** estas señales de categoría se centran en las actividades de descarga de usuarios de directivas en el ámbito. Una actividad de ejemplo en esta categoría sería descargar archivos de sitios de SharePoint.
- **Exfiltración:** estas señales de categoría se centran en el uso compartido o las actividades de extracción a orígenes internos y externos por parte de los usuarios de directivas de ámbito. Una actividad de ejemplo en esta categoría sería enviar correos electrónicos con datos adjuntos de la organización a destinatarios externos.
- **Ofuscación:** estas señales de categoría se centran en el enmascaramiento de actividades de riesgo por parte de los usuarios de directivas en el ámbito. Una actividad de ejemplo en esta categoría sería cambiar el nombre de los archivos de un dispositivo.
- **Limpieza: estas** señales de categoría se centran en las actividades de eliminación de usuarios de directivas en el ámbito. Una actividad de ejemplo en esta categoría sería eliminar archivos de un dispositivo.

>[!NOTE]
>La detección de secuencias usa indicadores que están habilitados en la configuración global para la administración de riesgos de insider y los indicadores seleccionados en una directiva. Si no se seleccionan los indicadores adecuados, la detección de secuencias no funcionará.

Puede personalizar la configuración de umbral individual para cada tipo de detección de secuencia cuando se configura en la directiva. Esta configuración de umbral ajusta las alertas en función del volumen de archivos asociados con la secuencia.

Para obtener más información sobre la administración de la detección de secuencias en la **vista Actividad del** usuario, vea Casos de administración de riesgos de [Insider: Actividad del usuario](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Detección de exfiltración acumulativa (versión preliminar)

Los indicadores de riesgo insider ayudan a identificar niveles inusuales de actividades de riesgo cuando se evalúan diariamente para los usuarios que están en el ámbito de las directivas de riesgo internas. La detección acumulativa de exfiltración usa modelos de aprendizaje automático para ayudarle a identificar cuándo las actividades de exfiltración del usuario superan los promedios de la organización cuando se miden con el tiempo y en varios tipos de actividad de exfiltración. Los analistas e investigadores de administración de riesgos de Insider pueden usar información acumulativa de detección de exfiltración para ayudar a identificar actividades de exfiltración que normalmente no generan alertas, pero que están por encima de lo que es típico para su organización. Algunos ejemplos pueden ser la salida lenta de los usuarios a través de un intervalo de días, o cuando los usuarios comparten datos repetidamente en varios canales más de lo habitual para el uso compartido de datos para su organización.

La detección acumulativa de exfiltración está habilitada de forma predeterminada al usar las siguientes plantillas de directiva:

- Robo de datos por parte de los usuarios que salen
- Pérdidas de datos generales
- Pérdidas de datos por usuarios prioritarios
- Pérdidas de datos de usuarios inconformes

>[!NOTE]
>La detección acumulativa de exfiltración usa indicadores de exfiltración que están habilitados en la configuración global para los indicadores de administración de riesgos e exfiltración de insider seleccionados en una directiva. Por lo tanto, la detección acumulativa de exfiltración solo se evalúa para los indicadores de exfiltración necesarios seleccionados.

Cuando se habilita la detección de exfiltración acumulativa para directivas de robo de datos o pérdida de datos, los conocimientos de las actividades de exfiltración acumulativas se muestran en la pestaña **Actividad** del usuario dentro de un caso de administración de riesgos de información interna.

Para obtener más información sobre la administración de actividades de usuario, vea Casos de administración de riesgos [de Insider: Actividades de usuario](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Estado de la directiva (versión preliminar)

El estado de la directiva le ofrece información sobre posibles problemas con las directivas de administración de riesgos de insider. La columna Estado de la pestaña Directivas puede alertar sobre problemas de directivas que pueden impedir que se informe de actividad del usuario o por qué el número de alertas de actividad es inusual. El estado de mantenimiento de la directiva también puede confirmar que la directiva está en buen estado y que no necesita cambios de configuración ni atención.

Si hay problemas con una directiva, el estado de mantenimiento de la directiva muestra advertencias de notificación y recomendaciones para ayudarle a tomar medidas para resolver problemas de directiva. Estas notificaciones pueden ayudarle a resolver los siguientes problemas:

- Directivas con configuración incompleta. Estos problemas pueden incluir la falta de usuarios o grupos en la directiva u otros pasos de configuración de directivas incompletos.
- Directivas con problemas de configuración de indicadores. Los indicadores son una parte importante de cada directiva. Si los indicadores no están configurados o si se seleccionan demasiados indicadores, es posible que la directiva no evalúe las actividades de riesgo según lo previsto.
- Los desencadenadores de directivas no funcionan o los requisitos de desencadenador de directivas no están configurados correctamente. La funcionalidad de la directiva puede depender de otros servicios o requisitos de configuración para detectar eficazmente eventos desencadenados para activar la asignación de puntuación de riesgo a los usuarios de la directiva. Estas dependencias pueden incluir problemas con la configuración del conector, Microsoft Defender para el uso compartido de alertas de extremo o las opciones de configuración de la directiva de prevención de pérdida de datos.
- Los límites de volumen se acercan o se acercan a los límites. Las directivas de administración de riesgos de Insider usan numerosos servicios y puntos de conexión de Microsoft 365 para agregar señales de actividad de riesgo. Según el número de usuarios de las directivas, los límites de volumen pueden retrasar la identificación y la presentación de informes de actividades de riesgo. Obtenga más información sobre estos límites en la sección Límites de plantillas de directiva de este artículo.

Para ver rápidamente el estado de mantenimiento de una directiva, navegue por la pestaña Directiva y la columna Estado. Aquí verá las siguientes opciones de estado de la directiva para cada directiva:

- Correcto: no se han identificado problemas con la directiva.
- Recomendaciones: hay algunos problemas con la directiva que pueden impedir que la directiva pueda funcionar como se esperaba.
- Advertencias: hay problemas con la directiva que le impedirán identificar actividades de riesgo.

Para obtener más información sobre las recomendaciones o advertencias, seleccione una directiva en la **pestaña** Directiva para abrir la tarjeta de detalles de la directiva. En la sección Notificaciones de la tarjeta de detalles se mostrará más información sobre las recomendaciones y advertencias, incluidas las instrucciones sobre cómo solucionar estos problemas.

![Mantenimiento de la directiva de administración de riesgos insider](../media/insider-risk-policy-health.png)

Use la siguiente tabla para obtener más información sobre las recomendaciones y las notificaciones de advertencia y las acciones que se deben realizar para resolver posibles problemas.

|**Mensajes de notificación**|**Plantillas de directiva**|**Causas / Probar esta acción para corregir**|
|:------------------------|:-------------------|:---------------------------|
| La directiva no asigna puntuaciones de riesgo a la actividad | Todas las plantillas de directiva | Es posible que desee revisar el ámbito de la directiva y activar la configuración de eventos para que la directiva pueda asignar puntuaciones de riesgo a la actividad <br><br> 1. Revise los usuarios seleccionados para la directiva. Si tiene pocos usuarios seleccionados, es posible que desee seleccionar usuarios adicionales. <br> 2. Si usa un conector de RRHH, compruebe que el conector de RECURSOS humanos envíe los datos correctos. <br> 3. Si usa una directiva DLP como evento de activación, compruebe la configuración de la directiva DLP para asegurarse de que está configurada para usarse en esta directiva. <br> 4. Para las directivas de infracción de seguridad, revise el estado de evaluación de alertas de Punto de conexión de Microsoft Defender seleccionado en Configuración de riesgos de Insider > detecciones inteligentes. Confirme que el filtro de alerta no es demasiado estrecho. |
| La directiva no ha generado alertas | Todas las plantillas de directiva | Es posible que desee revisar la configuración de la directiva para que analice la puntuación de la actividad que le interesa. <br><br> 1. Confirme que ha seleccionado los indicadores que desea puntuar. Entre más indicadores seleccionados, más actividades tienen asignadas las puntuaciones de riesgo. <br> 2. Revise la personalización del umbral para la directiva. Si los umbrales seleccionados no se alinean con la tolerancia a riesgos de su organización, ajuste las selecciones para que las alertas se crean en función de los umbrales preferidos. <br> 3. Revise los usuarios y grupos seleccionados para la directiva. Confirme que ha seleccionado todos los usuarios y grupos aplicables. <br> 4. Para las directivas de infracción de seguridad, confirme que ha seleccionado el estado del triaje de alertas que desea puntuar para alertas de Microsoft Defender para puntos de conexión en Detecciones inteligentes en la configuración.|
| No se incluye ningún usuario o grupo en esta directiva | Todas las plantillas de directiva | Los usuarios o grupos no están asignados a la directiva. <br><br> Edite la directiva y seleccione usuarios o grupos para la directiva. |
| No se han seleccionado indicadores para esta directiva | Todas las plantillas de directiva | Los indicadores no se han seleccionado para la directiva <br><br> Edite la directiva y seleccione los indicadores de directiva adecuados para la directiva. |
| No se incluyen grupos de usuarios prioritarios en esta directiva | - Pérdidas de datos por usuarios prioritarios <br> - Infracciones de directivas de seguridad por parte de usuarios prioritarios | Los grupos de usuarios prioritarios no están asignados a la directiva. <br><br> Configure los grupos de usuarios prioritarios en la configuración de administración de riesgos de Insider y asigne grupos de usuarios prioritarios a la directiva. |
| No se ha seleccionado ningún evento desencadenante para esta directiva | Todas las plantillas de directiva | Un evento desencadenante no está configurado para la directiva <br><br> Las puntuaciones de riesgo no se asignarán a las actividades del usuario hasta que edite la directiva y seleccione un evento desencadenante. |
| El conector de recursos humanos no está configurado ni funciona como se esperaba | - Robo de datos por parte del usuario que sale <br> - Infracciones de directivas de seguridad por parte del usuario que abandona <br> - Pérdidas de datos de usuarios inconformes <br> - Infracciones de directivas de seguridad por parte de usuarios inconformes | Hay un problema con el conector de RECURSOS humanos. <br><br> 1. Si usa un conector de recursos humanos, compruebe que el conector de RECURSOS humanos está enviando datos correctos <br><br> O <br><br> 2. Seleccione el evento de desencadenamiento eliminado de la cuenta de Azure AD. |
| No hay dispositivos incorporados | - Robo de datos por parte de los usuarios que salen <br> - Pérdidas de datos generales <br> - Pérdidas de datos de usuarios inconformes <br> - Pérdidas de datos por usuarios prioritarios | Los indicadores de dispositivo están seleccionados, pero no hay ningún dispositivo incorporado a Microsoft 365 <br><br> Comprueba si los dispositivos están incorporados y cumplen los requisitos. |
| El conector de RECURSOS no ha cargado datos recientemente | - Robo de datos por parte del usuario que sale <br> - Infracciones de directivas de seguridad por parte del usuario que abandona <br> - Pérdidas de datos de usuarios inconformes <br> - Infracciones de directivas de seguridad por parte de usuarios inconformes | El conector de RECURSOS humanos no ha importado datos en más de 7 días. <br><br> Compruebe que el conector de RECURSOS humanos esté configurado correctamente y envíe datos. |
| No podemos comprobar el estado del conector de RECURSOS humanos en este momento, vuelve a comprobarlo más tarde. | - Robo de datos por parte del usuario que sale <br> - Infracciones de directivas de seguridad por parte del usuario que abandona <br> - Pérdidas de datos de usuarios inconformes <br> - Infracciones de directivas de seguridad por parte de usuarios inconformes | La solución de administración de riesgos insider no puede comprobar el estado del conector de recursos humanos. <br><br> Compruebe que el conector de RECURSOS humanos esté configurado correctamente y envíe datos, o vuelva y compruebe el estado de la directiva.  |
| La directiva DLP no está seleccionada como evento desencadenante | - Pérdidas de datos generales <br> - Pérdidas de datos por usuarios prioritarios | No se ha seleccionado una directiva DLP como evento desencadenante o se ha eliminado la directiva DLP seleccionada. <br><br> Edite la directiva y seleccione una directiva DLP activa o "El usuario realiza una actividad de exfiltración" como evento desencadenante en la configuración de la directiva. |
| La directiva DLP usada en esta directiva está desactivada | - Pérdidas de datos generales <br> - Pérdidas de datos por usuarios prioritarios | La directiva DLP usada en esta directiva está desactivada. <br><br> 1. Active la directiva DLP asignada a esta directiva. <br><br> O <br><br> 2. Edite esta directiva y seleccione una nueva directiva DLP o "El usuario realiza una actividad de exfiltración" como evento desencadenante en la configuración de la directiva. |
| La directiva DLP no cumple los requisitos | - Pérdidas de datos generales <br> - Pérdidas de datos por usuarios prioritarios | Las directivas DLP usadas como eventos desencadenamiento deben configurarse para generar alertas de alta gravedad. <br><br>  1. Edite la directiva DLP para asignar alertas aplicables como *Gravedad alta.* <br><br> O <br><br> 2. Edite esta directiva y seleccione Usuario realiza una actividad *de exfiltración* como evento desencadenante. |
| Su organización no tiene una suscripción de Microsoft Defender para endpoint | - Infracciones de la directiva de seguridad general <br> - Infracciones de directivas de seguridad por parte de los usuarios que salen <br> - Infracciones de directivas de seguridad por parte de usuarios inconformes <br> - Infracciones de directivas de seguridad por parte de usuarios prioritarios | No se detectó una suscripción activa de Microsoft Defender para endpoint para su organización. <br><br> Hasta que no se agregó una suscripción de Microsoft Defender para endpoint, estas directivas no asignarán puntuaciones de riesgo a la actividad del usuario. |
| Las alertas de Microsoft Defenders para puntos de conexión no se comparten con el Centro de cumplimiento | - Infracciones de la directiva de seguridad general <br> - Infracciones de directivas de seguridad por parte de los usuarios que salen <br> - Infracciones de directivas de seguridad por parte de usuarios inconformes <br> - Infracciones de directivas de seguridad por parte de usuarios prioritarios | Las alertas de Microsoft Defender para puntos de conexión no se comparten con el centro de cumplimiento. <br><br> Configurar el uso compartido de alertas de Punto de conexión de Microsoft Defender. |
| Se está acercando al límite máximo de usuarios que se puntuan activamente para esta plantilla de directiva. | Todas las plantillas de directiva | Cada plantilla de directiva tiene un número máximo de usuarios en el ámbito. Consulta los detalles de la sección límite de plantilla. <br><br> Revise los usuarios de la pestaña Usuarios y quite los usuarios que ya no necesiten obtener una puntuación. |

## <a name="policy-template-limits"></a>Límites de plantilla de directiva

Las plantillas de directiva de administración de riesgos de Insider usan límites para administrar el volumen y la velocidad de procesamiento de las actividades de riesgo del usuario en el ámbito y cómo se integra este proceso con la compatibilidad con los servicios de Microsoft 365. Cada plantilla de directiva tiene un número máximo de usuarios a los que se pueden asignar puntuaciones de riesgo activamente para la directiva que pueda admitir y procesar e informar eficazmente de las actividades de riesgo. Los usuarios en el ámbito son usuarios con eventos desencadenados para la directiva.

El límite de cada directiva se calcula en función del número total de usuarios únicos que reciben puntuaciones de riesgo por tipo de plantilla de directiva. Si el número de usuarios de un tipo de plantilla de directiva está cerca o supera el límite de usuario, se reducirá el rendimiento de la directiva. Para ver el número actual de usuarios de una directiva, vaya a la pestaña Directiva y a la columna Usuarios en ámbito. Es posible que tenga hasta cinco directivas para cualquier plantilla de directiva. Estos límites máximos se aplican a los usuarios en todas las directivas mediante una plantilla de directiva determinada.

Use la tabla siguiente para determinar el número máximo de usuarios en el ámbito admitidos para cada plantilla de directiva:

|**Plantilla de directiva**|**Máximo de usuario actual en el ámbito**|
|:------------------|:--------------------------------|
| Pérdida de datos general | 15.000 |
| Pérdida de datos por parte de usuarios inconformes | 7,500 |
| Pérdida de datos por usuarios prioritarios | 1,000 |
| Robo de datos por parte de los usuarios que salen | 20,000 |
| Infracciones de la directiva de seguridad general | 1,000 |
| Infracción de la directiva de seguridad por parte de los usuarios prioritarios | 1,000 |
| Infracciones de directivas de seguridad por parte de los usuarios que salen | 15.000 |
| Infracciones de directivas de seguridad por parte de usuarios inconformes | 7,500 |

## <a name="create-a-new-policy"></a>Crear una nueva directiva

Para crear una nueva directiva de administración de riesgos de **insider,** usará el Asistente para directivas en la solución de administración de riesgos insider en el Centro de cumplimiento de Microsoft 365.

Siga estos pasos para crear una nueva directiva:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. Seleccione **Crear directiva** para abrir el asistente para directivas.
3. En la **página Plantilla de** directiva, elija una categoría de directiva y, a continuación, seleccione la plantilla para la nueva directiva. Estas plantillas están hechas de condiciones e indicadores que definen las actividades de riesgo que desea detectar e investigar. Revise los requisitos previos de la plantilla, desencadenar eventos y actividades detectadas para confirmar que esta plantilla de directiva se ajusta a sus necesidades.

    >[!IMPORTANT]
    >Algunas plantillas de directiva tienen requisitos previos que deben configurarse para que la directiva genere alertas relevantes. Si no ha configurado los requisitos previos de directiva aplicables, consulte **el paso 4** anterior.

4. Seleccione **Siguiente** para continuar.
5. En la **página Nombre y descripción,** complete los siguientes campos:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para la directiva. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional):** escriba una descripción para la directiva.

6. Seleccione **Siguiente** para continuar.
7. En la página Usuarios  y grupos, seleccione  Incluir todos los usuarios y grupos o Incluir usuarios y grupos específicos para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios;  seleccione **Agregar o editar grupos de usuarios prioritarios**. Al seleccionar **Incluir todos los usuarios y** grupos, se buscarán eventos desencadenados para que todos los usuarios y grupos de la organización comiencen a asignar puntuaciones de riesgo para la directiva. Si selecciona **Incluir usuarios y** grupos específicos, puede definir qué usuarios y grupos asignar a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la **página Contenido** para priorizar, puede asignar (si es necesario) los orígenes a priorizar, lo que aumenta la probabilidad de generar una alerta de gravedad alta para estos orígenes. Seleccione una de las siguientes opciones:

    - **Quiero especificar sitios de SharePoint, etiquetas de confidencialidad** o tipos de información confidencial como contenido prioritario. Si selecciona esta opción, se habilitarán las páginas detalladas del asistente para configurar estos canales.
    - **No quiero especificar contenido de** prioridad en este momento (podrá hacerlo después de crear la directiva). Si selecciona esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si seleccionó Quiero especificar sitios de **SharePoint,** etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario en el paso anterior, verá las páginas de detalles de sitios de *SharePoint,* tipos de información confidencial y etiquetas de confidencialidad.  Use estas páginas de detalles para definir sharepoint, tipos de información confidencial y etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta* bancaria de ESTADOS UNIDOS" y *"Número de tarjeta de crédito".*
    - **Etiquetas de confidencialidad:** seleccione Agregar etiqueta **de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*

12. Seleccione **Siguiente** para continuar.
13. En la **página Indicadores** y eventos desencadenantes, verá los indicadores que ha definido como disponibles en la página Indicadores de configuración de riesgo [](insider-risk-management-settings.md#indicators) de **Insider.**  >   Si seleccionó una plantilla de pérdida *de* datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable directiva **DLP** para habilitar los indicadores desencadenantes de la directiva o seleccionar el evento de activación integrado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, deberá seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Activar indicadores** en el asistente o seleccionar indicadores en la página Indicadores de directiva de configuración de administración de riesgos de   >    >   Insider.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración predeterminada del umbral de directiva para estos indicadores, deshabilite los umbrales predeterminados de uso **recomendados** por Microsoft e introduzca los valores de umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* *o Dispositivo,* seleccione los impulsores de puntuación de **riesgo** según corresponda. Los impulsores de puntuación de riesgo solo se aplican a indicadores seleccionados.
    - Si ha seleccionado  una plantilla de directiva Robo de datos  o Pérdida de datos, seleccione uno o varios *métodos* de detección de secuencia y un método de detección de **exfiltración** acumulativa para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la **página Umbrales de** indicador, seleccione la opción para usar umbrales de indicador predeterminados o para especificar umbrales personalizados para indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la **página Revisar,** revise la configuración que ha elegido para la directiva y las sugerencias o advertencias para las selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de directiva o **seleccione Enviar** para crear y activar la directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos insider existente, usará el Asistente para directivas en la solución de administración de riesgos **Insider** en el Centro de cumplimiento de Microsoft 365.

Siga estos pasos para administrar una directiva existente:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. En el panel de directivas, seleccione la directiva que desea administrar.
3. En la página detalles de la directiva, seleccione **Editar directiva**
4. En el asistente para directivas, no puede editar lo siguiente:
    - **Plantilla de directiva:** plantilla usada para definir los tipos de indicadores de riesgo supervisados por la directiva.
    - **Nombre:** el nombre descriptivo de la directiva
5. En la **página Nombre y descripción,** actualice la descripción de la directiva en el **campo** Descripción.
6. Seleccione **Siguiente** para continuar.
7. En la página Usuarios  y grupos, seleccione  Incluir todos los usuarios y grupos o Incluir usuarios y grupos específicos para definir qué usuarios o grupos se incluyen en la directiva, o si ha elegido una plantilla basada en usuarios prioritarios;  seleccione **Agregar o editar grupos de usuarios prioritarios**. Al seleccionar **Incluir todos los usuarios y** grupos, se buscarán eventos desencadenados para que todos los usuarios y grupos de la organización comiencen a asignar puntuaciones de riesgo para la directiva. Si selecciona **Incluir usuarios y** grupos específicos, puede definir qué usuarios y grupos asignar a la directiva.
8. Seleccione **Siguiente** para continuar.
9. En la **página Contenido** para priorizar, puede asignar (si es necesario) los orígenes a priorizar, lo que aumenta la probabilidad de generar una alerta de gravedad alta para estos orígenes. Seleccione una de las siguientes opciones:

    - **Quiero especificar sitios de SharePoint, etiquetas de confidencialidad** o tipos de información confidencial como contenido prioritario. Si selecciona esta opción, se habilitarán las páginas detalladas del asistente para configurar estos canales.
    - **No quiero especificar contenido de** prioridad en este momento (podrá hacerlo después de crear la directiva). Si selecciona esta opción, se omitirán las páginas de detalles del canal en el asistente.

10. Seleccione **Siguiente** para continuar.

11. Si seleccionó Quiero especificar sitios de **SharePoint,** etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario en el paso anterior, verá las páginas de detalles de sitios de *SharePoint,* tipos de información confidencial y etiquetas de confidencialidad.  Use estas páginas de detalles para definir sharepoint, tipos de información confidencial y etiquetas de confidencialidad para priorizar en la directiva.

    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione los sitios de SharePoint a los que tiene acceso y desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta* bancaria de ESTADOS UNIDOS" y *"Número de tarjeta de crédito".*
    - **Etiquetas de confidencialidad:** seleccione Agregar etiqueta **de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*

12. Seleccione **Siguiente** para continuar.
13. En la **página Indicadores** y eventos desencadenantes, verá los indicadores que ha definido como disponibles en la página Indicadores de configuración de riesgo [](insider-risk-management-settings.md#indicators) de **Insider.**  >   Si seleccionó una plantilla de pérdida *de* datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable directiva **DLP** para habilitar los indicadores desencadenantes de la directiva o seleccionar el evento de activación integrado.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, deberá seleccionar los indicadores que desea habilitar para todas las directivas. Puede usar el botón **Activar indicadores** en el asistente o seleccionar indicadores en la página Indicadores de directiva de configuración de administración de riesgos de   >    >   Insider.

    Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración predeterminada del umbral de directiva para estos indicadores, deshabilite los umbrales predeterminados de uso **recomendados** por Microsoft e introduzca los valores de umbral para cada indicador seleccionado.

    - Si ha seleccionado al menos un indicador de *Office* *o Dispositivo,* seleccione los impulsores de puntuación de **riesgo** según corresponda. Los impulsores de puntuación de riesgo solo se aplican a indicadores seleccionados.
    - Si ha seleccionado  una plantilla de directiva Robo de datos  o Pérdida de datos, seleccione uno o varios *métodos* de detección de secuencia y un método de detección de **exfiltración** acumulativa para aplicar a la directiva.

14. Seleccione **Siguiente** para continuar.
15. En la **página Umbrales de** indicador, seleccione la opción para usar umbrales de indicador predeterminados o para especificar umbrales personalizados para indicadores individuales. Para cada indicador, elija el nivel adecuado para generar el nivel deseado de alertas de actividad.
16. Seleccione **Siguiente** para continuar.
17. En la **página Revisar,** revise la configuración que ha elegido para la directiva y las sugerencias o advertencias para las selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de directiva o **seleccione Enviar** para crear y activar la directiva.

## <a name="copy-a-policy"></a>Copiar una directiva

Es posible que deba crear una nueva directiva que sea similar a una directiva existente, pero que necesite solo unos pocos cambios de configuración. En lugar de crear una nueva directiva desde cero, puede copiar una directiva existente y, a continuación, modificar las áreas que deben actualizarse en la nueva directiva.

Siga estos pasos para copiar una directiva existente:

1. En el Centro de cumplimiento de Microsoft 365, vaya a Administración de riesgos de Insider y seleccione la pestaña Directivas.
2. En el panel de directivas, seleccione la directiva que desea copiar.
3. En la página de detalles de la directiva, seleccione Copiar.
4. En el asistente para directivas, asigne un nombre a la nueva directiva y actualice la configuración de la directiva según sea necesario.

## <a name="immediately-start-scoring-user-activity"></a>Iniciar inmediatamente la puntuación de la actividad del usuario

Puede haber escenarios en los que necesite empezar inmediatamente a asignar puntuaciones de riesgo a los usuarios con directivas de riesgo internas fuera del flujo de trabajo de eventos desencadenante de la administración de riesgos insider. Use  Iniciar la actividad  de puntuación para los usuarios en la pestaña Directivas para agregar manualmente un usuario (o usuarios) a una o más directivas de riesgo internas durante un período de tiempo específico, para empezar inmediatamente a asignar puntuaciones de riesgo a su actividad y para omitir el requisito de que un usuario tenga un indicador de activación (como una coincidencia de directiva DLP). También puedes agregar un motivo para agregar el usuario a la directiva, que aparecerá en la escala de tiempo de actividad de los usuarios. Los usuarios agregados manualmente a las  directivas se muestran en el panel Usuarios y las alertas se crean si la actividad cumple los umbrales de alerta de directiva.

Algunos escenarios en los que es posible que desee iniciar inmediatamente la puntuación de actividades de usuario:

- Cuando los usuarios se identifican con problemas de riesgo y desea empezar inmediatamente a asignar puntuaciones de riesgo a su actividad para una o varias de sus directivas
- Cuando hay un incidente que puede requerir que comience inmediatamente a asignar puntuaciones de riesgo a la actividad de los usuarios implicados para una o varias de sus directivas
- Cuando aún no haya configurado el conector de recursos humanos, pero desea empezar a asignar puntuaciones de riesgo a las actividades del usuario para eventos de RECURSOS mediante la carga de un archivo .csv para los usuarios

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios.** Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios  agregados manualmente, vaya  a la pestaña Usuarios y seleccione el usuario en el panel Usuarios y abra la pestaña **Actividad** de usuario en el panel de detalles.

Para iniciar manualmente la actividad de puntuación de los usuarios en una o más directivas de administración de riesgos internas, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. En el panel de directivas, seleccione la directiva o directivas a las que desea agregar usuarios.
3. Seleccione **Iniciar la actividad de puntuación para los usuarios**.
4. En el **campo Motivo del** panel Agregar usuarios a **varias** directivas, agregue un motivo para agregar los usuarios.
5. En el campo This **should last for (choose between 5 and 30 days),** defina el número de días para puntuar la actividad del usuario para la directiva a la que se agregan.
6. Para buscar usuarios en Active Directory, use el **campo Usuario de búsqueda para agregar a directivas.** Escriba el nombre del usuario que desea agregar a las directivas. Seleccione el nombre de usuario y repita para asignar usuarios adicionales a las directivas. La lista de usuarios que ha seleccionado aparece en la sección usuarios del panel Agregar usuarios a varias directivas.
7. Para importar una lista de usuarios para agregar a las directivas, seleccione **Importar** para importar un archivo .csv (valores separados por comas). El archivo debe tener el siguiente formato y debe enumerar los nombres de entidad de seguridad de usuario en el archivo:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Seleccione agregar usuarios a directivas para aceptar los cambios y agregar usuarios a las directivas o seleccione Cancelar para descartar los cambios y cerrar el cuadro de diálogo.

## <a name="stop-scoring-users-in-a-policy"></a>Detener la puntuación de usuarios en una directiva

Para detener la puntuación de usuarios en una directiva, consulte el artículo Usuarios de administración de riesgos de [Insider: Quitar](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies) usuarios de la asignación en el ámbito a directivas.

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva, no se eliminan las alertas activas o archivadas generadas desde la directiva.

Para eliminar una directiva de administración de riesgos insider existente, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. En el panel de directivas, seleccione la directiva que desea eliminar.
3. Seleccione **Eliminar en** la barra de herramientas del panel.
4. En el **cuadro de** diálogo Eliminar, seleccione **Sí** para eliminar la directiva o **seleccione Cancelar** para cerrar el cuadro de diálogo.
