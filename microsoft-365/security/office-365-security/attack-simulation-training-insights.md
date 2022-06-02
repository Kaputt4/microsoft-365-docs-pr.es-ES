---
title: Ideas e informes entrenamiento de simulación de ataques
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
description: Los administradores pueden aprender cómo el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender afecta a los usuarios y puede obtener información sobre los resultados de simulación y entrenamiento.
ms.technology: mdo
ms.openlocfilehash: fb08de05e0a1f31187fc4dd045d0f1ce45db2aea
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65839376"
---
# <a name="insights-and-reports-for-attack-simulation-training-in-defender-for-office-365"></a>Ideas e informes para el entrenamiento de simulación de ataques en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En El entrenamiento de simulación de ataques en Microsoft Defender para Office Plan 2 o Microsoft 365 E5, Microsoft proporciona información e informes de los resultados de las simulaciones y los entrenamientos correspondientes. Esta información le mantiene informado sobre el progreso de preparación de amenazas de los usuarios, así como los pasos siguientes recomendados para preparar mejor a los usuarios para futuros ataques.

Ideas e informes están disponibles en las siguientes ubicaciones del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender:

- Pestaña **Información general** .
- Detalles de simulación en la pestaña **Simulaciones** .

En el resto de este artículo se describe la información disponible.

Para obtener información de introducción sobre el entrenamiento de simulación de ataques, consulte [Comenzar uso del entrenamiento de simulación de ataques](attack-simulation-training-get-started.md).

## <a name="insights-and-reports-on-the-overview-tab-of-attack-simulation-training"></a>Ideas e informes en la pestaña Información general del entrenamiento de simulación de ataques

Para ir a la pestaña **Información general**, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & collaboration** Attack simulation training (Correo electrónico & **entrenamiento de simulación de ataques** de colaboración\>) y compruebe que la pestaña **Información general** está seleccionada (es el valor predeterminado). Para ir directamente a la pestaña **Información general** de la página **Entrenamiento de simulación de ataque** , use <https://security.microsoft.com/attacksimulator?viewid=overview>.

En el resto de esta sección se describe la información disponible en la pestaña **Información general** del entrenamiento de simulación de ataques.

### <a name="recent-simulations-card"></a>Tarjeta de simulaciones recientes

**La tarjeta Simulaciones recientes** de la pestaña **Información general** muestra las tres últimas simulaciones que ha creado o ejecutado en su organización.

Puede seleccionar una simulación para ver los detalles.

Al seleccionar **Ver todas las simulaciones** , se le lleva a la pestaña **Simulaciones** .

Al seleccionar **Iniciar una simulación** , se inicia el asistente para la creación de la simulación. Para obtener más información, vea [Simular un ataque de suplantación de identidad (phishing) en Defender para Office 365](attack-simulation-training.md).

:::image type="content" source="../../media/attack-sim-training-overview-recent-simulations-card.png" alt-text="La tarjeta Simulaciones recientes de la pestaña Información general del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-overview-recent-simulations-card.png":::

### <a name="behavior-impact-on-compromise-rate-card"></a>Impacto del comportamiento en la tarjeta de velocidad de riesgo

La tarjeta **Impacto del comportamiento en la tasa de riesgo** de la pestaña **Información general** muestra cómo los usuarios respondieron a las simulaciones en comparación con los datos históricos de Microsoft 365. Puede usar estas conclusiones para realizar un seguimiento del progreso de la preparación de amenazas de los usuarios mediante la ejecución de varias simulaciones en los mismos grupos de usuarios.

Los propios datos del gráfico muestran la siguiente información:

- Tasa <sup>\*</sup>**de compromiso prevista**: la tasa de riesgo promedio para simulaciones de entrenamiento de simulación de ataque que usan el mismo tipo de carga en todas las demás organizaciones Microsoft 365.
- Tasa <sup>\*</sup>**de compromiso real**: el porcentaje real de usuarios que se redujo para la simulación.

Si mantiene el puntero sobre un punto de datos del gráfico, se muestran los valores de porcentaje reales.

La siguiente información de resumen también se muestra en la tarjeta:

- **usuarios menos susceptibles a la suplantación de identidad (phishing**): la diferencia entre el número real de usuarios en peligro por el ataque simulado y la tasa de riesgo prevista. Es menos probable que este número de usuarios se vea comprometido por ataques similares en el futuro.
- **x% mejor que la tasa prevista**: indica cómo lo hicieron los usuarios en general en contraste con la tasa de riesgo prevista.

:::image type="content" source="../../media/attack-sim-training-overview-behavior-impact-card.png" alt-text="El impacto en el comportamiento en la tarjeta de velocidad de riesgo en la pestaña Información general del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-overview-behavior-impact-card.png":::

Para ver un informe más detallado, haga clic en **Ver simulaciones y informe de eficacia de entrenamiento**. Este informe se explica [más adelante en este artículo](#training-efficacy-tab-for-the-attack-simulation-report).

### <a name="simulation-coverage-card"></a>Tarjeta de cobertura de simulación

La tarjeta **Cobertura de simulación** de la pestaña **Información general** muestra el porcentaje de usuarios de la organización que han recibido una simulación (**usuarios simulados**) frente a los que no han recibido una simulación (**usuarios no simulados**). Puede mantener el puntero sobre una sección del gráfico para ver el número real de usuarios en cada categoría.

Al seleccionar **Iniciar simulación para usuarios no simulados,** se inicia el asistente para la creación de la simulación, donde los usuarios que no han recibido la simulación se seleccionan automáticamente en la página **Usuario de destino** . Para obtener más información, vea [Simular un ataque de suplantación de identidad (phishing) en Defender para Office 365](attack-simulation-training.md).

Al seleccionar **Ver informe de cobertura de simulación** , se le lleva a la [pestaña Cobertura de usuario del informe Simulación de ataque](#user-coverage-tab-for-the-attack-simulation-report).

:::image type="content" source="../../media/attack-sim-training-overview-sim-coverage-card.png" alt-text="La tarjeta Cobertura de simulación de la pestaña Información general del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-overview-sim-coverage-card.png":::

### <a name="training-completion-card"></a>Tarjeta de finalización del entrenamiento

La tarjeta **De finalización del entrenamiento** de la pestaña **Información general** organiza los porcentajes de usuarios que recibieron entrenamientos en función de los resultados de las simulaciones en las categorías siguientes:

- **Completed**
- **En curso**
- **Incompleta**

Puede mantener el puntero sobre una sección del gráfico para ver el número real de usuarios en cada categoría.

Al seleccionar **Ver informe de finalización de entrenamiento** , se le llevará a la [pestaña Finalización del entrenamiento del informe Simulación de ataque](#training-completion-tab-for-the-attack-simulation-report).

### <a name="repeat-offenders-card"></a>Tarjeta de reincidentes

La tarjeta **Reincidentes** de la pestaña **Información general** muestra la información sobre los reincidentes. Un _delincuente reincidente_ es un usuario que se vio comprometido por simulaciones consecutivas. El número predeterminado de simulaciones consecutivas es dos, pero puede cambiar el valor en la pestaña **Configuración** del entrenamiento de simulación de ataques en <https://security.microsoft.com/attacksimulator?viewid=setting>.

El gráfico organiza los datos de reincidentes por [tipo de simulación](attack-simulation-training.md#select-a-social-engineering-technique):

- **Todo**
- **Datos adjuntos de malware**
- **Vínculo a malware**
- **Cosecha de credenciales**
- **Vínculo en datos adjuntos**
- **Dirección URL de unidad por**

Al seleccionar **Ver informe de reincidentes** , se le lleva a la [pestaña Reincidentes del informe Simulación de ataque](#repeat-offenders-tab-for-the-attack-simulation-report).

### <a name="recommendations-card"></a>tarjeta Recomendaciones

La **tarjeta Recomendaciones** de la pestaña **Información general** sugiere que se ejecuten diferentes tipos de simulaciones.

Al seleccionar **Iniciar ahora** se inicia el asistente para la creación de simulación con el tipo de simulación especificado seleccionado automáticamente en la página **Seleccionar técnica** . Para obtener más información, vea [Simular un ataque de suplantación de identidad (phishing) en Defender para Office 365](attack-simulation-training.md).

:::image type="content" source="../../media/attack-sim-training-overview-recommendations-card.png" alt-text="La tarjeta Recomendaciones de la pestaña Información general del entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-overview-recommendations-card.png":::

### <a name="attack-simulation-report"></a>Informe de simulación de ataques

Puede abrir el **informe simulación de ataques** desde la pestaña **Información general** haciendo clic en ver **...** botones de informe que están disponibles en muchas de las tarjetas que se describen en este artículo. Para ir directamente al informe, use <https://security.microsoft.com/attacksimulationreport>

#### <a name="training-efficacy-tab-for-the-attack-simulation-report"></a>Pestaña De eficacia de entrenamiento para el informe de simulación de ataques

En la página **Informe de simulación de ataques** , la pestaña **Eficacia del entrenamiento** está seleccionada de forma predeterminada. Esta pestaña proporciona la misma información que está disponible en el impacto del **comportamiento en** la tarjeta de velocidad de riesgo, con contexto adicional de la propia simulación.

:::image type="content" source="../../media/attack-sim-report-training-efficacy-view.png" alt-text="La pestaña Eficacia del entrenamiento en el informe Simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-report-training-efficacy-view.png":::

En el gráfico se muestran la **tasa de riesgo prevista** y la **tasa de riesgo real**. Si mantiene el puntero sobre una sección del gráfico, se muestran los valores de porcentaje reales de .

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Nombre de la simulación**
- **Técnica de simulación**
- **Tácticas de simulación**
- **Tasa en peligro prevista**
- **Tasa en peligro real**
- **Total de usuarios destinados**
- **Recuento de usuarios en los que se ha hecho clic**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga clic en **Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Use ![el icono](../../media/m365-cc-sc-search-icon.png) **Buscar Cuadro de búsqueda** para filtrar los resultados por **nombre de simulación** o **técnica de simulación**. No se admiten los caracteres comodín.

Si hace clic en el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="user-coverage-tab-for-the-attack-simulation-report"></a>Pestaña Cobertura de usuario para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-user-coverage-view.png" alt-text="Pestaña Cobertura de usuario del informe Simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-report-user-coverage-view.png":::

En la pestaña **Cobertura** de usuario, el gráfico muestra los **usuarios simulados** y **los usuarios no simulados**. Si mantiene el puntero sobre un punto de datos del gráfico, se muestran los valores reales.

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Username**
- **Dirección de correo electrónico**
- **Incluido en la simulación**
- **Fecha de la última simulación**
- **Último resultado de la simulación**
- **Recuento de clics**
- **Recuento de comprometidos**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga clic en **Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Use ![el icono](../../media/m365-cc-sc-search-icon.png) **Buscar Cuadro de búsqueda** para filtrar los resultados por **nombre de usuario** o **dirección de correo electrónico**. No se admiten los caracteres comodín.

Si hace clic en el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="training-completion-tab-for-the-attack-simulation-report"></a>Pestaña Finalización del entrenamiento para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-training-completion-view.png" alt-text="Pestaña Finalización del entrenamiento en el informe Simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-report-training-completion-view.png":::

En la pestaña **Finalización del entrenamiento** , el gráfico muestra el número de simulaciones **completadas**, **en curso** y **incompletas** . Si mantiene el puntero sobre una sección del gráfico, se muestran los valores reales.

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Username**
- **Dirección de correo electrónico**
- **Incluido en la simulación**
- **Fecha de la última simulación**
- **Último resultado de la simulación**
- **Nombre del entrenamiento más reciente completado**
- **Fecha de finalización**
- **Todos los entrenamientos**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga clic en **Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar el gráfico y la tabla de detalles por uno o varios de los valores siguientes:

- **Completed**
- **En curso**
- **Todo**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

Use ![el icono](../../media/m365-cc-sc-search-icon.png) **Buscar Cuadro de búsqueda** para filtrar los resultados por **nombre de usuario** o **dirección de correo electrónico**. No se admiten los caracteres comodín.

Si hace clic en el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

#### <a name="repeat-offenders-tab-for-the-attack-simulation-report"></a>Pestaña Reincidentes para el informe de simulación de ataques

:::image type="content" source="../../media/attack-sim-report-repeat-offenders-view.png" alt-text="Pestaña Repetición de delincuentes en el informe Simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-report-repeat-offenders-view.png":::

Un _delincuente reincidente_ es un usuario que se vio comprometido por simulaciones consecutivas. El número predeterminado de simulaciones consecutivas es dos, pero puede cambiar el valor en la pestaña **Configuración** del entrenamiento de simulación de ataques en <https://security.microsoft.com/attacksimulator?viewid=setting>.

En la pestaña **Reincidentes** , el gráfico organiza los datos de reincidentes por [tipo de simulación](attack-simulation-training.md#select-a-social-engineering-technique):

- **Todo**
- **Cosecha de credenciales**
- **Datos adjuntos de malware**
- **Vínculo en datos adjuntos**
- **Vínculo a malware**
- **Dirección URL de unidad por**

Si mantiene el puntero sobre un punto de datos del gráfico, se muestran los valores reales.

En la tabla de detalles debajo del gráfico se muestra la siguiente información:

- **Usuario**
- **Recuento de repeticiones**
- **Tipos de simulación**
- **Simulaciones**

Para ordenar los resultados, haga clic en un encabezado de columna disponible.

Haga clic en **Personalizar columnas** para quitar las columnas que se muestran. Cuando haya terminado, haga clic en **Aplicar**.

Haga clic en ![Icono de filtro.](../../media/m365-cc-sc-filter-icon.png) **Filtre** para filtrar el gráfico y la tabla de detalles por algunos o todos los valores de tipo de simulación:

- **Cosecha de credenciales**
- **Datos adjuntos de malware**
- **Vínculo en datos adjuntos**
- **Vínculo a malware**
- **Dirección URL de unidad por**

Cuando haya terminado de configurar los filtros, haga clic en **Aplicar**, **Cancelar** o **Borrar filtros**.

Use ![el icono](../../media/m365-cc-sc-search-icon.png) **Buscar Cuadro de búsqueda** para filtrar los resultados por cualquiera de los valores de columna. No se admiten los caracteres comodín.

Si hace clic en el ![icono Exportar.](../../media/m365-cc-sc-download-icon.png) **El botón Exportar informe** , el progreso de generación de informes se muestra como un porcentaje de completado. En el cuadro de diálogo que se abre, puede elegir abrir el archivo .csv, guardar el archivo .csv y recordar la selección.

## <a name="insights-and-reports-in-the-simulation-details-of-attack-simulation-training"></a>Ideas e informes en los detalles de simulación del entrenamiento de simulación de ataques

Para ir a la pestaña **Simulaciones**, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & collaboration **Attack simulation training** (**Enviar por correo electrónico &** entrenamiento de simulación de ataques de colaboración\>) y, a continuación, seleccione la pestaña **Simulaciones**. Para ir directamente a la pestaña **Simulaciones** de la página **Entrenamiento de simulación de ataque**, use <https://security.microsoft.com/attacksimulator?viewid=simulations>.

Al seleccionar una simulación de la lista, se abre una página de detalles. Esta página contiene los valores de configuración de la simulación que esperaría ver (estado, fecha de inicio, carga usada, etc.).

En el resto de esta sección se describen las conclusiones y los informes que están disponibles en la página de detalles de la simulación.

### <a name="simulation-impact-section"></a>Sección de impacto de simulación

En la sección **Impacto de simulación** de la página de detalles de la simulación se muestra cuántos usuarios han sido completamente engañados por la simulación y el número total de usuarios en la simulación. La información que se muestra varía en función del tipo de simulación. Por ejemplo:

- Vínculos: **se especificaron credenciales** y **no se especificaron credenciales**.

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-links.png" alt-text="La sección Impacto de simulación para detalles de simulación relacionados con vínculos" lightbox="../../media/attack-sim-training-sim-details-sim-impact-links.png":::

- Datos adjuntos: **datos adjuntos abiertos** y **No se han abierto los datos adjuntos**.

  :::image type="content" source="../../media/attack-sim-training-sim-details-sim-impact-attachments.png" alt-text="La sección Impacto de simulación para detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-sim-impact-attachments.png":::

Si mantiene el puntero sobre una sección del gráfico, se muestran los números reales de cada categoría.

### <a name="all-user-activity-section"></a>Toda la sección de actividad de usuario

La sección **Actividad de todos los usuarios** de la página de detalles de la simulación muestra números para los posibles resultados de la simulación. La información que se muestra varía en función del tipo de simulación. Por ejemplo:

- **SuccessfullyDeliveredEmail**
- **ReportedEmail**: cuántos usuarios notificaron que el mensaje de simulación era sospechoso.
- Enlaces:
  - **EmailLinkClicked**: cuántos usuarios han hecho clic en el vínculo del mensaje de simulación.
  - **CredSupplied**: después de hacer clic en el vínculo, cuántos usuarios han proporcionado sus credenciales.

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-links.png" alt-text="La sección Toda la actividad de usuario para obtener detalles de simulación relacionados con vínculos" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-links.png":::

- Accesorios:
  - **AttachmentOpened**: cuántos usuarios han abierto los datos adjuntos en el mensaje de simulación.

    :::image type="content" source="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png" alt-text="La sección Toda la actividad del usuario para obtener detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-all-user-activity-attachments.png":::

### <a name="training-completion-section"></a>Sección de finalización del entrenamiento

En la sección **Finalización del entrenamiento** de la página de detalles de la simulación se muestran los entrenamientos necesarios para la simulación y cuántos usuarios han completado los entrenamientos.

:::image type="content" source="../../media/attack-sim-training-sim-details-training-completed.png" alt-text="La sección Finalización del entrenamiento para detalles de simulación relacionados con datos adjuntos" lightbox="../../media/attack-sim-training-sim-details-training-completed.png":::

## <a name="recommended-actions-section"></a>Sección Acciones recomendadas

En la sección **Acciones recomendadas** de la página de detalles de la simulación se muestran las acciones de recomendación de [Puntuación segura de Microsoft](../defender/microsoft-secure-score.md) y el efecto que tendrá la acción en la puntuación de seguridad. Estas recomendaciones se basan en la carga útil que se usó en la simulación y ayudarán a proteger a los usuarios y al entorno. Al seleccionar una **acción de mejora** de la lista, se le llevará a la ubicación para implementar la acción sugerida.

:::image type="content" source="../../media/attack-sim-training-sim-details-recommended-actions.png" alt-text="La sección Acciones de recomendación sobre el entrenamiento de simulación de ataques" lightbox="../../media/attack-sim-training-sim-details-recommended-actions.png":::

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Creación de una simulación de ataque de suplantación de identidad (phishing)](attack-simulation-training.md)

[crear una carga útil para entrenar a los usuarios](attack-simulation-training-payloads.md#create-payloads)
