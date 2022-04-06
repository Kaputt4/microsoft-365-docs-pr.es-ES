---
title: Ideas e informa sobre el entrenamiento de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Los administradores pueden aprender cómo el aprendizaje de simulación de ataques en el portal de Microsoft 365 Defender afecta a los usuarios y pueden obtener información sobre los resultados de simulación y aprendizaje.
ms.technology: mdo
ms.openlocfilehash: a360343fd4406dc79d072927fef41369bbe21ed8
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473901"
---
# <a name="insights-and-reports-for-attack-simulation-training-in-defender-for-office-365"></a>Ideas e informes para el entrenamiento de simulación de ataques en Defender para Office 365

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En El aprendizaje de simulación de ataques en Microsoft Defender para Office Plan 2 o Microsoft 365 E5, Microsoft proporciona información e informes de los resultados de las simulaciones y los cursos correspondientes. Esta información te mantiene informado sobre el progreso de preparación de amenazas de los usuarios, así como los siguientes pasos recomendados para preparar mejor a los usuarios para futuros ataques.

Ideas y los informes están disponibles en las siguientes ubicaciones del aprendizaje de simulación de ataques en el portal de Microsoft 365 Defender ataque:

- Pestaña **Información** general.
- Detalles de simulación en la **pestaña Simulaciones** .

El resto de este artículo describe la información disponible.

Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta [Introducción al aprendizaje de simulación de ataques](attack-simulation-training-get-started.md).

## <a name="insights-and-reports-on-the-overview-tab-of-attack-simulation-training"></a>Ideas informes en la pestaña Información general del entrenamiento de simulación de ataques

Para ir a la  pestaña Información general, abra el portal <https://security.microsoft.com>de Microsoft 365 Defender en , vaya **a** \> Aprendizaje de simulación de ataques de colaboración de correo electrónico &  y compruebe que la pestaña Información general está seleccionada (es el valor predeterminado). Para ir directamente a la pestaña **Información general** de la **página De aprendizaje de simulación de** ataques, use <https://security.microsoft.com/attacksimulator?viewid=overview>.

El resto de esta sección describe la información disponible en la pestaña Información general del  entrenamiento de simulación de ataques.

### <a name="recent-simulations-card"></a>Tarjeta de simulaciones recientes

La **tarjeta Simulaciones recientes** **de la pestaña** Información general muestra las tres últimas simulaciones que ha creado o ejecutado en su organización.

Puede seleccionar una simulación para ver detalles.

Si selecciona **Ver todas las simulaciones** , podrá ir a la **pestaña Simulaciones** .

Al seleccionar **Iniciar una simulación** , se inicia el asistente para la creación de simulación. Para obtener más información, consulta [Simular un ataque de suplantación de identidad en Defender para Office 365](attack-simulation-training.md).

:::image type="content" source="../../media/attack-sim-training-overview-recent-simulations-card.png" alt-text="La tarjeta Simulaciones recientes de la pestaña Información general del aprendizaje de simulación de ataque en el portal Microsoft 365 Defender ataque" lightbox="../../media/attack-sim-training-overview-recent-simulations-card.png":::

### <a name="behavior-impact-on-compromise-rate-card"></a>Impacto del comportamiento en la tarjeta de tasa de riesgo

El **impacto del comportamiento en la tarjeta de** tasa  de compromiso de la pestaña Información general muestra cómo respondieron los usuarios a las simulaciones en comparación con los datos históricos de Microsoft 365. Puede usar estas perspectivas para realizar un seguimiento del progreso en la preparación de amenazas de los usuarios mediante la ejecución de varias simulaciones en los mismos grupos de usuarios.

Los datos del gráfico en sí muestran la siguiente información:

- **Tasa de compromiso predicho**<sup>\*</sup>: la tasa de compromiso promedio de las simulaciones de aprendizaje de simulación de ataque que usan el mismo tipo de carga en todas las demás Microsoft 365 organización.
- **Tasa de compromiso real**<sup>\*</sup>: el porcentaje real de usuarios que han caído en la simulación.

Si mantiene el mouse sobre un punto de datos en el gráfico, se muestran los valores porcentuales reales.

La siguiente información de resumen también se muestra en la tarjeta:

- **usuarios menos susceptibles a la suplantación** de identidad: la diferencia entre el número real de usuarios comprometidos por el ataque simulado y la tasa de compromiso predicho. Es menos probable que este número de usuarios se vea comprometido por ataques similares en el futuro.
- **x% mejor que la tasa predijeda**: indica cómo lo hacían los usuarios en general en contraste con la tasa de compromiso predicho.

:::image type="content" source="../../media/attack-sim-training-overview-behavior-impact-card.png" alt-text="El impacto del comportamiento en la tarjeta de tasa de compromiso en la pestaña Información general del aprendizaje de simulación de ataques en el portal Microsoft 365 Defender seguridad" lightbox="../../media/attack-sim-training-overview-behavior-impact-card.png":::

Para ver un informe más detallado, haga clic **en Ver simulaciones y informe de eficacia de aprendizaje**. Este informe se explica [más adelante en este artículo](#training-efficacy-tab-for-the-attack-simulation-report).

### <a name="simulation-coverage-card"></a>Tarjeta de cobertura de simulación

La **tarjeta** de cobertura de Simulación de la pestaña Información general muestra el porcentaje de usuarios de la organización que han recibido una  simulación **(usuarios** simulados) frente a los que no han recibido una simulación (usuarios no **simulados**). Puede mantener el mouse sobre una sección del gráfico para ver el número real de usuarios de cada categoría.

Al seleccionar **Iniciar simulación** para usuarios no simulados, se inicia el asistente para la creación de simulación donde los usuarios que no recibieron la simulación se seleccionan automáticamente en la **página Usuario de** destino. Para obtener más información, consulta [Simular un ataque de suplantación de identidad en Defender para Office 365](attack-simulation-training.md).

Si selecciona **Ver informe de cobertura de simulación** , se le llevará a la [pestaña Cobertura de usuario del informe de simulación de ataque](#user-coverage-tab-for-the-attack-simulation-report).

:::image type="content" source="../../media/attack-sim-training-overview-sim-coverage-card.png" alt-text="La tarjeta de cobertura de Simulation en la pestaña Información general del aprendizaje de simulación de ataque en el portal de Microsoft 365 Defender ataque" lightbox="../../media/attack-sim-training-overview-sim-coverage-card.png":::

### <a name="training-completion-card"></a>Tarjeta de finalización de aprendizaje

La **tarjeta de finalización** de aprendizaje  de la pestaña Información general organiza los porcentajes de usuarios que recibieron cursos en función de los resultados de las simulaciones en las siguientes categorías:

- **Completed**
- **En curso**
- **Incompleto**

Puede mantener el mouse sobre una sección del gráfico para ver el número real de usuarios de cada categoría.

Al seleccionar **Ver informe de finalización del aprendizaje**, ves a la [pestaña Finalización del aprendizaje del informe de simulación de ataque.](#training-completion-tab-for-the-attack-simulation-report)

### <a name="repeat-offenders-card"></a>Tarjeta reincidente

La **tarjeta Repetir infractores** de la **pestaña Información** general muestra la información sobre los infractores reincidentes. Un _infractor reincidente_ es un usuario que se ha visto comprometido por simulaciones consecutivas. El número predeterminado de simulaciones consecutivas es dos, pero puedes cambiar el valor en la **pestaña** Configuración del entrenamiento de simulación de ataque en <https://security.microsoft.com/attacksimulator?viewid=setting>.

El gráfico organiza los datos de reincidente por [tipo de simulación](attack-simulation-training.md#select-a-social-engineering-technique):

- **Todo**
- **Datos adjuntos de malware**
- **Vínculo a malware**
- **Recolección de credenciales**
- **Vincular en datos adjuntos**
- **Dirección URL de unidad por**

Al seleccionar **Ver informe de reincidente** , te llevará a la pestaña [Repetir infractores del informe de simulación de ataque](#repeat-offenders-tab-for-the-attack-simulation-report).

### <a name="recommendations-card"></a>Recomendaciones tarjeta

La **Recomendaciones** de **la pestaña Información** general sugiere distintos tipos de simulaciones para ejecutar.

Si selecciona **Iniciar ahora,** se inicia el asistente para la creación de simulación con el tipo de simulación especificado seleccionado automáticamente en la **página Seleccionar** técnica. Para obtener más información, consulta [Simular un ataque de suplantación de identidad en Defender para Office 365](attack-simulation-training.md).

:::image type="content" source="../../media/attack-sim-training-overview-recommendations-card.png" alt-text="La Recomendaciones en la pestaña Información general del aprendizaje de simulación de ataque en el portal Microsoft 365 Defender ataque" lightbox="../../media/attack-sim-training-overview-recommendations-card.png":::

### <a name="attack-simulation-report"></a>Informe de simulación de ataques

Puede abrir el informe de **simulación de ataque** desde la **pestaña Información** general haciendo clic en **ver ... botones** de informe que están disponibles en muchas de las tarjetas que se describen en este artículo. Para ir directamente al informe, use <https://security.microsoft.com/attacksimulationreport>

#### <a name="training-efficacy-tab-for-the-attack-simulation-report"></a>Pestaña De eficacia de aprendizaje para el informe de simulación de ataques

En la **página Informe de simulación de** ataque, la pestaña **Eficacia de aprendizaje** está seleccionada de forma predeterminada. Esta pestaña proporciona la misma información que está disponible en la tarjeta  impacto de comportamiento en la tarjeta de tasa de compromiso, con contexto adicional de la propia simulación.

:::image type="content" source="../../media/attack-sim-report-training-efficacy-view.png" alt-text="La pestaña Eficacia de aprendizaje del informe de simulación de ataques en el portal de Microsoft 365 Defender formación" lightbox="../../media/attack-sim-report-training-efficacy-view.png":::

El gráfico muestra la tasa **de compromiso predicho** y **la tasa real comprometida**. Si mantiene el mouse sobre una sección del gráfico, se muestran los valores de porcentaje reales para.

La tabla de detalles debajo del gráfico muestra la siguiente información:

- **Nombre de simulación**
- **Técnica de simulación**
- **Tácticas de simulación**
- **Tasa comprometida predicho**
- **Tasa real comprometida**
- **Total de usuarios dirigidos**
- **Recuento de usuarios clicados**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga **clic en Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Use ![el cuadro **Buscar icono**](../../media/m365-cc-sc-search-icon.png) de búsqueda para filtrar los resultados por **nombre de simulación** o **técnica de simulación**. No se admiten los caracteres comodín.

Si hace clic en el icono ![Exportar.](../../media/m365-cc-sc-download-icon.png) **Botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="user-coverage-tab-for-the-attack-simulation-report"></a>Ficha Cobertura de usuario para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-user-coverage-view.png" alt-text="La pestaña Cobertura de usuario del informe de simulación de ataques en el portal de Microsoft 365 Defender web" lightbox="../../media/attack-sim-report-user-coverage-view.png":::

En la **pestaña Cobertura de** usuario, el gráfico muestra los **usuarios simulados** y **los usuarios no simulados**. Si mantiene el mouse sobre un punto de datos del gráfico, se muestran los valores reales.

La tabla de detalles debajo del gráfico muestra la siguiente información:

- **Username**
- **Dirección de correo electrónico**
- **Incluido en la simulación**
- **Fecha de la última simulación**
- **Último resultado de simulación**
- **Recuento de clics**
- **Recuento de comprometidos**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga **clic en Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Use ![el cuadro **Buscar icono**](../../media/m365-cc-sc-search-icon.png) de búsqueda para filtrar los resultados por **nombre de usuario** o **dirección de correo electrónico**. No se admiten los caracteres comodín.

Si hace clic en el icono ![Exportar.](../../media/m365-cc-sc-download-icon.png) **Botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="training-completion-tab-for-the-attack-simulation-report"></a>Pestaña Finalización del aprendizaje para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-training-completion-view.png" alt-text="La pestaña Finalización del aprendizaje del informe de simulación de ataques en el portal de Microsoft 365 Defender formación" lightbox="../../media/attack-sim-report-training-completion-view.png":::

En la **pestaña Finalización del** aprendizaje, el gráfico muestra el número de simulaciones completadas **, en** **curso e incompletas**.  Si mantiene el mouse sobre una sección del gráfico, se muestran los valores reales.

La tabla de detalles debajo del gráfico muestra la siguiente información:

- **Username**
- **Dirección de correo electrónico**
- **Incluido en la simulación**
- **Fecha de la última simulación**
- **Último resultado de simulación**
- **Nombre de la formación más reciente completada**
- **Fecha completada**
- **Todos los cursos**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga **clic en Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Haga clic ![en Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar el gráfico y la tabla de detalles por uno o más de los siguientes valores:

- **Completed**
- **En curso**
- **Todo**

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar**, **Cancelar** o **Borrar filtros**.

Use ![el cuadro **Buscar icono**](../../media/m365-cc-sc-search-icon.png) de búsqueda para filtrar los resultados por **nombre de usuario** o **dirección de correo electrónico**. No se admiten los caracteres comodín.

Si hace clic en el icono ![Exportar.](../../media/m365-cc-sc-download-icon.png) **Botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="repeat-offenders-tab-for-the-attack-simulation-report"></a>Pestaña Reincidentes para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-repeat-offenders-view.png" alt-text="La pestaña Repetir infractores del informe de simulación de ataque en el portal de Microsoft 365 Defender ataque" lightbox="../../media/attack-sim-report-repeat-offenders-view.png":::

Un _infractor reincidente_ es un usuario que se ha visto comprometido por simulaciones consecutivas. El número predeterminado de simulaciones consecutivas es dos, pero puedes cambiar el valor en la **pestaña** Configuración del entrenamiento de simulación de ataque en <https://security.microsoft.com/attacksimulator?viewid=setting>.

En la **pestaña Repetir infractores** , el gráfico organiza los datos de reincidente por tipo [de simulación](attack-simulation-training.md#select-a-social-engineering-technique):

- **Todo**
- **Recolección de credenciales**
- **Datos adjuntos de malware**
- **Vínculo en datos adjuntos**
- **Vínculo a malware**
- **Dirección URL de unidad por**

Si mantiene el mouse sobre un punto de datos del gráfico, se muestran los valores reales.

La tabla de detalles debajo del gráfico muestra la siguiente información:

- **Usuario**
- **Recuento de repeticiones**
- **Tipos de simulación**
- **Simulaciones**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga **clic en Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Haga clic ![en Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtrar** para filtrar el gráfico y la tabla de detalles por algunos o todos los valores de tipo de simulación:

- **Recolección de credenciales**
- **Datos adjuntos de malware**
- **Vínculo en datos adjuntos**
- **Vínculo a malware**
- **Dirección URL de unidad por**

Cuando haya terminado de configurar los filtros, haga clic **en Aplicar**, **Cancelar** o **Borrar filtros**.

Use ![el cuadro **Buscar**](../../media/m365-cc-sc-search-icon.png) icono de búsqueda para filtrar los resultados por cualquiera de los valores de columna. No se admiten los caracteres comodín.

Si hace clic en el icono ![Exportar.](../../media/m365-cc-sc-download-icon.png) **Botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

## <a name="insights-and-reports-in-the-simulation-details-of-attack-simulation-training"></a>Ideas e informes en los detalles de simulación del entrenamiento de simulación de ataques

Para ir a la pestaña **Simulaciones**, abra el portal <https://security.microsoft.com>de Microsoft 365 Defender en , vaya a Correo electrónico & aprendizaje de simulación de ataques **y,** **a** \> continuación, seleccione la **pestaña Simulaciones**. Para ir directamente a la pestaña **Simulaciones** de la página **de aprendizaje de simulación de** ataques, use <https://security.microsoft.com/attacksimulator?viewid=simulations>.

Al seleccionar una simulación de la lista, se abre una página de detalles. Esta página contiene las opciones de configuración de la simulación que esperaría ver (estado, fecha de inicio, carga usada, etc.).

El resto de esta sección describe los conocimientos e informes que están disponibles en la página de detalles de la simulación.

### <a name="simulation-impact-section"></a>Sección impacto de simulación

La **sección Impacto de** la simulación en la página de detalles de la simulación muestra cuántos usuarios fueron completamente engañados por la simulación y el número total de usuarios en la simulación. La información que se muestra varía en función del tipo de simulación. Por ejemplo:

- Vínculos: **Credenciales especificadas** y **No se especificaron credenciales**.

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-links.png" alt-text="Sección Impacto de simulación para detalles de simulación relacionados con vínculos" lightbox="../../media/attack-sim-training-sim-details-sim-impact-links.png":::

- Datos **adjuntos: datos adjuntos** abiertos **y Datos adjuntos no abiertos**.

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-attachments.png" alt-text="Sección Impacto de simulación para detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-sim-impact-attachments.png":::

Si mantiene el mouse sobre una sección del gráfico, se muestran los números reales de cada categoría.

### <a name="all-user-activity-section"></a>Sección Toda la actividad del usuario

La **sección Todas las actividades del** usuario de la página de detalles de la simulación muestra números para los posibles resultados de la simulación. La información que se muestra varía en función del tipo de simulación. Por ejemplo:

- **SuccessfullyDeliveredEmail**
- **ReportedEmail**: cuántos usuarios informaron de que el mensaje de simulación era sospechoso.
- Vínculos:
  - **EmailLinkClicked**: cuántos usuarios han hecho clic en el vínculo del mensaje de simulación.
  - **CredSupplied**: después de hacer clic en el vínculo, cuántos usuarios proporcionaron sus credenciales.

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-links.png" alt-text="Sección Todas las actividades del usuario para obtener detalles de simulación relacionados con vínculos" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-links.png":::

- Datos adjuntos:
  - **AttachmentOpened**: cuántos usuarios abrieron los datos adjuntos en el mensaje de simulación.

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png" alt-text="Sección Todas las actividades del usuario para obtener detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png":::

### <a name="training-completion-section"></a>Sección finalización del aprendizaje

La **sección Finalización del** aprendizaje de la página de detalles de la simulación muestra los aprendizajes necesarios para la simulación y el número de usuarios que han completado los cursos.

:::image type="content" source="../../media/attack-sim-training-sim-details-training-completed.png" alt-text="Sección Finalización del aprendizaje para detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-training-completed.png":::

## <a name="recommended-actions-section"></a>Sección Acciones recomendadas

La **sección Acciones recomendadas** de la página de detalles de simulación muestra las acciones de recomendación de [Puntuación](../defender/microsoft-secure-score.md) segura de Microsoft y el efecto que tendrá la acción en la puntuación segura. Estas recomendaciones se basan en la carga que se usó en la simulación y ayudarán a proteger a los usuarios y al entorno. La selección de **una acción de mejora** de la lista le llevará a la ubicación para implementar la acción sugerida.

:::image type="content" source="../../media/attack-sim-training-sim-details-recommended-actions.png" alt-text="Sección Acciones de recomendación sobre el aprendizaje de simulación de ataques" lightbox="../../media/attack-sim-training-sim-details-recommended-actions.png":::

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Crear una simulación de ataque de suplantación de identidad](attack-simulation-training.md)

[crear una carga para entrenar a sus personas](attack-simulation-training-payloads.md)
