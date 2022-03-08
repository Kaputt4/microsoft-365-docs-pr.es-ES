---
title: Configuración de administración de riesgos de Insider
description: Obtenga información sobre la configuración de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
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
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 62616ed20513ee023986525b4f097c96ae3107ba
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330613"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introducción a la configuración de administración de riesgos de insider

La configuración de administración de riesgos de Insider se aplica a todas las directivas de administración de riesgos de insider, independientemente de la plantilla que elija al crear una directiva. Configuración se configuran mediante el control de configuración de riesgos **de Insider** ubicado en la parte superior de todas las páginas de administración de riesgos insider. Estos componentes de directiva de control de configuración para las siguientes áreas:

- Privacidad
- Indicadores
- Escalas de tiempo de la directiva
- Detecciones inteligentes
- Exportar alertas
- Grupos de usuarios prioritarios (versión preliminar)
- Activos físicos prioritarios (versión preliminar)
- Power Automate flujos (versión preliminar)
- Microsoft Teams (versión preliminar)
- Análisis

Antes de empezar y crear directivas de administración de riesgos internas, es importante comprender esta configuración y elegir los niveles que mejor se adapten a las necesidades de cumplimiento de la organización.

## <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en las revisiones de análisis e investigaciones de datos de alertas de riesgos internos. Para los usuarios con una coincidencia de directiva de riesgo de insider, puede elegir una de las siguientes opciones:

- **Mostrar versiones anónimas** de nombres de usuario: los nombres de los usuarios se anonimizan para impedir que los administradores, los investigadores de datos y los revisores vean quién está asociado con las alertas de directivas. Por ejemplo, el usuario “Grace Taylor” aparecería con un pseudónimo aleatorizado, como “AnonIS8-988” en todas las áreas relacionadas con la experiencia de administración de riesgos internos. Al elegir esta configuración, se anonimizan todos los usuarios con coincidencias de directivas actuales y pasadas, y se aplica a todas las directivas. La información del perfil de usuario en la alerta de riesgo insider y los detalles del caso no estarán disponibles cuando se elija esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán nombres de usuario para todos los usuarios que tengan coincidencias de directiva actuales o pasadas.

    >[!IMPORTANT]
    >Para mantener la integridad referencial de los usuarios que tienen alertas de riesgo de información interna o casos en Microsoft 365 u otros sistemas, el anonimización de nombres de usuario no se conserva para las alertas exportadas. Las alertas exportadas mostrarán nombres de usuario para cada alerta.

- **No mostrar versiones anónimas** de nombres de usuario: los nombres de usuario se muestran para todas las coincidencias de directiva actuales y pasadas para alertas y casos. La información de perfil de usuario (nombre, título, alias y organización o departamento) se muestra para el usuario para todas las alertas y casos de administración de riesgos de insider.

![Configuración de privacidad de la administración de riesgos de Insider.](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Las plantillas de directiva de riesgo insider definen el tipo de actividades de riesgo que desea detectar e investigar. Cada plantilla de directiva se basa en indicadores específicos que corresponden a desencadenadores específicos y actividades de riesgo. Todos los indicadores están deshabilitados de forma predeterminada y debe seleccionar uno o más indicadores de directiva antes de configurar una directiva de administración de riesgos insider.

Las directivas desencadenan alertas cuando los usuarios realizan actividades relacionadas con indicadores de directiva que cumplen un umbral obligatorio. La administración de riesgos de Insider usa dos tipos de indicadores:

- **Eventos desencadenamiento**: eventos que determinan si un usuario está activo en una directiva de administración de riesgos de insider. Si un usuario se agrega a una directiva de administración de riesgos insider no tiene un evento desencadenante, la directiva no evalúa la actividad del usuario. Por ejemplo, el usuario A se agrega a una directiva creada a partir  del robo de datos al salir de la plantilla de directiva de usuarios y la directiva y el Microsoft 365 de recursos humanos están configurados correctamente. Hasta que el usuario A tenga una fecha de finalización notificada por el conector de recursos humanos, las actividades del usuario A no se evalúan mediante esta directiva de administración de riesgos de insider para el riesgo. Otro ejemplo de un evento desencadenante es si un usuario tiene una  alerta de directiva DLP de alta gravedad al usar *directivas de pérdida de* datos.
- **Indicadores de directiva**: indicadores incluidos en las directivas de administración de riesgos internas que se usan para determinar una puntuación de riesgo para un usuario en el ámbito. Estos indicadores de directiva solo se activan después de que se produzca un evento desencadenante para un usuario. Algunos ejemplos de indicadores de directiva son cuando un usuario copia datos en servicios de almacenamiento en la nube personales o dispositivos de almacenamiento portátiles, si se quita una cuenta de usuario de Azure Active Directory o si un usuario comparte archivos y carpetas internos con partes externas no autorizadas.

Algunos indicadores de directiva también pueden usarse para personalizar eventos desencadenantes para plantillas de directiva específicas. Cuando se configura en el Asistente para directivas para las *fugas* de datos generales o *pérdidas* de datos por plantillas de usuarios prioritarios, estos indicadores le permiten más flexibilidad y personalización para las directivas y cuando los usuarios están en el ámbito de una directiva. Además, puede definir umbrales de actividad individuales para estos indicadores desencadenantes para un control más preciso en una directiva.

Los indicadores de directiva se segmentan en las siguientes áreas. Puede elegir los indicadores para activar y personalizar los límites de eventos del indicador para cada nivel de indicador al crear una directiva de riesgo de información interna:

- **Office: estos** incluyen indicadores de directiva para SharePoint sitios, Microsoft Teams y mensajería de correo electrónico.
- **Indicadores de dispositivos**: estos incluyen indicadores de directiva para la actividad, como compartir archivos a través de la red o con dispositivos. Los indicadores incluyen actividades que implican todos los tipos de archivo, excepto la actividad de archivos ejecutables (.exe) y de biblioteca de vínculos dinámicos (.dll). Si selecciona Indicadores de dispositivo, la actividad se procesa para dispositivos con Windows 10 compilación 1809 o posterior y *dispositivos* macOS (Catalina 10.15 o posterior). Para dispositivos Windows y macOS, primero debes incorporar dispositivos al centro de cumplimiento. Los indicadores de dispositivo también incluyen la detección de señales del explorador para ayudar a su organización a detectar y actuar en las señales de exfiltración de archivos no ejecutables vistos, copiados, compartidos o impresos en Microsoft Edge y Google Chrome. Para obtener más información sobre cómo configurar Windows dispositivos para la integración con riesgos de insider, consulte la siguiente sección Habilitar indicadores de [dispositivos e incorporar Windows dispositivos](insider-risk-management-settings.md#OnboardDevices) en este artículo. Para obtener más información sobre cómo configurar dispositivos macOS para la integración con riesgos de insider, consulte la siguiente sección Habilitar indicadores de dispositivos y incorporar dispositivos macOS en este artículo. Para obtener más información acerca de la detección de señales del explorador, vea [Learn about and configure insider risk management browser signal detection](insider-risk-management-browser-support.md).
- **Indicador de infracción** de directivas de seguridad (versión preliminar):Estos incluyen indicadores de Microsoft Defender para Endpoint relacionados con la instalación de software no aprobado o malintencionado o el desvío de controles de seguridad. Para recibir alertas en la administración de riesgos de insider, debe tener habilitada una licencia de Defender for Endpoint activa e integración de riesgos de insider. Para obtener más información sobre cómo configurar Defender for Endpoint para la integración de la administración de riesgos insider, consulte [Configure advanced features in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Indicadores de acceso a registros de estado (versión preliminar):** Estos incluyen indicadores de directiva para el acceso a registros médicos de pacientes. Por ejemplo, el intento de acceso a los registros médicos de pacientes en los registros del sistema de registros médicos electrónicos (EMR) se puede compartir con las directivas de salud de administración de riesgos internas. Para recibir este tipo de alertas en la administración de riesgos de insider, debe tener configurado un conector de datos específico de la salud y el conector de datos de RECURSOS HUMANOS.
- **Indicadores de acceso físico (versión preliminar):** Estos incluyen indicadores de directiva para el acceso físico a activos confidenciales. Por ejemplo, el intento de acceso a un área restringida en los registros del sistema de administración de errores físicos se puede compartir con directivas de administración de riesgos internas. Para recibir estos tipos de alertas en la administración de riesgos de insider, debe tener activos físicos prioritarios habilitados en la administración de riesgos de insider y el conector de datos de protección [física configurado.](import-physical-badging-data.md) Para obtener más información sobre cómo configurar el acceso físico, consulte la sección [Prioridad de acceso físico](#priority-physical-assets-preview) en este artículo.
- **Indicadores de Microsoft Defender para Aplicaciones en la nube (** versión preliminar):Estos incluyen indicadores de directivas de alertas compartidas de Defender para aplicaciones en la nube. La detección de anomalías habilitada automáticamente en Defender para aplicaciones en la nube comienza inmediatamente a detectar y recopilar resultados, destinados a numerosas anomalías de comportamiento entre los usuarios y las máquinas y dispositivos conectados a la red. Para incluir estas actividades en alertas de directivas de administración de riesgos insider, seleccione uno o más indicadores en esta sección. Para obtener más información sobre el análisis de Defender for Cloud Apps y la detección de anomalías, consulta Obtener análisis de [comportamiento y detección de anomalías](/cloud-app-security/anomaly-detection-policy).
- **Aumentadores de** puntuación de riesgo: estos incluyen aumentar la puntuación de riesgo para la actividad que está por encima de la actividad habitual del usuario durante un día o para los usuarios con casos anteriores resueltos como una infracción de la directiva. La habilitación de los aumentadores de puntuación de riesgo aumenta las puntuaciones de riesgo y la probabilidad de alertas para este tipo de actividades. Para la actividad que está por encima de la actividad habitual del usuario durante un día, se aumentan las puntuaciones si la actividad detectada se desvía del comportamiento típico del usuario. Para los usuarios con casos anteriores resueltos como una infracción de directiva, se aumentan las puntuaciones si un usuario ha resuelto anteriormente más de un caso como una infracción de directiva confirmada. Los aumentadores de puntuación de riesgo solo se pueden seleccionar si se seleccionan uno o varios indicadores.

En algunos casos, es posible que desee limitar los indicadores de directiva de riesgo de insider que se aplican a las directivas de riesgo de insider en su organización. Puede desactivar los indicadores de directiva para áreas específicas deshabilitándolos de todas las directivas de riesgo de insider. Los eventos desencadenantes solo se pueden modificar para las directivas creadas a partir de las plantillas *Pérdidas* de datos generales o *Pérdidas de datos por parte de los usuarios prioritarios* . Las directivas creadas a partir de todas las demás plantillas no tienen indicadores ni eventos de activación personalizables.

Para definir los indicadores de directiva de riesgo de insider que están habilitados en todas las directivas de riesgo **insider**, vaya a Configuración de riesgos de **InsiderIndicators** >  y seleccione uno o más indicadores de directiva. Los indicadores seleccionados en la página Configuración de indicadores no se pueden configurar individualmente al crear o editar una directiva de riesgo de insider en el asistente para directivas.

> [!NOTE]
> Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el panel **Usuarios**. Las actividades de los 90 días anteriores de estos usuarios pueden tardar hasta 24 horas en aparecer. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en  el panel Usuarios y abra la pestaña **Actividad de** usuario en el panel de detalles.

### <a name="enable-device-indicators-and-onboard-windows-devices"></a>Habilitar indicadores de dispositivos e incorporar Windows dispositivos
<a name="OnboardDevices"> </a>

Para habilitar la supervisión de actividades de riesgo en dispositivos Windows e incluir indicadores de directiva para estas actividades, los dispositivos Windows deben cumplir los siguientes requisitos y debe completar los siguientes pasos de incorporación.

#### <a name="step-1-prepare-your-endpoints"></a>Paso 1: Preparar los puntos de conexión

Asegúrese de que los dispositivos Windows 10 que planea informar en la administración de riesgos de insider cumplan estos requisitos.

1. Debe ejecutar Windows 10 x64 compilación 1809 o posterior y debe haber instalado la actualización de Windows 10 (compilación del sistema operativo [17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) a partir del 20 de febrero de 2020.
2. La cuenta de usuario usada para iniciar sesión en el dispositivo Windows 10 debe ser una cuenta Azure Active Directory (AAD). El Windows 10 [puede estar AAD](/azure/active-directory/devices/concept-azure-ad-join), híbrido AAD o unido a Active Directory, o AAD registrado.
3. Instale el Microsoft Edge en el dispositivo de punto de conexión para supervisar las acciones de la actividad de carga en la nube. Consulte [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Paso 2: Incorporación de dispositivos
<a name="OnboardStep2"> </a>

Debes habilitar la supervisión de dispositivos e incorporar los puntos de conexión para poder supervisar las actividades de administración de riesgos de información interna en un dispositivo. Ambas acciones se toman en el portal Microsoft 365 cumplimiento.

Cuando quieras incorporar dispositivos que aún no se han incorporado, descargarás el script adecuado e implementarás como se describe en los pasos siguientes.

Si ya tienes dispositivos incorporados en [Microsoft Defender para endpoint](/windows/security/threat-protection/), ya aparecerán en la lista de dispositivos administrados. Siga [el paso 3: Si tiene dispositivos incorporados en Microsoft Defender para endpoint](insider-risk-management-settings.md#OnboardStep3) en la siguiente sección.

En este escenario de implementación, incorporarás dispositivos que aún no se han incorporado y solo quieres supervisar las actividades de riesgo de insider en Windows 10 dispositivos.

1. Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. Abra la página de configuración del Centro de cumplimiento y elija **Incorporar dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. La lista estará vacía hasta que haya incorporado dispositivos.
4. Elija **Incorporación** para iniciar el proceso de incorporación.
5. Elige la forma en que quieres implementar en estos más dispositivos de la **lista Método de** implementación y, a continuación **, descarga el paquete**.
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez que se haya hecho y se incorpore el punto de conexión, debe estar visible en la lista de dispositivos y el punto de conexión empezará a informar de los registros de actividad de auditoría a la administración de riesgos de insider.

> [!NOTE]
> Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Paso 3: Si tienes dispositivos incorporados en Microsoft Defender para endpoint
<a name="OnboardStep3"> </a>

Si Microsoft Defender para endpoint ya está implementado y hay puntos de conexión en los que se informa, todos estos puntos de conexión aparecerán en la lista de dispositivos administrados. Puedes seguir incorporando nuevos dispositivos a la administración de riesgos de insider para ampliar la cobertura mediante la sección [Paso 2: Dispositivos de incorporación](insider-risk-management-settings.md#OnboardStep2) .

1. Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. Abra la página de configuración del Centro de cumplimiento y elija **Habilitar supervisión de dispositivos**.
3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. Debería ver la lista de dispositivos que ya están informando en Microsoft Defender para endpoint.
4. Elige **Incorporación si** necesitas incorporar más dispositivos.
5. Elige la forma en que quieres implementar en estos más dispositivos de la **lista Método de** implementación y, a continuación, **Descarga del paquete**.
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez hecho y el punto de conexión está incorporado, debe estar visible en la tabla **Dispositivos** y el punto de conexión empezará a informar de los registros de actividad de auditoría a la administración de riesgos de insider.

> [!NOTE]
>Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

### <a name="enable-device-indicators-and-onboard-macos-devices"></a>Habilitar indicadores de dispositivos e incorporar dispositivos macOS

Los dispositivos macOS (Catalina 10.15 o posterior) se pueden incorporar a Microsoft 365 para admitir directivas de administración de riesgos internas mediante Intune o JAMF Pro. Para obtener más información y instrucciones de configuración, consulte [Onboard macOS devices into Microsoft 365 overview (preview)](device-onboarding-macos-overview.md).

### <a name="indicator-level-settings-preview"></a>Configuración del nivel del indicador (versión preliminar)

Al crear una directiva en el asistente para directivas, puede configurar cómo el número diario de eventos de riesgo debe influir en la puntuación de riesgo de las alertas de riesgo de insider. Esta configuración de indicador le ayuda a controlar cómo el número de repeticiones de eventos de riesgo en su organización debe afectar a la puntuación de riesgo y, por lo tanto, la gravedad de alerta asociada, para estos eventos. Si lo prefiere, también puede optar por mantener los niveles de umbral de eventos predeterminados recomendados por Microsoft para todos los indicadores habilitados.

Por ejemplo, decide habilitar los indicadores SharePoint en la configuración de directiva de riesgo de insider y establecer umbrales personalizados para eventos SharePoint al configurar indicadores para una nueva directiva de *pérdidas* de datos de riesgo interno. Mientras se encuentra en el Asistente para directivas de riesgo de insider, se configuran tres niveles de eventos diarios diferentes para cada indicador SharePoint para influir en la puntuación de riesgo de las alertas asociadas a estos eventos.

![Configuración del indicador personalizado de administración de riesgos de Insider.](../media/insider-risk-custom-indicators.png)

Para el primer nivel de evento diario, se establece el umbral en *10* o más eventos por día para un menor impacto en la puntuación de riesgo de los eventos, *20* o más eventos por día para un impacto medio en la puntuación de riesgo de los eventos y *30* o más eventos por día un impacto mayor en la puntuación de riesgo para los eventos. Estas configuraciones significan de forma eficaz:

- Si hay de 1 a 9 eventos SharePoint que tienen lugar después de desencadenar el evento, las puntuaciones de riesgo se verán mínimamente afectadas y tienden a no generar una alerta.
- Si hay entre 10 y 19 eventos SharePoint que tienen lugar después de un evento desencadenante, la puntuación de riesgo es inherentemente inferior y los niveles de gravedad de alerta tienden a estar en un nivel bajo.
- Si hay entre 20 y 29 eventos SharePoint que tienen lugar después de un desencadenamiento, la puntuación de riesgo es inherentemente mayor y los niveles de gravedad de alerta tienden a estar en un nivel medio.
- Si hay 30 o más eventos SharePoint que tienen lugar después de un desencadenamiento, la puntuación de riesgo es inherentemente mayor y los niveles de gravedad de alerta tienden a estar en un nivel alto.

## <a name="policy-timeframes"></a>Períodos de tiempo de las directivas

Los períodos de tiempo de las directivas permiten definir períodos de revisión pasados y futuros que se activan después de coincidencias de directivas basadas en eventos y actividades para las plantillas de directivas de administración de riesgos internos. Según la plantilla de directiva que elija, están disponibles los siguientes plazos de directiva:

- **Ventana activación**: disponible para todas las plantillas de directiva, la ventana Activación es el número definido de días que la ventana se activa **después de** un evento desencadenante. La ventana se activa de 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos insider y ha establecido la *ventana* Activación en 30 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante activa la ventana  Activación y la directiva está activa para ese usuario durante 30 días después de que se produjo el evento desencadenante.
- **Detección de actividad pasada**: disponible para todas las plantillas  de directiva, la detección de actividad Pasada es el número definido de días que se activa la ventana antes **de** un evento desencadenante. La ventana se activa de 0 a 90 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos de insider y ha establecido la detección de actividad *pasada* en 90 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante activa la detección de actividad Past y la directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.

![Configuración del período de tiempo de administración de riesgos de Insider.](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecciones inteligentes

La configuración de detección inteligente ayuda a refinar cómo se procesan las detecciones de actividades de riesgo para las alertas. En determinadas circunstancias, es posible que deba definir los tipos de archivo que se deben omitir o desea aplicar un nivel de detección para eventos diarios para aumentar las puntuaciones de riesgo para los usuarios. Usa esta configuración para controlar las exclusiones de tipos de archivo, aumentar la puntuación de riesgo para actividades inusuales y límites de volumen de archivo.

### <a name="file-type-exclusions"></a>Exclusiones de tipos de archivo

Para excluir tipos de archivo específicos de todas las coincidencias de directivas de administración de riesgos insider, escriba extensiones de tipo de archivo separadas por comas. Por ejemplo, para excluir determinados tipos de archivos de música de coincidencias de directivas, puede escribir *aac,mp3,wav,wma* en el campo **Exclusiones de tipos de archivo**. Todas las directivas de administración de riesgos internas omitirán los archivos con estas extensiones.

### <a name="minimum-number-of-daily-events-to-boost-score-for-unusual-activity"></a>Número mínimo de eventos diarios para aumentar la puntuación de actividad inusual

Con esta configuración, se define el número de eventos diarios necesarios para aumentar la puntuación de riesgo de la actividad que se considera inusual para un usuario. Por ejemplo, supongamos que escribes 25 para este refuerzo de riesgos. Si un usuario hace una media de 10 descargas de archivos en los últimos 30 días, pero una directiva detecta que descargó 20 archivos en un día, la puntuación de esa actividad no se incrementará aunque sea inusual para ese usuario porque el número de archivos que descargó ese día fue menor que el número especificado para este refuerzo de riesgos.

### <a name="alert-volume"></a>Volumen de alertas

A las actividades de usuario detectadas por las directivas de riesgo de insider se les asigna una puntuación de riesgo específica, que a su vez determina la gravedad de la alerta (baja, mediana, alta). De forma predeterminada, generaremos una cierta cantidad de alertas de gravedad baja, media y alta, pero puede aumentar o disminuir el volumen según sus necesidades. Para ajustar el volumen de alertas de todas las directivas de administración de riesgos internas, elija una de las siguientes opciones:

- **Menos alertas**: verá todas las alertas de gravedad alta, menos alertas de gravedad media y ninguna de gravedad baja. Este nivel de configuración significa que es posible que se pierdan algunos verdaderos positivos.
- **Volumen predeterminado**: verá todas las alertas de gravedad alta y una cantidad equilibrada de alertas de gravedad media y baja.
- **Más alertas**: verá todas las alertas de gravedad media y alta y la mayoría de las alertas de gravedad baja. Este nivel de configuración puede dar como resultado más falsos positivos.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender para endpoint (versión preliminar)

[Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de extremo de empresa diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de las infracciones de seguridad en su organización, puede importar y filtrar alertas de Defender para puntos de conexión para las actividades que se usan en las directivas creadas a partir de plantillas de directiva de infracción de seguridad de la administración de riesgos insider.

En función de los tipos de señales que te interesan, puedes elegir importar alertas a la administración de riesgos de información interna en función del estado de evaluación de alertas de Defender for Endpoint. Puede definir uno o varios de los siguientes estados de triaje de alertas en la configuración global que se va a importar:

- Unknown
- Nuevo
- En curso
- Resuelto

Las alertas de Defender para endpoint se importan diariamente. Según el estado del triage que elijas, es posible que veas varias actividades de usuario para la misma alerta que los cambios de estado del triage en Defender for Endpoint.

Por ejemplo, si selecciona *Nuevo**, En* curso y Resuelto para  esta configuración, cuando se genera una alerta de Microsoft Defender para extremo y el estado es *Nuevo*, se importa una actividad de alerta inicial para el usuario en riesgo interno. Cuando el estado de evaluación de Defender for Endpoint cambia a *En curso*, se importa una segunda actividad para esta alerta para el usuario en riesgo interno. Cuando se establece el estado final de evaluación de Defender para el extremo de *Resuelto* , se importa una tercera actividad para esta alerta para el usuario en riesgo interno. Esta funcionalidad permite a los investigadores seguir la progresión de las alertas de Defender for Endpoint y elegir el nivel de visibilidad que su investigación requiere.

> [!IMPORTANT]
> Deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains"></a>Dominios

La configuración de dominio le ayuda a definir los niveles de riesgo de las actividades en dominios específicos. Estas actividades incluyen compartir archivos, enviar mensajes de correo electrónico, descargar o cargar contenido. Al especificar dominios en esta configuración, puede aumentar o disminuir la puntuación de riesgo para la actividad que tiene lugar con estos dominios.

Use Agregar dominio para definir un dominio para cada una de las opciones de configuración del dominio. Además, puedes usar caracteres comodín para ayudar a hacer coincidir las variaciones de dominios raíz o subdominios. Por ejemplo, para especificar sales.wingtiptoys.com y support.wingtiptoys.com, se usa la entrada comodín '*.wingtiptoys.com' para coincidir con estos subdominios (y cualquier otro subdominio en el mismo nivel). Para especificar subdominios de varios niveles para un dominio raíz, debe seleccionar la casilla Incluir **subdominios de varios niveles** .

Para cada una de las siguientes opciones de configuración de dominio, puede especificar hasta 500 dominios:

- **Dominios no permitidos:** Al especificar dominios no permitidos, la actividad que tenga lugar con estos dominios tendrá mayores *puntuaciones* de riesgo. Algunos ejemplos son actividades que implican compartir contenido con alguien (como enviar correo electrónico a alguien con una dirección gmail.com) y cuando los usuarios descargan contenido en un dispositivo desde uno de estos dominios no permitidos.
- **Dominios permitidos:** Las directivas omitirán determinadas actividades relacionadas con dominios permitidos y no generarán alertas. Estas actividades incluyen:

    - Correo electrónico enviado a dominios externos
    - Archivos, carpetas, sitios compartidos con dominios externos
    - Archivos cargados en dominios externos (con Microsoft Edge explorador)

    Al especificar dominios permitidos en la configuración, esta actividad con estos dominios se trata de forma similar a la forma en que se trata la actividad de la organización interna. Por ejemplo, los dominios agregados aquí se asignan a actividades que pueden implicar compartir contenido con alguien fuera de la organización (por ejemplo, enviar correo electrónico a alguien con una dirección gmail.com usuario).

- **Dominios de terceros:** Si su organización usa dominios de terceros con fines empresariales (como el almacenamiento en la nube), indójelos aquí para que pueda recibir alertas de actividad relacionadas con el indicador de dispositivo *Use* un explorador para descargar contenido de un sitio de terceros.

## <a name="export-alerts"></a>Exportar alertas

La información de alertas de administración de riesgos de Insider se puede exportar a las soluciones de administración de eventos (SIEM) y de administración de eventos (SIEM) y de orquestación de seguridad (SOAR) mediante el esquema de [la API](/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema) de actividad de administración Office 365 administración. Puede usar las API de Office 365 actividad de administración para exportar información de alerta a otras aplicaciones que su organización puede usar para administrar o agregar información de riesgo de información interna. La información de alerta se exporta y está disponible cada 60 minutos a través Office 365 API de actividad de administración.

Si su organización usa Microsoft Sentinel, también puede usar el conector de datos de administración de riesgos interno para importar información de alerta de riesgo interna a Sentinel. Para obtener más información, [vea Microsoft 365 Insider Risk Management (IRM) (Preview)](/azure/sentinel/data-connectors-reference#microsoft-365-insider-risk-management-irm-preview) en el artículo de Microsoft Sentinel.

>[!IMPORTANT]
>Para mantener la integridad referencial de los usuarios que tienen alertas de riesgo de información interna o casos en Microsoft 365 u otros sistemas, el anonimización de nombres de usuario no se conserva para las alertas exportadas. Las alertas exportadas mostrarán nombres de usuario para cada alerta.

Para usar las API para revisar la información de alerta de riesgo de insider:

1. Habilite la Office 365 api de actividad de administración en las alertas de Configuración **de Insider**. >  >  De forma predeterminada, esta configuración está deshabilitada para su Microsoft 365 organización.
2. Filtre las actividades Office 365 auditoría por *SecurityComplianceAlerts*.
3. Filtrar *SecurityComplianceAlerts* por la *categoría InsiderRiskManagement* .

![Configuración de alertas de exportación de la administración de riesgos insider.](../media/insider-risk-settings-export.png)

La información de alerta contiene información del esquema de alertas de seguridad y cumplimiento y el esquema Office 365 de la API de actividad de administración.

Los siguientes campos y valores se exportan para alertas de administración de riesgos insider para el esquema de alertas de seguridad & cumplimiento:

| **Parámetro Alert** | **Descripción** |
|:------------------|:----------------|
| AlertType | El tipo de alerta es *Personalizado*.  |
| AlertId | GUID de la alerta. Las alertas de administración de riesgos de Insider son mutables. A medida que cambia el estado de alerta, se genera un nuevo registro con el mismo AlertID. Este AlertID se puede usar para correlacionar las actualizaciones de una alerta. |
| Categoría | La categoría de la alerta *es InsiderRiskManagement*. Esta categoría se puede usar para distinguir de estas alertas de otras alertas de seguridad & cumplimiento. |
| Comentarios | Comentarios predeterminados para la alerta. Los valores *son Nueva alerta* (registrada cuando se crea una alerta) y *Alerta actualizada* (registrada cuando hay una actualización de una alerta). Use alertID para correlacionar las actualizaciones de una alerta. |
| Datos | Los datos de la alerta incluyen el identificador de usuario único, el nombre principal del usuario y la fecha y hora (UTC) cuando el usuario se desencadenó en una directiva. |
| Nombre | Nombre de la directiva para la directiva de administración de riesgos insider que generó la alerta. |
| PolicyId | GUID de la directiva de administración de riesgos insider que desencadenó la alerta. |
| Severity | Gravedad de la alerta. Los valores *son High*, *Medium* o *Low*. |
| Origen | El origen de la alerta. El valor es *Office 365 seguridad & cumplimiento*. |
| Estado | El estado de la alerta. Los valores *son Active* (*Needs Review* in insider risk), *Investigating* (*Confirmed* in insider risk), *Resolved* (*Resolved* in insider risk), *Dismissed* (*Dismissed* in insider risk). |
| Versión | La versión del esquema de alerta de seguridad y cumplimiento. |

Los siguientes campos y valores se exportan para alertas de administración de riesgos de insider para el esquema común de la API de Office 365 [actividad de administración](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema).

- UserId
- Id
- RecordType
- CreationTime
- Operación
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuarios prioritarios (versión preliminar)

Los usuarios de la organización pueden tener diferentes niveles de riesgo según su posición, nivel de acceso a información confidencial o historial de riesgos. Priorizar el examen y la puntuación de las actividades de estos usuarios puede ayudarle a alertar sobre posibles riesgos que pueden tener mayores consecuencias para su organización. Los grupos de usuarios prioritarios en la administración de riesgos de insider ayudan a definir los usuarios de la organización que necesitan una inspección más estrecha y una puntuación de riesgos más confidencial. Junto con las infracciones de la directiva de seguridad por parte de los usuarios *prioritarios y las pérdidas* de datos por plantillas de directiva de usuarios prioritarios, los usuarios agregados a un grupo de usuarios prioritarios tienen una mayor probabilidad de *alertas* y alertas de riesgo interno con niveles de gravedad más altos.

![Configuración de grupo de usuarios de prioridad de administración de riesgos insider.](../media/insider-risk-settings-priority-users.png)

En lugar de estar abiertos a la revisión por parte de todos los analistas e investigadores, es posible que los grupos de usuarios prioritarios también necesiten restringir las actividades de revisión a usuarios específicos o grupos de roles de riesgo de insider. Puede elegir asignar usuarios individuales y grupos de roles para revisar usuarios, alertas, casos e informes para cada grupo de usuarios prioritarios. Los grupos de usuarios prioritarios pueden tener permisos de revisión asignados a los grupos de roles integrados *Insider Risk Management*, *Insider Risk Management Analysts* y *Insider Risk Management Investigators* , uno o varios de estos grupos de roles, o a una selección personalizada de usuarios.

Por ejemplo, debe protegerse contra pérdidas de datos para un proyecto altamente confidencial en el que los usuarios tienen acceso a información confidencial. Elige crear el grupo de *usuarios Project* *prioridad* de usuarios confidenciales para los usuarios de la organización que trabajan en este proyecto. Además, este grupo de usuarios prioritario no debe tener usuarios, alertas, casos e informes asociados con el grupo visibles para todos los administradores, analistas e investigadores de administración de riesgos insider predeterminados. En **Configuración**, se crea el grupo Usuarios confidenciales *Project usuarios* prioritarios y se asignan dos usuarios como revisor que pueden ver datos relacionados con los grupos. Con el Asistente para directivas y la plantilla de directiva Pérdidas de datos por usuarios *prioritarios*, se crea una nueva directiva y se asigna a la directiva el grupo Usuarios de prioridad confidencial *Project* Usuarios. Las actividades examinadas por la directiva para los miembros del grupo de usuarios prioritarios de *Project* Confidenciales son más sensibles al riesgo y es más probable que las actividades de estos usuarios generen una alerta y tengan alertas con niveles de gravedad más altos.

### <a name="create-a-priority-user-group"></a>Crear un grupo de usuarios de prioridad

Para crear un nuevo grupo de usuarios de prioridad, usará la configuración de controles en la solución de administración de riesgos **insider** en el Centro de cumplimiento de Microsoft 365. Para crear un grupo de usuarios de prioridad, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin* .

Complete los pasos siguientes para crear un grupo de usuarios de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a Administración de riesgos **de Insider** y selecciona **Configuración de riesgos de Insider**.
2. Seleccione la **página Grupos de usuarios prioritarios (versión** preliminar).
3. En la **página Grupos de usuarios prioritarios (** versión preliminar), seleccione **Crear grupo de usuarios prioritarios** para iniciar el asistente para la creación de grupos.
4. En la **página Nombre y descripción** , complete los siguientes campos:
    - **Nombre (obligatorio):** Escriba un nombre descriptivo para el grupo de usuarios de prioridad. No puede cambiar el nombre del grupo de usuarios de prioridad después de completar el asistente.
    - **Descripción (opcional):** Escriba una descripción para el grupo de usuarios de prioridad.
5. Seleccione **Siguiente** para continuar.
6. En **la página** Elegir miembros, seleccione  Elegir miembros para buscar y seleccione qué cuentas de usuario habilitadas para correo se incluyen en el grupo o active la casilla **Seleccionar** todo para agregar todos los usuarios de la organización al grupo. Seleccione **Agregar** para continuar o **Cancelar** para cerrar sin agregar ningún usuario al grupo.
7. Seleccione **Siguiente** para continuar.
8. En la **página Elegir quién puede ver este** grupo, debe definir quién puede revisar usuarios, alertas, casos e informes para el grupo de usuarios prioritario. Se debe asignar al menos un grupo de roles de administración de riesgos de usuario o insider. Seleccione **Elegir usuarios y grupos de** roles y seleccione los usuarios o grupos de roles de administración de riesgos de insider que desea asignar al grupo de usuarios de prioridad. Seleccione **Agregar** para asignar los usuarios o grupos de roles seleccionados al grupo.
9. Seleccione Siguiente para continuar.
10. En la **página Revisar** , revise la configuración que ha elegido para el grupo de usuarios de prioridad. Seleccione los **vínculos Editar** para cambiar cualquiera de los valores de grupo o seleccione **Enviar** para crear y activar el grupo de usuarios de prioridad.
11. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="update-a-priority-user-group"></a>Actualizar un grupo de usuarios de prioridad

Para actualizar un grupo de usuarios de prioridad existente, usarás la configuración de controles en la solución de administración de riesgos **insider** en el Centro de cumplimiento de Microsoft 365. Para actualizar un grupo de usuarios de prioridad, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin* .

Siga estos pasos para editar un grupo de usuarios prioritario:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a Administración de riesgos **de Insider** y selecciona **Configuración de riesgos de Insider**.
2. Seleccione la **página Grupos de usuarios prioritarios (versión** preliminar).
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Editar grupo**.
4. En la **página Nombre y descripción** , actualice el campo Descripción si es necesario. No puede actualizar el nombre del grupo de usuarios de prioridad. Seleccione **Siguiente** para continuar.
5. En la **página Elegir miembros** , agregue nuevos miembros al grupo mediante el **control Elegir miembros** . Para quitar un usuario del grupo, seleccione la "X" junto al usuario que desea quitar. Seleccione **Siguiente** para continuar.
6. En la **página Elegir quién puede ver** este grupo, agregue o quite usuarios o grupos de roles que puedan revisar usuarios, alertas, casos e informes para el grupo de usuarios prioritario.
7. Seleccione **Siguiente** para continuar.
8. En la **página Revisar** , revise la configuración de actualización que ha elegido para el grupo de usuarios de prioridad. Seleccione los **vínculos Editar** para cambiar cualquiera de los valores de grupo o seleccione **Enviar** para actualizar el grupo de usuarios de prioridad.
9. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="delete-a-priority-user-group"></a>Eliminar un grupo de usuarios de prioridad

Para eliminar un grupo de usuarios de prioridad existente, usarás la configuración de controles en la solución de administración de riesgos **insider** en el Centro de cumplimiento de Microsoft 365. Para eliminar un grupo de usuarios de prioridad, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin* .

> [!IMPORTANT]
> Al eliminar un grupo de usuarios de prioridad, se eliminará de cualquier directiva activa a la que esté asignado. Si elimina un grupo de usuarios de prioridad asignado a una directiva activa, la directiva no contendrá usuarios en el ámbito y estará inactiva y no creará alertas.

Siga estos pasos para eliminar un grupo de usuarios prioritario:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a Administración de riesgos **de Insider** y selecciona **Configuración de riesgos de Insider**.
2. Seleccione la **página Grupos de usuarios prioritarios (versión** preliminar).
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Eliminar en** el menú del panel.
4. En el **cuadro de diálogo** Eliminar, seleccione **Sí** para eliminar el grupo de usuarios de prioridad o **seleccione Cancelar** para volver al panel.

## <a name="priority-physical-assets-preview"></a>Activos físicos prioritarios (versión preliminar)

Identificar el acceso a activos físicos prioritarios y correlacionar la actividad de acceso a eventos de usuario es un componente importante de la infraestructura de cumplimiento. Estos activos físicos representan ubicaciones de prioridad en la organización, como edificios de empresas, centros de datos o salas de servidores. Las actividades de riesgo de Insider pueden asociarse con usuarios que trabajan horas inusuales, intentar acceder a estas áreas confidenciales o seguras no autorizadas y solicitudes de acceso a áreas de alto nivel sin necesidades legítimas.

Con los activos físicos prioritarios [](import-physical-badging-data.md) habilitados y el conector de datos de protección física configurado, la administración de riesgos de insider integra las señales de los sistemas de control físico y acceso con otras actividades de riesgo del usuario. Al examinar patrones de comportamiento en los sistemas de acceso físico y correlacionar estas actividades con otros eventos de riesgo de insider, la administración de riesgos de insider puede ayudar a los investigadores y analistas de cumplimiento a tomar decisiones de respuesta más fundamentadas para las alertas. El acceso a los activos físicos prioritarios se puntua e identifica en los conocimientos de forma diferente al acceso a activos que no son prioritarios.

Por ejemplo, la organización tiene un sistema de mala gestión para los usuarios que supervisa y aprueba el acceso físico a áreas de trabajo normales y de proyectos confidenciales. Tiene varios usuarios trabajando en un proyecto confidencial y estos usuarios volverán a otras áreas de su organización cuando se complete el proyecto. A medida que el proyecto confidencial se acerca a su finalización, desea asegurarse de que el trabajo del proyecto permanece confidencial y de que el acceso a las áreas del proyecto está estrechamente controlado.

Puede habilitar el conector de datos de protección física en Microsoft 365 para importar información de acceso desde el sistema de protección física y especificar activos físicos prioritarios en la administración de riesgos de insider. Al importar información desde el sistema de administración de proyectos y correlacionar la información de acceso físico con otras actividades de riesgo identificadas en la administración de riesgos de información interna, observa que uno de los usuarios del proyecto está accediendo a las oficinas del proyecto después del horario laboral normal y también exporta grandes cantidades de datos a un servicio de almacenamiento en la nube personal desde su área de trabajo normal. Esta actividad de acceso físico asociada a la actividad en línea puede apuntar a posibles robos de datos y los investigadores y analistas de cumplimiento pueden tomar las acciones adecuadas según las circunstancias de este usuario.

![Activos físicos prioritarios de la administración de riesgos de Insider.](../media/insider-risk-settings-priority-assets.png)

### <a name="configure-priority-physical-assets"></a>Configurar activos físicos prioritarios

Para configurar activos físicos prioritarios, configurará el conector de configuración física y usará los controles de configuración en la solución de administración de riesgos **insider** en el Centro de cumplimiento de Microsoft 365. Para configurar activos físicos prioritarios, debe ser miembro del grupo de roles Administración de riesgos de *Insider* o Administración de riesgos *de Insider*.

Siga estos pasos para configurar activos físicos prioritarios:

1. Siga los pasos de configuración para la administración de riesgos insider en [el artículo Introducción a la administración de riesgos insider](insider-risk-management-configure.md) . En el paso 3, asegúrese de configurar el conector de badging físico.

    > [!IMPORTANT]
    > Para que las directivas de administración de riesgos internas usen y correlacionan los datos de señal relacionados con los usuarios que salen y terminan con los datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de Microsoft 365 recursos humanos. Si habilita el conector de protección física sin habilitar el conector de recursos humanos de Microsoft 365, las directivas de administración de riesgos internas solo procesarán eventos para actividades de acceso físico para los usuarios de la organización.

2. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a Administración de riesgos **de Insider** y selecciona Configuración de riesgos de **InsiderPriority** >  **activos físicos**.
3. En la  página Activos físicos prioritarios, puede agregar manualmente los ID de activos físicos que desea supervisar para los eventos de activos importados por el conector de pérdida física o importar un archivo .csv de todos los IDs de activos físicos importados por el conector de badging físico: a) Para agregar manualmente los IDs de activos físicos, elija Agregar activos físicos prioritarios **,**  escriba un identificador de activo físico y, a continuación, **seleccione Agregar**. Escriba otros IDs de activos físicos y, a continuación, **seleccione Agregar activos físicos prioritarios** para guardar todos los activos especificados.
    b) Para agregar una lista de los IDs de activos físicos de un archivo .csv, elija **Importar activos físicos prioritarios**. En el cuadro de diálogo explorador de archivos, seleccione .csv archivo que desea importar y, a continuación, **seleccione Abrir**. Los IDs de activos físicos de .csv archivos se agregan a la lista.
4. Vaya a la **página Indicadores de directiva** **en Configuración**.
5. En la **página Indicadores de** directiva, vaya a la sección **Indicadores** de acceso físico y active la casilla Acceso físico después de la finalización o un acceso fallido **al activo confidencial**.
6. Seleccione **Guardar** para configurar y salir.

### <a name="delete-a-priority-physical-asset"></a>Eliminar un activo físico de prioridad

Para eliminar un activo físico de prioridad existente, usarás la configuración de controles en la solución de administración de riesgos insider en el Centro de cumplimiento de Microsoft 365. Para eliminar un activo físico de prioridad, debe ser miembro del grupo de roles Insider Risk Management o Insider Risk Management Admin.

> [!IMPORTANT]
> La eliminación de un activo físico de prioridad lo elimina del examen por cualquier directiva activa a la que se incluyó anteriormente. Las alertas generadas por actividades asociadas al activo físico de prioridad no se eliminan.

Siga estos pasos para eliminar un activo físico de prioridad:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a Administración de riesgos **de Insider** y selecciona Configuración de riesgos de **InsiderPriority** >  **activos físicos**.
2. En la **página Activos físicos prioritarios** , seleccione el activo que desea eliminar.
3. Seleccione **Eliminar** en el menú de acciones para eliminar el activo.

## <a name="power-automate-flows-preview"></a>Power Automate flujos (versión preliminar)

[Microsoft Power Automate](/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar tareas comunes asociadas con estas aplicaciones y servicios. Al habilitar los flujos Power Automate para la administración de riesgos de información interna, puede automatizar tareas importantes para los casos y los usuarios. Puede configurar los flujos de Power Automate para recuperar información de usuarios, alertas y casos y compartir esta información con las partes interesadas y otras aplicaciones, así como automatizar acciones en la administración de riesgos de insider, como publicar en notas de caso. Power Automate se aplican a los casos y a cualquier usuario en el ámbito de una directiva.

Los clientes Microsoft 365 suscripciones que incluyan la administración de riesgos de insider no necesitan licencias de Power Automate adicionales para usar las plantillas de administración de riesgos Power Automate insider recomendadas. Estas plantillas se pueden personalizar para admitir su organización y cubrir los escenarios principales de administración de riesgos de insider. Si elige usar características de Power Automate premium en estas plantillas, cree una plantilla personalizada con el conector de cumplimiento de Microsoft 365 o use plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, puede que necesite más licencias Power Automate.

Las siguientes Power Automate se proporcionan a los clientes para admitir la automatización de procesos para los usuarios y casos de administración de riesgos de insider:

- Notificar a los usuarios cuando se agregan a una directiva de riesgos de **insider**: esta plantilla es para organizaciones que tienen directivas internas, privacidad o requisitos normativos que los usuarios deben recibir una notificación cuando están sujetos a directivas de administración de riesgos internas. Cuando este flujo se configura y selecciona para un usuario en la  página Usuarios, los usuarios y sus administradores se envían un mensaje de correo electrónico cuando el usuario se agrega a una directiva de administración de riesgos de insider. Esta plantilla también admite la actualización de una lista SharePoint hospedada en un sitio de SharePoint para ayudar a realizar un seguimiento de los detalles de los mensajes de notificación, como la fecha y hora y el destinatario del mensaje. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad, los** flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Power Automate flujos con esta plantilla están disponibles en el panel **Usuarios**.
- **Solicitar** información de recursos humanos o empresas sobre un usuario en un caso de riesgo interno: al actuar en un caso, es posible que los analistas de riesgos e investigadores de insider deban consultar con recursos humanos u otras partes interesadas para comprender el contexto de las actividades del caso. Cuando este flujo se configura y selecciona para un caso, los analistas e investigadores envían un mensaje de correo electrónico a las partes interesadas de recursos humanos y empresariales configuradas para este flujo. A cada destinatario se le envía un mensaje con opciones de respuesta preconfiguradas o personalizables. Cuando los destinatarios seleccionan una opción de respuesta, la respuesta se registra como una nota de caso e incluye información de fecha y hora y destinatario. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad, los** flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Power Automate flujos con esta plantilla están disponibles en el panel **Casos**.
- **Notificar al administrador cuando un usuario** tiene una alerta de riesgo de información interna: es posible que algunas organizaciones necesiten recibir una notificación de administración inmediata cuando un usuario tiene una alerta de administración de riesgos de información interna. Cuando se configura y selecciona este flujo, se envía un mensaje de correo electrónico al administrador del usuario del caso con la siguiente información sobre todas las alertas de caso:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

    El flujo actualiza automáticamente las notas de caso que el mensaje se envió y que se activó el flujo. Si ha elegido anonimizar a los usuarios en la configuración de **privacidad, los** flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Power Automate flujos con esta plantilla están disponibles en el panel **Casos**.
- **Cree un registro para casos de riesgo de insider en ServiceNow**: esta plantilla es para las organizaciones que desean usar su solución ServiceNow para realizar un seguimiento de los casos de administración de riesgos de insider.  Cuando en un caso, los analistas e investigadores de riesgos de insider pueden crear un registro para el caso en ServiceNow. Puede personalizar esta plantilla para rellenar campos seleccionados en ServiceNow en función de los requisitos de su organización. Power Automate flujos con esta plantilla están disponibles en el panel **Casos**. Para obtener más información sobre los campos de ServiceNow disponibles, consulte el [artículo de referencia de ServiceNow Connector](/connectors/service-now/) .

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Crear un flujo Power Automate de la plantilla de administración de riesgos insider

Para crear un flujo Power Automate a partir de una plantilla de administración de riesgos insider recomendada, usará los controles de configuración de la solución de administración de riesgos **Insider** en la opción Centro de cumplimiento de Microsoft 365 o administrar flujos **de Power Automate** desde **Automate**  control cuando se trabaja directamente en los **paneles Casos** **o Usuarios**.

Para crear un flujo Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin*. Para crear un flujo Power Automate con la opción Administrar **flujos de Power Automate**, debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para crear un flujo Power Automate de una plantilla de administración de riesgos insider recomendada:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos **de Insider** y seleccione Configuración de riesgos de **Insider** >  **Power Automate flujos**. También puede acceder desde las páginas **de** paneles **Casos** o Usuarios **seleccionando AutomateManage** >  **Power Automate flujos**.
2. En la **página Power Automate flujos**, seleccione una plantilla recomendada en las plantillas de administración de riesgos de Insider que le pueden **gustar** en la página.
3. El flujo enumera las conexiones incrustadas necesarias para el flujo y tendrá en cuenta si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestran como disponibles. Seleccione **Continuar**.
4. De forma predeterminada, los flujos recomendados están preconfigurados con la administración de riesgos insider recomendada y Microsoft 365 campos de datos de servicio necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar** opciones avanzadas y configurando las propiedades disponibles para el componente de flujo.
5. Si es necesario, agregue cualquier otro paso al flujo seleccionando el **botón Nuevo** paso. En la mayoría de los casos, esto no debe ser necesario para las plantillas predeterminadas recomendadas.
6. Seleccione **Guardar borrador** para guardar el flujo para una configuración adicional o **seleccione Guardar** para completar la configuración del flujo.
7. Seleccione **Cerrar** para volver a la **página Power Automate flujo**. La nueva plantilla aparecerá como un flujo en las pestañas  Mis flujos y estará disponible automáticamente en el control desplegable **Automatizar** al trabajar con casos de administración de riesgos insider para el usuario que crea el flujo.

> [!IMPORTANT]
> Si otros usuarios de la organización necesitan acceso al flujo, el flujo debe compartirse.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Crear un flujo de Power Automate personalizado para la administración de riesgos de insider

Algunos procesos y flujos de trabajo de su organización pueden estar fuera de las plantillas de flujo de administración de riesgos insider recomendadas y es posible que tenga la necesidad de crear flujos de Power Automate personalizados para áreas de administración de riesgos internos. Power Automate flujos son flexibles y admiten una personalización extensa, pero hay pasos que deben realizarse para integrarse con las características de administración de riesgos de insider.

Siga estos pasos para crear una plantilla de Power Automate personalizada para la administración de riesgos de insider:

1. **Compruebe su Power Automate de flujo** de correo electrónico: para crear flujos de Power Automate personalizados que usan desencadenadores de administración de riesgos insider, necesitará una Power Automate personalizada. Las plantillas de flujo de administración de riesgos insider recomendadas no requieren licencias adicionales y se incluyen como parte de la licencia de administración de riesgos de insider.
2. **Crear un flujo automatizado**: cree un flujo que realice una o varias tareas después de que se desencadene mediante un evento de administración de riesgos interno. Para obtener más información sobre cómo crear un flujo automatizado, consulte [Create a flow in Power Automate](/power-automate/get-started-logic-flow).
3. **Seleccione el Microsoft 365 de cumplimiento**: busque y seleccione el Microsoft 365 de cumplimiento. Este conector habilita acciones y desencadenadores de administración de riesgos insider. Para obtener más información sobre los conectores, consulte el [artículo información general sobre la referencia de](/connectors/connector-reference/) conector.
4. **Elija desencadenadores de administración de riesgos insider para el flujo**: la administración de riesgos de Insider tiene dos desencadenadores disponibles para flujos de Power Automate personalizados:
    - **Para un caso de administración de riesgos insider** seleccionado: los flujos con este desencadenador se pueden seleccionar en la página del panel De casos de administración de riesgos de insider.
    - **Para un usuario de administración de riesgos interno** seleccionado: los flujos con este desencadenador se pueden seleccionar en la página del panel de usuarios de administración de riesgos de insider.
5. Elija acciones de administración de riesgos de insider para su flujo: puede elegir entre varias acciones para que la administración de riesgos insider incluya en el flujo personalizado:
    - Obtener alerta de administración de riesgos de insider
    - Obtener un caso de administración de riesgos interno
    - Obtener usuario de administración de riesgos interno
    - Obtener alertas de administración de riesgos de información interna para un caso
    - Agregar nota de caso de administración de riesgos insider

### <a name="share-a-power-automate-flow"></a>Compartir un flujo Power Automate de datos

De forma predeterminada, Power Automate flujos creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de administración de riesgos de insider tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usará los controles de configuración de la solución de administración de riesgos **Insider** en la opción Centro de cumplimiento de Microsoft 365 o administrar flujos **de Power Automate** desde el control Automatizar cuando trabaje directamente en las páginas del panel Casos o  Usuarios. Una vez que haya compartido un flujo, todos los usuarios con los que se ha compartido pueden tener acceso al flujo en el menú desplegable  **Automatizar control de** los paneles Caso **y Usuario**.

Para compartir un flujo Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin*. Para compartir un flujo Power Automate con la opción Administrar **flujos de Power Automate**, debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para compartir un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos **de Insider** y seleccione Configuración de riesgos de **Insider** >  **Power Automate flujos**. También puede acceder desde las páginas **de** paneles **Casos** o Usuarios **seleccionando AutomateManage** >  **Power Automate flujos**.
2. En la **página Power Automate flujos**, seleccione la **pestaña Mis flujos** o **Flujos de** equipo.
3. Seleccione el flujo que desea compartir y, a continuación, **seleccione Compartir** en el menú opciones de flujo.
4. En la página de uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario del flujo.
5. En el **cuadro de diálogo Conexión usada** , seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso total al flujo.

### <a name="edit-a-power-automate-flow"></a>Editar un flujo Power Automate datos

Para editar un flujo, usará los controles de configuración de la solución de administración de riesgos **insider** en la opción Centro de cumplimiento de Microsoft 365 o administrar flujos **de Power Automate** desde el control **Automatizar** al trabajar directamente en los paneles **Casos o Usuarios**.

Para editar un flujo Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin*. Para editar un flujo Power Automate con la opción Administrar **flujos de Power Automate**, debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para editar un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos **de Insider** y seleccione Configuración de riesgos de **Insider** >  **Power Automate flujos**. También puede acceder desde las páginas **de** paneles **Casos** o Usuarios **seleccionando AutomateManage** >  **Power Automate flujos**.
2. En la **Power Automate flujos** de flujo, seleccione un flujo para editar y **seleccione Editar** en el menú control de flujo.
3. Seleccione los **puntos suspensivos** >  **Configuración** para cambiar una configuración de componente de flujo o **puntos** >  suspensivosDelete para eliminar un componente de flujo.
4. Seleccione **Guardar** y, a continuación, **Cerrar** para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminar un flujo Power Automate datos

Para eliminar un flujo, usará los controles de configuración de la solución de administración de riesgos **Insider** en Centro de cumplimiento de Microsoft 365 o la opción Administrar flujos **de Power Automate** del control **Automatizar** al trabajar directamente en los paneles **Casos o Usuarios**. Cuando se elimina un flujo, se quita como una opción para todos los usuarios.

Para eliminar un flujo Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Admin*. Para eliminar un flujo Power Automate con la opción Administrar **Power Automate flujos**, debe ser miembro de al menos un grupo de roles de administración de riesgos interno.

Siga estos pasos para eliminar un flujo Power Automate datos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a Administración de riesgos **de Insider** y seleccione Configuración de riesgos de **Insider** >  **Power Automate flujos**. También puede acceder desde las páginas **de** paneles **Casos** o Usuarios **seleccionando AutomateManage** >  **Power Automate flujos**.
2. En la **página Power Automate flujos** de flujo, seleccione un flujo que desea eliminar y **seleccione Eliminar en** el menú control de flujo.
3. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o **seleccione Cancelar** para salir de la acción de eliminación.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (versión preliminar)

Los analistas e investigadores de cumplimiento pueden usar fácilmente Microsoft Teams colaboración en casos de administración de riesgos de información interna. Pueden coordinar y comunicarse con otras partes interesadas en Microsoft Teams para:

- Coordinar y revisar las actividades de respuesta para casos en canales Teams privados
- Compartir y almacenar archivos y pruebas de forma segura relacionados con casos individuales
- Seguimiento y revisión de las actividades de respuesta de analistas e investigadores

Después Microsoft Teams para la administración de riesgos de insider, se crea un equipo de Microsoft Teams dedicado cada vez que se confirma una alerta y se crea un caso. De forma predeterminada, el equipo incluye automáticamente todos los miembros de los grupos de roles *Insider Risk Management*, *Insider Risk Management Analysts* y *Insider Risk Management Investigators* (hasta 100 usuarios iniciales). Es posible que se agregarán colaboradores de organización adicionales al equipo después de su creación y según corresponda. Para los casos existentes creados antes de habilitar Microsoft Teams, los analistas e investigadores pueden elegir crear un nuevo equipo de Microsoft Teams al trabajar en un caso si es necesario.  Una vez resuelto el caso asociado en la administración de riesgos de insider, el equipo se archiva automáticamente (se mueve a oculto y de solo lectura).

Para obtener más información sobre cómo usar equipos y canales en Microsoft Teams, vea [Overview of teams and channels in Microsoft Teams](/MicrosoftTeams/teams-channels-overview).

Habilitar Microsoft Teams para casos es rápido y fácil de configurar. Para habilitar Microsoft Teams para la administración de riesgos de insider, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a **Insider risk managementInsider** >  **risk settings**.
2. Seleccione la **Microsoft Teams** página.
3. Habilite Microsoft Teams integración para la administración de riesgos de insider.
4. Seleccione **Guardar** para configurar y salir.

![Administración de riesgos insider Microsoft Teams.](../media/insider-risk-settings-teams.png)

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Crear un equipo Microsoft Teams para casos existentes

Si habilita la Microsoft Teams para la administración de riesgos de insider después de tener casos existentes, deberá crear manualmente un equipo para cada caso según sea necesario. Después de habilitar Microsoft Teams en la configuración de administración de riesgos insider, los nuevos casos crearán automáticamente un nuevo Microsoft Teams equipo.

Los usuarios necesitan permiso para crear grupos Microsoft 365 en la organización para crear un equipo Microsoft Teams a partir de un caso. Para obtener más información acerca de la administración de permisos para Microsoft 365 grupos, vea [Administrar quién puede crear Microsoft 365 grupos](../solutions/manage-creation-of-groups.md).

Para crear un equipo para un caso, usará el control Crear equipo de Microsoft cuando trabaje directamente en un caso existente. Siga estos pasos para crear un nuevo equipo:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Insider risk** **managementCases** >  y seleccione un caso existente.
2. En el menú acción de caso, seleccione **Crear Microsoft Team**.
3. En el **campo Nombre de** equipo, escriba un nombre para el nuevo Microsoft Teams equipo.
4. Seleccione **Crear equipo de Microsoft** y, a continuación, **seleccione Cerrar**.

Según el número de usuarios asignados a grupos de roles de administración de riesgos de insider, puede tardar 15 minutos en agregarse al equipo de Microsoft Teams para un caso.

## <a name="analytics"></a>Análisis

Los análisis de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Los exámenes de análisis ofrecen las siguientes ventajas para su organización:

- Fácil de configurar: para empezar con los exámenes de análisis, puede seleccionar Ejecutar examen cuando se le solicite la recomendación de análisis o ir a Configuración de riesgos de **InsiderAnalytics**  >  y habilitar análisis.
- Privacidad por diseño: los resultados del examen y las perspectivas se devuelven como actividad de usuario agregada y anonimizada, los revisores no identifican los nombres de usuario individuales.
- Comprender los posibles riesgos a través de información consolidada: los resultados del examen pueden ayudarle a identificar rápidamente las posibles áreas de riesgo para los usuarios y qué directiva sería mejor para ayudar a mitigar estos riesgos.

Consulte el vídeo análisis de administración de riesgos de Insider para comprender cómo los análisis pueden ayudar a acelerar la identificación de posibles riesgos de [insider](https://www.youtube.com/watch?v=5c0P5MCXNXk) y ayudarle a tomar medidas rápidamente.

El análisis busca eventos de actividad de riesgo de varios orígenes para ayudar a identificar información sobre posibles áreas de riesgo. Según la configuración actual, el análisis busca actividades de riesgo que califiquen en las siguientes áreas:

- **Microsoft 365 registros de auditoría**: incluidos en todos los exámenes, este es el origen principal para identificar la mayoría de las actividades potencialmente arriesgadas.
- **Exchange Online**: incluida en todos los exámenes, la actividad Exchange Online ayuda a identificar actividades en las que los datos adjuntos se enviarán por correo electrónico a los servicios o contactos externos.
- **Azure Active Directory**: incluido en todos los exámenes, el historial Azure Active Directory ayuda a identificar actividades de riesgo asociadas con usuarios con cuentas de usuario eliminadas.
- **Microsoft 365 de datos de** recursos humanos: si están configurados, los eventos del conector de RECURSOS humanos ayudan a identificar actividades de riesgo asociadas con usuarios que tienen dimisión o próximas fechas de terminación.

La información de análisis de los exámenes se basa en las mismas señales de actividad de riesgo que usan las directivas de administración de riesgos internas y los resultados de informes basados en actividades de usuario de secuencia y únicas. Sin embargo, la puntuación de riesgos para el análisis se basa en hasta 30 días de actividad, mientras que las directivas de riesgo de insider usan la actividad diaria para obtener información. Cuando habilite y ejecute análisis por primera vez en su organización, verá los resultados del examen durante un día. Si dejas el análisis habilitado, verás los resultados de cada examen diario agregados a los informes de información para un intervalo máximo de los 30 días anteriores de actividad.

### <a name="enable-analytics-and-start-your-scan"></a>Habilitar análisis e iniciar el examen

Para habilitar el análisis de riesgos de insider, debe ser miembro del grupo de roles de administración global *insider Risk Management*, *Insider Risk Management Admin* *o Microsoft 365 Global admin*.
Siga estos pasos para habilitar el análisis de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Seleccione **Ejecutar examen en** **la pestaña Examinar los riesgos de insider en** la tarjeta de **la organización en** la pestaña Información general sobre la administración de riesgos de insider. Esto activa el análisis de la organización. También puede activar el examen en su organización navegando a Configuración de riesgos de **InsiderAnalytics** y habilitando Examinar la actividad del usuario del inquilino para identificar **posibles** riesgos de **insider** > .
3. En el **panel de detalles de Analytics** , seleccione **Ejecutar examen** para iniciar el examen de su organización. Los resultados del análisis pueden tardar hasta 48 horas antes de que la información esté disponible como informes para su revisión.

![Configuración de análisis de administración de riesgos de Insider.](../media/insider-risk-settings-analytics-enable.png)

### <a name="viewing-analytics-insights-and-creating-new-policies"></a>Visualización de información de análisis y creación de nuevas directivas

Una vez completado el primer examen de análisis para su organización, puede ver los conocimientos y recomendaciones de las actividades potencialmente arriesgadas por los usuarios. Los exámenes diarios continuarán a menos que desactives los análisis de tu organización. Para ver posibles riesgos para su organización, vaya a la  pestaña Información general y seleccione **Ver** resultados en la tarjeta de análisis de riesgos **de Insider**. Si el examen de la organización no se ha completado, verá un mensaje que indica que el examen sigue activo.

![Tarjeta lista para informes de análisis de administración de riesgos de Insider.](../media/insider-risk-analytics-ready-card.png)

Para los exámenes completados, verá los posibles riesgos detectados en su organización y los conocimientos y recomendaciones para abordar estos riesgos. Los riesgos identificados y los conocimientos específicos se incluyen en los informes agrupados por área, el número total de usuarios con riesgos identificados, el porcentaje de estos usuarios con actividades potencialmente arriesgadas y una directiva de riesgos insider recomendada para ayudar a mitigar estos riesgos. Los informes incluyen:

- **Información sobre pérdidas** de datos: actividades para todos los usuarios que pueden incluir el exceso accidental de información fuera de la organización o pérdidas de datos por parte de usuarios con intenciones malintencionadas.
- **Información sobre** el robo de datos: actividades para usuarios que salen o usuarios con cuentas de Azure Active Directory eliminadas que pueden incluir el uso compartido arriesgado de información fuera de la organización o el robo de datos por parte de usuarios con intenciones malintencionadas.
- **Información de exfiltración** superior: actividades de todos los usuarios que pueden incluir el uso compartido de datos fuera de la organización.

![Informe de información general de análisis de administración de riesgos de Insider.](../media/insider-risk-analytics-overview.png)

Para mostrar más información para una información, seleccione **Ver detalles** para mostrar el panel de detalles de la información. El panel de detalles incluye los resultados completos de la información, una recomendación de directiva  de riesgo interno y el botón Crear directiva para ayudarle a crear rápidamente la directiva recomendada. Si selecciona Crear directiva, se le llevará al Asistente para directivas y seleccionará automáticamente la plantilla de directiva recomendada relacionada con la información. Por ejemplo, si la información de análisis es para la actividad *de* pérdida de datos, la plantilla de directiva de *pérdidas* de datos generales se seleccionará previamente en el asistente para directivas.

![Informe de detalles de análisis de administración de riesgos de Insider.](../media/insider-risk-analytics-details.png)

### <a name="turn-off-analytics"></a>Desactivar análisis

Para desactivar el análisis de riesgos de insider, debe ser miembro del grupo de roles de administración global *insider Risk Management*, *Insider Risk Management Admin* o Microsoft 365 *Global admin*. Después de deshabilitar el análisis, los informes de información de análisis permanecerán estáticos y no se actualizarán para nuevos riesgos.

Complete los siguientes pasos para desactivar el análisis de riesgos de insider:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Selecciona **Configuración de riesgos de** >  **InsiderAnalytics** página.
3. En la **página Análisis** , desactiva Examinar la actividad de usuario del inquilino **para identificar posibles riesgos de insider**.

## <a name="admin-notifications"></a>Notificaciones de administrador

Las notificaciones de administrador envían automáticamente una notificación por correo electrónico a los usuarios incluidos en los grupos de roles *Insider Risk Management*, *Insider Risk Management Analysts* e *Insider Risk Management Investigators* cuando se genera la primera alerta para una nueva directiva. Esto está habilitado de forma predeterminada para todas las organizaciones y las directivas se comprueban cada 24 horas para las alertas de primera vez. Las notificaciones no se envían para las alertas que se producen en las directivas después de la primera alerta.

Si prefiere deshabilitar las notificaciones de administrador, siga estos pasos:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), ve a **Insider risk managementInsider** >  **risk settings**.
2. Seleccione la **página Notificaciones de administrador** .
3. Desactive la **casilla Enviar un correo electrónico de** notificación cuando se genere la primera alerta para una nueva directiva.
4. Seleccione **Guardar** para configurar y salir.

![Configuración de notificaciones de administración de riesgos de Insider.](../media/insider-risk-admin-notifications.png)
