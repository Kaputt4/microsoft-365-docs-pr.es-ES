---
title: Centro de administración de Microsoft 365 informes de uso de aplicaciones de Teams
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- Tier2
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenga información sobre cómo obtener el informe de uso de aplicaciones de Microsoft Teams y obtener información sobre la actividad de la aplicación de Teams en su organización.
ms.openlocfilehash: f2135a4fd6fbb8b61406855c1f773187c1d5f794
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68723043"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-apps-usage-reports"></a>Informes de Microsoft 365 en el Centro de administración: informes de uso de aplicaciones de Microsoft Teams

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el **informe de uso de aplicaciones de Microsoft Teams**, puede obtener información sobre la actividad de aplicaciones de Teams en su organización. En este artículo se explica cómo acceder al informe y ver e interpretar las distintas métricas del informe. 

Puede usar este informe para comprender quién está instalando o usando aplicaciones y profundizar en un nivel por aplicación y por usuario.

## <a name="whats-in-the-report"></a>¿Qué hay en el informe?

El informe de uso de aplicaciones de Teams está disponible en el Centro de administración de Microsoft 365 y los datos se proporcionan a través de dos informes independientes:

**Uso de** aplicaciones: este informe le ayuda a responder:
- ¿Cuántas aplicaciones tienen instalados los usuarios de su entorno? 
- ¿Cuántas aplicaciones tienen al menos un usuario activo en su entorno? 
- ¿Cuántas aplicaciones usa la plataforma (Windows, Mac, Web o mobile)? 
- ¿Cuántos usuarios activos y equipos activos usan la aplicación?

**Actividad del usuario** : este informe le ayuda a responder: 
- ¿Cuántos usuarios del entorno han instalado al menos una aplicación? 
- ¿Cuántos usuarios de su entorno han usado al menos una aplicación? 
- ¿Cuántos usuarios usan una aplicación entre plataformas (Windows, Mac, Web, etc.)? 
- ¿Cuántas aplicaciones ha usado cada usuario?

## <a name="how-to-get-to-the-microsoft-teams-apps-usage-report"></a>Cómo acceder al informe de uso de aplicaciones de Microsoft Teams

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.
2. En la página principal del panel, haga clic en el botón **Ver más** de la tarjeta de actividad de aplicaciones de Microsoft Teams.

    :::image type="content" source="../../media/teams-apps-tile.png" alt-text="Aplicación de Microsoft Teams.":::

## <a name="considerations"></a>Consideraciones

- Los datos de uso e instalación de una aplicación recién publicada pueden tardar unos cinco días en aparecer en el informe. Los datos de un día determinado se mostrarán en un plazo de 48 horas. Por ejemplo, los datos del 10 de enero deben aparecer en el informe alrededor del 12 de enero.  

- La fecha de inicio de todas las métricas de instalación es octubre de 2021. Solo se contarán las aplicaciones instaladas después de esa fecha. 

- Los identificadores de aplicación de este informe son los identificadores de aplicación externos (manifiesto). Para obtener más información sobre cómo vincular este identificador a una aplicación en la experiencia Administrar aplicaciones en el Centro de Administración de Teams, consulte [Administración de directivas de configuración de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-setup-policies#install-apps.md). 

- Para exportar los datos del informe a un archivo de .csv de Excel, seleccione el vínculo Exportar. Esto exporta datos para todos los usuarios o aplicaciones y le permite realizar una ordenación y un filtrado sencillos para un análisis posterior. 


## <a name="exploring-the-report---app-usage-tab"></a>Exploración del informe: pestaña Uso de aplicaciones

Para ver el **uso de** aplicaciones en el informe de uso de aplicaciones de Teams, elija la pestaña **Uso de aplicaciones** . <br/>

:::image type="content" source="../../media/teams-apps-usage-tab.png" alt-text="Actividad de usuario de Teams." lightbox="../../media/teams-apps-usage-tab.png":::

En la parte superior del informe, verá tres gráficos que describen las tendencias entre aplicaciones en toda la organización.

- Aplicaciones instaladas
- Aplicaciones usadas
- Plataforma

Puede filtrar todos los gráficos por el selector de intervalo de tiempo en la parte superior derecha. 

:::image type="content" source="../../media/teams-apps-usage-filter.png" alt-text="Filtro de tiempo de uso de aplicaciones de Microsoft Teams.":::

### <a name="apps-installed"></a>Aplicaciones instaladas
En este gráfico se muestra el número total de instalaciones de aplicaciones en toda la organización hasta cada fecha dentro del período seleccionado. Por ejemplo: si selecciona 28 de enero de 2022, el gráfico le mostrará el número total de instalaciones desde octubre de 2021 hasta el 28 de enero de 2022. 

:::image type="content" source="../../media/apps-installed.png" alt-text="Aplicaciones de Microsoft Teams instaladas.":::

### <a name="apps-used"></a>Aplicaciones usadas
En este gráfico se muestra el número de aplicaciones que se usan en toda la organización en cada fecha del período seleccionado. Por ejemplo: si selecciona 28 de enero, el gráfico le mostrará el número total de aplicaciones usadas el 28 de enero.

:::image type="content" source="../../media/apps-used.png" alt-text="Aplicaciones de Microsoft Teams usadas.":::
  
### <a name="platform"></a>Plataforma 
En este gráfico se muestra el número de aplicaciones que se usan en toda la organización por plataforma durante el período seleccionado. Las plataformas disponibles son Windows, Mac, Mobile (en iOS y Android) y Web.

:::image type="content" source="../../media/platform.png" alt-text="Plataforma de Microsoft Teams.":::

### <a name="apps-usage-details-table"></a>Tabla de detalles de uso de aplicaciones

En esta tabla se muestra la vista por aplicación con las siguientes métricas para cada aplicación. Un subconjunto de las columnas de métricas se incluye de forma predeterminada y puede seleccionar o editar la lista de columnas haciendo clic en **Elegir columnas**"** en la parte superior derecha.

:::image type="content" source="../../media/apps-usage-details.png" alt-text="Detalles de uso de aplicaciones." lightbox="../../media/apps-usage-details.png":::

|**Métrica**|**Definición**|**¿Se incluye de forma predeterminada?**|
|:-----|:-----|:-----|
|||
|Identificador de la aplicación   <br/> |Identificador de aplicación externo presente en el manifiesto de la aplicación.     <br/> |Sí |
|Fecha de último uso    <br/> |Fecha en la que cualquiera de la organización usó esa aplicación por última vez.   <br/> |Sí |
|Teams que usa esta aplicación   <br/> |El número de equipos de Teams distintos que tienen al menos un usuario que usa esta aplicación.   <br/> |Yes |
|Usuarios que usan esta aplicación    <br/> |Número de usuarios distintos de la organización que usan esta aplicación.   <br/> |Sí |
|Se usa en Windows    <br/> | Esto indica si al menos un usuario de la organización ha usado esa aplicación en Windows.  <br/> |Sí |
|Se usa en dispositivos móviles  <br/> |Esto indica si al menos un usuario de la organización ha usado esa aplicación en mobile. <br/> |Sí |
|Se usa en la web   <br/> | Esto indica si al menos un usuario de la organización ha usado esa aplicación en web.  <br/> |Sí |
|Se usa en Mac <br/> |Número de reuniones ad hoc organizadas por un usuario durante el período de tiempo especificado. <br/>|No |
|Nombre de la aplicación  <br/> |Nombre de esta aplicación como presente en el manifiesto de la aplicación.   <br/>|No |
|Publisher  <br/> |Publicador de esta aplicación como presente en el manifiesto de la aplicación. Esto solo está disponible para las aplicaciones publicadas en la Tienda global.  <br/>|No |
|||

## <a name="exploring-the-report---teams-apps-usage-user-activity-tab"></a>Exploración del informe: pestaña Actividad de usuario de uso de aplicaciones de Teams

Para ver la **actividad del usuario** en el informe de uso de aplicaciones de Teams, elija la pestaña **Actividad de usuario** . <br/>

:::image type="content" source="../../media/teams-apps-user-activity.png" alt-text="Actividad de usuario de Microsoft Teams." lightbox="../../media/teams-apps-user-activity.png":::

En la parte superior del informe, verá tres gráficos que describen las tendencias entre aplicaciones en toda la organización.

- Usuarios que han instalado aplicaciones
- Usuario que ha usado aplicaciones
- Plataforma

Puede filtrar todos los gráficos por el selector de intervalo de tiempo en la parte superior derecha. 

:::image type="content" source="../../media/teams-apps-usage-filter.png" alt-text="Filtro de tiempo de actividad del usuario de Microsoft Teams.":::

### <a name="users-who-have-installed-apps"></a>Usuarios que han instalado aplicaciones
En este gráfico se muestra el número total de usuarios únicos que han instalado una aplicación hasta cada fecha dentro del período seleccionado. Por ejemplo: si selecciona 28 de enero de 2022, el gráfico le mostrará el número total de usuarios desde octubre de 2021 hasta el 28 de enero de 2022.  

:::image type="content" source="../../media/users-who-installed-apps.png" alt-text="Gráfico usuarios de aplicaciones de Microsoft Teams que han instalado aplicaciones.":::

### <a name="user-who-have-used-apps"></a>Usuario que ha usado aplicaciones
En este gráfico se muestra el número de usuarios únicos que han usado cualquier aplicación en cada fecha dentro del período seleccionado. Por ejemplo: si selecciona el 28 de enero, el gráfico le mostrará el número total de usuarios el 28 de enero.  

:::image type="content" source="../../media/users-who-used-apps.png" alt-text="Aplicaciones de Microsoft Teams Los usuarios que han usado el gráfico de aplicaciones.":::

### <a name="platform"></a>Plataforma 
En este gráfico se muestra el número de aplicaciones que se usan en toda la organización por plataforma durante el período seleccionado. Las plataformas disponibles son Windows, Mac, Mobile (en iOS y Android) y Web.  

:::image type="content" source="../../media/user-activity-platform.png" alt-text="Plataforma de actividad de usuario de uso de Microsoft Teams.":::
  
### <a name="user-activity-details-table"></a>Tabla de detalles de la actividad del usuario

En esta tabla se muestra la vista por usuario con las siguientes métricas para cada aplicación. Un subconjunto de las columnas de métricas se incluye de forma predeterminada y puede seleccionar o editar la lista de columnas haciendo clic en **Elegir columnas** en la parte superior derecha. 

:::image type="content" source="../../media/user-activity-details.png" alt-text="Detalles de la actividad del usuario." lightbox="../../media/user-activity-details.png":::

|**Métrica**|**Definición**|**¿Se incluye de forma predeterminada?**|
|:-----|:-----|:-----|
||||
|Nombre de usuario    <br/> |Nombre de usuario de un usuario único. El valor está oculto de forma predeterminada.  <br/> |Yes |
|Aplicaciones instaladas     <br/> |Número de aplicaciones únicas (en la Tienda y personalizadas) que el usuario ha instalado.   <br/> |Sí |
|Aplicaciones usadas    <br/> |Número de aplicaciones únicas (en la Tienda y personalizadas) que el usuario ha abierto o usado.    <br/> |Sí |
|Aplicaciones usadas en un equipo     <br/> |Número de aplicaciones únicas (en la Tienda y personalizadas) que el usuario ha abierto o usado en un equipo de Teams.   <br/> |Sí |
|Se usa en Windows    <br/> | Esto indica si ese usuario ha usado alguna aplicación en Windows.  <br/> |Sí |
|Se usa en dispositivos móviles  <br/> |Esto indica si ese usuario ha usado alguna aplicación en Móvil (iOS o Android). <br/> |Sí |
|Se usa en la web   <br/> | Esto indica si ese usuario ha usado alguna aplicación en web.   <br/> |Sí |
|Se usa en Mac <br/> |Esto indica si ese usuario ha usado alguna aplicación en Mac.  <br/>|No |
|||

## <a name="managing-apps-in-the-teams-admin-center"></a>Administración de aplicaciones en el Centro de Administración de Teams

Para obtener más información sobre cómo administrar las aplicaciones de Teams, consulte [Acerca de las aplicaciones en Microsoft Teams](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md).

Para vincular una aplicación de este informe a la experiencia Administrar aplicaciones en el Centro de Administración de Teams, puede usar lo siguiente:

- Nombre de la aplicación
- Identificador de aplicación externa

Los identificadores de aplicación externos son equivalentes al identificador de la página Administrar aplicaciones para aplicaciones de la Tienda. En el caso de las aplicaciones personalizadas, para ver el identificador de aplicación externa en la página Administrar aplicaciones, siga las instrucciones de [Administración de directivas de configuración de aplicaciones en Microsoft Teams](/microsoftteams/teams-app-setup-policies) para agregar la columna en la configuración de columna. También puede verlo en la página de detalles de la aplicación para una aplicación personalizada.

 