---
title: informes de uso de aplicaciones de Centro de administración de Microsoft 365
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Obtenga información sobre cómo obtener un informe de uso de Aplicaciones Microsoft 365 para ver la actividad del usuario con licencia en todas las aplicaciones y cómo se usan las aplicaciones entre plataformas.
ms.openlocfilehash: 9efa15c1e4204ea29eadd14ed32bec8af688e480
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68722910"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso Aplicaciones Microsoft 365

En el panel Informes de Microsoft 365 se muestra la información general sobre la actividad en los productos de su organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).

Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar Aplicaciones Microsoft 365 aplicaciones examinando su actividad en todas las aplicaciones y cómo se usan en todas las plataformas.

> [!NOTE]
> Las activaciones de equipos compartidos no se incluyen en este informe.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Cómo llegar al informe de uso de Aplicaciones Microsoft 365

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta Usuarios activos Aplicaciones Microsoft 365.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretación del informe de uso de Aplicaciones Microsoft 365

Puede obtener una vista de la actividad de Aplicaciones Microsoft 365 del usuario examinando los gráficos **Usuarios** y **Plataforma**.

> [!div class="mx-imgBorder"]
> ![Aplicaciones Microsoft 365 informe de uso.](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

El informe de **uso de Aplicaciones Microsoft 365** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla mostrará los datos durante un máximo de 28 días a partir de la fecha actual (no la fecha en que se generó el informe).

Los datos de cada informe suelen cubrirse hasta los últimos dos días. Cada seis días, actualizaremos el informe con actualizaciones secundarias para garantizar la calidad de los datos.

La vista **Usuarios** muestra la tendencia en el número de usuarios activos para cada aplicación: Outlook, Word, Excel, PowerPoint, OneNote y Teams. Los "usuarios activos" son los que realizan cualquier acción intencionada dentro de estas aplicaciones.

La vista **Plataformas** muestra la tendencia de los usuarios activos en todas las aplicaciones de cada plataforma: Windows, Mac, Web y Mobile.

En el gráfico Usuarios, el eje Y es el número de usuarios activos únicos para la aplicación correspondiente. En el gráfico Plataformas, el eje Y es el número de usuarios únicos para la plataforma correspondiente. El eje X de ambos gráficos es la fecha en la que se usó una aplicación en una plataforma determinada.

Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico Usuarios, seleccione Outlook, Word, Excel, PowerPoint, OneDrive o Teams para ver solo la información relacionada con cada uno de ellos. Cambiar esta selección no cambia la información de la tabla de cuadrícula debajo de ella.

En la tabla, se muestra un desglose de los datos en el nivel de usuario. Puede agregar o quitar columnas de la tabla.


|Elemento|Descripción|
|---|---|
|Nombre de usuario|Dirección de correo electrónico del usuario que realizó la actividad en Microsoft Apps.|
|Última fecha de activación (UTC)|La última fecha en la que el usuario activó su suscripción Aplicaciones Microsoft 365 en un equipo o inicia sesión en un equipo compartido e inicia la aplicación con su cuenta.|
|Fecha de la última actividad (UTC)|La última fecha en que el usuario realizó una actividad intencionada. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.|


Las otras columnas identifican si el usuario estaba activo en esa plataforma para esa aplicación (dentro de Aplicaciones Microsoft 365) en el período seleccionado.

Seleccione el icono **Elegir columnas** para agregar o quitar columnas del informe.

También puede exportar los datos del informe a un archivo de excel .csv seleccionando el vínculo **Exportar** . Esto exporta datos para todos los usuarios y le permite realizar agregaciones, ordenaciones y filtrados sencillos para un análisis posterior. 