---
title: Directivas de administración de riesgos de Insider
description: Obtenga información sobre las directivas de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 9ff029904a34291f4131f2013ffe30b73aa3233c
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208786"
---
# <a name="insider-risk-management-policies"></a>Directivas de administración de riesgos de Insider

Las directivas de administración de riesgos de Insider determinan qué usuarios están en el ámbito y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de la organización o definir usuarios individuales o grupos para la administración en una directiva. Las directivas admiten las prioridades de contenido para centrarse en las condiciones de la Directiva en varios o distintos equipos de Microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Mediante el uso de plantillas, puede seleccionar indicadores de riesgos específicos y personalizar umbrales de eventos para los indicadores de Directiva, personalizando eficazmente la puntuación de riesgos y el nivel y la frecuencia de las alertas. Además, los aceleradores de puntuación de riesgo y las detecciones de anomalías ayudan a identificar la actividad de usuario que es de mayor importancia o más inusual. Las ventanas de directivas permiten definir el intervalo de tiempo para aplicar la Directiva a las actividades de alerta y se usan para determinar la duración de la Directiva una vez activada.

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

Las plantillas de administración de riesgos de internación son condiciones de directiva predefinidas que definen los tipos de indicadores de riesgo y el modelo de resultados de riesgos que usa la Directiva. Cada Directiva debe tener una plantilla asignada en el Asistente para la creación de directivas antes de que se cree la Directiva. La administración de riesgos de Insider admite hasta cinco directivas para cada plantilla de directiva. Al crear una nueva Directiva de riesgos de Insider con el Asistente para directivas, elija una de las siguientes plantillas de directiva:

### <a name="data-theft-by-departing-users"></a>Robo de datos al pertenecer a los usuarios

Cuando los usuarios dejan la organización, hay indicadores de riesgo específicos que normalmente se asocian con el robo de datos mediante el abandono de los usuarios. Esta plantilla de directiva usa indicadores para la puntuación de riesgos y se centra en la detección y las alertas de este área de riesgos. El robo de datos por parte de los usuarios puede incluir la descarga de archivos de SharePoint Online, la impresión de archivos y la copia de datos en la mensajería en la nube personal y los servicios de almacenamiento cerca de la retirada del empleo y las fechas de finalización. Esta plantilla inicia la puntuación para los indicadores de riesgo relacionados con estas actividades y el modo en que se relacionan con el estado de empleo del usuario.

>[!IMPORTANT]
>Cuando use esta plantilla, debe configurar un conector de Microsoft 365 de RRHH para importar periódicamente la información de fecha de retirada y de finalización para los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.

### <a name="general-data-leaks"></a>Pérdidas de datos generales

La protección de datos y la prevención de pérdidas de datos es un reto constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por los usuarios, dispositivos y servicios. Los usuarios están capacitados para crear, almacenar y compartir información a través de servicios y dispositivos que hacen que la administración de pérdidas de datos sea cada vez más compleja y difícil. Las pérdidas de datos pueden incluir el reuso compartido accidental de información fuera de la organización o el robo de datos con malas intenciones. Junto con una directiva de prevención de pérdida de datos (DLP) asignada, esta plantilla comienza la detección de detecciones en tiempo real de descargas de datos sospechosas de SharePoint Online, el uso compartido de archivos y carpetas, la impresión y la copia de datos en servicios de almacenamiento y mensajería en la nube personal.

Cuando se usa una plantilla de **fugas de datos** , se debe asignar una directiva DLP para desencadenar indicadores en la Directiva de riesgos de Insider para alertas de gravedad alta en la organización. Cuando se agrega una alerta de gravedad alta a un registro de auditoría de Office 365, las directivas de riesgo de Insider creadas con esta plantilla examinan automáticamente la alerta DLP de gravedad alta. Si la alerta contiene un usuario dentro del ámbito definido en la Directiva de riesgos de Insider, la Directiva se procesará como una nueva alerta y se le asignará una gravedad de riesgo de Insider y una puntuación de riesgo. Esta directiva permite evaluar esta alerta en contexto con otras actividades incluidas en el caso.

#### <a name="data-leaks-policy-guidelines"></a>Instrucciones de directiva de pérdidas de datos

Al crear o modificar directivas de DLP para usarlas con directivas de administración de riesgos de Insider, tenga en cuenta las siguientes directrices:

- Priorizar los eventos de exfiltración de datos y ser selectivo al asignar la configuración de **informes de incidentes** a *alta* al configurar reglas en las directivas de DLP. Por ejemplo, el correo electrónico de documentos confidenciales para un competidor conocido debe ser un evento de exfiltración de nivel de alerta *alto* . La sobreasignación del *alto* nivel de la configuración de **informes de incidentes** en otras reglas de directiva de DLP puede aumentar el ruido en el flujo de trabajo de la alerta de administración de riesgos de Insider y dificultar a los investigadores de datos y analistas que evalúen correctamente estas alertas. Por ejemplo, la asignación de niveles de alerta *elevados* para tener acceso a las actividades de denegación en las directivas de DLP hace que sea más difícil evaluar las actividades y el comportamiento de usuario verdaderamente arriesgados.
- Asegúrese de comprender y configurar correctamente los usuarios del ámbito en las directivas de DLP y de administración de riesgos de Insider. Solo los usuarios definidos como en el ámbito de las directivas de administración de riesgos de Insider que usen la plantilla de **fugas de datos** tendrán alertas de directivas de DLP de gravedad alta procesadas. Además, la Directiva de administración de riesgos de Insider examinará los usuarios definidos como en el ámbito de una regla para una alerta DLP de alta gravedad. Es importante que no se configuran innecesariamente los usuarios en el ámbito de las directivas de DLP y de riesgos de Insider en un modo conflictivo.

     Por ejemplo, si las reglas de la Directiva DLP se limitan solo a los usuarios del equipo de ventas y la Directiva de riesgos de Insider creada a partir de la plantilla de **fugas de datos** ha definido todos los usuarios como en el ámbito, la Directiva de riesgos de Insider solo procesará alertas de DLP de gravedad alta para los usuarios del equipo de ventas. La Directiva de riesgos de Insider no recibirá alertas de DLP de prioridad alta que los usuarios puedan procesar y que no estén definidas en las reglas de DLP en este ejemplo. Por el contrario, si la Directiva de administración de riesgos de Insider creada a partir de la plantilla de **pérdidas de datos** se limita a los usuarios del equipo de ventas y la Directiva de DLP asignada está en el ámbito de todos los usuarios, la Directiva de riesgos de Insider solo procesará alertas de DLP de gravedad alta para los miembros del equipo de ventas. La Directiva de administración de riesgos de Insider pasa por alto las alertas de DLP de gravedad alta para todos los usuarios que no estén en el equipo de ventas.

- Asegúrese de que la configuración de la regla de **informes de incidentes** de la Directiva DLP usada para esta plantilla de administración de riesgos de Insider esté configurada para alertas de nivel de gravedad *alto* . El nivel de gravedad *alto* es que los eventos desencadenantes y las alertas de administración de riesgos de Insider no se generarán a partir de las reglas de las directivas de DLP con el campo **informes de incidentes** establecido en *bajo* o *medio*.

    ![Configuración de alerta de la Directiva DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Al crear una nueva Directiva de DLP con las plantillas integradas, debe seleccionar la opción **crear o personalizar reglas de DLP avanzadas** para configurar los informes de **incidentes** para el nivel de gravedad *alta* .

Cada directiva de administración de riesgos de Insider creada a partir de la plantilla de **fugas de datos** solo puede tener asignada una directiva DLP. Considere la posibilidad de crear una directiva de DLP dedicada que combine las distintas actividades que quiera detectar y actúe como desencadenamiento de eventos para las directivas de riesgo de Insider que usan la plantilla de **fugas de datos** .

Consulte el artículo sobre cómo [crear, probar y ajustar una directiva DLP](create-test-tune-dlp-policy.md) para obtener una guía paso a paso sobre la configuración de directivas de DLP para su organización.

### <a name="data-leaks-by-priority-users-preview"></a>Pérdidas de datos por usuarios con prioridad (versión preliminar)

La protección de datos y la prevención de pérdidas de datos para los usuarios de la organización pueden depender de su posición, el nivel de acceso a la información confidencial o el historial de riesgos. Las pérdidas de datos pueden incluir el reuso compartido accidental de información confidencial fuera de la organización o el robo de datos con malas intenciones. Junto con una directiva de prevención de pérdida de datos (DLP) asignada, esta plantilla comienza la detección de detecciones en tiempo real de la actividad sospechosa y da como resultado una mayor probabilidad de alertas y alertas de riesgo de Insider con niveles de gravedad más elevados. Los usuarios con prioridad se definen en [grupos de usuarios prioritarios](insider-risk-management-settings.md#priority-user-groups-preview) configurados en el área de configuración de administración de riesgos de Insider.

Al igual que con la **plantilla de fugas de datos generales**, debe asignar una directiva DLP para desencadenar indicadores en la Directiva de riesgos de Insider para alertas de gravedad alta en la organización. Siga las instrucciones de directiva de pérdidas de datos anteriores al crear una directiva con esta plantilla. Además, tendrá que asignar a la Directiva los grupos de usuarios de prioridad creados en la configuración de **Administración de riesgos de Insider**  >  **Settings**  >  **Priority user groups** .

### <a name="data-leaks-by-disgruntled-users-preview"></a>Pérdidas de datos por usuarios descontentos (versión preliminar)

Cuando los usuarios experimentan un estrés de empleo, pueden ser disgustados, lo que puede aumentar la actividad de riesgo de Insider. Esta plantilla inicia la evaluación de la actividad del usuario cuando se identifica un indicador asociado con disgruntlement. Algunos ejemplos son las notificaciones de mejora de rendimiento, las revisiones de rendimiento deficientes o los cambios en el estado de nivel de trabajo. Las pérdidas de datos para los usuarios descontentos pueden incluir la descarga de archivos desde SharePoint Online y la copia de datos a servicios de almacenamiento en la nube y servicios de almacenamiento cercanos a los eventos Stressor de empleo.

Al usar esta plantilla, también debe configurar un conector de Microsoft 365 para la importación periódica de notificaciones de mejora de rendimiento, estado de revisión de rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.

### <a name="general-security-policy-violations-preview"></a>Infracciones de directivas de seguridad generales (versión preliminar)

En muchas organizaciones, los usuarios tienen permisos para instalar software en sus dispositivos o para modificar la configuración de dispositivo para ayudarle con sus tareas. Por equivocación o con intenciones maliciosas, los usuarios pueden instalar malware o deshabilitar características de seguridad importantes que ayuden a proteger la información de sus dispositivos o de los recursos de red. Esta plantilla de directiva usa alertas de seguridad de la protección contra amenazas avanzada de Microsoft defender (ATP) para empezar a obtener la puntuación de estas actividades y centrar la detección y las alertas en esta área de riesgo. Use esta plantilla para proporcionar información sobre infracciones de directivas de seguridad en escenarios en los que los usuarios pueden tener un historial de infracciones de directivas de seguridad que pueden ser un indicador de riesgo de Insider.

Necesitará tener Microsoft defender ATP configurado en su organización y habilitar ATP de Microsoft defender para la integración de la administración de riesgos de Insider en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Infracciones de la Directiva de seguridad al pertenecer a los usuarios (versión preliminar)

El hecho de que los usuarios dejen de estar en condiciones positivas o negativas puede ser un riesgo mayor para las infracciones de directivas de seguridad. Para ayudar a proteger contra infracciones de seguridad involuntarias o malintencionadas para los usuarios que se desvinculan, esta plantilla de directiva usa alertas de ATP de Microsoft defender para proporcionar información sobre actividades relacionadas con la seguridad. Estas actividades incluyen el usuario que instala malware u otras aplicaciones potencialmente dañinas y la deshabilitación de las características de seguridad en sus dispositivos. Los indicadores de Directiva se activan después de que los usuarios tengan una fecha de retirada o de finalización importada del conector de 365 de RRHH de Microsoft como evento desencadenante.

Cuando use esta plantilla, debe configurar un conector de Microsoft 365 de RRHH para importar periódicamente la información de fecha de retirada y de finalización para los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.

Necesitará tener Microsoft defender ATP configurado en su organización y habilitar ATP de Microsoft defender para la integración de la administración de riesgos de Insider en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Infracciones de directivas de seguridad por usuarios con prioridad (versión preliminar)

La protección contra violaciones de seguridad para los usuarios de la organización puede depender de la posición, el nivel de acceso a la información confidencial o el historial de riesgos. Debido a que las infracciones de seguridad de los usuarios con prioridad pueden tener un impacto muy importante en las áreas críticas de la organización, esta plantilla de directiva inicia la puntuación de estos indicadores y usa alertas de ATP de Microsoft defender para proporcionar información sobre las actividades relacionadas con la seguridad para estos usuarios. Estos pueden incluir los usuarios prioritarios que instalan malware u otras aplicaciones potencialmente dañinas y deshabilitan las características de seguridad en sus dispositivos. Los usuarios con prioridad se definen en grupos de usuarios prioritarios configurados en el área de configuración de administración de riesgos de Insider.

Necesitará tener Microsoft defender ATP configurado en su organización y habilitar ATP de Microsoft defender para la integración de la administración de riesgos de Insider en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Además, tendrá que asignar a la Directiva los grupos de usuarios de prioridad creados en la configuración de **Administración de riesgos de Insider**  >  **Settings**  >  **Priority user groups** .

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Infracciones de directivas de seguridad por usuarios descontentos (versión preliminar)

Los usuarios que experimenten un estrés de empleo pueden tener un mayor riesgo de infracciones de directivas de seguridad involuntarias o involuntarias. Estos incumplimientos pueden incluir el usuario que se coloca en un plan de mejora del rendimiento, el estado de la revisión de rendimiento deficiente o su degradación desde su posición actual. Esta plantilla de directiva inicia la puntuación de riesgos basándose en estos indicadores y actividades asociados con estos eventos para estos usuarios.

Al usar esta plantilla, también debe configurar un conector de Microsoft 365 para la importación periódica de notificaciones de mejora de rendimiento, estado de revisión de rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de la organización. Consulte el artículo [importar datos con el conector de recursos humanos](import-hr-data.md) para obtener una guía paso a paso para configurar el conector de 365 de RRHH de Microsoft para su organización.

También necesitará tener Microsoft defender ATP configurado en su organización y habilitar ATP de Microsoft defender para la integración de la administración de riesgos de Insider en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="offensive-language-in-email"></a>Lenguaje ofensivo en el correo electrónico

>[!IMPORTANT]
>A partir del 16 de octubre de 2020, ya no podrá crear directivas con esta plantilla. Todas las directivas activas que usen esta plantilla funcionarán hasta que se eliminen de forma permanente en el 2021 de enero. Estamos en desuso el clasificador integrado integrado que admite esta plantilla, ya que ha generado un gran número de falsos positivos. Para solucionar los problemas de lenguaje ofensivo, se recomienda usar las directivas de [cumplimiento normativo de comunicaciones](communication-compliance.md) de Microsoft 365. Para obtener más información acerca de los clasificadores integrados, consulte [Getting Started with trainable Classifiers](classifier-get-started-with.md).

La detección y la realización de acciones para evitar el comportamiento ofensivo y abusivo es un componente crítico de evitar el riesgo. Clasificadores integrados en Microsoft 365 analizar los mensajes de correo electrónico enviados desde buzones de Exchange online en su organización para diferentes tipos de problemas de cumplimiento. Estos clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el idioma en el correo electrónico que probablemente infrinja las directivas de Antiacoso. Use esta plantilla para crear rápidamente una directiva que use estos clasificadores para detectar automáticamente el contenido de los mensajes de correo electrónico que puedan considerarse abusivos u ofensivos. La administración de riesgos de Insiders usa clasificadores que exploran mensajes de correo electrónico enviados según los términos del idioma inglés y que se recomiendan en lenguaje ofensivo.

### <a name="policy-template-prerequisites-and-triggering-events"></a>Requisitos previos de la plantilla de directiva y desencadenamiento de eventos

Según la plantilla que elija para una directiva de administración de riesgos de Insider, los eventos de desencadenamiento y los requisitos previos de la Directiva varían. Los eventos desencadenantes son requisitos previos que determinan si un usuario está activo para una directiva de administración de riesgos de Insider. Si se agrega un usuario a una directiva de administración de riesgos de Insider, pero no tiene un evento desencadenador, la actividad del usuario no se evalúa a menos que se agreguen manualmente en el panel usuarios. Los requisitos previos de la Directiva son elementos necesarios para que la Directiva reciba las señales o las actividades necesarias para evaluar el riesgo.

En la tabla siguiente se enumeran los eventos desencadenantes y los requisitos previos de las directivas creadas desde cada plantilla de directiva de administración de riesgos de Insider:

| **Plantilla de directiva** | **Desencadenar eventos para directivas** | **Requisitos previos** |
| :------------------ | :--------------------------------- | :---------------- |
| Robo de datos al pertenecer a los usuarios | Indicador de fecha de retirada o de finalización del conector de RRHH | Conector de Microsoft 365 HR configurado para la terminación y los indicadores de fecha de retirada |
| Pérdidas de datos generales | Actividad de la Directiva de pérdida de datos que crea una alerta de gravedad alta | Directiva DLP configurada para alertas de alta gravedad |
| Pérdidas de datos por usuarios con prioridad | Actividad de la Directiva de pérdida de datos que crea una alerta de gravedad alta | Directiva DLP configurada para alertas de alta gravedad <br><br> Grupos de usuarios con prioridad configurados en configuración de riesgo de Insider |
| Pérdidas de datos por usuarios descontentos | Indicadores de cambio de rendimiento, rendimiento deficiente o cambio de nivel de trabajo del conector de RRHH | Conector de Microsoft 365 HR configurado para indicadores de disgruntlement |
| Infracciones de directivas de seguridad generales | Fraude defensivo de controles de seguridad o software no deseado detectados por ATP de Microsoft defender | Suscripción a ATP activa de Microsoft defender <br><br> Integración de ATP de Microsoft defender con Microsoft 365 Compliance Center configurado |
| Infracciones de directivas de seguridad mediante la desactivación de usuarios | Indicadores de fecha de retirada o de finalización del conector de RRHH | Conector de Microsoft 365 HR configurado para la terminación y los indicadores de fecha de retirada <br><br> Suscripción a ATP activa de Microsoft defender <br><br> Integración de ATP de Microsoft defender con Microsoft 365 Compliance Center configurado |
| Infracciones de directivas de seguridad por usuarios con prioridad | Fraude defensivo de controles de seguridad o software no deseado detectados por ATP de Microsoft defender | Suscripción a ATP activa de Microsoft defender <br><br> Integración de ATP de Microsoft defender con Microsoft 365 Compliance Center configurado <br><br> Grupos de usuarios con prioridad configurados en configuración de riesgo de Insider |
| Violaciones de directivas de seguridad por un usuario descontento | Indicadores de cambio de rendimiento, rendimiento deficiente o cambio de nivel de trabajo del conector de RRHH | Conector de Microsoft 365 HR configurado para indicadores de disgruntlement <br><br> Suscripción a ATP activa de Microsoft defender <br><br> Integración de ATP de Microsoft defender con Microsoft 365 Compliance Center configurado |
| Lenguaje ofensivo en el correo electrónico | Blasfemias, amenazas o lenguaje de acoso en mensajes de correo electrónico | Suscripción a Exchange Online activa |

## <a name="prioritize-content-in-policies"></a>Priorizar el contenido de las directivas

Las directivas de administración de riesgos de Insider admiten la especificación de una prioridad más alta para el contenido en función de dónde se almacenen o de cómo se clasifique. La especificación de contenido como prioridad aumenta la puntuación de riesgo para cualquier actividad asociada, lo que, a su vez, aumenta la posibilidad de generar una alerta de gravedad alta. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o que se haya especificado como prioridad en la Directiva.

Por ejemplo, su organización tiene un sitio dedicado de SharePoint para un proyecto extremadamente confidencial. Las pérdidas de datos para la información en este sitio de SharePoint podrían poner en peligro el proyecto y tendrían un impacto significativo en su éxito. Al establecer la prioridad de este sitio de SharePoint en una directiva de pérdidas de datos, los resultados de las actividades de calificación aumentan automáticamente. Esta priorización aumenta la probabilidad de que estas actividades generen una alerta de riesgo de Insider y eleva el nivel de gravedad de la alerta.

Al crear una directiva de administración de riesgos de Insider en el Asistente para directivas, puede elegir entre las siguientes prioridades:

- **Sitios de SharePoint**: cualquier actividad asociada a todos los tipos de archivo en los sitios de SharePoint definidos tiene asignado un resultado de mayor riesgo. 
- **Tipos de información confidencial**: cualquier actividad asociada con el contenido que contenga [tipos de información confidencial](sensitive-information-type-entity-definitions.md) se le asigna una puntuación de riesgo más alta.
- **Etiquetas de confidencialidad**: se asigna una puntuación de riesgo mayor a cualquier actividad asociada con contenido que tenga una [etiqueta de confidencialidad](sensitivity-labels.md) específica aplicada.

## <a name="create-a-new-policy"></a>Crear una nueva directiva

Para crear una nueva Directiva de administración de riesgos de Insider, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para crear una nueva Directiva:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. Seleccione **crear Directiva** para abrir el Asistente para directivas
3. En la página **nueva Directiva de riesgo de Insider** , complete los campos siguientes:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para la Directiva.
    - **Descripción (opcional)**: escriba una descripción para la Directiva.
    - **Elegir plantilla de directiva (obligatorio)**: Seleccione una de las [plantillas de directiva](insider-risk-management-policies.md#policy-templates) para definir los tipos de indicadores de riesgo que se supervisan mediante la Directiva.

    >[!IMPORTANT]
    >La mayoría de las plantillas de Directiva tienen requisitos previos que deben configurarse para que la Directiva genere alertas relevantes. Si no ha configurado los requisitos previos de directivas aplicables, consulte Introducción [a la administración de riesgos de Insider](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates).

4. Seleccione **siguiente** para continuar.
5. En la página **usuarios** , seleccione **Agregar usuario o grupo** o **Seleccione prioridad de grupos** de usuarios para definir los usuarios o grupos de usuarios con prioridad que se incluyen en la Directiva, en función de la plantilla de directiva que haya seleccionado. Marque la casilla de verificación **todos los usuarios y grupos con correo habilitado** , si procede (si no ha seleccionado una plantilla basada en el usuario con prioridad). Seleccione **siguiente** para continuar.
6. En la página **especificar el contenido que va a priorizar (opcional)** , puede asignar los orígenes para dar prioridad a los resultados de mayor riesgo. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados, o que se haya especificado como prioridad en esta página:
    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar información confidencial escriba** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
7. Seleccione **siguiente** para continuar.
8. En la página **seleccionar indicadores de directiva** , verá los [indicadores](insider-risk-management-settings.md#indicators) que ha definido como disponibles en la página indicadores de **configuración de riesgos de Insider**  >  **Indicators** . Si seleccionó una plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** para habilitar los indicadores desencadenadores de la Directiva. Seleccione los indicadores que desea aplicar a la Directiva. Si prefiere no usar la configuración de umbral de directiva predeterminada para estos indicadores, deshabilite **usar umbrales predeterminados recomendados por Microsoft** y escriba los valores de umbrales para cada indicador seleccionado. Si ha seleccionado al menos un indicador de *dispositivo* o *Oficina* , seleccione los **aceleradores de puntuación de riesgo** según corresponda. Los elevadores de puntuación de riesgo solo se aplican a los indicadores seleccionados.

    >[!IMPORTANT]
    >Si no se pueden seleccionar los indicadores de esta página, deberá seleccionar los indicadores que desea habilitar para todas las directivas en la página indicadores de directiva de configuración de **Administración de riesgos de Insider**  >  **Settings**  >  **Policy indicators** .

9. Seleccione **siguiente** para continuar.
10. En la página **intervalos de tiempo** de la Directiva, verá las condiciones de la ventana de [activación](insider-risk-management-settings.md#policy-timeframes) para la Directiva que se encuentra en la página intervalos de tiempo de la Directiva de configuración de riesgo del **Insider**  >  **Policy timeframes** .
11. Seleccione **siguiente** para continuar.
12. En la página **revisión** , revise la configuración que ha elegido para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para crear y activar la Directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos de Insider existente, use el Asistente para directivas de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365.

Complete los siguientes pasos para administrar una directiva existente:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea administrar.
3. En la página Detalles de la Directiva, seleccione **Editar Directiva** .
4. En el Asistente para directivas, no puede editar los campos siguientes:
    - **Name**: el nombre descriptivo de la Directiva.
    - **Elegir plantilla de directiva**: la plantilla que se usa para definir los tipos de indicadores de riesgo supervisados por la Directiva.
5. Escriba una nueva descripción para la Directiva en el campo **Descripción** . 
6. Seleccione **siguiente** para continuar.
7. En la página **usuarios** , seleccione **Agregar usuario o grupo** o **Seleccione prioridad de grupos** de usuarios para definir los usuarios o grupos de usuarios con prioridad que se incluyen en la Directiva, en función de la plantilla de directiva que haya seleccionado. Marque la casilla de verificación **todos los usuarios y grupos con correo habilitado** , si procede (si no ha seleccionado una plantilla basada en el usuario con prioridad). Seleccione **siguiente** para continuar.
8. En la página **especificar el contenido que va a priorizar (opcional)** , puede asignar los orígenes para dar prioridad a los resultados de mayor riesgo. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados, o que se haya especificado como prioridad en esta página:
    - **Sitios de SharePoint**: seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"Group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de información confidencial**: seleccione **Agregar información confidencial escriba** y seleccione los tipos de confidencialidad que desea priorizar. Por ejemplo, *"número de cuenta bancaria de Estados Unidos"* y *"número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad**: seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"confidencial"* y *"secreto"*.
9. Seleccione **siguiente** para continuar.
10. En la página **seleccionar indicadores de directiva** , verá los [indicadores](insider-risk-management-settings.md#indicators) que ha definido como disponibles en la página indicadores de **configuración de riesgos de Insider**  >  **Indicators** . Si seleccionó una plantilla de *fugas de datos* al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable **Directiva de DLP** para habilitar los indicadores desencadenadores de la Directiva. Seleccione los indicadores que desea aplicar a la Directiva. Si prefiere no usar la configuración de umbral de directiva predeterminada para estos indicadores, deshabilite **usar umbrales predeterminados recomendados por Microsoft** y escriba los valores de umbrales para cada indicador seleccionado. Si ha seleccionado al menos un indicador de *dispositivo* o *Oficina* , seleccione los **aceleradores de puntuación de riesgo** según corresponda. Los elevadores de puntuación de riesgo solo se aplican a los indicadores seleccionados.

    >[!IMPORTANT]
    >Si no se pueden seleccionar los indicadores de esta página, deberá seleccionar los indicadores que desea habilitar para todas las directivas en la página indicadores de directiva de configuración de **Administración de riesgos de Insider**  >  **Settings**  >  **Policy indicators** .

11. Seleccione **siguiente** para continuar.
12. En la página **intervalos de tiempo** de la Directiva, verá las condiciones de la ventana de [activación](insider-risk-management-settings.md#policy-timeframes) para la Directiva que se encuentra en la página intervalos de tiempo de la Directiva de configuración de riesgo del **Insider**  >  **Policy timeframes** .
13. Seleccione **siguiente** para continuar.
14. En la página **revisión** , revise la configuración que ha actualizado para la Directiva. Seleccione **Editar** para cambiar cualquiera de los valores de la Directiva o seleccione **Enviar** para actualizar y activar la Directiva.

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva no se eliminan las alertas activas o archivadas generadas desde la Directiva.

Para eliminar una directiva de administración de riesgos de Insider existente, siga estos pasos:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **directivas** .
2. En el panel de directivas, seleccione la Directiva que desea eliminar.
3. Seleccione **eliminar** en la barra de herramientas del panel.
4. En el cuadro de diálogo **eliminar** , seleccione **sí** para eliminar la Directiva o seleccione **Cancelar** para cerrar el cuadro de diálogo.
