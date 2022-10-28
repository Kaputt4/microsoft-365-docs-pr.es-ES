---
title: Informe de estado del antivirus Microsoft Defender estado del dispositivo
description: Use el informe Microsoft Defender Antivirus para realizar un seguimiento del estado del antivirus y Microsoft Defender versiones del motor, la inteligencia y la plataforma antivirus.
keywords: Microsoft Defender informe antivirus, versión del motor, versión de inteligencia y versiones de plataforma, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
ms.date: 09/06/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
ms.reviewer: mkaminska
ms.openlocfilehash: 9e8e54f6d788a8a4c35da2f318f55c0f7921ce67
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770357"
---
# <a name="device-health-microsoft-defender-antivirus-health-report"></a>Estado del dispositivo, Microsoft Defender informe de estado del antivirus

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

El informe Estado del dispositivo proporciona información sobre los dispositivos de la organización. El informe incluye información de tendencias que muestra el estado del antivirus y Microsoft Defender versiones del motor, la inteligencia y la plataforma antivirus.

> [!IMPORTANT]
> Para que Windows&nbsp;Server 2012 R2&nbsp;y Windows&nbsp;Server&nbsp;2016 aparezcan en los informes de estado del dispositivo, estos dispositivos deben incorporarse mediante el paquete de solución unificado&nbsp;moderno. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

En el panel de navegación del panel de seguridad de Microsoft 365, seleccione **Informes** y, a continuación, abra **Estado y cumplimiento del dispositivo**.

- La [pestaña **estado Microsoft Defender Antivirus**](#microsoft-defender-antivirus-health-tab) tiene ocho tarjetas que informan sobre los siguientes aspectos de Microsoft Defender Antivirus:
  - [Tarjeta de modo antivirus](#antivirus-mode-card)
  - [Tarjeta de versión del motor antivirus](#antivirus-engine-version-card)
  - [Tarjeta de versión de inteligencia de seguridad antivirus](#antivirus-security-intelligence-version-card)
  - [Tarjeta de versión de la plataforma antivirus](#antivirus-platform-version-card)
  - [Tarjeta de resultados del examen antivirus reciente](#recent-antivirus-scan-results-card)
  - [Tarjeta de actualizaciones del motor antivirus](#antivirus-engine-updates-card)
  - [Tarjeta de actualizaciones de inteligencia de seguridad](#security-intelligence-updates-card)
  - [Tarjeta de actualizaciones de la plataforma antivirus](#antivirus-platform-updates-card)

## <a name="report-access-permissions"></a>Permisos de acceso de informes

Para acceder al informe de cumplimiento de antivirus y estado del dispositivo en el panel seguridad de Microsoft 365, se requieren los siguientes permisos:

| Nombre del permiso | Tipo de permiso |
|:---|:---|
| Ver datos | Administración de amenazas y vulnerabilidades (TVM) |

Para asignar estos permisos:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta con el administrador de seguridad o Administrador global rol asignado.
1. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).
1. Seleccione el rol que desea editar.
1. Seleccione **Editar**.
1. En **Editar rol**, en la pestaña **General** , en **Nombre del** rol, escriba un nombre para el rol.
1. En **Descripción** , escriba un breve resumen del rol.
1. En **Permisos**, seleccione **Ver datos** y, en **Ver datos** , seleccione **Administración de amenazas y vulnerabilidades** (TVM).

Para obtener más información sobre la administración de roles de usuario, consulte [Creación y administración de roles para el control de acceso basado en rol](user-roles.md).

## <a name="microsoft-defender-antivirus-health-tab"></a>Microsoft Defender pestaña Estado del antivirus 
La pestaña estado Microsoft Defender Antivirus contiene ocho tarjetas que informan sobre varios aspectos de Microsoft Defender Antivirus en su organización:

Dos tarjetas, [tarjeta de modo antivirus](#antivirus-mode-card) y [tarjeta de resultados de análisis antivirus recientes](#recent-antivirus-scan-results-card), informan sobre Microsoft Defender funciones antivirus.

Las seis tarjetas restantes informan sobre el estado del antivirus de Microsoft Defender para los dispositivos de su organización:

| _tarjetas de versión_ : | _tarjetas de actualización_ {<a id="fn1">1</a>} |
|:---|:---|
| [Tarjeta de versión del motor antivirus](#antivirus-engine-version-card) <br> [Tarjeta de versión de inteligencia de seguridad antivirus](#antivirus-security-intelligence-version-card) <br> [Tarjeta de versión de la plataforma antivirus](#antivirus-platform-version-card) | [Tarjeta de actualizaciones del motor antivirus](#antivirus-engine-updates-card) <br> [Tarjeta de actualizaciones de inteligencia de seguridad](#security-intelligence-updates-card) <br> [Tarjeta de actualizaciones de la plataforma antivirus](#antivirus-platform-updates-card) |
| Las tres tarjetas de versión proporcionan informes de control flotante que proporcionan información adicional y permiten una exploración adicional. | Las tres tarjetas de informes actualizadas proporcionan vínculos a los recursos para obtener más información. |

<sup>{[1](#fn1)}</sup> Para las tres tarjetas de _actualizaciones_ (también conocidas como tarjetas de informes actualizadas), "**No hay datos disponibles**" (o valor "Desconocido") indica los dispositivos que no notifican el estado de actualización. Los dispositivos que no notifican el estado de actualización pueden deberse a diversos motivos, como:

- El equipo está desconectado de la red
- El equipo está apagado o en estado de hibernación
- Microsoft Defender Antivirus está deshabilitado
- El dispositivo es un dispositivo que no es de Windows (Mac o Linux)
- La protección en la nube no está habilitada
- El dispositivo no cumple los requisitos previos para el motor antivirus o la versión de la plataforma

### <a name="prerequisites"></a>Requisitos previos

Los informes actualizados generan información para los dispositivos que cumplen los siguientes criterios:

- Versión del motor: 1.1.19300.2+
- Versión de la plataforma: 4.18.2202.1+
- Protección en la nube habilitada
- Sistema operativo Windows*

*Actualmente, los informes actualizados solo están disponibles para dispositivos Windows. Los dispositivos multiplataforma, como Mac y Linux, aparecen en "No hay datos disponibles"/Desconocido

>:::image type="content" source="images/device-health-defender-antivirus-health-tab.png" alt-text="Muestra la pestaña estado del antivirus Microsoft Defender." lightbox="images/device-health-defender-antivirus-health-tab.png":::

### <a name="card-functionality"></a>Funcionalidad de tarjeta

La funcionalidad es básicamente la misma para todas las tarjetas. Al hacer clic en una barra numerada en cualquiera de las tarjetas, se abre el control flotante de **detalles del antivirus Microsoft Defender** que le permite revisar la información sobre todos los dispositivos configurados con el número de versión de un aspecto en esa tarjeta.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details.png" alt-text="Muestra el control flotante de detalles Microsoft Defender Antivirus." lightbox="images/device-health-defender-antivirus-health-antivirus-details.png":::

Si el número de versión en el que ha hecho clic es:

- Una versión actual y, a continuación, corrección **necesaria y recomendación** **de seguridad** no están presentes
- Una versión obsoleta, una notificación en la parte superior del informe está presente, lo que indica la **corrección necesaria** y hay un vínculo **de recomendación de seguridad** . Seleccione el vínculo de recomendación de seguridad para navegar a la consola de Administración de amenazas y vulnerabilidades, que puede recomendar las actualizaciones de antivirus adecuadas.

Para agregar o quitar tipos específicos de información sobre el control flotante de **detalles de Microsoft Defender Antivirus**, seleccione **Personalizar columnas**. En **Personalizar columnas**, seleccione o desactive los elementos para especificar lo que quiere incluir en el informe de detalles del antivirus de Microsoft Defender.

>:::image type="content" source="images/device-health-defender-antivirus-engine-version-details-custom-columns.png" alt-text="Muestra las opciones de columna personalizadas para Microsoft Defender informes de estado del antivirus." lightbox="images/device-health-defender-antivirus-engine-version-details-custom-columns.png":::

#### <a name="new-microsoft-defender-antivirus-filter-definitions"></a>Nuevas definiciones de filtro Microsoft Defender Antivirus

La tabla siguiente contiene una lista de términos que son nuevos en Microsoft Defender informes antivirus.

| Nombre de columna | Descripción |
|:---|:---|
| Tiempo de publicación de inteligencia de seguridad | Indica la fecha de lanzamiento de Microsoft de la versión de actualización de inteligencia de seguridad en el dispositivo. Los dispositivos con un tiempo de publicación de inteligencia de seguridad superior a siete días se consideran obsoletos en los informes. |
| Visto por última vez | Indica la fecha en que el dispositivo tuvo la última conexión. |
| Marca de tiempo de actualización de datos | Indica cuándo se recibieron por última vez los eventos de cliente para la generación de informes en: modo AV, versión del motor av, versión de la plataforma AV, versión de inteligencia de seguridad de AV e información de examen. |
| Hora de actualización de la firma | Indica cuándo se recibieron por última vez eventos de cliente para informar sobre el estado actualizado del motor, la plataforma y la firma. |

Dentro del control flotante: al hacer clic en el nombre del dispositivo, se le redirigirá a la "página Dispositivo" de ese dispositivo, donde puede acceder a informes detallados.

#### <a name="export-report"></a>Exportar informe

Hay dos niveles de informes que puede exportar:

##### <a name="top-level-export"></a>Exportación de nivel superior

Hay dos funcionalidades csv de exportación diferentes a través del portal:

- **Exportación de nivel superior** Puede usar el botón **Exportar** de nivel superior para recopilar un informe de estado de antivirus de Microsoft Defender de nivel superior (límite de 500 K).

>:::image type="content" source="images/device-health-defender-antivirus-health-tab-export.png" alt-text="Muestra el botón del informe de exportación de nivel superior" lightbox="images/device-health-defender-antivirus-health-tab-export.png":::

- **Exportación de nivel de control flotante** Puede usar el botón **Exportar** dentro de los controles flotantes para exportar un informe a una hoja de cálculo de Excel (límite de 100 K).

Los informes exportados capturan información basada en el punto de entrada en el informe de detalles y qué filtros o columnas personalizadas ha establecido.

Para obtener información sobre la exportación mediante la API, consulte los artículos siguientes:

- [Exportar informe de estado del antivirus del dispositivo](device-health-export-antivirus-health-report-api.md)
- [Exportación de propiedades y métodos de API de detalles de estado del antivirus de dispositivo](device-health-api-methods-properties.md)

> [!IMPORTANT]
>
> Actualmente, solo la **respuesta JSON de estado del antivirus** está disponible con carácter general. **Antivirus Health API a través de archivos** solo está disponible en versión preliminar pública.
>
> **La consulta personalizada de búsqueda avanzada** solo está disponible actualmente en versión preliminar pública, incluso si las consultas siguen estando visibles.

### <a name="microsoft-defender-antivirus-version-and-update-cards-functionality"></a>Microsoft Defender funcionalidad de tarjetas de actualización y versión antivirus

A continuación se muestran descripciones de las seis tarjetas que informan sobre la _información de versión_ y _actualización_ de Microsoft Defender motor antivirus, inteligencia de seguridad y componentes de plataforma:

#### <a name="full-report"></a>Informe completo

En cualquiera de las tres tarjetas de _versión_, seleccione **Ver informe completo** para mostrar los nueve informes de _versión_ de antivirus de Microsoft Defender más recientes para cada uno de los tres tipos de dispositivo: Windows, Mac y Linux; si existen menos de nueve, se mostrarán todos ellos. Una categoría **Other** captura las versiones recientes del motor antivirus que se clasifican en el décimo lugar y por debajo, si se detectan.

>:::image type="content" source="images/device-health-defender-antivirus-health-view-full-report.png" alt-text="Muestra la distribución de los nueve sistemas operativos principales de cada tipo." lightbox="images/device-health-defender-antivirus-health-view-full-report.png":::

Una ventaja principal de las tres tarjetas de _versión_ es que proporcionan indicadores rápidos sobre si se están usando las versiones más actuales de los motores antivirus, las plataformas y la inteligencia de seguridad. Junto con la información detallada que está vinculada a la tarjeta, las tarjetas de versiones se convierten en una herramienta eficaz para comprobar si las versiones están actualizadas y recopilar información sobre equipos individuales o grupos de equipos.
Lo ideal es que, al ejecutar estos informes, indiquen que están instaladas las versiones antivirus más actuales, en lugar de las versiones anteriores.
Use estos informes para determinar si su organización aprovecha al máximo las versiones más actuales.

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png" alt-text="Muestra Microsoft Defender detalles de la versión del antivirus" lightbox="images/device-health-defender-antivirus-health-antivirus-details-up-to-date.png":::

Para ayudar a garantizar que la solución antimalware detecta las amenazas más recientes, obtenga actualizaciones automáticamente como parte de Windows Update.

Para obtener más información sobre las versiones actuales y cómo actualizar los distintos componentes de antivirus de Microsoft Defender, visite [Microsoft Defender compatibilidad con la plataforma antivirus](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="card-descriptions"></a>Descripciones de tarjetas

A continuación se muestran breves resúmenes de la información recopilada notificada en cada una de las tarjetas de _versión del Antivirus_ :

#### <a name="antivirus-mode-card"></a>Tarjeta de modo antivirus

Los informes sobre cuántos dispositivos de su organización , en la fecha indicada en la tarjeta, se encuentran en cualquiera de los siguientes modos Microsoft Defender Antivirus:

| valor | mode |
|---|---|
| 0 | Activo |
| 1 | Pasiva |
| 2 | Deshabilitado (desinstalado, deshabilitado o SideBySidePassive {también conocido como Examen periódico bajo}) |
| 3 | Otros (No en ejecución, Desconocido) |
| 4 | EDRBlocked |

>:::image type="content" source="images/device-health-defender-antivirus-health-antivirus-mode.png" alt-text="Muestra el filtrado Microsoft Defender modos antivirus" lightbox="images/device-health-defender-antivirus-health-antivirus-mode.png":::

A continuación se muestran las descripciones de cada modo:

- **Modo activo**: en modo activo, Microsoft Defender Antivirus se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan, se corrigen las amenazas y las amenazas detectadas se enumeran en los informes de seguridad de la organización y en la aplicación de Seguridad de Windows.
- **Modo pasivo**: en modo pasivo, Microsoft Defender Antivirus no se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan y se notifican amenazas detectadas, pero Microsoft Defender Antivirus no corrige las amenazas. IMPORTANTE: El Antivirus de Microsoft Defender solo se puede ejecutar en modo pasivo en los puntos de conexión que se incorporan a Microsoft Defender para punto de conexión. Consulte [Requisitos para que el Antivirus de Microsoft Defender se ejecute en modo pasivo](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode).
- **Modo deshabilitado** : sinónimo de: desinstalado, deshabilitado, sideBySidePassive y Examen periódico bajo. Cuando está deshabilitado, no se usa Microsoft Defender Antivirus. Los archivos no se examinan y las amenazas no se corrigen. En general, Microsoft no recomienda deshabilitar ni desinstalar Microsoft Defender Antivirus.
- **Modo Otros** : No en ejecución, Desconocido
- **EDR en modo de bloque** : en el modo bloqueado de detección y respuesta de puntos de conexión (EDR). Consulte [Detección y respuesta de puntos de conexión en modo de bloque](edr-in-block-mode.md)

Los dispositivos que se encuentran en pasivos, LPS o desactivados presentan un riesgo de seguridad potencial y se deben investigar.

Para obtener más información sobre LPS, consulte [Uso del examen periódico limitado en Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

#### <a name="recent-antivirus-scan-results-card"></a>Tarjeta de resultados del examen antivirus reciente

Esta tarjeta tiene dos gráficos de barras que muestran los resultados completos de los exámenes rápidos y los exámenes completos. En ambos gráficos, la primera barra indica la tasa de finalización de los exámenes e indica **Completado**, **Cancelado** o **Erróneo**. La segunda barra de cada sección proporciona los códigos de error para los exámenes con errores.
Al examinar las columnas **Mode (Modo** ) y **Recent scan results (Resultados del examen reciente** ), puede identificar rápidamente los dispositivos que no están en modo de examen antivirus activo y los dispositivos que han producido errores o han cancelado los exámenes antivirus recientes. Puede volver al informe con esta información y recopilar más detalles y recomendaciones de seguridad. Si se notifica algún código de error en esta tarjeta, habrá un vínculo para obtener más información sobre los códigos de error.

Para obtener más información sobre las versiones actuales de antivirus de Microsoft Defender y cómo actualizar los distintos componentes de antivirus de Microsoft Defender, visite [Administrar actualizaciones Microsoft Defender Antivirus y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

#### <a name="antivirus-engine-version-card"></a>Tarjeta de versión del motor antivirus

Muestra los resultados en tiempo real de las versiones más actuales del motor Microsoft Defender Antivirus instaladas en dispositivos Windows, dispositivos Mac y dispositivos Linux de su organización. Microsoft Defender motor antivirus se actualiza mensualmente.
Para obtener más información sobre las versiones actuales y cómo actualizar los distintos componentes Microsoft Defender Antivirus, consulte [Microsoft Defender compatibilidad con la plataforma antivirus](manage-updates-baselines-microsoft-defender-antivirus.md).

#### <a name="antivirus-security-intelligence-version-card"></a>Tarjeta de versión de inteligencia de seguridad antivirus

Enumera las versiones de _inteligencia de seguridad de antivirus más comunes Microsoft Defender_ instaladas en los dispositivos de la red.
Microsoft actualiza continuamente Microsoft Defender inteligencia de seguridad para abordar las amenazas más recientes y para refinar la lógica de detección. Estos refinamientos para la inteligencia de seguridad mejoran Microsoft Defender capacidad de antivirus (y otras soluciones antimalware de Microsoft) para identificar con precisión posibles amenazas. Esta inteligencia de seguridad funciona directamente con la protección basada en la nube para ofrecer una protección de próxima generación mejorada con inteligencia artificial que es rápida y eficaz.

##### <a name="antivirus-platform-version-card"></a>Tarjeta de versión de la plataforma antivirus

Muestra los resultados en tiempo real de las versiones más actuales de la plataforma antivirus de Microsoft Defender instaladas en las versiones de dispositivos Windows, Mac y Linux de su organización. Microsoft Defender plataforma antivirus se actualiza mensualmente.
Para obtener más información sobre las versiones actuales y cómo actualizar los distintos componentes Microsoft Defender Antivirus, consulte [Microsoft Defender compatibilidad con la plataforma antivirus](manage-updates-baselines-microsoft-defender-antivirus.md).

#### <a name="up-to-date-cards"></a>Tarjetas actualizadas

Las tarjetas actualizadas muestran el estado actualizado del **motor antivirus**, la **plataforma antivirus** y las versiones de actualización **de inteligencia de seguridad** . Hay tres estados posibles: _Actualizado_ ('True'), _obsoleto_ ('False') y _sin datos disponibles_ ('Desconocido').

> [!IMPORTANT]
>
> Recientemente se ha mejorado y simplificado la lógica utilizada para la determinación actualizada. El nuevo comportamiento se documenta en esta sección.

Las definiciones de _Actualizado_, _Obsoleto_ y _Sin datos disponibles_ se proporcionan para cada tarjeta siguiente.

Microsoft Defender Antivirus usa los criterios adicionales de "Hora de actualización de firma" (la última vez que el dispositivo se comunica con informes actualizados) para crear informes y determinaciones actualizados para las actualizaciones de motor, plataforma e inteligencia de seguridad.

El estado actualizado se marca automáticamente como "desconocido" o "sin datos disponibles" si el dispositivo no se ha comunicado con los informes durante más de siete días (tiempo de actualización de la firma >7).

Para obtener más información sobre los términos mencionados anteriormente, consulte la sección: [Nuevas definiciones de filtro Microsoft Defender Antivirus](#new-microsoft-defender-antivirus-filter-definitions).

> [!NOTE]
>
> **Requisitos previos de informes actualizados**
>
> Los informes actualizados generan información para los dispositivos que cumplen los siguientes criterios:
>
> - Versión del motor: 1.1.19300.2+
> - Versión de la plataforma: 4.18.2202.1+
> - Protección en la nube habilitada
> - Sistema operativo Windows*
>
>*Actualmente, los informes actualizados solo están disponibles para dispositivos Windows. Los dispositivos multiplataforma, como Mac y Linux, aparecen en "No hay datos disponibles"
>

##### <a name="up-to-date-definitions"></a>Definiciones actualizadas

A continuación se muestran definiciones actualizadas para el motor y la plataforma:

| El motor o plataforma en el dispositivo se considera: | Si: |
|:---|:---|
| **actualizado** | el dispositivo comunicado con el evento de informe de Defender ('Hora de actualización de la firma') en los últimos siete días y el tiempo de compilación de la versión del motor o de la plataforma se encuentra en los últimos 60 días. |
| **desactualizadas** | el dispositivo comunicado con el evento de informe de Defender ('Hora de actualización de firma') en los últimos siete días, pero el tiempo de compilación de la versión del motor o de la plataforma es anterior a 60 días. |
| **unknown (no hay datos disponibles)** | el dispositivo no se ha comunicado con el evento de informe ('Hora de actualización de firma') durante más de siete días. |

A continuación se muestran definiciones actualizadas de inteligencia de seguridad:

| Se considera la actualización de inteligencia de seguridad | Si: |
|:---|:---|
|**Actualizado** | la versión de inteligencia de seguridad del dispositivo se escribió en los últimos siete días y el dispositivo se ha comunicado con el evento del informe en los últimos siete días. |

Para obtener más información, consulte:

- [Tarjeta de actualizaciones del motor antivirus](#antivirus-engine-updates-card)
- [Tarjeta de actualizaciones de inteligencia de seguridad](#security-intelligence-updates-card)
- [Tarjeta de actualizaciones de la plataforma antivirus](#antivirus-platform-updates-card)

##### <a name="antivirus-engine-updates-card"></a>Tarjeta de actualizaciones del motor antivirus

Esta tarjeta identifica los dispositivos que tienen versiones del motor antivirus que están actualizadas frente a obsoletas.

**La definición general de "_Actualizado_":** la versión del motor en el dispositivo es la versión más reciente del motor. El motor se suele publicar _mensualmente_, a través de Windows Update (WU)). Hay un período de gracia de tres días dado desde el día en que se libera Windows Update (WU).

En la tabla siguiente se establecen los valores posibles para los informes actualizados de **Antivirus Engine**. El estado notificado se basa en la última vez que se recibió el evento de informes (_hora de actualización de la firma_). Si el dispositivo no se ha comunicado con los informes durante más de siete días (tiempo de actualización de la firma >7 días), el estado se marca automáticamente como "Desconocido" o "Sin datos disponibles".

| Hora de la última actualización del evento (también conocida como "Hora de actualización de firma" en los informes) | _Estado notificado_: |
|:----|:----|
| < 7 días (nuevo) | informes de cliente _<br/> <br/> (no actualizados actualizados desconocidos)_ |
| > 7 días (de edad) | _Desconocido_ |

Para obtener información sobre la administración de versiones de actualización Microsoft Defender Antivirus, consulte: [Versiones mensuales de la plataforma y del motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

#### <a name="antivirus-platform-updates-card"></a>Tarjeta de actualizaciones de la plataforma antivirus

Esta tarjeta identifica los dispositivos que tienen versiones de la plataforma Antivirus actualizadas frente a obsoletas.

**Definición general de "Actualizado"** La versión de la plataforma en el dispositivo es la versión más reciente de la plataforma. Normalmente, la plataforma se publica _mensualmente_ a través de Windows Update (WU). Hay un período de gracia de tres días a partir del día en que wu se libera.

En la tabla siguiente se establecen los posibles valores de informe actualizados para **La plataforma antivirus**. Los valores notificados se basan en la última vez que se recibió el evento de informes (hora de actualización de la firma). Si el dispositivo no se ha comunicado con los informes durante más de siete días (tiempo de actualización de la firma >7 días), el estado se marca automáticamente como "Desconocido"/ "No hay datos disponibles".

| Hora de la última actualización del evento (también conocida como "Hora de actualización de firma" en los informes) | _Estado notificado_: |
|:----|:----|
| < 7 días (nuevo) | informes de cliente _<br/> <br/> (no actualizados actualizados desconocidos)_ |
| > 7 días (de edad) | _Desconocido_ |

Para obtener información sobre la administración de versiones de actualización Microsoft Defender Antivirus, consulte: [Versiones mensuales de la plataforma y del motor](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

##### <a name="security-intelligence-updates-card"></a>Tarjeta de actualizaciones de inteligencia de seguridad

Esta tarjeta identifica los dispositivos que tienen versiones de inteligencia de seguridad actualizadas frente a obsoletas.

**La definición general de "Actualizado":** la versión de inteligencia de seguridad del dispositivo se escribió en los últimos 7 días.

En la tabla siguiente se establecen los posibles valores de informe actualizados para las actualizaciones **de Security Intelligence** . Los valores notificados se basan en la última vez que se recibió el evento de informes y en la hora de publicación de la inteligencia de seguridad. Si el dispositivo no se ha comunicado con los informes durante más de siete días (tiempo de actualización de la firma >7 días), el estado se marca automáticamente como "Desconocido/ Sin datos disponibles". De lo contrario, la determinación se realiza en función de si el tiempo de publicación de inteligencia de seguridad es dentro de los siete días.

| Hora de última actualización del evento <br/> (También conocido como "Hora de actualización de firma" en los informes) | Hora de publicación de Security Intelligence | _Estado notificado_: |
|:----|:----|:----|
| >7 días (de edad) | >7 días (de edad) | _Desconocido_ |
| <7 días (nuevo) | >7 días (de edad) | _Obsoleto_ |
| >7 días (de edad) | <7 días (nuevo) | _Desconocido_ |
| <7 días (nuevo) | <7 días (nuevo) | Hasta la fecha |

## <a name="see-also"></a>Vea también

- [Exportación de propiedades y métodos de API de detalles de estado del antivirus de dispositivo](device-health-api-methods-properties.md)
- [Exportar informe de estado del antivirus del dispositivo](device-health-api-methods-properties.md)
- [Informe de protección contra amenazas](threat-protection-reports.md)

> [!TIP]
> Para obtener información relacionada con el antivirus para otras plataformas, consulte:
>
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
