---
title: Configuración de administración de riesgos de Insider
description: Más información sobre la configuración de administración de riesgos interno en Microsoft 365
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
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 1e719b03db1c6de0279606d5f46f44eb02368c7e
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126619"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introducción a la configuración de administración de riesgos interno

La configuración de administración de riesgos de Insider se aplica a todas las directivas de administración de riesgos de Insider, independientemente de la plantilla que elijas al crear una directiva. Las opciones se configuran mediante el control de configuración de riesgos de **Insider** que se encuentra en la parte superior de todas las pestañas de administración de riesgos de Insider. Estos componentes de directiva de control de configuración para las siguientes áreas:

- Privacidad
- Indicadores
- Escalas de tiempo de directiva
- Detecciones inteligentes
- Exportar alertas (versión preliminar)
- Grupos de usuarios de prioridad (versión preliminar)
- Activos físicos de prioridad (versión preliminar)
- Flujos de Power Automate (versión preliminar)
- Microsoft Teams (versión preliminar)

Antes de empezar y crear directivas de administración de riesgos internas, es importante comprender esta configuración y elegir los niveles de configuración que mejor se adapten a las necesidades de cumplimiento de la organización.

## <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directiva es importante y puede ayudar a promover la objectividad en la investigación de datos y las revisiones de análisis para alertas de riesgos de insider. Para los usuarios con una coincidencia de directiva de riesgo interno, puede elegir una de las siguientes opciones:

- **Mostrar versiones anónimas** de nombres de usuario: los nombres de los usuarios se anonimizan para evitar que los administradores, investigadores de datos y revisores vean quién está asociado con las alertas de directiva. Por ejemplo, un usuario "Grace Grace" aparecería con un seudónimo aleatorio como "AnonIS8-988" en todas las áreas de la experiencia de administración de riesgos de Insider. Al elegir esta opción, se anonimizan todos los usuarios con coincidencias de directiva actuales y pasadas y se aplica a todas las directivas. La información de perfil de usuario en la alerta de riesgo insider y los detalles del caso no estarán disponibles cuando se seleccione esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta opción, se mostrarán nombres de usuario para todos los usuarios que tengan coincidencias de directiva actuales o pasadas.
- **No mostrar versiones anónimas** de nombres de usuario: los nombres de usuario se muestran para todas las coincidencias de directiva actuales y pasadas para alertas y casos. La información de perfil de usuario (el nombre, el título, el alias y la organización o el departamento) se muestra al usuario para todas las alertas y casos de administración de riesgos de Insider.

![Configuración de privacidad de la administración de riesgos de Insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Las plantillas de directiva de riesgos de Insider definen el tipo de actividades de riesgo que desea detectar e investigar. Cada plantilla de directiva se basa en indicadores específicos que corresponden a desencadenadores específicos y actividades de riesgo. Todos los indicadores están deshabilitados de forma predeterminada y debe seleccionar uno o más indicadores de directiva antes de configurar una directiva de administración de riesgos interno.

Las directivas desencadenan alertas cuando los usuarios realizan actividades relacionadas con indicadores de directiva que cumplen un umbral requerido. La administración de riesgos de Insider usa dos tipos de indicadores:

- **Eventos desencadenamientos:** eventos que determinan si un usuario está activo para una directiva de administración de riesgos interno. Si un usuario se agrega a una directiva de administración de riesgos de Insider no tiene un evento desencadenante, la actividad del usuario no se evalúa mediante la directiva. Por ejemplo, el usuario A se agrega  a una directiva creada a partir del robo de datos al salir de la plantilla de directiva de usuarios y la directiva y el conector de RECURSOS de Microsoft 365 están configurados correctamente. Hasta que el usuario A tenga una fecha de finalización notificada por el conector de recursos humanos, las actividades del usuario A no se evalúan mediante esta directiva de administración de riesgos de Insider para el riesgo. Otro ejemplo de un evento desencadenante  es si un usuario tiene una alerta de directiva DLP de gravedad alta al usar *directivas de pérdida de* datos.
- **Indicadores de directiva:** indicadores incluidos en las directivas de administración de riesgos internas que se usan para determinar una puntuación de riesgo para un usuario en el ámbito. Estos indicadores de directiva solo se activan después de que se produzca un evento desencadenante para un usuario. Algunos ejemplos de indicadores de directiva son cuando un usuario copia datos en servicios de almacenamiento en la nube personales o dispositivos de almacenamiento portátiles, o si un usuario comparte archivos y carpetas internos con partes externas no autorizadas.

Los indicadores de directiva se segmentan en las siguientes áreas. Puedes elegir los indicadores para activar y personalizar los límites de eventos de indicador para cada nivel de indicador al crear una directiva de riesgo interno:

- **Indicadores de Office:** estos incluyen indicadores de directiva para sitios de SharePoint, Teams y mensajería de correo electrónico.
- **Indicadores de dispositivo:** estos incluyen indicadores de directiva para la actividad, como compartir archivos a través de la red o con dispositivos. Los indicadores incluyen actividad que implica Microsoft Office archivos, . Archivos CSV y . Archivos PDF. Si seleccionas **indicadores de dispositivo,** la actividad solo se procesará para dispositivos con Windows 10 Compilación 1809 o superior. Para obtener más información sobre cómo configurar dispositivos para la integración con riesgos de Insider, consulta la siguiente sección Habilitar indicadores [de dispositivos e incorporar dispositivos.](insider-risk-management-settings.md#OnboardDevices)
- **Indicador de infracción** de directiva de seguridad: estos incluyen indicadores de Microsoft Defender para Endpoint relacionados con la instalación de software no aprobada o malintencionada o la omisión de controles de seguridad. Para recibir alertas en la administración de riesgos de Insider, debes tener habilitada una licencia de Defender para endpoint activa e integración de riesgos de Insider. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar las características avanzadas de [Microsoft Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)
- **Puntuación de riesgo: esto** incluye aumentar la puntuación de riesgo para actividades inusuales o infracciones de directivas pasadas. La habilitación de marcadores de puntuación de riesgo aumenta las puntuaciones de riesgo y la probabilidad de alertas para estos tipos de actividades. Los indicadores de puntuación de riesgo solo se pueden seleccionar si se seleccionan uno o más indicadores.

![Configuración del indicador de administración de riesgos de Insider](../media/insider-risk-settings-indicators.png)

En algunos casos, es posible que desee limitar los indicadores de directiva de riesgo interno que se aplican a las directivas de riesgo interno de su organización. Puedes desactivar los indicadores de directiva para áreas específicas deshabilitándolos de todas las directivas de riesgo interno. Los eventos desencadenamientos no se pueden modificar para las plantillas de directiva de riesgo interno.

Para definir los indicadores de directiva de riesgo interno que están habilitados en todas las directivas de riesgo de **Insider,** vaya a Indicadores de configuración de riesgo de Insider y seleccione uno o más indicadores  >   de directiva. Los indicadores seleccionados en la página Configuración de indicadores no se pueden configurar individualmente al crear o editar una directiva de riesgo interno en el asistente para directivas.

>[!NOTE]
>Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios.** Las actividades de los 90 días anteriores para estos usuarios pueden tardar hasta 24 horas en mostrarse. Para ver las actividades de los usuarios agregados manualmente,  seleccione el usuario en el panel Usuarios y abra la pestaña Actividad del usuario en el panel de detalles. 

### <a name="enable-device-indicators-and-onboard-devices"></a>Habilitar indicadores de dispositivo e incorporar dispositivos
<a name="OnboardDevices"> </a>

Para habilitar la supervisión de actividades de riesgo en dispositivos e incluir indicadores de directiva para estas actividades, los dispositivos deben cumplir los siguientes requisitos y debe completar los siguientes pasos de incorporación.

#### <a name="step-1-prepare-your-endpoints"></a>Paso 1: Preparar los puntos de conexión

Asegúrate de que los dispositivos Windows 10 que planeas informar en la administración de riesgos de Insider cumplen estos requisitos.

1. Debe ejecutar Windows 10 x64 compilación 1809 o posterior y debe tener instalada la actualización de Windows 10 (compilación del sistema operativo [17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) a partir del 20 de febrero de 2020.
2. Todos los dispositivos deben estar [unidos a Azure Active Directory (AAD)](/azure/active-directory/devices/concept-azure-ad-join) o unidos a Azure AD híbrido.
3. Instala el explorador Microsoft Chromium Edge en el dispositivo del punto de conexión para supervisar las acciones de la actividad de carga en la nube. Consulte [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Paso 2: Incorporar dispositivos
<a name="OnboardStep2"> </a>

Debes habilitar la supervisión de dispositivos e incorporar los puntos de conexión antes de poder supervisar las actividades de administración de riesgos de insider en un dispositivo. Ambas acciones se realizan en el portal de cumplimiento de Microsoft 365.

Cuando quieras incorporar dispositivos que aún no se han incorporado, descargarás el script adecuado e implementarás como se indica en los pasos siguientes.

Si ya tiene dispositivos incorporados en [ Microsoft Defender para punto de conexión (MDATP)](/windows/security/threat-protection/), estos aparecerán en la lista de dispositivos administrados. Siga [el paso 3: Si tiene dispositivos incorporados](insider-risk-management-settings.md#OnboardStep3) en Microsoft Defender para Endpoint en la siguiente sección.

En este escenario de implementación, incorporarás dispositivos que aún no se han incorporado y solo quieres supervisar las actividades de riesgo interno en dispositivos Windows 10.

1. Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).
2. Abra la página de configuración del Centro de cumplimiento y elija **Incorporar dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. La lista estará vacía hasta que haya incorporado dispositivos.
4. Elija **Incorporación** para iniciar el proceso de incorporación.
5. Elige la forma en que quieres implementar en estos dispositivos más de la lista **de métodos de** implementación y luego **descarga el paquete.**
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez hecho esto y se ha incorporado el punto de conexión, debe estar visible en la lista de dispositivos y el punto de conexión empezará a notificar los registros de actividad de auditoría a la administración de riesgos de Insider.

> [!NOTE]
> Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Paso 3: Si tiene dispositivos incorporados en Microsoft Defender para endpoint
<a name="OnboardStep3"> </a>

Si Microsoft Defender para endpoint ya está implementado y hay puntos de conexión en los que se informa, todos estos puntos de conexión aparecerán en la lista de dispositivos administrados. Puedes seguir incorporando nuevos dispositivos en la administración de riesgos de Insider para ampliar la cobertura mediante la sección [Paso 2: Incorporar dispositivos.](insider-risk-management-settings.md#OnboardStep2)

1. Abra el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com).
2. Abra la página de configuración del Centro de cumplimiento y elija **Habilitar supervisión de dispositivos**.
3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. Debe ver la lista de dispositivos sobre los que ya se envían informes a Microsoft Defender para punto de conexión.
4. Elige **La incorporación** si necesitas incorporar más dispositivos.
5. Elige la forma en que quieres implementar en estos más dispositivos de la lista **de métodos de** implementación y, a continuación, **descarga el paquete.**
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez hecho esto y se ha  incorporado el punto de conexión, debe estar visible en la tabla Dispositivos y el punto de conexión empezará a notificar los registros de actividad de auditoría a la administración de riesgos de Insider.

> [!NOTE]
>Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

### <a name="indicator-level-settings-preview"></a>Configuración del nivel de indicador (versión preliminar)

Al crear una directiva en el asistente para directivas, puedes configurar cómo el número diario de eventos de riesgo debe influir en la puntuación de riesgo de las alertas de riesgo de Insider. Esta configuración de indicador le ayuda a controlar cómo el número de repeticiones de eventos de riesgo en su organización debe afectar a la puntuación de riesgo y, en consecuencia, a la gravedad de alerta asociada a estos eventos. Si lo prefiere, también puede optar por mantener los niveles de umbral de eventos predeterminados recomendados por Microsoft para todos los indicadores habilitados.

Por ejemplo, decide habilitar los indicadores de SharePoint en la configuración de directiva de riesgo interno y establecer umbrales personalizados para eventos de SharePoint al configurar indicadores para una nueva directiva de pérdida *de* datos de riesgo interno. Mientras se encuentra en el Asistente para directivas de riesgo interno, puede configurar tres niveles de eventos diarios diferentes para cada indicador de SharePoint para influir en la puntuación de riesgo para las alertas asociadas a estos eventos.

![Configuración de indicadores personalizados de administración de riesgos de Insider](../media/insider-risk-custom-indicators.png)

Para el primer nivel de evento diario, se establece el umbral en *10* o más eventos por día para un menor impacto en la puntuación de riesgo para los eventos, *20* o más eventos por día para un impacto medio en la puntuación de riesgo de los eventos y *30* o más eventos por día, un impacto mayor en la puntuación de riesgo para los eventos. Estas configuraciones significan de hecho:

- Si hay de 1 a 9 eventos de SharePoint que tienen lugar después de desencadenar el evento, las puntuaciones de riesgo se verán mínimamente afectadas y tendrían a no generar una alerta.
- Si hay entre 10 y 19 eventos de SharePoint que tienen lugar después de un evento desencadenante, la puntuación de riesgo es inherentemente inferior y los niveles de gravedad de alerta tienden a estar en un nivel bajo.
- Si hay entre 20 y 29 eventos de SharePoint que tienen lugar después de una activación, la puntuación de riesgo es inherentemente mayor y los niveles de gravedad de alerta tienden a estar en un nivel medio.
- Si hay 30 o más eventos de SharePoint que tienen lugar después de una activación, la puntuación de riesgo es inherentemente mayor y los niveles de gravedad de alerta tienden a estar en un nivel alto.

## <a name="policy-timeframes"></a>Períodos de tiempo de directiva

Los períodos de tiempo de directiva permiten definir períodos de revisión pasados y futuros que se desencadenan después de las coincidencias de directiva basadas en eventos y actividades para las plantillas de directiva de administración de riesgos de Insider. Según la plantilla de directiva que elija, están disponibles los siguientes períodos de tiempo de directiva:

- **Ventana activación:** disponible para todas  las plantillas de directiva, la ventana Activación es el número definido de días que la ventana se **activa** después de un evento desencadenante. La ventana se activa de 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos interno y ha establecido la *ventana* Activación en 30 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante  activa la ventana Activación y la directiva está activa para ese usuario durante 30 días después de que se produjo el evento desencadenante.
- **Detección de actividad** pasada: disponible  para todas las plantillas de directiva, la  detección de actividad pasada es el número definido de días que se activa la ventana antes de que se desencadene un evento. La ventana se activa de 0 a 180 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de Insider y ha establecido la detección de *actividad* pasada en 90 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante  activa la detección de actividad pasada y la directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.

![Configuración del período de tiempo de administración de riesgos de Insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecciones inteligentes

La configuración de detección inteligente ayuda a refinar cómo se procesan las detecciones de actividades de riesgo para las alertas. En determinadas circunstancias, es posible que deba definir tipos de archivos para omitir o que desee aplicar un nivel de detección para los archivos para ayudar a definir una barra mínima para las alertas. Usa esta configuración para controlar el volumen de alertas general, las exclusiones de tipos de archivo y los límites de volumen de archivos.

### <a name="anomaly-detections"></a>Detecciones de anomalías

Las detecciones anómalas incluyen la configuración de exclusiones de tipos de archivo y límites de volumen de archivos.

- **Exclusiones de tipo de archivo:** para excluir tipos de archivo específicos de todas las coincidencias de directivas de administración de riesgos de Insider, escriba las extensiones de tipo de archivo separadas por comas. Por ejemplo, para excluir determinados tipos de archivos de música de **coincidencias** de directiva, puede escribir *aac,mp3,wav,wma* en el campo Exclusiones de tipo de archivo. Todas las directivas de administración de riesgos de Insider omitirían los archivos con estas extensiones.
- **Límite de límite de volumen de archivos:** para definir un nivel de archivo mínimo antes de que se notifican alertas de actividad en directivas de riesgo interno, escriba el número de archivos. Por ejemplo, escribiría "10" si no desea generar alertas de riesgo interno cuando un usuario descargue 10 archivos o menos, incluso si las directivas consideran que esta actividad es una anomalía.

### <a name="alert-volume"></a>Volumen de alertas

A las actividades de usuario detectadas por las directivas de riesgo internas se les asigna una puntuación de riesgo específica, que a su vez determina la gravedad de la alerta (baja, media, alta). De forma predeterminada, generaremos una cierta cantidad de alertas de gravedad baja, media y alta, pero puedes aumentar o disminuir el volumen para adaptarlo a tus necesidades. Para ajustar el volumen de alertas para todas las directivas de administración de riesgos internas, elija una de las siguientes opciones:

- **Menos alertas:** verás todas las alertas de gravedad alta, menos alertas de gravedad media y ninguna de gravedad baja. Este nivel de configuración significa que podría perderse algunos positivos reales.
- **Volumen predeterminado:** verás todas las alertas de gravedad alta y una cantidad equilibrada de alertas de gravedad media y baja.
- **Más alertas:** verás todas las alertas de gravedad media y alta y la mayoría de las alertas de gravedad baja. Este nivel de configuración puede dar como resultado más falsos positivos.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender para endpoint (versión preliminar)

[Microsoft Defender para endpoint es](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) una plataforma de seguridad de puntos de conexión empresarial diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de la infracción de seguridad en su organización, puede importar y filtrar alertas de Defender para puntos de conexión para actividades usadas en directivas creadas a partir de plantillas de directiva de infracción de seguridad de administración de riesgos internas.

Según los tipos de señales que te interesen, puedes elegir importar alertas a la administración de riesgos de Insider en función del estado de evaluación de alertas de Defender for Endpoint. Puede definir uno o varios de los siguientes estados de la triage de alertas en la configuración global que se va a importar:

- Unknown
- Nuevo
- En curso
- Resuelto

Las alertas de Defender para endpoint se importan diariamente. Según el estado de la triage que elijas, es posible que veas varias actividades de usuario para la misma alerta que el estado de la triage cambia en Defender for Endpoint.

Por ejemplo, si selecciona Nuevo *,* En curso y Resuelto para esta configuración, cuando se genera una alerta de Microsoft Defender para endpoint y el estado es  *Nuevo*, se importa una actividad de alerta inicial para el usuario en riesgo interno. Cuando el estado de evaluación de Defender para extremo cambia a En *curso,* se importa una segunda actividad para esta alerta para el usuario en riesgo interno. Cuando se establece el estado final de evaluación de Defender para extremo de *Resuelto,* se importa una tercera actividad para esta alerta para el usuario en riesgo interno. Esta funcionalidad permite a los investigadores seguir el progreso de las alertas de Defender for Endpoint y elegir el nivel de visibilidad que requiere su investigación.

>[!IMPORTANT]
>Tendrás que configurar Microsoft Defender para Endpoint en tu organización y habilitar Defender para Endpoint para la integración de la administración de riesgos interno en el Centro de seguridad de Defender para importar alertas de infracción de seguridad. Para obtener más información sobre cómo configurar Defender para Endpoint para la integración de la administración de riesgos de Insider, consulta Configurar características avanzadas [en Defender para Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="domains-preview"></a>Dominios (versión preliminar)

La configuración de dominio le ayuda a definir los niveles de riesgo para las comunicaciones con dominios específicos. Estas comunicaciones incluyen compartir archivos, mensajes de correo electrónico o descargar contenido. Al especificar dominios en esta configuración, puede aumentar o disminuir la puntuación de riesgo para la actividad que tiene lugar con estos dominios. Por ejemplo, para especificar contoso.com y sales.wingtiptoys.com como dominios permitidos, escribirá "contoso.com sales.wingtiptoys.com" en el **campo Dominios permitidos.**

Para cada una de las siguientes configuraciones de dominio, puede especificar hasta 500 dominios:

- **Dominios no permitidos:** Al especificar dominios no permitidos, la actividad que tenga lugar con estos dominios tendrá puntuaciones *de* riesgo más altas.
- **Dominios permitidos:** Al especificar dominios permitidos en la configuración, la  actividad que tenga lugar con estos dominios tendrá puntuaciones de riesgo más bajas y se tratará de forma similar a la forma en que se trata la actividad de la organización interna. Por ejemplo, las actividades de correo electrónico de estos dominios se analizan de forma similar a la forma en que se analiza la actividad de correo electrónico interno.
- **Dominios de terceros:** Los dominios de terceros son dominios que se usan para fines empresariales en su organización y el contenido confidencial puede almacenarse en estas ubicaciones. Al especificar un dominio de terceros, puede recibir alertas para cualquier actividad de riesgo en estos dominios.

## <a name="export-alerts-preview"></a>Exportar alertas (versión preliminar)

La información de alertas de administración de riesgos de Insider se puede exportar a los servicios de administración de eventos e información de seguridad (SIEM) a través del esquema de la API de actividad de administración [de Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema) Puede usar las API de actividad de administración de Office 365 para exportar información de alerta a otras aplicaciones que su organización puede usar para administrar o agregar información de riesgo interno.

Para usar las API para revisar la información de alerta de riesgo interno:

1. Habilite la compatibilidad con la API de actividad de administración de Office 365 en la exportación de configuración de administración de riesgos de **Insider.**  >    >   De forma predeterminada, esta configuración está deshabilitada para su organización de Microsoft 365.
2. Filtrar las actividades comunes de auditoría de Office 365 *por SecurityComplianceAlerts*.
3. Filtra *SecurityComplianceAlerts* por la *categoría InsiderRiskManagement.*

![Configuración de alertas de exportación de administración de riesgos de Insider](../media/insider-risk-settings-export.png)

La información de alerta contiene información del esquema de alertas de seguridad y cumplimiento y el esquema común de la API de actividad de administración de Office 365.

Los siguientes campos y valores se exportan para las alertas de administración de riesgos interno para el esquema de alertas de seguridad & cumplimiento:

| **Parámetro de alerta** | **Descripción** |
|:------------------|:----------------|
| AlertType | El tipo de la alerta es *Personalizado*.  |
| AlertId | GUID de la alerta. Las alertas de administración de riesgos de Insider son mutables. A medida que cambia el estado de alerta, se genera un nuevo registro con el mismo AlertID. Este AlertID se puede usar para correlacionar las actualizaciones de una alerta. |
| Categoría | La categoría de la alerta es *InsiderRiskManagement*. Esta categoría se puede usar para distinguir entre estas alertas y otras alertas de seguridad & cumplimiento. |
| Comentarios | Comentarios predeterminados de la alerta. Los valores *son Alerta nueva* (registrada cuando se crea una alerta) y Alerta *actualizada* (registrada cuando hay una actualización de una alerta). Usa AlertID para correlacionar las actualizaciones de una alerta. |
| Datos | Los datos de la alerta incluyen el identificador de usuario único, el nombre principal del usuario y la fecha y hora (UTC) cuando el usuario se desencadenó en una directiva. |
| Nombre | Nombre de la directiva de administración de riesgos interno que generó la alerta. |
| PolicyId | GUID de la directiva de administración de riesgos de Insider que desencadenó la alerta. |
| Severity | La gravedad de la alerta. Los valores *son High*, *Medium* o *Low*. |
| Origen | El origen de la alerta. El valor es *Seguridad de Office 365 & cumplimiento.* |
| Estado | El estado de la alerta. Los valores son *Active* (*Needs Review* in insider risk), *Investigating* (*Confirmed* in insider risk), *Resolved* (*Resolved* in insider risk), Dismissed ( *Dismissed* in insider risk). |
| Versión | La versión del esquema de alertas de seguridad y cumplimiento. |

Los siguientes campos y valores se exportan para las alertas de administración de riesgos de Insider para el esquema común de la API de actividad de administración de [Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

- UserId
- Id
- RecordType
- CreationTime
- Operación
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuarios de prioridad (versión preliminar)

Los usuarios de su organización pueden tener distintos niveles de riesgo en función de su posición, nivel de acceso a información confidencial o historial de riesgos. Priorizar el examen y la puntuación de las actividades de estos usuarios puede ayudarle a alertar sobre posibles riesgos que pueden tener consecuencias más altas para su organización. Los grupos de usuarios prioritarios en la administración de riesgos interno ayudan a definir los usuarios de la organización que necesitan una inspección más minuciosa y una puntuación de riesgos más confidencial. Junto con las infracciones de la directiva de seguridad por parte de los usuarios prioritarios y las pérdidas de datos por las plantillas de directiva de usuarios *prioritarios,* los usuarios agregados a un grupo de usuarios de prioridad tienen una mayor probabilidad de *alertas* de riesgo interno y alertas con niveles de gravedad más altos.

![Configuración del grupo de usuarios de prioridad de administración de riesgos de Insider](../media/insider-risk-settings-priority-users.png)

Por ejemplo, debe protegerse contra pérdidas de datos para un proyecto extremadamente confidencial en el que los usuarios tienen acceso a información confidencial. Puede crear un grupo *de usuarios confidenciales* *de prioridad de* usuarios de proyecto para los usuarios de la organización que trabajan en este proyecto. Con el Asistente para directivas y las pérdidas de datos por  plantilla de directiva de usuarios *prioritarios,* se crea una nueva directiva y se asigna el grupo usuarios de prioridad Usuarios confidenciales del proyecto a la directiva. Las actividades examinadas por la  directiva para los miembros del grupo de usuarios de prioridad Usuarios confidenciales del proyecto son más sensibles a los riesgos y es más probable que las actividades de estos usuarios generen una alerta y tengan alertas con niveles de gravedad más altos.

### <a name="create-a-priority-user-group"></a>Crear un grupo de usuarios de prioridad

Para crear un nuevo grupo de usuarios prioritarios, usará la configuración de controles en la solución de administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365. Para crear un grupo de usuarios de prioridad, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administración de riesgos *de Insider.*

Complete los pasos siguientes para crear un grupo de usuarios de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione **Configuración de riesgos de Insider.**
2. Seleccionar la **pestaña Grupos de usuarios de** prioridad
3. En la **pestaña Grupos de usuarios de** prioridad, seleccione Crear grupo de usuarios de **prioridad** para iniciar el Asistente para la creación de grupos.
4. En la **página Definir grupo,** complete los campos siguientes:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para el grupo de usuarios de prioridad. No puede cambiar el nombre del grupo de usuarios de prioridad después de completar el asistente.
    - **Descripción (opcional):** escriba una descripción para el grupo de usuarios de prioridad.
5. Seleccione **Siguiente** para continuar.
6. En la página Elegir  miembros, seleccione Elegir miembros para buscar y seleccione las  cuentas de usuario habilitadas para correo que se incluyen en el grupo o active la casilla Seleccionar todo para agregar todos los usuarios de su organización al grupo.  Seleccione **Agregar para** continuar o **Cancelar** para cerrar sin agregar ningún usuario al grupo.
7. Seleccione **Siguiente** para continuar.
8. En la **página** Revisar, revisa la configuración que has elegido para el grupo de usuarios de prioridad. Seleccione **Editar** para cambiar cualquiera de los valores del grupo o **seleccione** Enviar para crear y activar el grupo de usuarios de prioridad.
9. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="update-a-priority-user-group"></a>Actualizar un grupo de usuarios de prioridad

Para actualizar un grupo de usuarios de prioridad existente, usará la configuración de controles en la solución de administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365. Para actualizar un grupo de usuarios de prioridad, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administración de riesgos *de Insider.*

Complete los siguientes pasos para editar un grupo de usuarios de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione **Configuración de riesgos de Insider.**
2. Seleccionar la **pestaña Grupos de usuarios de** prioridad
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Editar grupo.**
4. En la **página Definir grupo,** actualice el campo Descripción si es necesario. No puede actualizar el nombre del grupo de usuarios de prioridad. Seleccione **Siguiente** para continuar.
5. En la **página Elegir miembros,** agregue nuevos miembros al grupo mediante el control **Elegir miembros.** Para quitar un usuario del grupo, seleccione la "X" junto al usuario que desea quitar. Seleccione **Siguiente** para continuar.
6. En la **página** Revisar, revisa la configuración de actualización que has elegido para el grupo de usuarios de prioridad. Seleccione **Editar** para cambiar cualquiera de los valores de grupo o **seleccione** Enviar para actualizar el grupo de usuarios de prioridad.
7. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="delete-a-priority-user-group"></a>Eliminar un grupo de usuarios de prioridad

Para eliminar un grupo de usuarios de prioridad existente, usará la configuración de controles en la solución de administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365. Para eliminar un grupo de usuarios de prioridad, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administración de riesgos *de Insider.*

>[!IMPORTANT]
>La eliminación de un grupo de usuarios de prioridad lo quitará de cualquier directiva activa a la que esté asignado. Si eliminas un grupo de usuarios de prioridad asignado a una directiva activa, la directiva no contendrá ningún usuario en el ámbito y estará inactiva y no creará alertas.

Complete los siguientes pasos para eliminar un grupo de usuarios de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione **Configuración de riesgos de Insider.**
2. Seleccionar la **pestaña Grupos de usuarios de** prioridad
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Eliminar** en el menú del panel.
4. En el **cuadro de** diálogo Eliminar, seleccione **Sí** para eliminar el grupo de usuarios de prioridad o **cancelar** para volver al panel.

## <a name="priority-physical-assets-preview"></a>Activos físicos de prioridad (versión preliminar)

La identificación del acceso a activos físicos prioritarios y la correlación de la actividad de acceso a los eventos de usuario es un componente importante de la infraestructura de cumplimiento. Estos activos físicos representan ubicaciones de prioridad en su organización, como edificios empresariales, centros de datos o salas de servidores. Las actividades de riesgo interno pueden asociarse a usuarios que trabajan horas inusuales, intentar acceder a estas áreas confidenciales o seguras no autorizadas y solicitudes de acceso a áreas de alto nivel sin necesidades legítimas.

Con los activos físicos prioritarios habilitados y el conector de datos de riesgo físico configurado, la administración de riesgos interno integra las señales de los sistemas de control físico y acceso con otras actividades de riesgo del usuario. [](import-physical-badging-data.md) Al examinar patrones de comportamiento en los sistemas de acceso físico y correlacionar estas actividades con otros eventos de riesgo interno, la administración de riesgos interno puede ayudar a los investigadores y analistas de cumplimiento a tomar decisiones de respuesta más fundamentadas para las alertas. El acceso a los activos físicos de prioridad se puntua y se identifica en la información de forma diferente al acceso a los activos no prioritarios.

Por ejemplo, su organización tiene un sistema de gobierno para los usuarios que supervisa y aprueba el acceso físico a áreas normales de trabajo y proyectos confidenciales. Tiene varios usuarios trabajando en un proyecto confidencial y estos usuarios volverán a otras áreas de la organización cuando se complete el proyecto. A medida que el proyecto confidencial se acerca a su finalización, desea asegurarse de que el trabajo del proyecto sea confidencial y de que el acceso a las áreas del proyecto esté estrechamente controlado.

Elija habilitar el conector de datos de administración física en Microsoft 365 para importar información de acceso desde su sistema de administración de daños físicos y especificar activos físicos de prioridad en la administración de riesgos interno. Al importar información desde el sistema que está en mal estado y correlacionar la información de acceso físico con otras actividades de riesgo identificadas en la administración de riesgos interno, observa que uno de los usuarios del proyecto obtiene acceso a las oficinas del proyecto después del horario laboral normal y también exporta grandes cantidades de datos a un servicio de almacenamiento en la nube personal desde su área de trabajo normal. Esta actividad de acceso físico asociada a la actividad en línea puede apuntar a posibles robos de datos y los analistas y investigadores de cumplimiento pueden tomar las medidas adecuadas según lo dictan las circunstancias para este usuario.

### <a name="configure-priority-physical-assets"></a>Configurar activos físicos de prioridad

Para configurar activos físicos de prioridad, configurará el conector de configuración física y usará controles de configuración en la solución de administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365. Para configurar activos físicos de prioridad, debe ser miembro del grupo de roles Administración de riesgos de *Insider* o Administración de riesgos *de Insider.*

Complete los siguientes pasos para configurar activos físicos de prioridad:

1. Siga los pasos de configuración para la administración de riesgos de insider en el artículo Introducción a la administración de [riesgos de Insider.](insider-risk-management-configure.md) En el paso 3, asegúrese de configurar el conector de badging físico.

    >[!IMPORTANT]
    >Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Recursos Humanos de Microsoft 365. Si habilita el conector de protección física sin habilitar el conector de Recursos Humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para actividades de acceso físico para los usuarios de su organización.

2. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider** Activos físicos  >  **prioridad.**
3. En **la** página Activos físicos de prioridad, puede agregar manualmente los IDs de activos físicos que desea supervisar para los eventos de activos importados por el conector de configuración física o importar un archivo . Archivo CSV de todos los identificadores de activos físicos importados por el conector de administración de activos físicos: a) Para agregar manualmente identificadores de activos físicos, elija Agregar activos físicos de **prioridad,** escriba un id. de activo físico y, a continuación, seleccione Agregar **.** Escribe otros IDs de activos físicos y, a continuación, selecciona **Agregar activos físicos de prioridad** para guardar todos los activos especificados.
    b) Para agregar una lista de los IDs de activos físicos de un archivo . Archivo CSV, elija **Importar activos físicos de prioridad.** En el cuadro de diálogo del explorador de archivos, seleccione el archivo . Archivo CSV que desea importar y, a continuación, seleccione **Abrir**. Los IDs de activos físicos del archivo . Los archivos CSV se agregan a la lista.
4. Vaya a la **pestaña Indicadores de** directiva en Configuración.
5. En la **página Indicadores de directiva,** vaya a la sección Indicadores de acceso físico **y** active la casilla acceso físico después de la finalización o el acceso fallido al **activo confidencial.**
6. Seleccione **Guardar para** configurar y salir.

### <a name="delete-a-priority-physical-asset"></a>Eliminar un activo físico de prioridad

Para eliminar un activo físico de prioridad existente, usará la configuración de controles en la solución de administración de riesgos de Insider en el Centro de cumplimiento de Microsoft 365. Para eliminar un activo físico de prioridad, debes ser miembro del grupo de roles Administración de riesgos de Insider o Administración de riesgos de Insider.

>[!IMPORTANT]
>La eliminación de un activo físico de prioridad lo elimina del examen por cualquier directiva activa a la que se incluyó anteriormente. Las alertas generadas por actividades asociadas con el activo físico de prioridad no se eliminan.

Complete los siguientes pasos para eliminar un activo físico de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider** Activos físicos  >  **prioridad.**
2. En la **página Activos físicos de** prioridad, seleccione el activo que desea eliminar.
3. Seleccione **Eliminar** en el menú de acciones para eliminar el activo.

## <a name="power-automate-flows-preview"></a>Flujos de Power Automate (versión preliminar)

[Microsoft Power Automate es](/power-automate/getting-started) un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas a estas aplicaciones y servicios. Al habilitar los flujos de Power Automate para la administración de riesgos interno, puede automatizar tareas importantes para casos y usuarios. Puede configurar los flujos de Power Automate para recuperar información de usuarios, alertas y casos, y compartir esta información con las partes interesadas y otras aplicaciones, así como automatizar acciones en la administración de riesgos de Insider, como publicar en notas del caso. Los flujos de Power Automate son aplicables a casos y a cualquier usuario en el ámbito de una directiva.

Los clientes con suscripciones de Microsoft 365 que incluyen la administración de riesgos de Insider no necesitan licencias adicionales de Power Automate para usar las plantillas recomendadas de Administración de riesgos interno de Power Automate. Estas plantillas se pueden personalizar para dar soporte a su organización y cubrir los principales escenarios de administración de riesgos de Insider. Si decide usar las características premium de Power Automate en estas plantillas, crear una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o usar plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, es posible que necesite más licencias de Power Automate.

Las siguientes plantillas de Power Automate se proporcionan a los clientes para admitir la automatización de procesos para usuarios y casos de administración de riesgos insider:

- **Notificar** a los usuarios cuando se les agrega a una directiva de riesgos internos: esta plantilla es para las organizaciones que tienen directivas internas, privacidad o requisitos normativos que los usuarios deben recibir una notificación cuando están sujetos a directivas de administración de riesgos internos. Cuando este flujo se configura y selecciona para un usuario en la página de usuarios, los usuarios y sus administradores se envían un mensaje de correo electrónico cuando el usuario se agrega a una directiva de administración de riesgos de Insider. Esta plantilla también admite la actualización de una lista de SharePoint hospedada en un sitio de SharePoint para ayudar a realizar un seguimiento de los detalles de los mensajes de notificación, como la fecha y hora y el destinatario del mensaje. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad,** los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el panel **Usuarios.**
- Solicitar información de recursos humanos o empresariales sobre un usuario en un caso de riesgo **interno:** al actuar en un caso, es posible que los analistas de riesgos e investigadores de Insider deban consultar con recursos humanos u otras partes interesadas para comprender el contexto de las actividades del caso. Cuando este flujo se configura y selecciona para un caso, los analistas e investigadores envían un mensaje de correo electrónico a las partes interesadas de recursos humanos y empresariales configuradas para este flujo. Cada destinatario recibe un mensaje con opciones de respuesta preconfiguradas o personalizables. Cuando los destinatarios seleccionan una opción de respuesta, la respuesta se registra como una nota de caso e incluye información de destinatario y fecha y hora. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad,** los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el panel **Casos.**
- **Notificar al administrador cuando un usuario** tiene una alerta de riesgo interno: es posible que algunas organizaciones necesiten tener una notificación de administración inmediata cuando un usuario tiene una alerta de administración de riesgos interno. Cuando se configura y selecciona este flujo, se envía un mensaje de correo electrónico al administrador del usuario del caso con la siguiente información sobre todas las alertas de caso:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

    El flujo actualiza automáticamente las notas de caso que el mensaje se envió y que se activó el flujo. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad,** los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el panel **Casos.**

- **Agregar aviso de** calendario para realizar un seguimiento en un caso de riesgo interno: esta plantilla permite a los investigadores de riesgos y analistas agregar avisos de calendario para casos a su calendario de Office 365 Outlook. Este flujo elimina la necesidad de que los usuarios salgan o cambien del flujo de trabajo de administración de riesgos interno al procesar casos y eliminar las alertas. Cuando se configura y selecciona este flujo, se agrega un aviso al calendario de Outlook de Office 365 para el usuario que ejecuta el flujo. Los flujos de Power Automate que usan esta plantilla están disponibles en el panel **Casos.**
- **Cree un registro para casos** de riesgo interno en ServiceNow: esta plantilla es para las organizaciones que desean usar su solución ServiceNow para realizar un seguimiento de los casos de administración de riesgos de Insider.  Cuando en un caso, los analistas e investigadores de riesgos de Insider pueden crear un registro para el caso en ServiceNow. Puedes personalizar esta plantilla para rellenar los campos seleccionados en ServiceNow en función de los requisitos de tu organización. Los flujos de Power Automate que usan esta plantilla están disponibles en el panel **Casos.** Para obtener más información sobre los campos de ServiceNow disponibles, consulte el artículo de referencia [de ServiceNow Connector.](/connectors/service-now/)

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Crear un flujo de Power Automate a partir de la plantilla de administración de riesgos interno

Para crear un flujo de Power Automate a partir de una plantilla de administración de riesgos internos recomendada, usará los controles de configuración de la solución de  administración de riesgos de **Insider** en el Centro de cumplimiento de Microsoft 365 o la opción Administrar flujos de **Power Automate** desde el control **Automatizar** cuando trabaje directamente en los paneles **Casos** o Usuarios.

Para crear un flujo de Power Automate en el área de configuración, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administrador de administración de riesgos de *Insider.* Para crear un flujo de Power Automate con la opción Administrar flujos de **Power Automate,** debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para crear un flujo de Power Automate a partir de una plantilla de administración de riesgos insider recomendada:

1. En el [Centro de cumplimiento de Microsoft 365,](https://compliance.microsoft.com/)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider**  >  **Flujos de Power Automate.** También puede obtener acceso desde las páginas de paneles **Casos** o Usuarios eligiendo **Automatizar** los flujos de Power   >  **Automate.**
2. En la **página Flujos de Power Automate,** selecciona una plantilla recomendada de las plantillas de administración de riesgos de Insider que te pueden **gustar** en la sección de la página.
3. El flujo enumera las conexiones incrustadas necesarias para el flujo y tendrá en cuenta si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestran como disponibles. Seleccione **Continuar**.
4. De forma predeterminada, los flujos recomendados están preconfigurados con la administración de riesgos insider recomendada y los campos de datos de servicio de Microsoft 365 necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar** opciones avanzadas y configurando las propiedades disponibles para el componente de flujo.
5. Si es necesario, agregue cualquier otro paso al flujo seleccionando el **botón Nuevo** paso. En la mayoría de los casos, esto no debe ser necesario para las plantillas predeterminadas recomendadas.
6. Seleccione **Guardar borrador** para guardar el flujo para una configuración adicional o seleccione **Guardar** para completar la configuración del flujo.
7. Seleccione **Cerrar para** volver a la página de flujo de Power **Automate.** La nueva plantilla aparecerá como un  flujo en las pestañas Mis  flujos y estará disponible automáticamente en el control desplegable Automatizar al trabajar con casos de administración de riesgos insider para el usuario que crea el flujo.

>[!IMPORTANT]
>Si otros usuarios de la organización necesitan tener acceso al flujo, el flujo debe compartirse.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Crear un flujo personalizado de Power Automate para la administración de riesgos interno

Algunos procesos y flujos de trabajo de su organización pueden estar fuera de las plantillas de flujo de administración de riesgos internos recomendadas y es posible que tenga que crear flujos personalizados de Power Automate para áreas de administración de riesgos internos. Los flujos de Power Automate son flexibles y admiten una amplia personalización, pero hay pasos que deben realizarse para integrarse con las características de administración de riesgos de Insider.

Complete los pasos siguientes para crear una plantilla de Power Automate personalizada para la administración de riesgos interno:

1. **Compruebe su licencia de flujo de Power Automate:** para crear flujos personalizados de Power Automate que usen desencadenadores de administración de riesgos interno, necesitará una licencia de Power Automate. Las plantillas de flujo de administración de riesgos insider recomendadas no requieren licencias adicionales y se incluyen como parte de la licencia de administración de riesgos de Insider.
2. **Crear un flujo automatizado:** cree un flujo que realice una o más tareas después de que se desencadene por un evento de administración de riesgos interno. Para obtener más información sobre cómo crear un flujo automatizado, vea [Crear un flujo en Power Automate.](/power-automate/get-started-logic-flow)
3. **Seleccione el conector de cumplimiento de Microsoft 365:** busque y seleccione el conector de cumplimiento de Microsoft 365. Este conector permite acciones y desencadenadores de administración de riesgos interno. Para obtener más información acerca de los conectores, vea el artículo de introducción [a la referencia del](/connectors/connector-reference/) conector.
4. **Elige los desencadenadores de administración de** riesgos de Insider para tu flujo: la administración de riesgos de Insider tiene dos desencadenadores disponibles para flujos personalizados de Power Automate:
    - **Para un caso de administración de** riesgos insider seleccionado: los flujos con este desencadenador se pueden seleccionar en la página del panel de casos de administración de riesgos de Insider.
    - **Para un usuario de administración de** riesgos interno seleccionado: los flujos con este desencadenador se pueden seleccionar en la página del panel usuarios de administración de riesgos de Insider.
5. Elija las acciones de administración de riesgos de Insider para su flujo: puede elegir entre varias acciones para que la administración de riesgos insider incluya en el flujo personalizado:
    - Obtener alerta de administración de riesgos interno
    - Obtener un caso de administración de riesgos interno
    - Obtener usuario de administración de riesgos interno
    - Obtener alertas de administración de riesgos interno para un caso
    - Agregar nota de caso de administración de riesgos interno

### <a name="share-a-power-automate-flow"></a>Compartir un flujo de Power Automate

De forma predeterminada, los flujos de Power Automate creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de administración de riesgos de Insider tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usará los controles de configuración de la solución de administración de riesgos de **Insider** en el Centro  de  cumplimiento de Microsoft 365 o la opción Administrar flujos de **Power Automate** desde el control Automatizar cuando trabaje directamente en las páginas del panel Casos o Usuarios. Una vez que haya compartido un flujo, todos los usuarios con los  que se ha compartido pueden tener acceso al flujo en el desplegable **Control** automático de los paneles Caso **y Usuario.**

Para compartir un flujo de Power Automate en el área de configuración, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administrador de administración de riesgos de *Insider.* Para compartir un flujo de Power Automate con la opción Administrar flujos de **Power Automate,** debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para compartir un flujo de Power Automate:

1. En el [Centro de cumplimiento de Microsoft 365,](htttps://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider**  >  **Flujos de Power Automate.** También puede obtener acceso desde las páginas de paneles **Casos** o Usuarios eligiendo **Automatizar** los flujos de Power   >  **Automate.**
2. En la página **Flujos de Power Automate,** seleccione la **pestaña Mis flujos** o **Flujos de** equipo.
3. Seleccione el flujo que desea compartir y, a continuación, **seleccione Compartir** en el menú de opciones de flujo.
4. En la página de uso compartido del flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
5. En el **cuadro de diálogo** Conexión usada, seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso completo al flujo.

### <a name="edit-a-power-automate-flow"></a>Editar un flujo de Power Automate

Para editar un flujo, usará los controles de configuración de la solución de administración de riesgos de **Insider** en el Centro  de cumplimiento de Microsoft 365 o la opción Administrar flujos de **Power Automate** desde el control **Automatizar** cuando trabaje directamente en los paneles **Casos** o Usuarios.

Para editar un flujo de Power Automate en el área de configuración, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administrador de administración de riesgos de *Insider.* Para editar un flujo de Power Automate con la opción Administrar flujos de **Power Automate,** debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para editar un flujo de Power Automate:

1. En el [Centro de cumplimiento de Microsoft 365,](htttps://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider**  >  **Flujos de Power Automate.** También puede obtener acceso desde las páginas de paneles **Casos** o Usuarios eligiendo **Automatizar** los flujos de Power   >  **Automate.**
2. En la **página Flujos de Power Automate,** seleccione un flujo para editar y seleccione **Editar** en el menú de control de flujo.
3. Seleccione la configuración **de puntos suspensivos** para cambiar la configuración de un componente de flujo o la eliminación de puntos suspensivos  >   para eliminar un componente de   >   flujo.
4. Seleccione **Guardar** y, a **continuación,** Cerrar para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo de Power Automate

Para eliminar un flujo, usará los controles de configuración de la solución de administración de riesgos de **Insider** en el Centro  de cumplimiento de Microsoft 365 o la opción Administrar flujos de **Power Automate** desde el control **Automatizar** cuando trabaje directamente en los paneles **Casos** o Usuarios. Cuando se elimina un flujo, se quita como una opción para todos los usuarios.

Para eliminar un flujo de Power Automate en el área de configuración, debes ser miembro del grupo de roles Administración de riesgos de *Insider* o Administrador de administración de riesgos de *Insider.* Para eliminar un flujo de Power Automate con la opción Administrar flujos de **Power Automate,** debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para eliminar un flujo de Power Automate:

1. En el [Centro de cumplimiento de Microsoft 365,](htttps://compliance.microsoft.com)vaya a Administración de riesgos de **Insider** y seleccione Configuración de riesgos de **Insider**  >  **Flujos de Power Automate.** También puede obtener acceso desde las páginas de paneles **Casos** o Usuarios eligiendo **Automatizar** los flujos de Power   >  **Automate.**
2. En la **página Flujos de Power Automate,** seleccione un flujo para eliminar y seleccione **Eliminar** en el menú de control de flujo.
3. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o **cancelar** para salir de la acción de eliminación.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (versión preliminar)

Los analistas e investigadores de cumplimiento pueden usar fácilmente Microsoft Teams para colaborar en casos de administración de riesgos interno. Pueden coordinar y comunicarse con otras partes interesadas de Microsoft Teams para:

- Coordinar y revisar las actividades de respuesta para casos en canales privados de Teams
- Compartir y almacenar archivos y evidencias relacionados con casos individuales de forma segura
- Realizar un seguimiento y revisar las actividades de respuesta de analistas e investigadores

Después de habilitar Microsoft Teams para la administración de riesgos interno, se crea un equipo dedicado de Microsoft Teams cada vez que se confirma una alerta y se crea un caso. De forma predeterminada, el equipo incluye automáticamente a todos los miembros de los grupos de roles *Insider Risk Management*, *Insider Risk Management Analysts* y *Insider Risk Management Researchers* (hasta 100 usuarios iniciales). Se pueden agregar colaboradores de organización adicionales al equipo después de crearlo y según corresponda. Para los casos existentes creados antes de habilitar Microsoft Teams, los analistas e investigadores pueden elegir crear un nuevo equipo de Microsoft Teams cuando trabajen en un caso si es necesario.  Una vez resuelto el caso asociado en la administración de riesgos interno, el equipo se archiva automáticamente (se mueve a oculto y de solo lectura).

Para obtener más información sobre cómo usar equipos y canales en Microsoft Teams, vea Información general sobre equipos [y canales en Microsoft Teams.](/MicrosoftTeams/teams-channels-overview)

Habilitar la compatibilidad de Microsoft Teams para casos es rápido y fácil de configurar. Para habilitar Microsoft Teams para la administración de riesgos interno, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365,](htttps://compliance.microsoft.com)vaya a Configuración de riesgos de **Insider de** administración de riesgos de  >  **Insider.**
2. Seleccione la **pestaña Microsoft Teams.**
3. Habilitar la integración de Microsoft Teams para la administración de riesgos interno.
4. Seleccione **Guardar para** configurar y salir.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Crear un equipo de Microsoft Teams para casos existentes

Si habilita el soporte técnico de Microsoft Teams para la administración de riesgos interno después de tener casos existentes, deberá crear manualmente un equipo para cada caso según sea necesario. Después de habilitar el soporte técnico de Microsoft Teams en la configuración de administración de riesgos interno, los nuevos casos crearán automáticamente un nuevo equipo de Microsoft Teams.

Los usuarios necesitan permiso para crear grupos de Microsoft 365 en su organización para crear un equipo de Microsoft Teams a partir de un caso. Para obtener más información acerca de la administración de permisos para Grupos de Microsoft 365, vea Administrar quién puede crear Grupos de [Microsoft 365.](/microsoft-365/solutions/manage-creation-of-groups)

Para crear un equipo para un caso, usará el control Crear Microsoft Team cuando trabaje directamente en un caso existente. Complete los pasos siguientes para crear un nuevo equipo:

1. En el [Centro de cumplimiento de Microsoft 365,](htttps://compliance.microsoft.com)vaya a Casos de administración de riesgos de **Insider**  >   y seleccione un caso existente.
2. En el menú de acciones del caso, **seleccione Crear Microsoft Team**.
3. En el **campo Nombre del** equipo, escriba un nombre para el nuevo equipo de Microsoft Teams.
4. Seleccione **Crear equipo de Microsoft** y, a continuación, seleccione **Cerrar**.

En función del número de usuarios asignados a grupos de roles de administración de riesgos de Insider, todos los investigadores y analistas pueden tardar 15 minutos en agregarse al equipo de Microsoft Teams para un caso.
