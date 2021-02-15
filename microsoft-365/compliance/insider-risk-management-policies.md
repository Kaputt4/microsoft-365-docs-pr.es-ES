---
title: Directivas de administración de riesgos de Insider
description: Más información sobre las directivas de administración de riesgos internas en Microsoft 365
keywords: Microsoft 365, administración de riesgos interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 9f8424beb7e4a078d14bce755fc399ecd41764d9
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126639"
---
# <a name="insider-risk-management-policies"></a>Directivas de administración de riesgos de Insider

Las directivas de administración de riesgos internas determinan qué usuarios están en el ámbito y qué tipos de indicadores de riesgo están configurados para las alertas. Puede crear rápidamente una directiva que se aplique a todos los usuarios de la organización o definir usuarios o grupos individuales para la administración en una directiva. Las directivas admiten prioridades de contenido para centrar las condiciones de directiva en varios o específicos microsoft Teams, sitios de SharePoint, tipos de confidencialidad de datos y etiquetas de datos. Con las plantillas, puede seleccionar indicadores de riesgo específicos y personalizar los umbrales de eventos para los indicadores de directiva, personalizando eficazmente las puntuaciones de riesgo y el nivel y la frecuencia de las alertas. Además, las puntuaciones de riesgo y las detecciones de anomalías ayudan a identificar la actividad del usuario que es de mayor importancia o más inusual. Las ventanas de directivas te permiten definir el período de tiempo para aplicar la directiva a actividades de alerta y se usan para determinar la duración de la directiva una vez activada.

## <a name="policy-dashboard"></a>Panel de directivas

El **panel directiva** le permite ver rápidamente las directivas de su organización y el estado actual de las alertas asociadas a cada directiva.

- **Nombre de la** directiva: el nombre asignado a la directiva en el asistente para directivas.
- **Alertas activas:** número de alertas activas para cada directiva.
- **Alertas confirmadas:** número total de alertas generadas por casos de la directiva en los últimos 365 días.
- **Acciones realizadas en alertas:** el número total de alertas que se confirmaron o descartaron durante los últimos 365 días.
- **Efectividad de** la directiva: el porcentaje determinado por el total de alertas confirmadas dividido por el total de acciones realizadas en las alertas (que es la suma de las alertas que se confirmaron o descartaron durante el año anterior).
- **Activo:** el estado del caso, *ya sea Sí* o *No*.

![Panel de directivas de administración de riesgos de Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de administración de riesgos de Insider son condiciones de directiva predefinidas que definen los tipos de indicadores de riesgo y el modelo de puntuación de riesgos que usa la directiva. Cada directiva debe tener una plantilla asignada en el Asistente para la creación de directivas antes de crear la directiva. La administración de riesgos de Insider admite hasta cinco directivas para cada plantilla de directiva. Al crear una nueva directiva de riesgo interno con el asistente para directivas, elegirá una de las siguientes plantillas de directiva:

### <a name="data-theft-by-departing-users"></a>Robo de datos al salir de usuarios

Cuando los usuarios abandonan la organización, normalmente hay indicadores de riesgo específicos asociados con el robo de datos al salir de los usuarios. Esta plantilla de directiva usa indicadores para la puntuación de riesgos y centra la detección y las alertas en esta área de riesgo. El robo de datos para los usuarios que se van puede incluir la descarga de archivos de SharePoint Online, la impresión de archivos y la copia de datos en servicios de almacenamiento y mensajería en la nube personales cerca de su renuncia laboral y fechas de finalización. Esta plantilla empieza a puntuar los indicadores de riesgo relacionados con estas actividades y cómo se correlacionan con el estado de empleo del usuario.

>[!IMPORTANT]
>Al usar esta plantilla, debe configurar un conector de Recursos Humanos de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización de los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.

### <a name="general-data-leaks"></a>Pérdidas de datos generales

La protección de datos y la prevención de pérdidas de datos es un desafío constante para la mayoría de las organizaciones, especialmente con el rápido crecimiento de los nuevos datos creados por usuarios, dispositivos y servicios. Los usuarios tienen la capacidad de crear, almacenar y compartir información entre servicios y dispositivos que hacen que la administración de pérdidas de datos sea cada vez más compleja y difícil. Las pérdidas de datos pueden incluir el exceso accidental de información fuera de la organización o el robo de datos con intención malintencionada. Junto con una directiva de prevención de pérdida de datos (DLP) asignada, esta plantilla comienza a puntuar detecciones en tiempo real de descargas de datos sospechosos de SharePoint Online, uso compartido de archivos y carpetas, impresión de archivos y copia de datos en servicios de almacenamiento y mensajería en la nube personales.

Al usar una plantilla de pérdida de datos, debe asignar una directiva DLP para desencadenar indicadores en la directiva de riesgo interno para **alertas** de gravedad alta en su organización. Cada vez que se genera una alerta de gravedad alta mediante una regla de directiva DLP al registro de auditoría de Office 365, las directivas de riesgo interno creadas con esta plantilla examinan automáticamente la alerta DLP de gravedad alta. Si la alerta contiene un usuario en el ámbito definido en la directiva de riesgo interno, la directiva de riesgo de insider la procesa como una alerta nueva y se le asigna una gravedad de riesgo y una puntuación de riesgo de insider. Esta directiva le permite evaluar esta alerta en contexto con otras actividades incluidas en el caso.

#### <a name="data-leaks-policy-guidelines"></a>Directrices de directiva de pérdida de datos

Al crear o modificar directivas DLP para usarlas con directivas de administración de riesgos internas, tenga en cuenta las siguientes directrices:

- Priorice los eventos de exfiltración  de datos y sea selectivo al asignar la configuración de informes de incidentes a *Alta* al configurar reglas en las directivas DLP. Por ejemplo, enviar por correo electrónico documentos confidenciales a una competencia conocida debe ser un *evento* de exfiltración de nivel de alerta alto. La asignación  de un  nivel superior en la configuración de informes de incidentes en otras reglas de directiva DLP puede aumentar el ruido en el flujo de trabajo de alertas de administración de riesgos interno y dificultar que los investigadores y analistas de datos evalúen correctamente estas alertas. Por ejemplo, la asignación de niveles de *alerta* altos para tener acceso a actividades por denegación en directivas DLP hace que sea más difícil evaluar actividades y comportamientos de usuario realmente arriesgados.
- Asegúrese de comprender y configurar correctamente los usuarios del ámbito en las directivas de administración de riesgos de DLP y insider. Solo los usuarios definidos como en el ámbito de las directivas de administración de riesgos internas que usan la plantilla pérdida de datos tendrán **alertas** de directiva DLP de gravedad alta procesadas. Además, solo los usuarios definidos como dentro del ámbito en una regla para una alerta DLP de gravedad alta serán examinados por la directiva de administración de riesgos de Insider para su consideración. Es importante que no configure usuarios en el ámbito, sin saberlo, tanto en las directivas de riesgo DE DLP como en las directivas de riesgo interno de forma conflictiva.

     Por ejemplo, si las reglas de directiva DLP se aplican únicamente a los usuarios del equipo de ventas y la directiva de riesgo interno creada a partir de la plantilla pérdida **de** datos ha definido todos los usuarios como dentro del ámbito, la directiva de riesgo interno solo procesará realmente alertas DLP de gravedad alta para los usuarios del equipo de ventas. La directiva de riesgo interno no recibirá ninguna alerta DLP de prioridad alta para que los usuarios procese que no están definidas en las reglas DLP de este ejemplo. Por el contrario, si la directiva de administración de riesgos interno creada a partir de las plantillas de pérdida de datos se asigna únicamente a los usuarios del equipo de ventas y la directiva DLP asignada está en el ámbito de todos los usuarios, la directiva de riesgo interno solo procesará **alertas** dlp de gravedad alta para los miembros del equipo de ventas. La directiva de administración de riesgos interno omitirá las alertas DLP de gravedad alta para todos los usuarios que no están en el equipo de ventas.

- Asegúrese de que la configuración **de regla de** informes de incidentes en la directiva DLP usada para esta plantilla de administración de riesgos interno esté configurada para alertas de nivel de gravedad alta.  El *nivel* de gravedad alta es el desencadenamiento de eventos y las alertas  de administración de riesgos internas no se generarán a partir de reglas de directivas DLP con el campo Informes de incidentes establecido en *Bajo* o *Medio.*

    ![Configuración de alerta de directiva DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Al crear una nueva directiva DLP con las plantillas integradas, deberá seleccionar la opción  Crear o personalizar  reglas **de DLP** avanzadas para configurar la configuración de informes de incidentes para el nivel de gravedad alta.

Cada directiva de administración de riesgos interno creada a partir de la **plantilla pérdida de** datos solo puede tener asignada una directiva DLP. Considere la posibilidad de crear una directiva DLP dedicada que combine las distintas actividades que desea detectar y actuar como eventos desencadenantes para las directivas de riesgo interno que usan la plantilla **pérdida de** datos.

Consulte el [artículo Crear, probar y](create-test-tune-dlp-policy.md) ajustar una directiva DLP para obtener instrucciones paso a paso para configurar directivas DLP para su organización.

### <a name="data-leaks-by-priority-users-preview"></a>Pérdidas de datos por usuarios prioritarios (versión preliminar)

La protección de datos y la prevención de pérdidas de datos para los usuarios de su organización pueden depender de su posición, nivel de acceso a información confidencial o historial de riesgos. Las pérdidas de datos pueden incluir un exceso accidental de información altamente confidencial fuera de su organización o el robo de datos con intención malintencionada. Junto con una directiva de prevención de pérdida de datos (DLP) asignada, esta plantilla comienza a puntuar detecciones en tiempo real de actividad sospechosa y da lugar a una mayor probabilidad de alertas de riesgo interno y alertas con niveles de gravedad más altos. Los usuarios con prioridad se definen en [grupos de usuarios de prioridad](insider-risk-management-settings.md#priority-user-groups-preview) configurados en el área de configuración de administración de riesgos interno.

Al igual que con la plantilla pérdida de datos general, debe asignar una directiva DLP para activar indicadores en la directiva de riesgo interno para **alertas** de gravedad alta en su organización. Siga las directrices de directiva de pérdida de datos anteriores al crear una directiva con esta plantilla. Además, tendrá que asignar a la directiva grupos de usuarios de prioridad creados en los grupos de usuarios de prioridad de configuración de administración de riesgos de **Insider.**  >    >  

### <a name="data-leaks-by-disgruntled-users-preview"></a>Pérdidas de datos de usuarios descontentos (versión preliminar)

Cuando los usuarios experimentan factores de estrés laborales, es posible que se descontenten, lo que puede aumentar las posibilidades de actividad de riesgo interno. Esta plantilla comienza a puntuar la actividad del usuario cuando se identifica un indicador asociado con el descontento. Algunos ejemplos son las notificaciones de mejora del rendimiento, las revisiones de rendimiento deficientes o los cambios en el estado del nivel de trabajo. Las pérdidas de datos para usuarios descontentos pueden incluir la descarga de archivos de SharePoint Online y la copia de datos en servicios de almacenamiento y mensajería en la nube personales cerca de eventos de estrés laboral.

Al usar esta plantilla, también debe configurar un conector de Recursos Humanos de Microsoft 365 para importar periódicamente notificaciones de mejora del rendimiento, estado de revisión del rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.

### <a name="general-security-policy-violations-preview"></a>Infracciones de directivas de seguridad generales (versión preliminar)

En muchas organizaciones, los usuarios tienen permisos para instalar software en sus dispositivos o modificar la configuración del dispositivo para ayudar con sus tareas. Ya sea de forma involuntaria o con intención malintencionada, los usuarios pueden instalar malware o deshabilitar características de seguridad importantes que ayudan a proteger la información en su dispositivo o en los recursos de red. Esta plantilla de directiva usa alertas de seguridad de Microsoft Defender para Endpoint para empezar a puntuar estas actividades y la detección de foco y alertas en este área de riesgo. Use esta plantilla para proporcionar información sobre infracciones de directivas de seguridad en escenarios en los que los usuarios pueden tener un historial de infracciones de directivas de seguridad que pueden ser un indicador de riesgo interno.

Tendrás que configurar Microsoft Defender para Endpoint en tu organización y habilitar Defender para Endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar características avanzadas [en Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-departing-users-preview"></a>Infracciones de directivas de seguridad al abandonar usuarios (versión preliminar)

La salida de usuarios, ya sea en términos positivos o negativos, puede ser un riesgo mayor para las infracciones de la directiva de seguridad. Para ayudar a protegerse contra infracciones de seguridad inadvertidas o malintencionadas para los usuarios que se marchan, esta plantilla de directiva usa alertas de Defender para puntos de conexión para proporcionar información sobre las actividades relacionadas con la seguridad. Estas actividades incluyen que el usuario instale malware u otras aplicaciones potencialmente dañinas y deshabilite las características de seguridad en sus dispositivos. Los indicadores de directiva se activan después de que los usuarios tengan una fecha de dimisión o finalización importada desde el conector de RECURSOS de Microsoft 365 como evento desencadenante.

Al usar esta plantilla, debe configurar un conector de Recursos Humanos de Microsoft 365 para importar periódicamente la información de fecha de dimisión y finalización de los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.

Tendrás que configurar Microsoft Defender para Endpoint en tu organización y habilitar Defender para Endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar características avanzadas [en Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-priority-users-preview"></a>Infracciones de directivas de seguridad por parte de usuarios prioritarios (versión preliminar)

La protección contra las infracciones de seguridad de los usuarios de su organización puede depender de su posición, nivel de acceso a información confidencial o historial de riesgos. Dado que las infracciones de seguridad por parte de los usuarios prioritarios pueden tener un impacto sobresalido en las áreas críticas de la organización, esta plantilla de directiva empieza a puntuar en estos indicadores y usa Alertas de Microsoft Defender para puntos de conexión para proporcionar información sobre las actividades relacionadas con la seguridad de estos usuarios. Estos pueden incluir los usuarios prioritarios que instalan malware u otras aplicaciones potencialmente dañinas y deshabilitan las características de seguridad en sus dispositivos. Los usuarios con prioridad se definen en grupos de usuarios de prioridad configurados en el área de configuración de administración de riesgos interno.

Tendrás que configurar Microsoft Defender para Endpoint en tu organización y habilitar Defender para Endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar características avanzadas [en Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) Además, tendrá que asignar a la directiva grupos de usuarios de prioridad creados en los grupos de usuarios de prioridad de configuración de administración de riesgos de **Insider.**  >    >  

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Infracciones de directivas de seguridad por parte de usuarios descontentos (versión preliminar)

Los usuarios que experimentan factores de tensión laboral pueden tener un mayor riesgo de infracciones de la directiva de seguridad inadvertida o malintencionada. Estos estresores pueden incluir que el usuario se coloque en un plan de mejora del rendimiento, un estado de revisión de rendimiento deficiente o que se le rebaja de su posición actual. Esta plantilla de directiva inicia la puntuación de riesgos en función de estos indicadores y actividades asociadas a estos eventos para estos usuarios.

Al usar esta plantilla, también debe configurar un conector de Recursos Humanos de Microsoft 365 para importar periódicamente notificaciones de mejora del rendimiento, estado de revisión del rendimiento deficiente o información de cambio de nivel de trabajo para los usuarios de su organización. Consulte el [artículo Importar datos](import-hr-data.md) con el conector de RECURSOS humanos para obtener instrucciones paso a paso para configurar el conector de RRHH de Microsoft 365 para su organización.

También tendrás que configurar Microsoft Defender para Endpoint en tu organización y habilitar Defender for Endpoint para la integración de la administración de riesgos de Insider en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar características avanzadas [en Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="policy-template-prerequisites-and-triggering-events"></a>Requisitos previos de la plantilla de directiva y eventos desencadenantes

Según la plantilla que elija para una directiva de administración de riesgos interno, los eventos desencadenantes y los requisitos previos de la directiva varían. Los eventos desencadenantes son requisitos previos que determinan si un usuario está activo para una directiva de administración de riesgos interno. Si un usuario se agrega a una directiva de administración de riesgos de Insider pero no tiene un evento desencadenante, la directiva no evalúa la actividad del usuario a menos que se agrega manualmente en el panel Usuarios. Los requisitos previos de la directiva son elementos necesarios para que la directiva reciba las señales o actividades necesarias para evaluar el riesgo.

En la siguiente tabla se enumeran los eventos desencadenantes y los requisitos previos para las directivas creadas a partir de cada plantilla de directiva de administración de riesgos internas:

| **Plantilla de directiva** | **Desencadenar eventos para directivas** | **Requisitos previos** |
| :------------------ | :--------------------------------- | :---------------- |
| Robo de datos al salir de usuarios | Indicador de fecha de dimisión o finalización del conector de RECURSOS HUMANOS | Conector de Recursos Humanos de Microsoft 365 configurado para indicadores de fecha de terminación y dimisión |
| Pérdidas de datos generales | Actividad de directiva de pérdida de datos que crea una alerta de gravedad alta | Directiva DLP configurada para alertas de gravedad alta |
| Pérdidas de datos por usuarios prioritarios | Actividad de directiva de pérdida de datos que crea una alerta de gravedad alta | Directiva DLP configurada para alertas de gravedad alta <br><br> Grupos de usuarios de prioridad configurados en la configuración de riesgos interno |
| Pérdidas de datos de usuarios descontentos | Mejora del rendimiento, rendimiento deficiente o indicadores de cambio de nivel de trabajo desde el conector de RECURSOS HUMANOS | Conector de Recursos Humanos de Microsoft 365 configurado para indicadores de descontento |
| Infracciones de la directiva de seguridad general | Fraude de defensa de controles de seguridad o software no deseado detectado por Microsoft Defender para Endpoint | Suscripción de Active Microsoft Defender para puntos de conexión <br><br> Integración de Microsoft Defender para puntos de conexión con el Centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de la directiva de seguridad al abandonar usuarios | Indicadores de fecha de dimisión o finalización del conector de RECURSOS HUMANOS | Conector de Recursos Humanos de Microsoft 365 configurado para indicadores de fecha de terminación y dimisión <br><br> Suscripción de Active Microsoft Defender para puntos de conexión <br><br> Integración de Microsoft Defender para puntos de conexión con el Centro de cumplimiento de Microsoft 365 configurado |
| Infracciones de directivas de seguridad por parte de usuarios prioritarios | Fraude de defensa de controles de seguridad o software no deseado detectado por Microsoft Defender para endpoint | Suscripción de Active Microsoft Defender para puntos de conexión <br><br> Integración de Microsoft Defender para puntos de conexión con el Centro de cumplimiento de Microsoft 365 configurado <br><br> Grupos de usuarios de prioridad configurados en la configuración de riesgos interno |
| Infracciones de la directiva de seguridad por parte de usuarios descontentos | Mejora del rendimiento, rendimiento deficiente o indicadores de cambio de nivel de trabajo desde el conector de RECURSOS HUMANOS | Conector de Recursos Humanos de Microsoft 365 configurado para indicadores de descontento <br><br> Suscripción de Active Microsoft Defender para puntos de conexión <br><br> Integración de Microsoft Defender para puntos de conexión con el Centro de cumplimiento de Microsoft 365 configurado |

## <a name="prioritize-content-in-policies"></a>Priorizar contenido en directivas

Las directivas de administración de riesgos de Insider admiten la especificación de una prioridad más alta para el contenido según dónde se almacene o cómo se clasifique. Especificar contenido como prioridad aumenta la puntuación de riesgo de cualquier actividad asociada, lo que a su vez aumenta la posibilidad de generar una alerta de gravedad alta. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o se haya especificado como prioridad en la directiva.

Por ejemplo, su organización tiene un sitio de SharePoint dedicado para un proyecto extremadamente confidencial. Las pérdidas de datos de información en este sitio de SharePoint podrían poner en peligro el proyecto y tendrían un impacto significativo en su éxito. Al priorizar este sitio de SharePoint en una directiva de pérdida de datos, las puntuaciones de riesgo para las actividades que califiquen se incrementan automáticamente. Esta priorización aumenta la probabilidad de que estas actividades generen una alerta de riesgo interno y aumenta el nivel de gravedad de la alerta.

Al crear una directiva de administración de riesgos interno en el asistente para directivas, puede elegir entre las siguientes prioridades:

- **Sitios de SharePoint:** se asigna una puntuación de riesgo más alta a cualquier actividad asociada con todos los tipos de archivo de los sitios de SharePoint definidos. 
- **Tipos de información confidencial:** se [](sensitive-information-type-entity-definitions.md) asigna una puntuación de riesgo más alta a cualquier actividad asociada con contenido que contenga tipos de información confidencial.
- **Etiquetas de confidencialidad:** se [](sensitivity-labels.md) asigna una puntuación de riesgo más alta a cualquier actividad asociada con contenido al que se apliquen etiquetas de confidencialidad específicas.

## <a name="create-a-new-policy"></a>Crear una nueva directiva

Para crear una nueva directiva de administración de riesgos de **Insider,** usará el asistente para directivas en la solución de administración de riesgos de Insider en el Centro de cumplimiento de Microsoft 365.

Complete los pasos siguientes para crear una nueva directiva:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. Seleccione **Crear directiva** para abrir el asistente para directivas
3. En la **página Nueva directiva de riesgo interno,** complete los siguientes campos:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para la directiva.
    - **Descripción (opcional):** escriba una descripción para la directiva.
    - **Elija la plantilla de directiva (necesaria):** seleccione una de las plantillas de directiva para definir los tipos de indicadores de riesgo que supervisa la directiva. [](insider-risk-management-policies.md#policy-templates)

    >[!IMPORTANT]
    >La mayoría de las plantillas de directiva tienen requisitos previos que deben configurarse para que la directiva genere alertas relevantes. Si no ha configurado los requisitos previos de directiva aplicables, consulte Introducción a la administración de [riesgos de Insider.](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)

4. Seleccione **Siguiente** para continuar.
5. En **la** página  Usuarios, seleccione  Agregar usuario o grupo o Elegir grupos de usuarios prioritarios para definir qué usuarios o grupos de usuarios de prioridad se incluyen en la directiva, en función de la plantilla de directiva que haya seleccionado. Active la casilla Todos los usuarios y grupos **habilitados** para correo si procede (si no ha seleccionado una plantilla basada en usuarios de prioridad). Seleccione **Siguiente** para continuar.
6. En la **página Especificar qué contenido se debe priorizar (opcional),** puede asignar los orígenes para priorizar para obtener puntuaciones de riesgo más altas. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o se haya especificado como prioridad en esta página:
    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta bancaria de* ESTADOS UNIDOS" y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad:** seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*
7. Seleccione **Siguiente** para continuar.
8. En la **página Seleccionar** indicadores de [](insider-risk-management-settings.md#indicators) directiva, verás los indicadores que has definido como disponibles en la página Indicadores de configuración de riesgo de **Insider.**  >   Si seleccionó una *plantilla de* pérdida de datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable de directivas **DLP** para habilitar los indicadores desencadenantes de la directiva. Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración de umbral de directiva predeterminada para estos indicadores, deshabilite los umbrales de uso predeterminados **recomendados** por Microsoft y escriba los valores de umbral para cada indicador seleccionado. Si ha seleccionado al menos un indicador de *Office* *o dispositivo,* seleccione los indicadores de puntuación de **riesgo** según corresponda. Los indicadores de puntuación de riesgo solo se aplican a los indicadores seleccionados.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, tendrás que seleccionar los indicadores que quieras habilitar para todas las directivas en la página indicadores de directiva de configuración de administración de riesgos de **Insider.**  >    >  

9. Seleccione **Siguiente** para continuar.
10. En la **página Períodos de** tiempo [](insider-risk-management-settings.md#policy-timeframes) de directiva, verás las condiciones de la ventana de activación de la directiva que se encuentra en la página Períodos de tiempo de la directiva de configuración de riesgos de **Insider.**  >  
11. Seleccione **Siguiente** para continuar.
12. En la **página** Revisar, revisa la configuración que has elegido para la directiva. Selecciona **Editar** para cambiar cualquiera de los valores de directiva o **selecciona** Enviar para crear y activar la directiva.

## <a name="update-a-policy"></a>Actualizar una directiva

Para actualizar una directiva de administración de riesgos interno existente, usará el Asistente para directivas en la solución de administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365.

Siga estos pasos para administrar una directiva existente:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. En el panel de directivas, seleccione la directiva que desea administrar.
3. En la página de detalles de la directiva, seleccione **Editar directiva**
4. En el Asistente para directivas, no puede editar los campos siguientes:
    - **Nombre:** nombre descriptivo de la directiva
    - **Elegir plantilla de** directiva: la plantilla que se usa para definir los tipos de indicadores de riesgo supervisados por la directiva.
5. Escriba una nueva descripción para la directiva en el **campo** Descripción. 
6. Seleccione **Siguiente** para continuar.
7. En **la** página  Usuarios, seleccione  Agregar usuario o grupo o Elegir grupos de usuarios prioritarios para definir qué usuarios o grupos de usuarios de prioridad se incluyen en la directiva, en función de la plantilla de directiva que haya seleccionado. Active la casilla Todos los usuarios y grupos **habilitados** para correo si procede (si no ha seleccionado una plantilla basada en usuarios de prioridad). Seleccione **Siguiente** para continuar.
8. En la **página Especificar qué contenido se debe priorizar (opcional),** puede asignar los orígenes para priorizar para obtener puntuaciones de riesgo más altas. Sin embargo, algunas actividades no generarán ninguna alerta a menos que el contenido relacionado contenga tipos de información confidencial integrados o personalizados o se haya especificado como prioridad en esta página:
    - **Sitios de SharePoint:** seleccione **Agregar sitio de SharePoint** y seleccione las organizaciones de SharePoint que desea priorizar. Por ejemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de información confidencial:** selecciona **Agregar tipo de información confidencial** y selecciona los tipos de confidencialidad que quieres priorizar. Por ejemplo, *"Número de cuenta bancaria de* ESTADOS UNIDOS" y *"Número de tarjeta de crédito"*.
    - **Etiquetas de confidencialidad:** seleccione **Agregar etiqueta de confidencialidad** y seleccione las etiquetas que desea priorizar. Por ejemplo, *"Confidencial"* y *"Secreto".*
9. Seleccione **Siguiente** para continuar.
10. En la **página Seleccionar** indicadores de [](insider-risk-management-settings.md#indicators) directiva, verás los indicadores que has definido como disponibles en la página Indicadores de configuración de riesgo de **Insider.**  >   Si seleccionó una *plantilla de* pérdida de datos al principio del asistente, debe seleccionar una directiva DLP en la lista desplegable de directivas **DLP** para habilitar los indicadores desencadenantes de la directiva. Seleccione los indicadores que desea aplicar a la directiva. Si prefiere no usar la configuración de umbral de directiva predeterminada para estos indicadores, deshabilite los umbrales de uso predeterminados **recomendados** por Microsoft y escriba los valores de umbral para cada indicador seleccionado. Si ha seleccionado al menos un indicador de *Office* *o dispositivo,* seleccione los indicadores de puntuación de **riesgo** según corresponda. Los indicadores de puntuación de riesgo solo se aplican a los indicadores seleccionados.

    >[!IMPORTANT]
    >Si los indicadores de esta página no se pueden seleccionar, tendrás que seleccionar los indicadores que quieras habilitar para todas las directivas en la página indicadores de directiva de configuración de administración de riesgos de **Insider.**  >    >  

11. Seleccione **Siguiente** para continuar.
12. En la **página Períodos de** tiempo [](insider-risk-management-settings.md#policy-timeframes) de directiva, verás las condiciones de la ventana de activación de la directiva que se encuentra en la página Períodos de tiempo de la directiva de configuración de riesgos de **Insider.**  >  
13. Seleccione **Siguiente** para continuar.
14. En la **página** Revisar, revise la configuración que ha actualizado para la directiva. Selecciona **Editar** para cambiar cualquiera de los valores de directiva o **selecciona** Enviar para actualizar y activar la directiva.

## <a name="delete-a-policy"></a>Eliminar una directiva

>[!NOTE]
>Al eliminar una directiva, no se eliminan las alertas activas o archivadas generadas desde la directiva.

Para eliminar una directiva de administración de riesgos interno existente, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione la **pestaña** Directivas.
2. En el panel de directivas, seleccione la directiva que desea eliminar.
3. Seleccione **Eliminar en la** barra de herramientas del panel.
4. En el **cuadro de** diálogo Eliminar, seleccione **Sí** para eliminar la directiva o **cancele** para cerrar el cuadro de diálogo.
