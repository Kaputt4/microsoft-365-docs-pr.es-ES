---
title: 'Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones de Microsoft 365'
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Obtenga información sobre cómo obtener un informe de aplicaciones de Microsoft 365 para uso con el panel informes de Microsoft 365 en el Centro de administración de Microsoft 365.
ms.openlocfilehash: 88ef5e1291c35bbac050609e26e2ac5adef9d981
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579595"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones de Microsoft 365

El panel informes  de Microsoft 365 muestra la introducción a la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).

 Por ejemplo, puedes comprender la actividad de cada usuario con licencia para usar aplicaciones de Aplicaciones de Microsoft 365 al ver su actividad en todas las aplicaciones y cómo se usan en todas las plataformas.


 > [!NOTE]
 > Debe ser un administrador global, un lector global o un lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint o Skype Empresarial para ver informes.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Cómo obtener acceso al informe de uso de Aplicaciones de Microsoft 365

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
2. En la página principal del panel, haga clic en el botón **Ver más** en la tarjeta Usuarios activos - Aplicaciones de Microsoft 365.

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretar el informe de uso de Aplicaciones de Microsoft 365

Para obtener una vista de la actividad de Aplicaciones de Microsoft 365 del usuario, consulte los gráficos **Usuarios** **y Plataforma.**

![Informe de uso de Aplicaciones de Microsoft 365](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

|Item|Descripción|
 |:-----|:-----|
 |1. <br/> |El informe de uso de Aplicaciones de **Microsoft 365** se puede ver para ver las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día determinado en el informe, la tabla (7) mostrará datos hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe). <br/> |
 |2. <br/> |Los datos de cada informe suelen abarcar hasta los últimos siete días. <br/> |
 |3. <br/> |La **vista** Usuarios muestra la tendencia en el número de usuarios activos para cada aplicación: Outlook, Word, Excel, PowerPoint, OneNote y Teams. Los "usuarios activos" son aquellos que realizan acciones intencionadas dentro de estas aplicaciones. <br/> |
 |4. <br/> |La **vista** Plataformas muestra la tendencia de los usuarios activos en todas las aplicaciones de cada plataforma: Windows, Mac, Web y Mobile. <br/> |
 |5.<br/>|En el **gráfico Usuarios,** el eje Y es el número de usuarios activos únicos para la aplicación correspondiente. En el **gráfico Plataformas,** el eje Y es el número de usuarios   únicos para la plataforma correspondiente. El eje X en ambos gráficos es la fecha en la que se usó una aplicación en una plataforma determinada.<br/>|
 6.<br/>|Puede filtrar la serie que ve en el gráfico seleccionando un elemento en la leyenda. Por ejemplo, en el gráfico **Usuarios,** seleccione Outlook, Word, Excel, PowerPoint, OneDrive o Teams para ver solo la información relacionada con cada uno. Cambiar esta selección no cambia la información de la tabla de cuadrícula debajo de ella.|
 |7.<br/>|En la tabla, se muestra un desglose de los datos en el nivel de usuario. Puede agregar o quitar columnas de la tabla. <br/><br/>**Username** es la dirección de correo electrónico del usuario que realizó la actividad en Microsoft Apps.<br><br/>**La última fecha de activación (UTC)** es la última fecha en la que el usuario activó su suscripción a Aplicaciones de Microsoft 365.<br/><br/>**La última fecha de actividad (UTC)** es la última fecha en la que el usuario realizó una actividad intencionada. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/><br/>Las otras columnas identifican si el usuario estaba activo en esa plataforma para esa aplicación (dentro de Aplicaciones de Microsoft 365) en el período seleccionado. |
 |8.<br/>|Seleccione el **icono Elegir columnas** para agregar o quitar columnas del informe.|
 |9.<br/>|También puede exportar los datos del informe a un archivo .csv de Excel seleccionando el **vínculo** Exportar. Esto exporta datos para todos los usuarios y permite realizar una agregación, ordenación y filtrado simples para un análisis posterior. Si tiene menos de 100 usuarios, puede ordenar y filtrar dentro de la tabla en el propio informe. Si tiene más de 100 usuarios, para filtrar y ordenar, tendrá que exportar los datos.|
