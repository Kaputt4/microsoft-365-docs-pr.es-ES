---
title: Configuración de administración de riesgos internos
description: Más información sobre la configuración de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 5e9f9eb04d2fb239c69aacd8927cde7f295c7716
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787548"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introducción a la configuración de administración de riesgos internos

La configuración de administración de riesgos internos se aplica a todas las directivas de administración de riesgos internos, independientemente de la plantilla que elija al crear una directiva. La configuración se configura mediante el control **de configuración de riesgo insider** ubicado en la parte superior de todas las páginas de administración de riesgos internos. Esta configuración controla los componentes de directiva para las siguientes áreas:

- [Privacidad](#privacy)
- [Indicadores](#indicators)
- [Períodos de tiempo de las directivas](#policy-timeframes)
- [Detecciones inteligentes](#intelligent-detections)
- [Exportar alertas](#export-alerts)
- [Grupos de usuarios prioritarios (versión preliminar)](#priority-user-groups-preview)
- [Activos físicos prioritarios (versión preliminar)](#priority-physical-assets-preview)
- [Flujos de Power Automate (versión preliminar)](#power-automate-flows-preview)
- [Microsoft Teams (versión preliminar)](#microsoft-teams-preview)
- [Análisis](#analytics)
- [notificaciones de Administración](#admin-notifications)

Antes de empezar a trabajar y crear directivas de administración de riesgos internos, es importante comprender esta configuración y elegir los niveles de configuración que mejor se adapten a las necesidades de cumplimiento de su organización.

## <a name="privacy"></a>Privacidad

Proteger la privacidad de los usuarios que tienen coincidencias de directivas es importante y puede ayudar a promover la objetividad en las revisiones de análisis e investigaciones de datos de alertas de riesgos internos. Para los usuarios con una coincidencia de directiva de riesgo interno, puede elegir una de las siguientes opciones:

- **Mostrar versiones anónimas de nombres de usuario**: los nombres de los usuarios se anonimizan para evitar que los administradores, investigadores de datos y revisores vean quién está asociado a las alertas de directiva. Por ejemplo, el usuario “Grace Taylor” aparecería con un pseudónimo aleatorizado, como “AnonIS8-988” en todas las áreas relacionadas con la experiencia de administración de riesgos internos. Al elegir esta configuración, se anonimizan todos los usuarios con coincidencias de directivas actuales y pasadas, y se aplica a todas las directivas. La información del perfil de usuario en la alerta de riesgo interno y los detalles del caso no estarán disponibles cuando se elija esta opción. Sin embargo, los nombres de usuario se muestran al agregar nuevos usuarios a directivas existentes o al asignar usuarios a nuevas directivas. Si decide desactivar esta configuración, se mostrarán nombres de usuario para todos los usuarios que tengan coincidencias de directivas actuales o anteriores.

    >[!IMPORTANT]
    >Para mantener la integridad referencial de los usuarios que tienen alertas o casos de riesgo internos en Microsoft 365 u otros sistemas, no se conserva el anonimato de los nombres de usuario para las alertas exportadas. Las alertas exportadas mostrarán los nombres de usuario de cada alerta.

- **No muestre versiones anonimizadas de nombres de usuario**: los nombres de usuario se muestran para todas las coincidencias de directivas actuales y anteriores para alertas y casos. La información del perfil de usuario (el nombre, el título, el alias y la organización o el departamento) se muestra para el usuario para todas las alertas y casos de administración de riesgos internos.

![Configuración de privacidad de administración de riesgos internos.](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Las plantillas de directivas de riesgo internos definen el tipo de actividades de riesgo que desea detectar e investigar. Cada plantilla de directiva se basa en indicadores específicos que corresponden a desencadenadores y actividades de riesgo específicos. Todos los indicadores están deshabilitados de forma predeterminada y debe seleccionar uno o varios indicadores de directiva antes de configurar una directiva de administración de riesgos internos.

Las alertas las desencadenan las directivas cuando los usuarios realizan actividades relacionadas con indicadores de directiva que cumplen un umbral necesario. La administración de riesgos internos usa dos tipos de indicadores:

- **Desencadenamiento de eventos**: eventos que determinan si un usuario está activo en una directiva de administración de riesgos internos. Si un usuario se agrega a una directiva de administración de riesgos internos no tiene un evento desencadenante, la directiva no evalúa la actividad del usuario. Por ejemplo, el usuario A se agrega a una directiva creada a partir del robo de datos mediante la plantilla de directiva de *usuarios que abandonan* y la directiva y el conector de RR. HH. de Microsoft 365 están configurados correctamente. Hasta que el usuario A tenga una fecha de finalización notificada por el conector de RR. HH., las actividades del usuario A no se evalúan mediante esta directiva de administración de riesgos internos para el riesgo. Otro ejemplo de un evento desencadenante es si un usuario tiene una alerta de directiva DLP de *gravedad alta* cuando se usan *directivas de pérdida de datos* .
- **Indicadores de directiva:** indicadores incluidos en las directivas de administración de riesgos internos que se usan para determinar una puntuación de riesgo para un usuario dentro del ámbito. Estos indicadores de directiva solo se activan después de que se produzca un evento desencadenante para un usuario. Algunos ejemplos de indicadores de directiva son cuando un usuario copia datos en servicios de almacenamiento en la nube personales o dispositivos de almacenamiento portátiles, si se quita una cuenta de usuario de Azure Active Directory o si un usuario comparte archivos y carpetas internos con entidades externas no autorizadas.

También se pueden usar determinados indicadores de directiva para personalizar eventos desencadenantes para plantillas de directiva específicas. Cuando se configura en el Asistente para directivas para las plantillas *Pérdidas generales de datos* o *Pérdidas de datos por parte de usuarios prioritarios* , estos indicadores le permiten más flexibilidad y personalización para las directivas y cuando los usuarios están en el ámbito de una directiva. Además, puede definir umbrales de actividad individuales para estos indicadores desencadenantes para un control más preciso en una directiva.

Los indicadores de directiva se segmentan en las áreas siguientes. Puede elegir los indicadores para activar y personalizar los límites de eventos del indicador para cada nivel de indicador al crear una directiva de riesgo interno:

- **Indicadores de Office**: incluyen indicadores de directiva para sitios de SharePoint, Microsoft Teams y mensajería de correo electrónico.
- **Indicadores de dispositivo**: incluyen indicadores de directiva para la actividad, como compartir archivos a través de la red o con dispositivos. Los indicadores incluyen actividades que implican todos los tipos de archivo, excepto la actividad de archivo ejecutable (.exe) y la biblioteca de vínculos dinámicos (.dll). Si selecciona *Indicadores de* dispositivo, la actividad se procesa para dispositivos con Windows 10 Compilación 1809 o posterior y dispositivos macOS (Catalina 10.15 o posterior). Para dispositivos Windows y macOS, primero debe incorporar dispositivos al portal de cumplimiento. Los indicadores de dispositivo también incluyen la detección de señales del explorador para ayudar a su organización a detectar y actuar sobre señales de filtración para archivos no ejecutables vistos, copiados, compartidos o impresos en Microsoft Edge y Google Chrome. Para obtener más información sobre cómo configurar dispositivos Windows para la integración con el riesgo interno, consulte la siguiente sección [Habilitación de indicadores de dispositivo e incorporación de dispositivos Windows](insider-risk-management-settings.md#OnboardDevices) en este artículo. Para obtener más información sobre cómo configurar dispositivos macOS para la integración con el riesgo interno, consulte la siguiente sección Habilitación de indicadores de dispositivo e incorporación de dispositivos macOS en este artículo. Para obtener más información sobre la detección de señales del explorador, consulte [Información sobre y configuración de la detección de señales del explorador de administración de riesgos internos](insider-risk-management-browser-support.md).
- **Indicador de infracción de directiva de seguridad (versión preliminar):** estos incluyen indicadores de Microsoft Defender para punto de conexión relacionados con la instalación de software no aprobada o malintencionada o la omisión de los controles de seguridad. Para recibir alertas en la administración de riesgos internos, debe tener habilitada una licencia de Defender para punto de conexión activa e integración de riesgos internos. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de administración de riesgos internos, consulte [Configuración de características avanzadas en Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Indicadores de acceso a registros de salud (versión preliminar):** estos incluyen indicadores de directiva para el acceso a los registros médicos de los pacientes. Por ejemplo, el intento de acceso a los registros médicos de los pacientes en los registros electrónicos del sistema de registros médicos (EMR) se puede compartir con las directivas de atención sanitaria de administración de riesgos internos. Para recibir estos tipos de alertas en la administración de riesgos internos, debe tener configurado un conector de datos específico del sector sanitario y el conector de datos de RR. HH.
- **Indicadores de acceso físico (versión preliminar):** incluyen indicadores de directiva para el acceso físico a los recursos confidenciales. Por ejemplo, el intento de acceso a un área restringida en los registros del sistema físico de badging se puede compartir con directivas de administración de riesgos internos. Para recibir estos tipos de alertas en la administración de riesgos internos, debe tener habilitados los recursos físicos prioritarios en la administración de riesgos internos y el [conector de datos de errores físicos](import-physical-badging-data.md) configurados. Para más información sobre cómo configurar el acceso físico, consulte la [sección Acceso físico prioritario](#priority-physical-assets-preview) de este artículo.
- **Microsoft Defender for Cloud Apps indicadores (versión preliminar):** incluyen indicadores de directivas de alertas compartidas de Defender for Cloud Apps. La detección de anomalías habilitada automáticamente en Defender for Cloud Apps comienza inmediatamente a detectar y intercalar resultados, apuntando a numerosas anomalías de comportamiento entre los usuarios y las máquinas y dispositivos conectados a la red. Para incluir estas actividades en alertas de directivas de administración de riesgos internos, seleccione uno o varios indicadores en esta sección. Para más información sobre el análisis y la detección de anomalías de Defender for Cloud Apps, consulte [Obtención de análisis de comportamiento y detección de anomalías](/cloud-app-security/anomaly-detection-policy).
- **Refuerzos de la puntuación de riesgo**: estos incluyen aumentar la puntuación de riesgo para la actividad que está por encima de la actividad habitual del usuario durante un día o para los usuarios con casos anteriores resueltos como una infracción de la directiva. Habilitar refuerzos de puntuación de riesgo aumenta las puntuaciones de riesgo y la probabilidad de alertas para estos tipos de actividades. En el caso de la actividad que está por encima de la actividad habitual del usuario durante un día, se aumentan las puntuaciones si la actividad detectada se desvía del comportamiento típico del usuario. En el caso de los usuarios con casos anteriores resueltos como infracción de directiva, se aumentan las puntuaciones si un usuario tenía más de un caso resuelto anteriormente como una infracción de directiva confirmada. Los refuerzos de puntuación de riesgo solo se pueden seleccionar si se seleccionan uno o varios indicadores.

En algunos casos, es posible que desee limitar los indicadores de directivas de riesgo internos que se aplican a las directivas de riesgo internos de su organización. Puede desactivar los indicadores de directiva para áreas específicas si los deshabilita de todas las directivas de riesgo internos. Los eventos desencadenantes solo se pueden modificar para las directivas creadas a partir de las plantillas General *data leaks (Pérdidas de datos)* o *Data leaks by priority users (Pérdidas de datos por parte de usuarios prioritarios* ). Las directivas creadas a partir de todas las demás plantillas no tienen indicadores o eventos desencadenantes personalizables.

Para definir los indicadores de directivas de riesgo internos que están habilitados en todas las directivas de riesgo internos, vaya a **Indicadores** de **configuración de** >  riesgo internos y seleccione uno o varios indicadores de directiva. Los indicadores seleccionados en la página Configuración de indicadores no se pueden configurar individualmente al crear o editar una directiva de riesgo interno en el asistente para directivas.

> [!NOTE]
> Los nuevos usuarios agregados manualmente pueden tardar varias horas en aparecer en el **panel Usuarios**. Las actividades de los 90 días anteriores de estos usuarios pueden tardar hasta 24 horas en aparecer. Para ver las actividades de los usuarios agregados manualmente, seleccione el usuario en el **panel Usuarios** y abra la pestaña **Actividad de usuario** en el panel de detalles.

### <a name="enable-device-indicators-and-onboard-windows-devices"></a>Habilitación de indicadores de dispositivo e incorporación de dispositivos Windows
<a name="OnboardDevices"> </a>

Para habilitar la detección de actividades de riesgo en dispositivos Windows e incluir indicadores de directiva para estas actividades, los dispositivos Windows deben cumplir los siguientes requisitos y debe completar los siguientes pasos de incorporación.

#### <a name="step-1-prepare-your-endpoints"></a>Paso 1: Preparación de los puntos de conexión

Asegúrese de que los dispositivos Windows 10 que planea informar en la administración de riesgos internos cumplen estos requisitos.

1. Debe ejecutar Windows 10 compilación x64 1809 o posterior y debe haber instalado la [actualización de Windows 10 (compilación del sistema operativo 17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) del 20 de febrero de 2020.
2. La cuenta de usuario que se usa para iniciar sesión en el dispositivo Windows 10 debe ser una cuenta activa de Azure Active Directory (AAD). El dispositivo Windows 10 puede ser [AAD](/azure/active-directory/devices/concept-azure-ad-join), AAD híbrido, unido a Active Directory o AAD registrado.
3. Instale el explorador Microsoft Edge en el dispositivo de punto de conexión para detectar acciones para la actividad de carga en la nube. Consulte [Descargar el nuevo Microsoft Edge basado en Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Paso 2: Incorporación de dispositivos
<a name="OnboardStep2"> </a>

Debe habilitar la supervisión de dispositivos e incorporar los puntos de conexión para poder detectar actividades de administración de riesgos internos en un dispositivo. Ambas acciones se realizan en el portal de cumplimiento Microsoft Purview.

Cuando quiera incorporar dispositivos que aún no se han incorporado, descargará el script adecuado e implementará como se describe en los pasos siguientes.

Si ya tiene dispositivos incorporados a [Microsoft Defender para punto de conexión](/windows/security/threat-protection/), ya aparecerán en la lista de dispositivos administrados. Siga [el paso 3: Si tiene dispositivos incorporados a Microsoft Defender para punto de conexión](insider-risk-management-settings.md#OnboardStep3) en la sección siguiente.

En este escenario de implementación, incorporará dispositivos que aún no se han incorporado y solo quiere detectar actividades de riesgo interno en Windows 10 dispositivos.

1. Abra el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com).
2. Abra la página de configuración del portal de cumplimiento y elija **Incorporar dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. La lista estará vacía hasta que haya incorporado dispositivos.
4. Elija **Incorporación** para iniciar el proceso de incorporación.
5. Elija la forma en que desea realizar la implementación en estos dispositivos en la lista **Método de implementación** y, a continuación, **descargue el paquete**.
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez hecho y incorporado el punto de conexión, debe estar visible en la lista de dispositivos y el punto de conexión comenzará a notificar los registros de actividad de auditoría a la administración de riesgos internos.

> [!NOTE]
> Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Paso 3: Si tiene dispositivos incorporados a Microsoft Defender para punto de conexión
<a name="OnboardStep3"> </a>

Si Microsoft Defender para punto de conexión ya está implementado y hay puntos de conexión en los que se informa, todos estos puntos de conexión aparecerán en la lista de dispositivos administrados. Puede seguir incorporando nuevos dispositivos a la administración de riesgos internos para expandir la cobertura mediante la sección [Paso 2: Incorporación de dispositivos](insider-risk-management-settings.md#OnboardStep2) .

1. Abra el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com).
2. Abra la página de configuración del portal de cumplimiento y elija **Habilitar supervisión de dispositivos**.
3. Elija **Administración de dispositivos** para abrir la lista de **Dispositivos**. Debería ver la lista de dispositivos que ya están informando en Microsoft Defender para punto de conexión.
4. Elija **Incorporación** si necesita incorporar más dispositivos.
5. Elija la forma en que desea realizar la implementación en estos más dispositivos en la lista **Método de implementación** y, a continuación, **Descargar paquete**.
6. Siga los procedimientos adecuados que puede consultar en [Herramientas y métodos de incorporación para equipos con Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Este vínculo le lleva a una página de aterrizaje en la que puede acceder a los procedimientos de Microsoft Defender para punto de conexión que coinciden con el paquete de implementación que seleccionó en el paso 5:
    - Incorporar equipos con Windows 10 usando Directiva de grupo
    - Incorporar equipos con Windows con Microsoft Endpoint Configuration Manager
    - Incorporar equipos con Windows 10 con herramientas de administración de dispositivos móviles
    - Incorporar equipos con Windows 10 usando un script local
    - Incorporar equipos de infraestructura de escritorio virtual no persistente (VDI).

Una vez hecho y incorporado el punto de conexión, debe estar visible en la tabla **Dispositivos** y el punto de conexión comenzará a notificar los registros de actividad de auditoría a la administración de riesgos internos.

> [!NOTE]
>Esta experiencia requiere la aplicación de una licencia. Sin la licencia necesaria, los datos no serán visibles ni accesibles.

### <a name="enable-device-indicators-and-onboard-macos-devices"></a>Habilitación de indicadores de dispositivo e incorporación de dispositivos macOS

Los dispositivos macOS (Catalina 10.15 o posterior) se pueden incorporar a Microsoft 365 para admitir directivas de administración de riesgos internos mediante Intune o JAMF Pro. Para obtener más información y instrucciones de configuración, consulte [Incorporación de dispositivos macOS a La información general de Microsoft 365 (versión preliminar).](device-onboarding-macos-overview.md)

### <a name="indicator-level-settings-preview"></a>Configuración del nivel de indicador (versión preliminar)

Al crear una directiva en el Asistente para directivas, puede configurar cómo debe influir el número diario de eventos de riesgo en la puntuación de riesgo de las alertas de riesgo internos. Esta configuración de indicador le ayuda a controlar cómo el número de repeticiones de eventos de riesgo en su organización debe afectar a la puntuación de riesgo y, por tanto, a la gravedad de la alerta asociada para estos eventos. Si lo prefiere, también puede optar por mantener los niveles de umbral de eventos predeterminados recomendados por Microsoft para todos los indicadores habilitados.

Por ejemplo, decide habilitar indicadores de SharePoint en la configuración de la directiva de riesgo interno y **establecer umbrales personalizados** para eventos de SharePoint al configurar indicadores para una nueva directiva de *pérdida de datos* de riesgo interno. Mientras que en el Asistente para directivas de riesgo internos, se configuran tres niveles de eventos diarios diferentes para cada indicador de SharePoint con el fin de influir en la puntuación de riesgo de las alertas asociadas a estos eventos.

![Configuración de indicadores personalizados de administración de riesgos internos.](../media/insider-risk-custom-indicators.png)

Para el primer nivel de evento diario, establece el umbral en *10 o más eventos al día* para un impacto menor en la puntuación de riesgo de los eventos, *20 o más eventos al día* para un impacto medio en la puntuación de riesgo de los eventos y *30 o más eventos al día* un mayor impacto en la puntuación de riesgo de los eventos. Esta configuración significa de forma eficaz:

- Si hay entre 1 y 9 eventos de SharePoint que tienen lugar después de desencadenar el evento, las puntuaciones de riesgo se ven mínimamente afectadas y tienden a no generar una alerta.
- Si hay entre 10 y 19 eventos de SharePoint que tienen lugar después de un evento desencadenante, la puntuación de riesgo es intrínsecamente inferior y los niveles de gravedad de alerta tienden a estar en un nivel bajo.
- Si hay entre 20 y 29 eventos de SharePoint que tienen lugar después de un desencadenamiento, la puntuación de riesgo es intrínsecamente mayor y los niveles de gravedad de alerta tienden a estar en un nivel medio.
- Si hay 30 o más eventos de SharePoint que tienen lugar después de un desencadenamiento, la puntuación de riesgo es intrínsecamente mayor y los niveles de gravedad de alerta tienden a estar en un nivel alto.

Otra opción para los umbrales de directiva es asignar el evento desencadenante de directivas a la actividad que está por encima de la cantidad habitual de actividad diaria para los usuarios. En lugar de definirse mediante una configuración de umbral específica, cada umbral se personaliza dinámicamente para las actividades anómalas detectadas para los usuarios de directivas dentro del ámbito. Si se admite la actividad de umbral para actividades anómalas para un indicador individual, puede seleccionar **Actividad por encima de la actividad habitual del usuario para el día** en el Asistente para directivas para ese indicador. Si esta opción no aparece, el desencadenador de actividad anómalo no está disponible para el indicador. Si la **opción Actividad está por encima de la actividad habitual del usuario para el día** aparece para un indicador, pero no se puede seleccionar, debe habilitar esta opción en **Configuración** >  de riesgo interno **Indicadores de directiva.**

## <a name="policy-timeframes"></a>Períodos de tiempo de las directivas

Los períodos de tiempo de las directivas permiten definir períodos de revisión pasados y futuros que se activan después de coincidencias de directivas basadas en eventos y actividades para las plantillas de directivas de administración de riesgos internos. En función de la plantilla de directiva que elija, están disponibles los siguientes períodos de tiempo de directiva:

- **Ventana de activación**: disponible para todas las plantillas de directiva, la *ventana Activación* es el número definido de días que la ventana activa **después** de un evento desencadenante. La ventana se activa de 1 a 30 días después de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos internos y ha establecido la *ventana Activación* en 30 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante activa la *ventana Activación* y la directiva está activa para ese usuario durante 30 días después de que se produjo el evento desencadenante.
- **Detección de actividad anterior**: disponible para todas las plantillas de directiva, la *detección de actividad pasada* es el número definido de días que la ventana activa **antes** de un evento desencadenante. La ventana se activa de 0 a 90 días antes de que se produzca un evento desencadenante para cualquier usuario asignado a la directiva. Por ejemplo, ha configurado una directiva de administración de riesgos internos y ha establecido la *detección de actividad pasada* en 90 días. Han pasado varios meses desde que configuró la directiva y se produce un evento desencadenante para uno de los usuarios incluidos en la directiva. El evento desencadenante activa la *detección de actividad pasada* y la directiva recopila actividades históricas para ese usuario durante 90 días antes del evento desencadenante.

![Configuración del período de tiempo de administración de riesgos internos.](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecciones inteligentes

La configuración de detección inteligente ayuda a refinar la forma en que se procesan las detecciones de actividades de riesgo para las alertas. En determinadas circunstancias, es posible que deba definir tipos de archivo que se deben omitir o que desee aplicar un nivel de detección para los eventos diarios para aumentar las puntuaciones de riesgo para los usuarios. Use esta configuración para controlar las exclusiones de tipos de archivo, aumentar la puntuación de riesgo para la actividad inusual y los límites de volumen de archivos.

### <a name="file-type-exclusions"></a>Exclusiones de tipos de archivo

Para excluir tipos de archivo específicos de todas las coincidencias de directivas de administración de riesgos internos, escriba extensiones de tipo de archivo separadas por comas. Por ejemplo, para excluir determinados tipos de archivos de música de coincidencias de directivas, puede escribir *aac,mp3,wav,wma* en el campo **Exclusiones de tipos de archivo**. Todas las directivas de administración de riesgos internos omitirán los archivos con estas extensiones.

### <a name="minimum-number-of-daily-events-to-boost-score-for-unusual-activity"></a>Número mínimo de eventos diarios para aumentar la puntuación de actividad inusual

Con esta configuración, definirá cuántos eventos diarios son necesarios para aumentar la puntuación de riesgo de la actividad que se considera inusual para un usuario. Por ejemplo, supongamos que escribe 25 para este refuerzo de riesgo. Si un usuario realiza un promedio de 10 descargas de archivos en los últimos 30 días, pero una directiva detecta que descargó 20 archivos en un día, la puntuación de esa actividad no se mejorará aunque sea inusual para ese usuario porque el número de archivos que descargó ese día era menor que el número especificado para este refuerzo de riesgo.

### <a name="alert-volume"></a>Volumen de alertas

A las actividades de usuario detectadas por las directivas de riesgo internos se les asigna una puntuación de riesgo específica, que a su vez determina la gravedad de la alerta (baja, media, alta). De forma predeterminada, generaremos una cierta cantidad de alertas de gravedad baja, media y alta, pero puede aumentar o reducir el volumen para satisfacer sus necesidades. Para ajustar el volumen de alertas para todas las directivas de administración de riesgos internos, elija una de las siguientes opciones:

- **Menos alertas**: verá todas las alertas de gravedad alta, menos alertas de gravedad media y ninguna baja gravedad. Este nivel de configuración significa que podría perder algunos verdaderos positivos.
- **Volumen predeterminado**: verá todas las alertas de gravedad alta y una cantidad equilibrada de alertas de gravedad media y baja.
- **Más alertas**: verá todas las alertas de gravedad media y alta y las alertas de gravedad más baja. Este nivel de configuración podría dar lugar a más falsos positivos.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender para punto de conexión (versión preliminar)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) es una plataforma de seguridad de punto de conexión empresarial diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas. Para tener una mejor visibilidad de las infracciones de seguridad en su organización, puede importar y filtrar alertas de Defender para punto de conexión para las actividades que se usan en las directivas creadas a partir de plantillas de directivas de infracción de seguridad de administración de riesgos internos.

En función de los tipos de señales que le interesen, puede optar por importar alertas a la administración de riesgos internos en función del estado de evaluación de prioridades de alertas de Defender para punto de conexión. Puede definir uno o varios de los siguientes estados de evaluación de prioridad de alertas en la configuración global que se va a importar:

- Unknown
- Nuevo
- En curso
- Resuelto

Las alertas de Defender para punto de conexión se importan diariamente. En función del estado de evaluación de prioridades que elija, es posible que vea varias actividades de usuario para la misma alerta que cambia el estado de evaluación de prioridades en Defender para punto de conexión.

Por ejemplo, si selecciona *Nuevo*, *En curso* y *Resuelto* para esta configuración, cuando se genera una alerta de Microsoft Defender para punto de conexión y el estado es *Nuevo*, se importa una actividad de alerta inicial para el usuario en riesgo interno. Cuando el estado de evaluación de prioridades de Defender para punto de conexión cambia a *En curso*, se importa una segunda actividad para esta alerta para el usuario en riesgo interno. Cuando se establece el estado final de evaluación de prioridades de Defender para punto de conexión de *Resuelto* , se importa una tercera actividad para esta alerta para el usuario en riesgo interno. Esta funcionalidad permite a los investigadores seguir la progresión de las alertas de Defender para punto de conexión y elegir el nivel de visibilidad que requiere su investigación.

> [!IMPORTANT]
> Deberá tener configurado ATP de Microsoft Defender en su organización y habilitar Defender para punto de conexión para la integración de la administración de riesgos internos en el Centro de seguridad de Defender para importar las alertas de infracciones de seguridad. Para obtener más información sobre cómo configurar Defender para punto de conexión para la integración de la administración de riesgos internos, vea [Configurar las características avanzadas de Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains"></a>Dominios

La configuración de dominio le ayuda a definir los niveles de riesgo de las actividades en dominios específicos. Estas actividades incluyen el uso compartido de archivos, el envío de mensajes de correo electrónico, la descarga o la carga de contenido. Al especificar dominios en esta configuración, puede aumentar o reducir la puntuación de riesgo de la actividad que tiene lugar con estos dominios.

Use Agregar dominio para definir un dominio para cada uno de los valores de dominio. Además, puede usar caracteres comodín para ayudar a hacer coincidir las variaciones de dominios raíz o subdominios. Por ejemplo, para especificar sales.wingtiptoys.com y support.wingtiptoys.com, use la entrada comodín "*.wingtiptoys.com" para hacer coincidir estos subdominios (y cualquier otro subdominio en el mismo nivel). Para especificar subdominios de varios niveles para un dominio raíz, debe seleccionar la casilla **Incluir subdominios de varios niveles** .

Para cada una de las siguientes configuraciones de dominio, puede escribir hasta 500 dominios:

- **Dominios no permitidos:** Al especificar dominios no permitidos, la actividad que tiene lugar con estos dominios tendrá puntuaciones *de riesgo más altas* . Algunos ejemplos son actividades que implican compartir contenido con alguien (como enviar correo electrónico a alguien con una dirección de gmail.com) y cuando los usuarios descargan contenido en un dispositivo desde uno de estos dominios no permitidos.
- **Dominios permitidos:** Determinadas actividades relacionadas con los dominios permitidos las omitirán las directivas y no generarán alertas. Estas actividades incluyen:

    - Correo electrónico enviado a dominios externos
    - Archivos, carpetas, sitios compartidos con dominios externos
    - Archivos cargados en dominios externos (con el explorador Microsoft Edge)

    Al especificar dominios permitidos en la configuración, esta actividad con estos dominios se trata de forma similar a cómo se trata la actividad interna de la organización. Por ejemplo, los dominios agregados aquí se asignan a actividades que pueden implicar compartir contenido con alguien de fuera de la organización (por ejemplo, enviar correo electrónico a alguien con una dirección de gmail.com).

- **Dominios de terceros:** Si su organización usa dominios de terceros con fines empresariales (como el almacenamiento en la nube), insclúyelos aquí para que pueda recibir alertas de actividad relacionada con el indicador de dispositivo *Use un explorador para descargar contenido de un sitio de terceros*.

## <a name="export-alerts"></a>Exportar alertas

La información de alertas de administración de riesgos internos se puede exportar a la información de seguridad y a las soluciones de administración de eventos (SIEM) y respuesta automatizada de orquestación de seguridad (SOAR) mediante el [esquema de api de actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema). Puede usar las API de actividad de administración de Office 365 para exportar información de alertas a otras aplicaciones que su organización puede usar para administrar o agregar información de riesgo interno. La información de alertas se exporta y está disponible cada 60 minutos a través de las API de actividad de administración de Office 365.

Si su organización usa Microsoft Sentinel, también puede usar el conector de datos de administración de riesgos internos para importar información de alertas de riesgo internos a Sentinel. Para obtener más información, consulte [Insider Risk Management (IRM) (versión preliminar)](/azure/sentinel/data-connectors-reference#microsoft-365-insider-risk-management-irm-preview) en el artículo de Microsoft Sentinel.

>[!IMPORTANT]
>Para mantener la integridad referencial de los usuarios que tienen alertas o casos de riesgo internos en Microsoft 365 u otros sistemas, no se conserva el anonimato de los nombres de usuario para las alertas exportadas. Las alertas exportadas mostrarán los nombres de usuario de cada alerta.

Para usar las API para revisar la información de alertas de riesgo internos:

1. Habilite la compatibilidad con la API de actividad de Office 365 Management en **Configuración de administración de** >  riesgos de Insider Export alerts (**Exportación** >  de **alertas**). De forma predeterminada, esta configuración está deshabilitada para la organización de Microsoft 365.
2. Filtre las actividades comunes de auditoría de Office 365 por *SecurityComplianceAlerts*.
3. Filtre *SecurityComplianceAlerts* por la categoría *InsiderRiskManagement* .

![Configuración de alertas de exportación de administración de riesgos internos.](../media/insider-risk-settings-export.png)

La información de alerta contiene información del esquema de alertas de seguridad y cumplimiento y del esquema común de la API de actividad de Office 365 Management.

Los siguientes campos y valores se exportan para las alertas de administración de riesgos internos para el esquema de alertas de cumplimiento de seguridad &:

| **Parámetro de alerta** | **Descripción** |
|:------------------|:----------------|
| AlertType | El tipo de la alerta es *Custom*.  |
| AlertId | GUID de la alerta. Las alertas de administración de riesgos internos son mutables. A medida que cambia el estado de la alerta, se genera un nuevo registro con el mismo AlertID. Este AlertID se puede usar para correlacionar las actualizaciones de una alerta. |
| Categoría | La categoría de la alerta es *InsiderRiskManagement*. Esta categoría se puede usar para distinguir de estas alertas de otras alertas de cumplimiento de seguridad &. |
| Comentarios | Comentarios predeterminados para la alerta. Los valores son *Nueva alerta* (registrada cuando se crea una alerta) y *Alerta actualizada* (registrada cuando hay una actualización de una alerta). Use AlertID para correlacionar las actualizaciones de una alerta. |
| Datos | Los datos de la alerta incluyen el identificador de usuario único, el nombre principal de usuario y la fecha y hora (UTC) cuando el usuario se desencadenó en una directiva. |
| Nombre | Nombre de directiva para la directiva de administración de riesgos internos que generó la alerta. |
| PolicyId | GUID de la directiva de administración de riesgos internos que desencadenó la alerta. |
| Severity | Gravedad de la alerta. Los valores son *Alto*, *Medio* o *Bajo*. |
| Origen | Origen de la alerta. El valor es *Office 365 Security & Compliance*. |
| Estado | Estado de la alerta. Los valores son *Activos* (*Revisión de necesidades* en riesgo interno), *Investigar* (*Confirmado* en riesgo interno), *Resuelto* (*Resuelto* en riesgo interno), *Descartado* (*Descartado* en riesgo interno). |
| Versión | Versión del esquema de alertas de seguridad y cumplimiento. |

Los siguientes campos y valores se exportan para las alertas de administración de riesgos internos para el [esquema común de la API de actividad de Office 365 Management](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema).

- UserId
- Id
- RecordType
- CreationTime
- Operación
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuarios prioritarios (versión preliminar)

Los usuarios de su organización pueden tener distintos niveles de riesgo en función de su posición, nivel de acceso a información confidencial o historial de riesgos. Priorizar el examen y la puntuación de las actividades de estos usuarios puede ayudarle a alertar sobre posibles riesgos que pueden tener mayores consecuencias para su organización. Los grupos de usuarios prioritarios en la administración de riesgos internos ayudan a definir los usuarios de su organización que necesitan una inspección más detallada y una puntuación de riesgos más confidencial. Junto con las infracciones de la *directiva de seguridad por parte de los usuarios prioritarios* y *las pérdidas de datos por plantillas de directiva de usuarios prioritarios* , los usuarios agregados a un grupo de usuarios prioritarios tienen una mayor probabilidad de alertas de riesgo interno y alertas con niveles de gravedad más altos.

![Configuración del grupo de usuarios de prioridad de administración de riesgos internos.](../media/insider-risk-settings-priority-users.png)

En lugar de estar abiertos a la revisión por todos los analistas e investigadores, es posible que los grupos de usuarios prioritarios también necesiten restringir las actividades de revisión a usuarios específicos o grupos de roles de riesgo internos. Puede optar por asignar usuarios individuales y grupos de roles para revisar usuarios, alertas, casos e informes para cada grupo de usuarios prioritarios. Los grupos de usuarios prioritarios pueden tener permisos de revisión asignados a los grupos de roles integrados *Insider Risk Management*, *Insider Risk Management Analysts* y *Insider Risk Management Investigators* , uno o varios de estos grupos de roles o a una selección personalizada de usuarios.

Por ejemplo, debe protegerse frente a las pérdidas de datos de un proyecto altamente confidencial en el que los usuarios tengan acceso a información confidencial. Elija crear un grupo de usuarios *prioritarios de usuarios* del *proyecto confidencial* para los usuarios de su organización que trabajen en este proyecto. Además, este grupo de usuarios prioritario no debe tener usuarios, alertas, casos e informes asociados al grupo visibles para todos los administradores, analistas e investigadores de administración de riesgos internos predeterminados. En **Configuración**, se crea el grupo *usuarios prioritarios Usuarios del proyecto confidencial* y se asignan dos usuarios como revisores que pueden ver los datos relacionados con los grupos. Con el Asistente para directivas y la plantilla de directiva *Pérdidas de datos por usuarios prioritarios* , se crea una nueva directiva y se asigna el grupo Usuarios prioritarios *de usuarios de proyecto confidencial* a la directiva. Las actividades examinadas por la directiva para los miembros del grupo de usuarios *prioritarios Usuarios del proyecto confidencial* son más sensibles al riesgo y es más probable que estos usuarios generen una alerta y tengan alertas con niveles de gravedad más altos.

### <a name="create-a-priority-user-group"></a>Creación de un grupo de usuarios prioritario

Para crear un nuevo grupo de usuarios de prioridad, usará controles de configuración en la solución **de administración de riesgos Insider** en el portal de cumplimiento Microsoft Purview. Para crear un grupo de usuarios prioritario, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*.

Complete los pasos siguientes para crear un grupo de usuarios prioritario:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgo de Insider**.
2. Seleccione la página **Grupos de usuarios prioritarios (versión preliminar).**
3. En la página **Grupos de usuarios prioritarios (versión preliminar),** seleccione **Crear grupo de usuarios de prioridad** para iniciar el Asistente para la creación de grupos.
4. En la página **Nombre y descripción** , complete los campos siguientes:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para el grupo de usuarios de prioridad. No puede cambiar el nombre del grupo de usuarios de prioridad después de completar el asistente.
    - **Descripción (opcional):** escriba una descripción para el grupo de usuarios de prioridad.
5. Seleccione **Siguiente** para continuar.
6. En la página **Elegir miembros** , seleccione **Elegir miembros** para buscar y seleccione qué cuentas de usuario habilitadas para correo se incluyen en el grupo o active la casilla **Seleccionar todo** para agregar todos los usuarios de la organización al grupo. Seleccione **Agregar** para continuar o **Cancelar** para cerrar sin agregar usuarios al grupo.
7. Seleccione **Siguiente** para continuar.
8. En la página **Elegir quién puede ver este grupo** , debe definir quién puede revisar usuarios, alertas, casos e informes para el grupo de usuarios prioritario. Se debe asignar al menos un grupo de roles de administración de riesgos internos o de usuario. Seleccione **Elegir usuarios y grupos de roles** y seleccione los usuarios o grupos de roles de administración de riesgos internos que desea asignar al grupo de usuarios de prioridad. Seleccione **Agregar** para asignar los usuarios o grupos de roles seleccionados al grupo.
9. Seleccione Siguiente para continuar.
10. En la página **Revisar** , revise la configuración que ha elegido para el grupo de usuarios de prioridad. Seleccione los vínculos **Editar** para cambiar cualquiera de los valores de grupo o seleccione **Enviar** para crear y activar el grupo de usuarios de prioridad.
11. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="update-a-priority-user-group"></a>Actualización de un grupo de usuarios prioritario

Para actualizar un grupo de usuarios de prioridad existente, usará controles de configuración en la solución **de administración de riesgos Insider** en el portal de cumplimiento Microsoft Purview. Para actualizar un grupo de usuarios prioritario, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*.

Complete los pasos siguientes para editar un grupo de usuarios prioritario:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgo de Insider**.
2. Seleccione la página **Grupos de usuarios prioritarios (versión preliminar).**
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Editar grupo**.
4. En la página **Nombre y descripción** , actualice el campo Descripción si es necesario. No se puede actualizar el nombre del grupo de usuarios de prioridad. Seleccione **Siguiente** para continuar.
5. En la página **Elegir miembros** , agregue nuevos miembros al grupo mediante el control **Elegir miembros** . Para quitar un usuario del grupo, seleccione la "X" junto al usuario que desea quitar. Seleccione **Siguiente** para continuar.
6. En la página **Elegir quién puede ver este grupo** , agregue o quite usuarios o grupos de roles que puedan revisar usuarios, alertas, casos e informes para el grupo de usuarios de prioridad.
7. Seleccione **Siguiente** para continuar.
8. En la página **Revisar** , revise la configuración de actualización que ha elegido para el grupo de usuarios de prioridad. Seleccione los vínculos **Editar** para cambiar cualquiera de los valores del grupo o seleccione **Enviar** para actualizar el grupo de usuarios de prioridad.
9. En la página de confirmación, seleccione **Listo** para salir del asistente.

### <a name="delete-a-priority-user-group"></a>Eliminación de un grupo de usuarios prioritario

Para eliminar un grupo de usuarios de prioridad existente, usará controles de configuración en la solución **de administración de riesgos Insider** de la portal de cumplimiento Microsoft Purview. Para eliminar un grupo de usuarios prioritario, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*.

> [!IMPORTANT]
> Al eliminar un grupo de usuarios de prioridad, se quitará de cualquier directiva activa a la que esté asignado. Si elimina un grupo de usuarios de prioridad asignado a una directiva activa, la directiva no contendrá ningún usuario en el ámbito y estará inactiva y no creará alertas.

Complete los pasos siguientes para eliminar un grupo de usuarios de prioridad:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgo de Insider**.
2. Seleccione la página **Grupos de usuarios prioritarios (versión preliminar).**
3. Seleccione el grupo de usuarios de prioridad que desea editar y seleccione **Eliminar** en el menú del panel.
4. En el cuadro de diálogo **Eliminar** , seleccione **Sí** para eliminar el grupo de usuarios de prioridad o seleccione **Cancelar** para volver al panel.

## <a name="priority-physical-assets-preview"></a>Activos físicos prioritarios (versión preliminar)

La identificación del acceso a recursos físicos prioritarios y la correlación de la actividad de acceso a eventos de usuario es un componente importante de la infraestructura de cumplimiento. Estos recursos físicos representan ubicaciones prioritarias de su organización, como edificios de la empresa, centros de datos o salas de servidores. Las actividades de riesgo internos pueden estar asociadas a usuarios que trabajan horas inusuales, intentan acceder a estas áreas confidenciales o seguras no autorizadas y solicitan acceso a áreas de alto nivel sin necesidad legítima.

Con los recursos físicos prioritarios habilitados y el [conector de datos de badging físico](import-physical-badging-data.md) configurado, la administración de riesgos internos integra las señales de los sistemas de control físico y acceso con otras actividades de riesgo del usuario. Al examinar patrones de comportamiento en los sistemas de acceso físico y correlacionar estas actividades con otros eventos de riesgo internos, la administración de riesgos internos puede ayudar a los investigadores y analistas de cumplimiento a tomar decisiones de respuesta más informadas para las alertas. El acceso a los recursos físicos prioritarios se puntúa e identifica en la información de forma diferente del acceso a los recursos que no son prioritarios.

Por ejemplo, su organización tiene un sistema de badging para los usuarios que rigen y aprueban el acceso físico a áreas normales de trabajo y proyectos confidenciales. Tiene varios usuarios trabajando en un proyecto confidencial y estos usuarios volverán a otras áreas de la organización cuando se complete el proyecto. A medida que el proyecto confidencial está a punto de finalizar, quiere asegurarse de que el trabajo del proyecto sigue siendo confidencial y de que el acceso a las áreas del proyecto está estrechamente controlado.

Elija habilitar el conector de datos de badging físico en Microsoft 365 para importar información de acceso desde el sistema de falsificación física y especificar los recursos físicos prioritarios en la administración de riesgos internos. Al importar información desde el sistema de desajuste y correlacionar la información de acceso físico con otras actividades de riesgo identificadas en la administración de riesgos internos, observa que uno de los usuarios del proyecto accede a las oficinas del proyecto después del horario laboral normal y también exporta grandes cantidades de datos a un servicio de almacenamiento en la nube personal desde su área de trabajo normal. Esta actividad de acceso físico asociada a la actividad en línea puede apuntar a posibles robos de datos y los investigadores y analistas de cumplimiento pueden tomar las acciones adecuadas según las circunstancias de este usuario.

![Activos físicos prioritarios de administración de riesgos internos.](../media/insider-risk-settings-priority-assets.png)

### <a name="configure-priority-physical-assets"></a>Configuración de recursos físicos prioritarios

Para configurar los recursos físicos prioritarios, configurará el conector de badging físico y usará los controles de configuración en la solución **de administración de riesgos Insider** de la portal de cumplimiento Microsoft Purview. Para configurar los recursos físicos prioritarios, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*.

Complete los pasos siguientes para configurar los recursos físicos prioritarios:

1. Siga los pasos de configuración para la administración de riesgos internos en el artículo [Introducción a la administración de riesgos internos](insider-risk-management-configure.md) . En el paso 3, asegúrese de configurar el conector de badging físico.

    > [!IMPORTANT]
    > Para que las directivas de administración de riesgos internos usen y correlacionen los datos de señal relacionados con los usuarios que salen y finalizan con datos de eventos de las plataformas de control físico y acceso, también debe configurar el conector de RR. HH. de Microsoft 365. Si habilita el conector de badging físico sin habilitar el conector de RR. HH. de Microsoft 365, las directivas de administración de riesgos internos solo procesarán eventos para las actividades de acceso físico para los usuarios de su organización.

2. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de** >  riesgos internos **Prioridad de los recursos físicos**.
3. En la página **Activos físicos** prioritarios, puede agregar manualmente los identificadores de recursos físicos que desea detectar eventos de recursos importados por el conector de badging físico o importar un archivo .csv de todos los identificadores de recursos físicos importados por el conector de errores físicos: a) Para agregar manualmente identificadores de recursos físicos, elija **Agregar recursos físicos de prioridad**, escriba un identificador de recurso físico,  a continuación, seleccione **Agregar**. Escriba otros identificadores de recursos físicos y, a continuación, seleccione **Agregar recursos físicos de prioridad** para guardar todos los recursos especificados.
    b) Para agregar una lista de identificadores de recursos físicos desde un archivo .csv, elija **Importar recursos físicos de prioridad**. En el cuadro de diálogo explorador de archivos, seleccione el archivo .csv que desea importar y, a continuación, seleccione **Abrir**. Los identificadores de recursos físicos de los archivos .csv se agregan a la lista.
4. Vaya a la página **Indicadores de directiva en** **Configuración**.
5. En la página **Indicadores de directiva** , vaya a la sección **Indicadores de acceso físico** y active la casilla **Acceso físico después de la terminación o acceso erróneo al recurso confidencial**.
6. Seleccione **Guardar** para configurar y salir.

### <a name="delete-a-priority-physical-asset"></a>Eliminación de un recurso físico prioritario

Para eliminar un recurso físico de prioridad existente, usará controles de configuración en la solución de administración de riesgos Insider de la portal de cumplimiento Microsoft Purview. Para eliminar un recurso físico prioritario, debe ser miembro del grupo de roles Insider Risk Management o Insider Risk Management Administración.

> [!IMPORTANT]
> La eliminación de un recurso físico de prioridad lo quita del examen por cualquier directiva activa a la que se haya incluido anteriormente. Las alertas generadas por actividades asociadas al recurso físico de prioridad no se eliminan.

Complete los pasos siguientes para eliminar un recurso físico de prioridad:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de** >  riesgos internos **Prioridad de los recursos físicos**.
2. En la página **Activos físicos prioritarios** , seleccione el recurso que desea eliminar.
3. Seleccione **Eliminar** en el menú de acciones para eliminar el recurso.

## <a name="power-automate-flows-preview"></a>Flujos de Power Automate (versión preliminar)

[Microsoft Power Automate](/power-automate/getting-started) es un servicio de flujo de trabajo que automatiza las acciones entre aplicaciones y servicios. Mediante el uso de flujos de plantillas o creados manualmente, puede automatizar las tareas comunes asociadas a estas aplicaciones y servicios. Al habilitar flujos de Power Automate para la administración de riesgos internos, puede automatizar tareas importantes para casos y usuarios. Puede configurar flujos de Power Automate para recuperar información de usuarios, alertas y casos, y compartir esta información con las partes interesadas y otras aplicaciones, así como automatizar acciones en la administración de riesgos internos, como publicar en notas de casos. Los flujos de Power Automate son aplicables a los casos y a cualquier usuario en el ámbito de una directiva.

Los clientes con suscripciones de Microsoft 365 que incluyen la administración de riesgos internos no necesitan licencias adicionales de Power Automate para usar las plantillas recomendadas de Power Automate de administración de riesgos internos. Estas plantillas se pueden personalizar para admitir su organización y cubrir los principales escenarios de administración de riesgos internos. Si decide usar las características premium de Power Automate en estas plantillas, cree una plantilla personalizada con el conector de Microsoft Purview o use plantillas de Power Automate para otras áreas de cumplimiento en Microsoft 365, es posible que necesite más licencias de Power Automate.

Las siguientes plantillas de Power Automate se proporcionan a los clientes para admitir la automatización de procesos para usuarios y casos de administración de riesgos internos:

- **Notificar a los usuarios cuando se agregan a una directiva de riesgo** interno: esta plantilla es para organizaciones que tienen directivas internas, privacidad o requisitos normativos, a los que se debe notificar a los usuarios cuando están sujetos a directivas de administración de riesgos internos. Cuando este flujo se configura y selecciona para un usuario en la página **Usuarios** , los usuarios y sus administradores se envían un mensaje de correo electrónico cuando el usuario se agrega a una directiva de administración de riesgos internos. Esta plantilla también admite la actualización de una lista de SharePoint hospedada en un sitio de SharePoint para ayudar a realizar un seguimiento de los detalles del mensaje de notificación, como la fecha y hora y el destinatario del mensaje. Si ha elegido anonimizar a los usuarios en **la configuración de privacidad**, los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el **panel Usuarios**.
- **Solicitar información de RR. HH. o de la empresa sobre un usuario en un caso de riesgo** interno: al actuar sobre un caso, es posible que los analistas e investigadores de riesgos internos necesiten consultar con RR. HH. u otras partes interesadas para comprender el contexto de las actividades del caso. Cuando este flujo se configura y selecciona para un caso, los analistas e investigadores envían un mensaje de correo electrónico a las partes interesadas de recursos humanos y empresariales configuradas para este flujo. A cada destinatario se le envía un mensaje con opciones de respuesta preconfiguradas o personalizables. Cuando los destinatarios seleccionan una opción de respuesta, la respuesta se registra como una nota de caso e incluye información de destinatario y fecha y hora. Si ha elegido anonimizar a los usuarios en **la configuración de privacidad**, los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el **panel Casos**.
- **Notificar al administrador cuando un usuario tiene una alerta de riesgo interno**: es posible que algunas organizaciones necesiten tener una notificación de administración inmediata cuando un usuario tenga una alerta de administración de riesgos internos. Cuando se configura y selecciona este flujo, el administrador del usuario del caso se envía un mensaje de correo electrónico con la siguiente información sobre todas las alertas de casos:
    - Directiva aplicable para la alerta
    - Fecha y hora de la alerta
    - Nivel de gravedad de la alerta

    El flujo actualiza automáticamente las notas del caso que el mensaje se envió y que el flujo se activó. Si ha elegido anonimizar a los usuarios en **la configuración de privacidad**, los flujos creados a partir de esta plantilla no funcionarán según lo previsto para que se mantenga la privacidad del usuario. Los flujos de Power Automate que usan esta plantilla están disponibles en el **panel Casos**.
- **Crear un registro para casos de riesgo internos en ServiceNow**: esta plantilla es para las organizaciones que quieren usar su solución ServiceNow para realizar un seguimiento de los casos de administración de riesgos internos.  Cuando se trata de un caso, los analistas e investigadores de riesgos internos pueden crear un registro para el caso en ServiceNow. Puede personalizar esta plantilla para rellenar los campos seleccionados en ServiceNow en función de los requisitos de su organización. Los flujos de Power Automate que usan esta plantilla están disponibles en el **panel Casos**. Para obtener más información sobre los campos de ServiceNow disponibles, consulte el artículo [de referencia del conector de ServiceNow](/connectors/service-now/) .

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Creación de un flujo de Power Automate a partir de una plantilla de administración de riesgos internos

Para crear un flujo de Power Automate a partir de una plantilla de administración de riesgos internos recomendada, usará los controles de configuración de la solución **de administración de riesgos Insider** en el portal de cumplimiento Microsoft Purview o la opción **Administrar flujos de Power Automate** desde el control **Automatizar** al trabajar directamente en los paneles **Casos** o **Usuarios**.

Para crear un flujo de Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*. Para crear un flujo de Power Automate con la opción **Administrar flujos de Power Automate** , debe ser miembro de al menos un grupo de roles de administración de riesgos internos.

Complete los pasos siguientes para crear un flujo de Power Automate a partir de una plantilla de administración de riesgos internos recomendada:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgos internos** > **Flujos de Power Automate**. También puede acceder desde las páginas **Casos** o **Paneles de usuarios** eligiendo **Automatizar** > **la administración de flujos de Power Automate**.
2. En la página **Flujos de Power Automate** , seleccione una plantilla recomendada en la sección **Plantillas de administración de riesgos de Insider que le gustaría** en la página.
3. El flujo enumera las conexiones incrustadas necesarias para el flujo y observará si los estados de conexión están disponibles. Si es necesario, actualice las conexiones que no se muestren como disponibles. Seleccione **Continuar**.
4. De forma predeterminada, los flujos recomendados se configuran previamente con los campos de datos de servicios de microsoft 365 y administración de riesgos internos recomendados necesarios para completar la tarea asignada para el flujo. Si es necesario, personalice los componentes de flujo mediante el control **Mostrar opciones avanzadas** y configurando las propiedades disponibles para el componente de flujo.
5. Si es necesario, agregue cualquier otro paso al flujo seleccionando el botón **Nuevo paso** . En la mayoría de los casos, esto no debe ser necesario para las plantillas predeterminadas recomendadas.
6. Seleccione **Guardar borrador** para guardar el flujo para una configuración adicional o seleccione **Guardar** para completar la configuración del flujo.
7. Seleccione **Cerrar** para volver a la página **flujo de Power Automate** . La nueva plantilla se mostrará como un flujo en las pestañas **Mis flujos** y estará disponible automáticamente en el control desplegable **Automatizar** al trabajar con casos de administración de riesgos internos para el usuario que crea el flujo.

> [!IMPORTANT]
> Si otros usuarios de la organización necesitan acceso al flujo, el flujo debe compartirse.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Creación de un flujo personalizado de Power Automate para la administración de riesgos internos

Algunos procesos y flujos de trabajo de su organización pueden estar fuera de las plantillas de flujo de administración de riesgos internos recomendadas y es posible que tenga la necesidad de crear flujos personalizados de Power Automate para áreas de administración de riesgos internos. Los flujos de Power Automate son flexibles y admiten una amplia personalización, pero hay pasos que deben realizarse para integrarse con las características de administración de riesgos internos.

Complete los pasos siguientes para crear una plantilla de Power Automate personalizada para la administración de riesgos internos:

1. **Compruebe la licencia de flujo de Power Automate**: para crear flujos de Power Automate personalizados que usen desencadenadores de administración de riesgos internos, necesitará una licencia de Power Automate. Las plantillas de flujo de administración de riesgos internos recomendadas no requieren licencias adicionales y se incluyen como parte de la licencia de administración de riesgos internos.
2. **Creación de un flujo automatizado**: cree un flujo que realice una o varias tareas después de que se desencadene mediante un evento de administración de riesgos internos. Para obtener más información sobre cómo crear un flujo automatizado, consulte [Creación de un flujo en Power Automate](/power-automate/get-started-logic-flow).
3. **Seleccione el conector de Microsoft Purview**: busque y seleccione el conector de Microsoft Purview. Este conector permite acciones y desencadenadores de administración de riesgos internos. Para obtener más información sobre los conectores, consulte el artículo [Información general](/connectors/connector-reference/) sobre la referencia del conector.
4. **Elija desencadenadores de administración de riesgos internos para el flujo**: La administración de riesgos internos tiene dos desencadenadores disponibles para flujos personalizados de Power Automate:
    - **Para un caso de administración de riesgos internos seleccionado**: los flujos con este desencadenador se pueden seleccionar en la página del panel Casos de administración de riesgos internos.
    - **Para un usuario de administración de riesgos internos seleccionado**: los flujos con este desencadenador se pueden seleccionar en la página del panel Usuarios de administración de riesgos internos.
5. Elija acciones de administración de riesgos internos para el flujo: puede elegir entre varias acciones para que la administración de riesgos internos se incluya en el flujo personalizado:
    - Obtención de una alerta de administración de riesgos internos
    - Obtener un caso de administración de riesgos internos
    - Obtención de un usuario de administración de riesgos internos
    - Obtención de alertas de administración de riesgos internos para un caso
    - Adición de una nota de casos de administración de riesgos internos

### <a name="share-a-power-automate-flow"></a>Uso compartido de un flujo de Power Automate

De forma predeterminada, los flujos de Power Automate creados por un usuario solo están disponibles para ese usuario. Para que otros usuarios de administración de riesgos internos tengan acceso y usen un flujo, el creador del flujo debe compartir el flujo. Para compartir un flujo, usará los controles de configuración de la **solución de administración de riesgos Insider** en el portal de cumplimiento Microsoft Purview o la opción **Administrar flujos de Power Automate** desde el control Automatizar al trabajar directamente en las páginas del panel **Casos** o **Usuarios**. Una vez que haya compartido un flujo, todos los usuarios con los que se ha compartido pueden acceder al flujo en la lista desplegable **Automatizar** control de los paneles **Caso** y **Usuario**.

Para compartir un flujo de Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*. Para compartir un flujo de Power Automate con la opción **Administrar flujos de Power Automate** , debe ser miembro de al menos un grupo de roles de administración de riesgos internos.

Complete los pasos siguientes para compartir un flujo de Power Automate:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgos internos** > **Flujos de Power Automate**. También puede acceder desde las páginas **Casos** o **Paneles de usuarios** eligiendo **Automatizar** > **la administración de flujos de Power Automate**.
2. En la página **Flujos de Power Automate** , seleccione la pestaña **Mis flujos** o **Flujos de equipo** .
3. Seleccione el flujo que desea compartir y, a continuación, seleccione **Compartir** en el menú de opciones de flujo.
4. En la página de uso compartido de flujo, escriba el nombre del usuario o grupo que desea agregar como propietario para el flujo.
5. En el cuadro de diálogo **Conexión usada** , seleccione **Aceptar** para confirmar que el usuario o grupo agregado tendrá acceso total al flujo.

### <a name="edit-a-power-automate-flow"></a>Edición de un flujo de Power Automate

Para editar un flujo, usará los controles de configuración de la solución **de administración de riesgos Insider** en el portal de cumplimiento Microsoft Purview o la opción **Administrar flujos de Power Automate** desde el control **Automatizar** al trabajar directamente en los paneles **Casos** o **Usuarios**.

Para editar un flujo de Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*. Para editar un flujo de Power Automate con la opción **Administrar flujos de Power Automate** , debe ser miembro de al menos un grupo de roles de administración de riesgos internos.

Complete los pasos siguientes para editar un flujo de Power Automate:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgos internos** > **Flujos de Power Automate**. También puede acceder desde las páginas **Casos** o **Paneles de usuarios** eligiendo **Automatizar** > **la administración de flujos de Power Automate**.
2. En la página **Flujos de Power Automate** , seleccione un flujo para editar y seleccione **Editar** en el menú de control de flujo.
3. Seleccione los **puntos suspensivos** > **Configuración** para cambiar una configuración de componente de flujo o **puntos suspensivos** > **Eliminar** para eliminar un componente de flujo.
4. Seleccione **Guardar** y, a continuación, **Cerrar** para completar la edición del flujo.

### <a name="delete-a-power-automate-flow"></a>Eliminación de un flujo de Power Automate

Para eliminar un flujo, usará los controles de configuración de la solución **de administración de riesgos insider** en el portal de cumplimiento Microsoft Purview o la opción **Administrar flujos de Power Automate** desde el control **Automatizar** al trabajar directamente en los paneles **Casos** o **Usuarios**. Cuando se elimina un flujo, se quita como una opción para todos los usuarios.

Para eliminar un flujo de Power Automate en el área de configuración, debe ser miembro del grupo de roles *Insider Risk Management* o *Insider Risk Management Administración*. Para eliminar un flujo de Power Automate con la opción **Administrar flujos de Power Automate** , debe ser miembro de al menos un grupo de roles de administración de riesgos internos.

Complete los pasos siguientes para eliminar un flujo de Power Automate:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione **Configuración de riesgos internos** > **Flujos de Power Automate**. También puede acceder desde las páginas **Casos** o **Paneles de usuarios** eligiendo **Automatizar** > **la administración de flujos de Power Automate**.
2. En la página **Flujos de Power Automate** , seleccione un flujo que desea eliminar y seleccione **Eliminar** en el menú de control de flujo.
3. En el cuadro de diálogo de confirmación de eliminación, seleccione **Eliminar** para quitar el flujo o seleccione **Cancelar** para salir de la acción de eliminación.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (versión preliminar)

Los analistas e investigadores de cumplimiento pueden usar fácilmente Microsoft Teams para colaborar en casos de administración de riesgos internos. Pueden coordinar y comunicarse con otras partes interesadas de Microsoft Teams para:

- Coordinar y revisar las actividades de respuesta para casos en canales privados de Teams
- Compartir y almacenar de forma segura archivos y pruebas relacionados con casos individuales
- Seguimiento y revisión de las actividades de respuesta por parte de analistas e investigadores

Una vez que Microsoft Teams está habilitado para la administración de riesgos internos, se crea un equipo de Microsoft Teams dedicado cada vez que se confirma una alerta y se crea un caso. De forma predeterminada, el equipo incluye automáticamente todos los miembros de los grupos de roles *Insider Risk Management*, *Insider Risk Management Analysts* y *Insider Risk Management Investigators* (hasta 100 usuarios iniciales). Es posible que se agreguen colaboradores adicionales a la organización al equipo una vez creado y según corresponda. En el caso de los casos existentes creados antes de habilitar Microsoft Teams, los analistas e investigadores pueden optar por crear un nuevo equipo de Microsoft Teams cuando trabajen en un caso si es necesario.  Una vez resuelto el caso asociado en la administración de riesgos internos, el equipo se archiva automáticamente (se mueve a oculto y de solo lectura).

Para obtener más información sobre cómo usar equipos y canales en Microsoft Teams, consulte [Introducción a los equipos y canales en Microsoft Teams](/MicrosoftTeams/teams-channels-overview).

La habilitación del soporte técnico de Microsoft Teams para casos es rápida y fácil de configurar. Para habilitar Microsoft Teams para la administración de riesgos internos, siga estos pasos:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de** >  riesgos internos **Configuración de riesgos internos**.
2. Seleccione la página **Microsoft Teams** .
3. Habilite la integración de Microsoft Teams para la administración de riesgos internos.
4. Seleccione **Guardar** para configurar y salir.

![Administración de riesgos internos de Microsoft Teams.](../media/insider-risk-settings-teams.png)

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Creación de un equipo de Microsoft Teams para casos existentes

Si habilita el soporte técnico de Microsoft Teams para la administración de riesgos internos después de tener casos existentes, deberá crear manualmente un equipo para cada caso según sea necesario. Después de habilitar el soporte técnico de Microsoft Teams en la configuración de administración de riesgos internos, los nuevos casos crearán automáticamente un nuevo equipo de Microsoft Teams.

Los usuarios necesitan permiso para crear grupos de Microsoft 365 en su organización para crear un equipo de Microsoft Teams a partir de un caso. Para obtener más información sobre cómo administrar permisos para Grupos de Microsoft 365, consulte [Administrar quién puede crear Grupos de Microsoft 365](../solutions/manage-creation-of-groups.md).

Para crear un equipo para un caso, usará el control Crear equipo de Microsoft al trabajar directamente en un caso existente. Complete los pasos siguientes para crear un nuevo equipo:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Casos** de **administración** >  de riesgos internos y seleccione un caso existente.
2. En el menú de acciones del caso, seleccione **Crear equipo de Microsoft**.
3. En el campo **Nombre del equipo** , escriba un nombre para el nuevo equipo de Microsoft Teams.
4. Seleccione **Crear equipo de Microsoft** y, después, **Cerrar**.

En función del número de usuarios asignados a los grupos de roles de administración de riesgos internos, todos los investigadores y analistas pueden tardar 15 minutos en agregarse al equipo de Microsoft Teams para un caso.

## <a name="analytics"></a>Análisis

Los análisis de riesgos internos le permiten realizar una evaluación de los posibles riesgos internos en su organización sin necesidad de configurar ninguna directiva de riesgos internos. Esta evaluación puede ayudar a su organización a identificar áreas potenciales de mayor riesgo para los usuarios y ayudar a determinar el tipo y el alcance de las directivas de administración de riesgos internos que puede considerar configurar. Los exámenes de análisis ofrecen las siguientes ventajas para su organización:

- Fácil de configurar: para empezar a trabajar con los exámenes de análisis, puede seleccionar Ejecutar examen cuando se le solicite la recomendación de análisis o ir a Configuración  >  de **riesgo de Insider****Análisis** y habilitar el análisis.
- Privacidad por diseño: los resultados del examen y la información se devuelven como actividad de usuario agregada y anonimizada, los revisores no pueden identificar los nombres de usuario individuales.
- Comprender los posibles riesgos a través de información consolidada: los resultados del examen pueden ayudarle a identificar rápidamente posibles áreas de riesgo para los usuarios y qué directiva sería mejor para ayudar a mitigar estos riesgos.

Consulte el [vídeo de Insider Risk Management Analytics](https://www.youtube.com/watch?v=5c0P5MCXNXk) para ayudar a comprender cómo el análisis puede ayudar a acelerar la identificación de posibles riesgos internos y ayudarle a tomar medidas rápidamente.

Análisis examina los eventos de actividad de riesgo de varios orígenes para ayudar a identificar información sobre las posibles áreas de riesgo. En función de la configuración actual, el análisis busca actividades de riesgo aptas en las siguientes áreas:

- **Registros de auditoría de Microsoft 365**: incluidos en todos los exámenes, este es el origen principal para identificar la mayoría de las actividades potencialmente de riesgo.
- **Exchange Online**: incluida en todos los exámenes, Exchange Online actividad ayuda a identificar las actividades en las que los datos adjuntos se envían por correo electrónico a contactos o servicios externos.
- **Azure Active Directory**: incluido en todos los exámenes, el historial de Azure Active Directory ayuda a identificar las actividades de riesgo asociadas a los usuarios con cuentas de usuario eliminadas.
- **Conector de datos de RR. HH. de Microsoft 365**: si está configurado, los eventos del conector de RR. HH. ayudan a identificar las actividades de riesgo asociadas a los usuarios que tienen dimisiones o próximas fechas de finalización.

La información de análisis de los exámenes se basa en las mismas señales de actividad de riesgo usadas por las directivas de administración de riesgos internos y en los resultados de informes basados en actividades de usuario únicas y de secuencia. Sin embargo, la puntuación de riesgos para el análisis se basa en hasta 10 días de actividad, mientras que las directivas de riesgo interno usan la actividad diaria para obtener información. La primera vez que habilite y ejecute análisis en su organización, verá los resultados del examen durante un día. Si deja el análisis habilitado, verá los resultados de cada examen diario agregado a los informes de información para un intervalo máximo de los 10 días anteriores de actividad.

### <a name="enable-analytics-and-start-your-scan"></a>Habilitación del análisis e inicio del examen

Para habilitar el análisis de riesgos internos, debe ser miembro del grupo de roles *Insider Risk Management*, *Insider Risk Management Administración* o *Microsoft 365 Global admin*.
Complete los pasos siguientes para habilitar el análisis de riesgos internos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Seleccione **Ejecutar examen** en la tarjeta **Buscar riesgos internos en** la tarjeta de la organización en la pestaña **Información general sobre** la administración de riesgos internos. Esto activa el análisis de la organización. También puede activar el examen en su organización; para ello, vaya a Configuración  >  de **riesgo de Insider****Analytics** y habilite **Examinar la actividad de usuario del inquilino para identificar posibles riesgos** internos.
3. En el panel **Detalles de Analytics** , seleccione **Ejecutar examen** para iniciar el examen de su organización. Los resultados del análisis pueden tardar hasta 48 horas antes de que la información esté disponible como informes para su revisión.

![Configuración de análisis de administración de riesgos internos.](../media/insider-risk-settings-analytics-enable.png)

### <a name="viewing-analytics-insights-and-creating-new-policies"></a>Visualización de información de análisis y creación de nuevas directivas

Una vez completado el primer examen de análisis para su organización, los miembros del grupo de roles *Insider Risk Management Administración* recibirán automáticamente una notificación por correo electrónico y podrán ver las conclusiones iniciales y las recomendaciones para actividades potencialmente de riesgo por parte de los usuarios. Los exámenes diarios continúan a menos que desactive el análisis de su organización. Las notificaciones por correo electrónico a los administradores se proporcionan para cada una de las tres categorías de ámbito para el análisis (fugas de datos, robo y filtración) después de la primera instancia de actividad en su organización. Las notificaciones por correo electrónico no se envían a los administradores para la detección de actividad de seguimiento resultante de los exámenes diarios. Si **los análisis** de **Configuración de** >  **administración** >  de riesgos internos están deshabilitados y, a continuación, se vuelven a habilitar en su organización, se restablecen las notificaciones automáticas por correo electrónico y se envían correos electrónicos a los miembros del grupo de roles *Insider Risk Management Administración* para obtener nuevas conclusiones de examen.

Para ver posibles riesgos para su organización, vaya a la pestaña **Información general** y seleccione **Ver resultados** en la tarjeta **análisis de riesgos de Insider** . Si el examen de su organización no está completo, verá un mensaje que indica que el examen sigue activo.

![Tarjeta lista para informes de análisis de administración de riesgos internos.](../media/insider-risk-analytics-ready-card.png)

En el caso de los exámenes completados, verá los posibles riesgos detectados en su organización y las conclusiones y recomendaciones para abordar estos riesgos. Los riesgos identificados y la información específica se incluyen en los informes agrupados por área, el número total de usuarios con riesgos identificados, el porcentaje de estos usuarios con actividades potencialmente de riesgo y una directiva de riesgo interno recomendada para ayudar a mitigar estos riesgos. Los informes incluyen:

- **Información sobre fugas de datos**: actividades para todos los usuarios que pueden incluir el uso compartido accidental de información fuera de su organización o filtraciones de datos por parte de usuarios con intención malintencionada.
- **Información sobre robo de datos**: actividades para usuarios que abandonan o usuarios con cuentas de Azure Active Directory eliminadas que pueden incluir el uso compartido de información fuera de su organización o el robo de datos por parte de usuarios con intención malintencionada.
- **Información de filtración superior**: actividades de todos los usuarios que pueden incluir el uso compartido de datos fuera de su organización.

![Informe de información general de análisis de administración de riesgos internos.](../media/insider-risk-analytics-overview.png)

Para mostrar más información sobre una información, seleccione **Ver detalles** para mostrar el panel de detalles de la información. El panel de detalles incluye los resultados completos de la información, una recomendación de directiva de riesgo interno y el botón **Crear directiva** para ayudarle a crear rápidamente la directiva recomendada. Al seleccionar Crear directiva, se le lleva al Asistente para directivas y se selecciona automáticamente la plantilla de directiva recomendada relacionada con la información. Por ejemplo, si la información de análisis es para la actividad *de pérdida de datos* , la plantilla de directiva General *data leaks* se seleccionará previamente en el Asistente para directivas.

![Informe de detalles de análisis de administración de riesgos internos.](../media/insider-risk-analytics-details.png)

### <a name="turn-off-analytics"></a>Desactivar el análisis

Para desactivar el análisis de riesgos internos, debe ser miembro del grupo de roles *Insider Risk Management*, *Insider Risk Management Administración* o Microsoft 365 *Global admin*. Después de deshabilitar el análisis, los informes de información de análisis permanecerán estáticos y no se actualizarán para nuevos riesgos.

Complete los pasos siguientes para desactivar el análisis de riesgos internos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider**.
2. Seleccione **la página Análisis de configuración de** >  riesgos internos.
3. En la página **Análisis** , desactive **Examinar la actividad de usuario del inquilino para identificar posibles riesgos** internos.

## <a name="admin-notifications"></a>notificaciones de Administración

Administración notificaciones envían automáticamente una notificación por correo electrónico a grupos de roles de administración de riesgos internos seleccionables. Puede habilitar las notificaciones y asignar qué grupos de roles recibirán las notificaciones para los siguientes escenarios:

- Envíe un correo electrónico de notificación cuando se genere la primera alerta para una nueva directiva. Las directivas se comprueban cada 24 horas para las alertas por primera vez y las notificaciones no se envían en alertas posteriores para la directiva.
- Envíe un correo electrónico diario cuando se generen nuevas alertas de gravedad alta. Las directivas se comprueban cada 24 horas para detectar alertas de gravedad alta.
- Enviar un correo electrónico semanal que resume las directivas que tienen advertencias sin resolver

Si ha habilitado el análisis de administración de riesgos internos para su organización, los miembros del grupo de roles *Insider Risk Management Administración* reciben automáticamente una notificación por correo electrónico para obtener información de análisis inicial para las actividades de filtración, robo y fuga de datos.

Si prefiere deshabilitar las notificaciones de administrador y análisis, siga estos pasos:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de** >  riesgos internos **Configuración de riesgos internos**.
2. Seleccione la página **Administración notificaciones**.
3. Desactive la casilla de las siguientes opciones según corresponda:
    - **Enviar un correo electrónico de notificación cuando se genera la primera alerta para una nueva directiva**
    - **Envío de una notificación por correo electrónico cuando haya una nueva información disponible en Analytics**
    - **Enviar una notificación por correo electrónico cuando Analytics está desactivado**

4. Seleccione **Guardar** para configurar y salir.
