---
title: Configuración de administración de riesgos de Insider
description: Obtenga información sobre la configuración de administración de riesgos de Insider en Microsoft 365
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
ms.openlocfilehash: 8c56b7b597ea76c74412f49afa896a0d2f1b69a1
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214909"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introducción a la configuración de administración de riesgos de Insider

La configuración de la administración de riesgos de Insider se aplica a todas las directivas de administración de riesgos de Insider, independientemente de la plantilla que elija al crear una directiva. La configuración se configura con el control de **configuración de riesgos de Insider** ubicado en la parte superior de todas las pestañas de administración de riesgos de Insider. Esta configuración controla los componentes de directiva para las siguientes áreas:

- Privacidad
- Indicadores
- Escalas de tiempo de Directiva
- Detecciones inteligentes
- Exportar alertas (versión preliminar)
- Grupos de usuarios con prioridad (versión preliminar)
- Activos de prioridad física (versión preliminar)
- Flujos de automatización de la potencia (versión preliminar)
- Microsoft Teams (versión preliminar)

Antes de empezar y crear directivas de administración de riesgos de Insider, es importante comprender esta configuración y elegir los niveles de configuración mejor para las necesidades de cumplimiento de la organización.

## <a name="privacy"></a>Privacidad

La protección de la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en la investigación de datos y análisis de revisiones de alertas de riesgo de Insider. Para los usuarios con una directiva de riesgo de Insider coinciden, puede elegir una de las siguientes opciones:

- **Mostrar anonimizan versiones de**nombres de usuario: los nombres de los usuarios se anonimizan para evitar que los administradores, investigadores de datos y revisores vean quiénes están asociados con las alertas de directiva. Por ejemplo, un usuario de "el período de gracia de Taylor" aparecería con un Pseudonym aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de administración de riesgos de Insider. La elección de esta opción anonymizes todos los usuarios con coincidencias de directivas actuales y pasadas y se aplica a todas las directivas. Cuando se selecciona esta opción, la información de Perfil de usuario en la alerta de riesgo de Insider y los detalles de casos no estarán disponibles. Sin embargo, los nombres de usuario se muestran cuando se agregan nuevos usuarios a directivas existentes o cuando se asignan usuarios a nuevas directivas. Si decide desactivar esta opción, los nombres de usuario se mostrarán para todos los usuarios que tengan coincidencias de directivas actuales o pasadas.
- **No mostrar anonimizan versiones de nombres de usuario**: los nombres de usuario se muestran en todas las coincidencias de directivas actuales y pasadas para alertas y casos. La información del perfil de usuario (el nombre, el cargo, el alias y la organización o departamento) se muestra al usuario para todos los casos y alertas de administración de riesgos del Insider.

![Configuración de privacidad de administración de riesgos de Insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Plantillas de directivas de riesgos de Insider definen el tipo de actividades de riesgo que desea detectar e investigar. Cada plantilla de Directiva se basa en indicadores específicos que corresponden a desencadenadores y actividades de riesgos específicos. Todos los indicadores están deshabilitados de forma predeterminada y debe seleccionar uno o más indicadores de Directiva antes de configurar una directiva de administración de riesgos de Insider.

Las directivas desencadenan alertas cuando los usuarios realizan actividades relacionadas con los indicadores de directiva que cumplen un umbral requerido. La administración de riesgos de Insiders usa dos tipos de indicadores:

- **Desencadenar eventos**: eventos que determinan si un usuario está activo para una directiva de administración de riesgos de Insider. Si se agrega un usuario a una directiva de administración de riesgos de Insider, no se produce un evento desencadenante, la Directiva no evalúa la actividad del usuario. Por ejemplo, el usuario A se agrega a una directiva creada a partir de la plantilla de directiva de los *usuarios que inician el robo de datos* y la Directiva y el conector de 365 de RRHH de Microsoft están configurados correctamente. Hasta que el usuario A tiene una fecha de finalización notificada por el conector de recursos humanos, esta directiva de administración de riesgos de Insider no evalúa las actividades del usuario A. Otro ejemplo de un evento desencadenante es si un usuario tiene una alerta de directiva DLP de gravedad *alta* al usar directivas de *pérdida de datos* .
- **Indicadores de directiva**: indicadores incluidos en las directivas de administración de riesgos de Insider usadas para determinar una puntuación de riesgo para un usuario dentro del ámbito. Estos indicadores de directiva solo se activan después de que se produzca un evento desencadenador para un usuario. Algunos ejemplos de indicadores de Directiva son cuando un usuario copia datos en servicios de almacenamiento en la nube personal o dispositivos de almacenamiento portátil, o si un usuario comparte archivos y carpetas internos con partes externas no autorizadas.

Los indicadores de Directiva se segmentan en las siguientes áreas. Puede elegir los indicadores para activar y personalizar los límites de eventos de indicador para cada nivel de indicador al crear una directiva de riesgos de Insider:

- **Indicadores de Office**: incluyen indicadores de directiva para los sitios de SharePoint, los equipos y la mensajería de correo electrónico.
- **Indicadores de dispositivo**: Estos incluyen indicadores de directiva para actividades como compartir archivos a través de la red o con dispositivos. Los indicadores incluyen actividades relacionadas con los archivos de Microsoft Office. Archivos CSV y. Archivos PDF. Si seleccionas **indicadores de dispositivo**, la actividad solo se procesa para dispositivos con Windows 10 compilación 1809 o posterior. Para obtener más información sobre la configuración de dispositivos para la integración con riesgos de Insider, vea [Getting Started with Endpoint DLP](endpoint-dlp-getting-started.md).
- **Indicador de infracción**de la Directiva de seguridad: incluyen indicadores de ATP de Microsoft defender relacionados con la instalación de software no aprobado o malintencionado o la omisión de controles de seguridad. Para recibir alertas en la administración de riesgos de Insiders, debe tener habilitada una licencia de ATP de Microsoft defender activa y una integración de riesgos de Insider. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Elevadores de puntuación de riesgo**: incluyen la elevación de la puntuación de riesgo para actividades inusuales o infracciones de directivas pasadas. La habilitación de los elevadores de puntuación de riesgo aumenta los resultados de los riesgos y la probabilidad de que se presenten alertas para estos tipos de actividades. Los elevadores de puntuación de riesgo solo se pueden seleccionar si uno o más de los indicadores anteriores están seleccionados.

![Configuración del indicador de administración de riesgos de Insider](../media/insider-risk-settings-indicators.png)

En algunos casos, es posible que quiera limitar los indicadores de directiva de riesgos de Insider que se aplican a las directivas de riesgo de Insider de su organización. Puede desactivar los indicadores de directiva para áreas específicas al deshabilitarlas de todas las directivas de riesgo de Insider. Los eventos desencadenantes no se pueden modificar para las plantillas de directiva de riesgos de Insider.

Para definir los indicadores de directiva de riesgos de Insider que están habilitados en todas las directivas de riesgo de Insider, vaya a indicadores de **configuración de riesgos**de Insider  >  **Indicators** y seleccione uno o más indicadores de directiva. Los indicadores seleccionados en la página de configuración de indicadores no se pueden configurar individualmente al crear o editar una directiva de riesgos del Insider en el Asistente para directivas.

>[!NOTE]
>Puede tardar varias horas en aparecer nuevos usuarios agregados manualmente en el **Panel de usuarios**. Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el **Panel de usuarios** y abra la ficha **actividad de usuario** en el panel de detalles.

### <a name="indicator-level-settings-preview"></a>Configuración de nivel de indicador (versión preliminar)

Al crear una directiva en el Asistente para directivas, puede configurar la forma en que el número diario de eventos de riesgo debe influir en la puntuación de riesgo de las alertas de riesgo de Insider. Estas opciones de indicador le ayudan a controlar cómo el número de repeticiones de eventos de riesgo de su organización debe afectar a la puntuación del riesgo y, por lo tanto, a la gravedad de la alerta asociada para estos eventos. Si lo prefiere, también puede mantener los niveles predeterminados de umbral de eventos recomendados por Microsoft para todos los indicadores habilitados.

Por ejemplo, decide habilitar los indicadores de SharePoint en la configuración de la Directiva de riesgos de Insider y establecer umbrales personalizados para eventos de SharePoint al configurar indicadores para una nueva Directiva de *pérdidas de datos* de riesgo de Insider. En el Asistente para directivas de riesgos de Insider, se configuran tres niveles de eventos diarios distintos para cada indicador de SharePoint para influir en la puntuación de riesgo para las alertas asociadas con estos eventos.

![Configuración de indicador personalizado de administración de riesgos de Insider](../media/insider-risk-custom-indicators.png)

Para el primer nivel de eventos diarios, establezca el umbral en *10 o más eventos por día* para una menor repercusión en la puntuación de riesgo para los eventos, *20 o más eventos por* día para un impacto medio en la puntuación de riesgo para los eventos, y *30 o más eventos por día* de mayor impacto en la puntuación de riesgo para los eventos. Esta configuración significa realmente:

- Si hay 1-9 eventos de SharePoint que tienen lugar después de desencadenar el evento, los resultados de los riesgos se ven afectados de forma mínima y no generar una alerta.
- Si hay 10-19 eventos de SharePoint que se producen después de un evento de desencadenamiento, la puntuación de riesgo es intrínsecamente baja y los niveles de gravedad de alerta tienden a estar en un nivel bajo.
- Si hay 20-29 eventos de SharePoint que se producen después de un desencadenamiento, la puntuación de riesgo es intrínsecamente superior y los niveles de gravedad de alerta tienden a ser de nivel medio.
- Si hay 30 o más eventos de SharePoint que se producen después de un desencadenamiento, la puntuación de riesgo es intrínsecamente superior y los niveles de gravedad de alerta tienden a ser de un nivel alto.

## <a name="policy-timeframes"></a>Plazos de la Directiva

Los plazos de la Directiva permiten definir períodos de revisión pasados y futuros que se desencadenan después de las coincidencias de directivas basadas en eventos y actividades para las plantillas de directiva de administración de riesgos de Insider. Según la plantilla de directiva que elija, estarán disponibles los siguientes intervalos de tiempo de la Directiva:

- **Ventana activación**: disponible para todas las plantillas de Directiva, la *ventana de activación* es el número de días definido que la ventana activa **después** de un evento desencadenante. La ventana se activa durante 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido la *ventana de activación* en 30 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa la *ventana de activación* y la Directiva está activa para ese usuario durante 30 días después de que se haya producido el evento desencadenante.
- **Detección de actividad pasada**: disponible para todas las plantillas de Directiva, la *detección de actividad anterior* es el número de días definidos que la ventana activa **antes** de un evento desencadenante. La ventana se activa de 0 a 180 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la Directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido la *detección de actividad pasada* en 90 días. Transcurridos varios meses desde la configuración de la Directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la Directiva. El evento desencadenador activa la *detección de actividad pasada* y la Directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.

![Configuración de tiempo de administración de riesgos de Insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecciones inteligentes

La configuración de detección inteligente ayuda a refinar cómo se procesan las detecciones de actividades de riesgo para las alertas. En determinadas circunstancias, es posible que necesite definir tipos de archivo para omitir o desea aplicar un nivel de detección para los archivos a fin de definir una barra mínima para las alertas. Al usar directivas de lenguaje ofensivo, es posible que deba aumentar o disminuir la sensibilidad de la detección para controlar la cantidad de coincidencias de directivas de informes. Use estas opciones para controlar el volumen general de alertas, las exclusiones de los tipos de archivo, los límites del volumen de archivos y la sensibilidad de la detección de idiomas ofensivos.

![Configuración de detecciones inteligentes de administración de riesgos de Insider](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>Detecciones de anomalías

Las detecciones anómalas incluyen la configuración de las exclusiones de tipo de archivo y los límites del volumen de archivo.

- **Exclusiones de tipo de archivo**: para excluir tipos de archivo específicos de toda la coincidencia de directivas de administración de riesgos de Insider, escriba extensiones de tipo de archivo separadas por comas. Por ejemplo, para excluir determinados tipos de archivos de música de las coincidencias de directivas, puede escribir *AAC, MP3, WAV, WMA* en el campo **exclusiones de tipo de archivo** . Todas las directivas de administración de riesgos de Insider omitirán los archivos con estas extensiones.
- **Límite de volumen de archivo desactivado**: para definir un nivel de archivo mínimo antes de notificar las alertas de actividad en las directivas de riesgo de Insider, escriba el número de archivos. Por ejemplo, escribiría ' 10 ' si no desea generar alertas de riesgo de Insider cuando un usuario descarga 10 archivos o menos, incluso si las directivas consideran que esta actividad es una anomalía.

### <a name="offensive-language-detections"></a>Detecciones de idiomas ofensivos

>[!IMPORTANT]
>A partir del 16 de octubre de 2020, ya no podrá crear directivas con esta plantilla. Todas las directivas activas que usen esta plantilla funcionarán hasta que se eliminen de forma permanente en el 2021 de enero. Estamos en desuso el clasificador integrado integrado que admite esta plantilla, ya que ha generado un gran número de falsos positivos. Para solucionar los problemas de lenguaje ofensivo, se recomienda usar las directivas de [cumplimiento normativo de comunicaciones](communication-compliance.md) de Microsoft 365. Para obtener más información acerca de los clasificadores integrados, consulte [Getting Started with trainable Classifiers](classifier-get-started-with.md).

Para ajustar la confidencialidad del clasificador de idioma ofensivo para las directivas que usan el *idioma ofensivo en* la plantilla de correo electrónico, elija una de las siguientes opciones:

- **Bajo**: el nivel de confidencialidad más bajo con el intervalo más amplio para la detección de un idioma y una opinión ofensivos. La probabilidad de falsos positivos para la coincidencia de idiomas ofensivos es elevada.
- **Media**: el nivel de confidencialidad de nivel medio con un intervalo equilibrado para la sumisión y el lenguaje ofensivo de detección. La probabilidad de falsos positivos para la coincidencia de lenguaje ofensivo es la media.
- **Alta**: el nivel de confidencialidad más alto con un intervalo estrecho para la detección de lenguaje ofensivo y su opinión. La probabilidad de falsos positivos para la coincidencia de lenguaje ofensivo es baja.

### <a name="alert-volume"></a>Volumen de alertas

Las actividades de usuario detectadas por las directivas de riesgo de Insider tienen asignada una puntuación de riesgo específica, que a su vez determina la gravedad de la alerta (baja, media, alta). De forma predeterminada, se generará una determinada cantidad de alertas de gravedad baja, media y alta, pero puede aumentar o disminuir el volumen según sus necesidades. Para ajustar el volumen de alertas de todas las directivas de administración de riesgos de Insider, elija una de las siguientes opciones:

- **Menos alertas**: verá todas las alertas de gravedad alta, menos alertas de mediana gravedad y no hay gravedad baja. Este nivel de configuración significa que podría omitir algunos verdaderos positivos.
- **Volumen predeterminado**: verá todas las alertas de gravedad alta y una cantidad equilibrada de alertas de gravedad media y baja.
- **Más alertas**: verá todas las alertas de gravedad media y alta y la mayoría de las alertas de gravedad baja. Este nivel de configuración puede tener como resultado más falsos positivos.

### <a name="microsoft-defender-advanced-threat-protection-preview"></a>Protección contra amenazas avanzada de Microsoft defender (vista previa)

La [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (ATP) es una plataforma de seguridad de extremos corporativos diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de la infracción de seguridad en su organización, puede importar y filtrar las alertas de ATP de Microsoft defender para actividades usadas en directivas creadas a partir de plantillas de directivas de infracción de seguridad de administración de riesgos de Insider.

En función de los tipos de señales que le interesen, puede optar por importar las alertas a la administración de riesgos de Insider en función del estado de clasificación de alertas de ATP de Microsoft defender. Puede definir uno o más de los siguientes Estados de clasificación de alertas en la configuración global que se va a importar:

- Unknown
- Nuevo
- En curso
- Resuelto

Las alertas de Microsoft defender ATP se importan diariamente. Según el estado de clasificación que elija, es posible que vea varias actividades de usuario para la misma alerta que los cambios de estado de clasificación en ATP de Microsoft defender.

Por ejemplo, si selecciona *nuevo*, *en curso*y *resuelto* para esta configuración, cuando se genera una alerta de ATP de Microsoft defender y el estado es *nuevo*, se importa una actividad de alerta inicial para el usuario en riesgo de Insider. Cuando el estado de clasificación de ATP de Microsoft defender cambia a *en curso*, se importa una segunda actividad para esta alerta para el usuario en riesgo de Insider. Una vez que se ha establecido el estado de clasificación de la evaluación de ATP de Microsoft defender *, se importa* una tercera actividad para esta alerta para el usuario en riesgo de Insider. Esta funcionalidad permite a los investigadores seguir la progresión de las alertas de ATP de Microsoft defender y elegir el nivel de visibilidad que requiere la investigación.

>[!IMPORTANT]
>Necesitará tener Microsoft defender ATP configurado en su organización y habilitar ATP de Microsoft defender para la integración de la administración de riesgos de Insider en el centro de seguridad de defender para importar las alertas de infracción de seguridad. Para obtener más información sobre cómo configurar ATP de Microsoft defender para la integración de la administración de riesgos de Insider, vea [Configure Advanced Features in Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains-preview"></a>Dominios (versión preliminar)

La configuración de dominio ayuda a definir los niveles de riesgo para las comunicaciones a dominios específicos. Estas comunicaciones incluyen el uso compartido de archivos, mensajes de correo electrónico o la descarga de contenido. Al especificar dominios en esta configuración, puede aumentar o disminuir la puntuación de riesgos para la actividad que se realiza con estos dominios. Por ejemplo, para especificar contoso.com y sales.wingtiptoys.com como dominios permitidos, escribirá "contoso.com sales.wingtiptoys.com" en el campo **dominios permitidos** .

Para cada una de las siguientes opciones de dominio, puede introducir hasta 500 dominios:

- **Dominios no permitidos:** Al especificar dominios no permitidos, la actividad que tiene lugar con estos dominios tendrá una puntuación de riesgo *mayor* .
- **Dominios permitidos:** Al especificar dominios permitidos en la configuración, la actividad que se realiza con estos dominios tendrá una *menor* puntuación de riesgos y se tratará de forma similar a cómo se trata la actividad de la organización interna. Por ejemplo, las actividades de correo electrónico en estos dominios se analizan de forma similar a cómo se analiza la actividad de correo electrónico interna.
- **Dominios de terceros:** Los dominios de terceros son dominios que se usan con fines empresariales en la organización y el contenido confidencial se puede almacenar en estas ubicaciones. Al especificar un dominio de terceros, puede recibir alertas para cualquier actividad arriesgada en estos dominios.

## <a name="export-alerts-preview"></a>Exportar alertas (versión preliminar)

La información de alerta de administración de riesgos de Insider es exportable a los servicios de administración de eventos e información de seguridad (SIEM) a través del [esquema de API de actividad de administración 365 de Office](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema). Puede usar las API de actividad de administración de Office 365 para exportar información de alertas a otras aplicaciones que su organización puede usar para administrar o agregar información de riesgos de Insider.

Para usar las API para revisar la información de alertas de los riesgos de Insider:

1. Habilitar la API de actividad de administración 365 de Office en la exportación de configuración de **Administración de riesgos de Insider**  >  **Settings**  >  **Export**. De forma predeterminada, esta opción está deshabilitada para la organización de Microsoft 365.
2. Filtrar las actividades de auditoría comunes de Office 365 por *SecurityComplianceAlerts*.
3. Filtrar *SecurityComplianceAlerts* por la categoría *InsiderRiskManagement* .

![Configuración de alertas de exportación de administración de riesgos de Insider](../media/insider-risk-settings-export.png)

La información de alerta contiene información del esquema de alerta de seguridad y cumplimiento y del esquema común de la API de actividad de administración de Office 365.

Los siguientes campos y valores se exportan para las alertas de administración de riesgos de Insider para el esquema de alerta de cumplimiento de & de seguridad:

| **Parámetro de alerta** | **Descripción** |
|:------------------|:----------------|
| AlertType | El tipo de la alerta es *personalizado*.  |
| AlertId | GUID de la alerta. Las alertas de administración de riesgos de Insider son mutables. Cuando el estado de alerta cambia, se genera un nuevo registro con el mismo AlertID. Esta AlertID se puede usar para correlacionar las actualizaciones de una alerta. |
| Categoría | La categoría de la alerta es *InsiderRiskManagement*. Esta categoría puede usarse para distinguir estas alertas de otras alertas de seguridad & cumplimiento. |
| Comentarios | Comentarios predeterminados para la alerta. Los valores son *alertas nuevas* (registradas cuando se crea una alerta) y *alertas actualizadas* (registradas cuando hay una actualización de una alerta). Use AlertID para correlacionar las actualizaciones de una alerta. |
| Datos | Los datos de la alerta incluyen el identificador de usuario único, el nombre principal de usuario y la fecha y hora (UTC) cuando el usuario se desencadenó en una directiva. |
| Nombre | Nombre de la Directiva para la Directiva de administración de riesgos de Insider que generó la alerta. |
| PolicyId | El GUID de la Directiva de administración de riesgos de Insider que activó la alerta. |
| Severity | La gravedad de la alerta. Los valores son *alta*, *media*o *baja*. |
| Origen | Origen de la alerta. El valor es *Office 365 Security & Compliance*. |
| Estado | El estado de la alerta. Los valores *están activos* (*necesita revisión* en el riesgo de Insider), la *investigación* (*confirmada* en el riesgo de Insider), *resuelto* (*resuelto* en el riesgo de Insider), *despedido* (se*descarta* en el riesgo de Insider). |
| Versión | La versión del esquema de alertas de seguridad y cumplimiento. |

Los siguientes campos y valores se exportan para las alertas de administración de riesgos de Insider del [esquema común de la API de actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema).

- UserId
- Id
- RecordType
- CreationTime
- Operación
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuarios con prioridad (versión preliminar)

Los usuarios de la organización pueden tener distintos niveles de riesgo en función de su posición, el nivel de acceso a la información confidencial o el historial de riesgos. La priorización del examen y la puntuación de las actividades de estos usuarios puede ayudar a alertarle de posibles riesgos que puedan tener consecuencias más altas para la organización. Los grupos de usuarios con prioridad en la ayuda de administración de riesgos de Insider definen los usuarios de la organización que necesitan una inspección más estrecha y una puntuación de riesgo más confidencial. Junto con las *infracciones de directivas de seguridad por los usuarios prioritarios* y las *pérdidas de datos por prioridad* de las plantillas de Directiva, los usuarios agregados a un grupo de usuarios con prioridad aumentan las probabilidades de alertas de riesgo de Insider y alertas con niveles de gravedad más elevados.

![Prioridad de administración de riesgos de Insider configuración de grupo de usuarios](../media/insider-risk-settings-priority-users.png)

Por ejemplo, debe protegerse contra pérdidas de datos para un proyecto extremadamente confidencial en el que los usuarios tienen acceso a información confidencial. Elija crear *usuarios* de *proyecto confidenciales* grupo de usuarios con prioridad para los usuarios de su organización que trabajen en este proyecto. Mediante el Asistente para directivas y la plantilla de directiva de *pérdidas de datos por usuarios prioritarios* , se crea una nueva Directiva y se asigna el grupo de prioridad usuarios de *proyecto confidencial* a la Directiva. Actividades examinadas por la Directiva para miembros del grupo de usuarios con prioridad *confidencial los usuarios de Project* es más sensible al riesgo y las actividades de estos usuarios serán más probables que generen una alerta y que tengan alertas con niveles de gravedad más elevados.

### <a name="create-a-priority-user-group"></a>Crear un grupo de usuarios con prioridad

Para crear un nuevo grupo de usuarios con prioridad, use los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365. Para crear un grupo de usuarios con prioridad, debe ser miembro del grupo de roles de *Administración de riesgos de Insiders* o administradores de administración de riesgos de *Insider* .

Complete los pasos siguientes para crear un grupo de usuarios con prioridad:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**.
2. Seleccione la ficha **grupos de usuarios con prioridad**
3. En la ficha **grupos de usuarios con prioridad** , seleccione **Crear grupo de usuarios con prioridad** para iniciar el Asistente para la creación de grupos.
4. En la página **definir grupo** , complete los campos siguientes:
    - **Nombre (obligatorio)**: escriba un nombre descriptivo para el grupo de usuarios con prioridad. No puede cambiar el nombre del grupo de usuarios de prioridad después de completar el asistente.
    - **Descripción (opcional)**: escriba una descripción para el grupo de usuarios con prioridad.
5. Seleccione **siguiente** para continuar.
6. En la página **elegir miembros** , seleccione **elegir miembros** para buscar y seleccione las cuentas de usuario habilitadas para correo que se incluirán en el grupo o seleccione la casilla **seleccionar todo** para agregar todos los usuarios de la organización al grupo. Seleccione **Agregar** para continuar o **Cancelar** para cerrar sin agregar ningún usuario al grupo.
7. Seleccione **siguiente** para continuar.
8. En la página **revisión** , revise la configuración que ha elegido para el grupo de usuarios de prioridad. Seleccione **Editar** para cambiar cualquiera de los valores de grupo o seleccione **Enviar** para crear y activar el grupo de usuarios con prioridad.
9. En la página Confirmación, seleccione **listo** para salir del asistente.

### <a name="update-a-priority-user-group"></a>Actualizar un grupo de usuarios con prioridad

Para actualizar un grupo de usuarios con prioridad existente, debe usar los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365. Para actualizar un grupo de usuarios con prioridad, debe ser miembro del grupo de roles de *Administración de riesgos de Insiders* o administradores de administración de riesgos de *Insider* .

Complete los pasos siguientes para editar un grupo de usuarios con prioridad:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**.
2. Seleccione la ficha **grupos de usuarios con prioridad**
3. Seleccione el grupo de usuarios con prioridad que desea editar y seleccione **Editar Grupo**.
4. En la página **definir grupo** , actualice el campo Descripción si es necesario. No puede actualizar el nombre del grupo de usuarios de prioridad. Seleccione **siguiente** para continuar.
5. En la página **elegir miembros** , agregue nuevos miembros al grupo mediante el control **elegir miembros** . Para quitar un usuario del grupo, seleccione la "X" junto al usuario que desea quitar. Seleccione **siguiente** para continuar.
6. En la página **revisión** , revise la configuración de actualización que ha elegido para el grupo de usuarios de prioridad. Seleccione **Editar** para cambiar cualquiera de los valores de grupo o seleccione **Enviar** para actualizar el grupo de usuarios con prioridad.
7. En la página Confirmación, seleccione **listo** para salir del asistente.

### <a name="delete-a-priority-user-group"></a>Eliminar un grupo de usuarios con prioridad

Para eliminar un grupo de usuarios con prioridad existente, debe usar los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365. Para eliminar un grupo de usuarios con prioridad, debe ser miembro del grupo de roles de *Administración de riesgos de Insiders* o administradores de administración de riesgos de *Insider* .

>[!IMPORTANT]
>Eliminar un grupo de usuarios con prioridad lo quitará de cualquier directiva activa a la que esté asignado. Si elimina un grupo de usuarios con prioridad asignado a una Directiva activa, la Directiva no contendrá ningún usuario dentro del ámbito y, de hecho, estará inactiva y no creará alertas.

Complete los siguientes pasos para eliminar un grupo de usuarios con prioridad:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**.
2. Seleccione la ficha **grupos de usuarios con prioridad**
3. Seleccione el grupo de usuarios con prioridad que desea editar y seleccione **eliminar** en el menú del panel.
4. En el cuadro de diálogo **eliminar** , seleccione **sí** para eliminar el grupo de prioridad de usuario o seleccione **Cancelar** para volver al panel.

## <a name="priority-physical-assets-preview"></a>Activos de prioridad física (versión preliminar)

Identificar el acceso a los activos físicos prioritarios y correlacionar la actividad de acceso a los eventos de usuario es un componente importante de la infraestructura de cumplimiento. Estos activos físicos representan ubicaciones de prioridad en su organización, como edificios de empresas, centros de datos o salas de servidores. Las actividades de riesgo de Insider pueden asociarse con los usuarios que trabajan en horas inusuales, intentar obtener acceso a estas áreas seguras o confidenciales no autorizadas, y solicitudes de acceso a áreas de alto nivel sin necesidades legítimas.

Con la prioridad de activos físicos habilitada y el [conector de datos físico distintivos](import-physical-badging-data.md) configurado, la administración de riesgos de Insider integra las señales de su control físico y accede a los sistemas con otras actividades de riesgo de los usuarios. Mediante el examen de patrones de comportamiento en sistemas de acceso físico y la correlación de estas actividades con otros eventos de riesgo de Insider, la administración de riesgos de Insider puede ayudar a los investigadores y a los analistas de cumplimiento a tomar decisiones de respuesta para las alertas. El acceso a los activos físicos prioritarios se puntúa y se identifica de manera diferente que el acceso a los activos sin prioridad.

Por ejemplo, su organización tiene un sistema distintivos para los usuarios que supervisa y aprueba el acceso físico a las áreas de proyecto confidenciales y de trabajo normal. Tiene varios usuarios trabajando en un proyecto confidencial y estos usuarios volverán a otras áreas de la organización cuando se complete el proyecto. A medida que el proyecto confidencial se acerque a su finalización, querrá asegurarse de que el trabajo del proyecto permanece confidencial y que el acceso a las áreas del proyecto está muy controlado.

Elija Habilitar el conector de datos físico distintivos en Microsoft 365 para importar la información de acceso desde el sistema de distintivos físico y especificar los activos con prioridad en la administración de riesgos de Insider. Al importar información de su sistema de distintivos y correlacionar la información de acceso físico con otras actividades de riesgo identificadas en la administración de riesgos de Insider, observa que uno de los usuarios del proyecto tiene acceso a las oficinas de proyecto después del horario de trabajo normal y que también está exportando grandes cantidades de datos a un servicio de almacenamiento en la nube de trabajo normal. Esta actividad de acceso físico asociada con la actividad en línea puede apuntar a posibles investigadores y analistas de cumplimiento y analistas pueden tomar las medidas oportunas según las circunstancias de este usuario.

### <a name="configure-priority-physical-assets"></a>Configurar los activos físicos con prioridad

Para configurar los activos físicos con prioridad, debe configurar el conector de distintivos físico y usar los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365. Para configurar los activos físicos con prioridad, debe ser miembro del grupo de roles de *Administración de riesgos de Insiders* o administradores de administración de riesgos de *Insider*.

Complete los pasos siguientes para configurar los activos físicos con prioridad:

1. Siga los pasos de configuración de la administración de riesgos de Insider en el artículo [Introducción a la administración de riesgos de Insider](insider-risk-management-configure.md) . En el paso 3, asegúrese de configurar el conector de distintivos físico.

    >[!IMPORTANT]
    >Para que las directivas de administración de riesgos de Insider puedan usar y correlacionar datos de señal relacionados con los usuarios que se desponen y finalizan con datos de eventos de las plataformas de acceso y control físico, también debe configurar el conector de 365 de RRHH de Microsoft. Si habilita el conector de distintivos físico sin habilitar el conector de 365 de h de Microsoft, las directivas de administración de riesgos de Insider solo procesarán eventos de actividades de acceso físico para los usuarios de su organización.

2. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de internación**  >  **prioridad de activos físicos**.
3. En la página **activos con prioridad** , puede Agregar manualmente los identificadores de activos físicos que desea supervisar para los eventos de activos importados por el conector de distintivos físico o importar un. Archivo CSV de todos los identificadores de activos físicos importados por el conector distintivos físico: a) para agregar manualmente identificadores de activos físicos, elija **Agregar activos físicos con prioridad**, especifique un identificador de activo físico y, a continuación, seleccione **Agregar**. Especifique otros identificadores de activos físicos y, a continuación, seleccione **Agregar activos físicos con prioridad** para guardar todos los activos especificados.
    b) para agregar una lista de identificadores de activos físicos desde un. Archivo CSV, elija **importar activos físicos con prioridad**. En el cuadro de diálogo explorador de archivos, seleccione. Archivo CSV que desea importar y, a continuación, seleccione **abrir**. Los identificadores de activos físicos del. Los archivos CSV se agregan a la lista.
4. Vaya a la ficha **indicadores de directiva** en configuración.
5. En la página **indicadores de directiva** , vaya a la sección indicadores de **acceso físico** y active la casilla de **acceso físico tras la finalización o error de acceso al activo confidencial**.
6. Seleccione **Guardar** para configurar y salir.

### <a name="delete-a-priority-physical-asset"></a>Eliminación de un activo físico con prioridad

Para eliminar un activo físico con prioridad existente, debe usar los controles de configuración de la solución de administración de riesgos de Insider en el centro de cumplimiento de Microsoft 365. Para eliminar un activo físico con prioridad, debe ser miembro del grupo de roles de administración de riesgos de Insider o de administrador de administración de riesgos de Insider.

>[!IMPORTANT]
>La eliminación de un activo físico con prioridad quita el examen de cualquier directiva activa a la que se incluyó anteriormente. Las alertas generadas por actividades asociadas con el activo físico de prioridad no se eliminan.

Complete los siguientes pasos para eliminar un activo físico con prioridad:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de internación**  >  **prioridad de activos físicos**.
2. En la página **activos físicos con prioridad** , seleccione el recurso que desea eliminar.
3. Seleccione **eliminar** en el menú Acción para eliminar el recurso.

## <a name="power-automate-flows-preview"></a>Flujos de automatización de la potencia (versión preliminar)

[Microsoft Power Automate](https://docs.microsoft.com/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza acciones en aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas con estas aplicaciones y servicios. Cuando habilita los flujos de alimentación automatizada para la administración de riesgos de Insider, puede automatizar tareas importantes para casos y usuarios. Puede configurar los flujos de alimentación automatizada para recuperar información de usuarios, alertas y casos, y compartir esta información con las partes interesadas y otras aplicaciones, así como automatizar acciones en la administración de riesgos de Insider, como la publicación en notas de mayúsculas o minúsculas. Los flujos de alimentación automatizada se aplican a los casos y a los usuarios del ámbito de una directiva.

Los clientes con suscripciones de Microsoft 365 que incluyen la administración de riesgos de Insider no necesitan otras licencias de Power automatizada para usar las plantillas recomendadas de administración de riesgos de Insider. Estas plantillas se pueden personalizar para apoyar a su organización y cubrir los principales escenarios de administración de riesgos de Insider. Si decide usar las características de automatizar la alimentación avanzada en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use las plantillas de Power automatizada para otras áreas de cumplimiento en Microsoft 365, es posible que necesite otras licencias de Power automatizada.

Las siguientes plantillas de automatización se proporcionan a los clientes para que admitan la automatización de procesos para usuarios y casos de la administración de riesgos de Insider:

- **Notificar a los usuarios cuando se agregan a una directiva de riesgos de Insider**: esta plantilla es para organizaciones que tienen requisitos de directivas, privacidad o normativas internas que los usuarios deben recibir una notificación cuando están sujetos a las directivas de administración de riesgos de Insider. Cuando este flujo está configurado y seleccionado para un usuario de la página usuarios, a los usuarios y a sus administradores se les envía un mensaje de correo electrónico cuando el usuario se agrega a una directiva de administración de riesgos de Insider. Esta plantilla también admite la actualización de una lista de SharePoint hospedada en un sitio de SharePoint para ayudar a hacer un seguimiento de los detalles de los mensajes de notificación, como la fecha y la hora y el destinatario del mensaje. La automatización de la alimentación los flujos con esta plantilla están disponibles en el **Panel de usuarios**.
- **Solicitar información de recursos humanos o empresas sobre un usuario en un caso de riesgo de Insider**: cuando actúe en un caso, es posible que los analistas e investigadores de riesgos para Insiders tengan que consultar con recursos humanos u otras partes interesadas para comprender el contexto de las actividades de caso. Cuando este flujo está configurado y seleccionado para un caso, los analistas e investigadores envían un mensaje de correo electrónico a las partes interesadas de RRHH y empresas configuradas para este flujo. A cada destinatario se le envía un mensaje con opciones de respuesta preconfiguradas o personalizables. Cuando los destinatarios seleccionan una opción de respuesta, la respuesta se registra como una nota de caso e incluye la información de destinatarios y fecha y hora. La automatización de la alimentación los flujos con esta plantilla están disponibles en el **Panel casos**.
- **Notificar al administrador cuando un usuario tiene una alerta de riesgo de Insider**: es posible que algunas organizaciones necesiten una notificación de administración inmediata cuando un usuario tiene una alerta de administración de riesgos de Insider. Cuando se configura y se selecciona este flujo, se envía un mensaje de correo electrónico al administrador del caso al usuario con la siguiente información acerca de todas las alertas de casos: 
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

    El flujo actualiza automáticamente las notas de mayúsculas y minúsculas en las que se envió el mensaje y se activó el flujo. La automatización de la alimentación los flujos con esta plantilla están disponibles en el **Panel casos**.

- **Agregar aviso de calendario para realizar un seguimiento de un caso de riesgo de Insider**: esta plantilla permite a los investigadores y analistas de riesgos agregar recordatorios de calendario para los casos a su calendario de Office 365 Outlook. Este flujo elimina la necesidad de que los usuarios salgan o cambien del flujo de trabajo de administración de riesgos de Insider al procesar los casos y las alertas de clasificación. Cuando este flujo está configurado y seleccionado, se agrega un aviso al calendario de Office 365 Outlook para el usuario que ejecuta el flujo. La automatización de la alimentación los flujos con esta plantilla están disponibles en el **Panel casos**.

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Crear un flujo de automatización de potencia desde la plantilla de administración de riesgos de Insider

Para crear un flujo de automatización de potencia desde una plantilla de administración de riesgos de Insider recomendada, use los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365 o la opción **administrar flujos de automatización de energía** del control **automatizar** cuando trabaje directamente en los paneles de **casos** o **usuarios**.

Para crear un flujo de autoconsumo en el área de configuración, debe ser miembro del grupo de roles *Administración de riesgos de Insider* o administrador de administración de riesgos de *Insider* . Para crear un flujo de automatización de potencia con la opción **administrar flujos de automatización eléctrica** , debe pertenecer al menos a un grupo de roles de administración de riesgos de la Insider.

Complete los pasos siguientes para crear un flujo de automatización de eficacia desde una plantilla de administración de riesgos de Insider recomendada:

1. En el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**para la  >  **automatización de flujos de energía**. También puede acceder a desde las páginas **casos** o **usuarios de paneles** eligiendo **automatizar**  >  **administrar flujos de alimentación automatizada**.
2. En la página **flujos de automatización eléctrica** , seleccione una plantilla recomendada de las **plantillas de administración de riesgos** de localizador a las que se refiere la sección de la página.
3. El flujo enumera las conexiones incrustadas necesarias para el flujo y observará si los Estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestren como disponibles. Seleccione **continuar**.
4. De forma predeterminada, los flujos recomendados están preconfigurados con los campos de datos de servicio de Microsoft 365 recomendados de administración de riesgos de Insider recomendados para completar la tarea asignada al flujo. Si es necesario, Personalice los componentes de flujo mediante el control **Mostrar opciones avanzadas** y configurando las propiedades disponibles para el componente de flujo.
5. Si es necesario, agregue pasos adicionales al flujo seleccionando el botón **nuevo paso** . En la mayoría de los casos, esto no debería ser necesario para las plantillas predeterminadas recomendadas.
6. Seleccione **Guardar borrador** para guardar el flujo para más configuraciones o seleccione **Guardar** para completar la configuración del flujo.
7. Seleccione **cerrar** para volver a la página **flujo de energía automatizada** . La nueva plantilla se mostrará como un flujo en las fichas **Mis flujos** y estará disponible automáticamente en el control desplegable **automatizar** al trabajar con casos de administración de riesgos de Insider para el usuario que crea el flujo.

>[!IMPORTANT]
>Si otros usuarios de su organización necesitan tener acceso al flujo, el flujo debe compartirse.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Crear un flujo de automatización de energía personalizada para la administración de riesgos de Insider

Algunos procesos y flujos de trabajo de su organización pueden estar fuera de las plantillas de flujo de administración de riesgos de Insider recomendadas y es posible que tenga que crear flujos de alimentación automatizada personalizados para áreas de administración de riesgos de Insider. Los flujos de automatización de la potencia son flexibles y admiten una amplia personalización, pero hay pasos que deben realizarse para integrarse con las características de administración de riesgos de Insider.

Complete los siguientes pasos para crear una plantilla de Power automatizada personalizada para la administración de riesgos de Insider:

1. **Consulte su licencia de flujo de automatización de energía**: para crear flujos de alimentación automatizada personalizados que usan desencadenadores de administración de riesgos de Insider, necesitará una licencia de automatización de la potencia. Las plantillas de flujo de administración de riesgos de Insider recomendadas no requieren licencias adicionales y se incluyen como parte de la licencia de administración de riesgos de Insider.
2. **Cree un flujo automatizado**: cree un flujo que realice una o varias tareas después de que se desencadene por un evento de administración de riesgos de Insider. Para obtener más información sobre cómo crear un flujo automatizado, consulte [Create a Flow with Power automaticing](https://docs.microsoft.com/power-automate/get-started-logic-flow).
3. **Seleccione el conector de cumplimiento de microsoft 365**: Busque y seleccione el conector de cumplimiento de Microsoft 365. Este conector habilita las acciones y los desencadenadores de administración de riesgos de Insider. Para obtener más información acerca de los conectores, consulte el artículo de [información general de referencia de conector](https://docs.microsoft.com/connectors/connector-reference/) .
4. **Elija los desencadenadores de administración de riesgos de Insider para su flujo: la**administración de riesgos de Insider tiene dos desencadenadores disponibles para flujos de alimentación automatizada personalizados:
    - **Para un caso de administración de riesgos de Insider seleccionado**: los flujos con este desencadenador se pueden seleccionar en la página de panel de escenarios de administración de riesgos de Insider.
    - **Para un usuario seleccionado de la administración de riesgos de Insider**: los flujos con este desencadenador se pueden seleccionar en la página del panel de usuarios de administración de riesgos de Insider.
5. Elija las acciones de administración de riesgos de Insider para su flujo: puede elegir entre varias acciones de administración de riesgos de Insider para incluirla en el flujo personalizado:
    - Obtener alerta de administración de riesgos de Insider
    - Obtener caso de administración de riesgos de Insider
    - Obtener usuario de administración de riesgos de Insider
    - Obtener alertas de administración de riesgos de Insider para un caso
    - Agregar Nota del caso de administración de riesgos de Insider

### <a name="share-a-power-automate-flow"></a>Compartir un flujo de automatización de la alimentación

De forma predeterminada, los flujos de automatización creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de administración de riesgos de Insider puedan tener acceso y usar un flujo, el flujo debe compartirse con el creador del flujo. Para compartir un flujo, use los controles de configuración de la **solución de administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365 o la opción **administrar flujos de automatización de energía** del control automatizar cuando trabaje directamente en las páginas de panel de **usuarios** o **casos** . Una vez que haya compartido un flujo, todos los usuarios con los que se haya compartido pueden tener acceso al flujo **en el cuadro** desplegable de control automatizar en los paneles **caso** y **usuario**.

Para compartir un flujo de autoconsumo en el área de configuración, debe ser miembro del grupo de roles *Administración de riesgos de Insider* o administrador de administración de riesgos de *Insider* . Para compartir un flujo de automatización automatizada con la opción **administrar flujos de alimentación automatizada** , debe ser miembro de al menos un grupo de roles de administración de riesgos de Insider.

Complete los pasos siguientes para compartir un flujo de automatización de la alimentación:

1. En el [centro de cumplimiento de Microsoft 365](htttps://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**para la  >  **automatización de flujos de energía**. También puede acceder a desde las páginas **casos** o **usuarios de paneles** eligiendo **automatizar**  >  **administrar flujos de alimentación automatizada**.
2. En la página **flujos de automatización eléctrica** , seleccione la pestaña **Mis flujos** o **flujos de equipo** .
3. Seleccione el flujo que desea compartir y, a continuación, seleccione **compartir** en el menú opciones de flujo.
4. En la página uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
5. En el cuadro de diálogo **conexión utilizada** , seleccione **Aceptar** para confirmar que el flujo de usuario o grupo agregado tendrá acceso total al flujo.

### <a name="edit-a-power-automate-flow"></a>Edición de un flujo de automatización de la alimentación

Para editar un flujo, use los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365 o la opción **administrar flujos de alimentación automatizada** desde el control **automatizado** cuando trabaja directamente en los **paneles de usuarios**o **casos** .

Para editar un flujo de automatización de energía en el área configuración, debe ser miembro del grupo de roles *Administración de riesgos de Insider* o administrador de administración de riesgos de *Insider* . Para editar un flujo de automatización automatizada con la opción **administrar flujos de alimentación automatizada** , debe ser miembro de al menos un grupo de roles de administración de riesgos de Insider.

Complete los pasos siguientes para editar un flujo de automatización de consumo:

1. En el [centro de cumplimiento de Microsoft 365](htttps://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**para la  >  **automatización de flujos de energía**. También puede acceder a desde las páginas **casos** o **usuarios de paneles** eligiendo **automatizar**  >  **administrar flujos de alimentación automatizada**.
2. En la página **flujos de automatización eléctrica** , seleccione un flujo para editarlo y seleccione **Editar** en el menú de control de flujo.
3. Seleccione la configuración de **puntos suspensivos**  >  **Settings** para cambiar una configuración del componente de flujo o **puntos suspensivos**  >  **Delete** para eliminar un componente de flujo.
4. Seleccione **Guardar** y, a continuación, **cerrar** para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo de automatización de alimentación

Para eliminar un flujo, use los controles de configuración de la solución de **Administración de riesgos de Insider** en el centro de cumplimiento de Microsoft 365 o la opción **administrar flujos de alimentación automatizada** desde el control **automatizado** cuando trabaja directamente en los **paneles de usuarios**o **casos** . Cuando se elimina un flujo, se quita como una opción para todos los usuarios.

Para eliminar un flujo de automatización de alimentación en el área configuración, debe ser miembro del grupo de roles *Administración de riesgos de Insider* o *Administrador de administración de riesgos de Insider* . Para eliminar un flujo de automatización de alimentación con la opción **administrar flujos de alimentación automatizada** , debe ser miembro de al menos un grupo de roles de administración de riesgos de Insider.

Complete los pasos siguientes para eliminar un flujo de automatización de la alimentación:

1. En el [centro de cumplimiento de Microsoft 365](htttps://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **configuración de riesgos de Insider**para la  >  **automatización de flujos de energía**. También puede acceder a desde las páginas **casos** o **usuarios de paneles** eligiendo **automatizar**  >  **administrar flujos de alimentación automatizada**.
2. En la página **flujos de automatización eléctrica** , seleccione un flujo para eliminar y seleccione **eliminar** en el menú de control de flujo.
3. En el cuadro de diálogo de confirmación de eliminación, seleccione **eliminar** para quitar el flujo o seleccione **Cancelar** para salir de la acción de eliminación.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (versión preliminar)

Los analistas de cumplimiento e investigadores pueden usar fácilmente Microsoft Teams para colaborar en casos de administración de riesgos de Insider. Pueden coordinar y comunicarse con otras partes interesadas en Microsoft Teams para:

- Coordinar y revisar actividades de respuesta para casos en canales de equipos privados
- Compartir y almacenar de forma segura archivos y pruebas relacionados con casos individuales
- Seguimiento y revisión de las actividades de respuesta por parte de analistas e investigadores

Una vez que Microsoft Teams está habilitado para la administración de riesgos de Insider, se crea un equipo dedicado de Microsoft Teams cada vez que se confirma una alerta y se crea un caso. De forma predeterminada, el equipo incluye automáticamente a todos los miembros de los grupos de funciones de *Administración de riesgos*de Insider, *analistas de administración*de riesgos de Insider y investigadores de administración de riesgos de *insider* (hasta 100 usuarios iniciales). Se pueden agregar colaboradores de organización adicionales al equipo después de su creación y según corresponda. Para los casos existentes creados antes de la habilitación de Microsoft Teams, los analistas e investigadores pueden optar por crear un nuevo equipo de Microsoft Teams al trabajar en un caso si es necesario.  Una vez que se resuelve el caso asociado en la administración de riesgos de Insider, el equipo se archiva automáticamente (se mueve a oculto y de solo lectura).

Para obtener más información sobre cómo usar equipos y canales en Microsoft Teams, vea [información general sobre los equipos y canales en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview).

La habilitación de la compatibilidad con Microsoft Teams para casos es rápida y fácil de configurar. Para habilitar Microsoft Teams para la administración de riesgos de Insider, siga los pasos que se indican a continuación:

1. En el [centro de cumplimiento de Microsoft 365](htttps://compliance.microsoft.com), vaya a configuración de riesgos de Insider de **Administración de riesgos de Insider**  >  **Insider risk settings**.
2. Seleccione la pestaña **Microsoft Teams** .
3. Habilite la integración de Microsoft Teams para la administración de riesgos de Insider.
4. Seleccione **Guardar** para configurar y salir.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Crear un equipo de Microsoft Teams para casos existentes

Si habilita la compatibilidad con Microsoft Teams para la administración de riesgos de Insider después de tener casos, tendrá que crear manualmente un equipo para cada caso, según sea necesario. Después de habilitar la compatibilidad de Microsoft Teams con la configuración de la administración de riesgos de Insider, se creará automáticamente un nuevo equipo de Microsoft Teams.

Los usuarios necesitan permiso para crear grupos de 365 de Microsoft en su organización para crear un equipo de Microsoft Teams a partir de un caso. Para obtener más información acerca de la administración de permisos para grupos de Microsoft 365, consulte [Manage The Can Create microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups).

Para crear un equipo para un caso, deberá usar el control de Microsoft Teams cuando trabaje directamente en un caso existente. Complete los siguientes pasos para crear un nuevo equipo:

1. En el [centro de cumplimiento de Microsoft 365](htttps://compliance.microsoft.com), vaya a escenarios de **Administración de riesgos de Insider**  >  **Cases** y seleccione un caso existente.
2. En el menú Acción de escenario, seleccione **crear Microsoft Team**.
3. En el campo **nombre del equipo** , escriba un nombre para el nuevo equipo de Microsoft Teams.
4. Seleccione **crear Microsoft Team** y, a continuación, haga clic en **cerrar**.

Según el número de usuarios asignados a los grupos de roles de administración de riesgos de Insider, es posible que se detengan 15 minutos para que todos los investigadores y analistas se agreguen al equipo de Microsoft Teams para un caso.
