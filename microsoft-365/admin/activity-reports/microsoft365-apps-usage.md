---
title: 'Microsoft 365 Reports en el centro de administración: uso de aplicaciones de Microsoft 365'
ms.author: sirkkuw
author: sirkkuw
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
description: Obtenga información sobre cómo obtener un informe de aplicaciones de Microsoft 365 para uso mediante el panel informes de Microsoft 365 en el centro de administración de Microsoft 365.
ms.openlocfilehash: 3230098336cd17236d754dbfea796c373ea98fe4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948969"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365 Reports en el centro de administración: uso de aplicaciones de Microsoft 365

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md).

 Por ejemplo, puede comprender la actividad de cada usuario con licencia para usar las aplicaciones de Microsoft 365 apps observando su actividad en todas las aplicaciones y cómo se usan en todas las plataformas.


 > [!NOTE]
 > Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint o Skype empresarial para ver los informes.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Cómo acceder al informe de uso de aplicaciones de 365 de Microsoft

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

 2. En la lista desplegable **seleccionar un informe** , seleccione **Office 365**   \>  **Microsoft 365 aplicaciones de uso** .

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretar el informe de uso de aplicaciones de Microsoft 365

Puede obtener una vista de la actividad de Microsoft 365 apps del usuario consultando los gráficos **usuarios** y **plataforma** .

![Informe de uso de aplicaciones de Microsoft 365](../../media/proplususagenumbers.png)

|Item|Descripción|
 |:-----|:-----|
 |1. <br/> |El informe de **uso de aplicaciones de Microsoft 365** puede visualizarse para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe). <br/> |
 |2. <br/> |Los datos de cada informe normalmente cubren los últimos siete días. <br/> |
 |3. <br/> |La vista **usuarios** muestra la tendencia en el número de usuarios activos para cada aplicación: Outlook, Word, Excel, PowerPoint, OneNote y Teams. "Usuarios activos" son todos los que realizan acciones intencionadas en estas aplicaciones. <br/> |
 |4. <br/> |La vista **plataformas** muestra la tendencia de los usuarios activos en todas las aplicaciones de cada plataforma: Windows, Mac, Web y móvil. <br/> |
 |5.<br/>|En el gráfico **usuarios** , el eje Y es el número de usuarios activos únicos para la aplicación correspondiente. En el gráfico **plataformas**   , el eje Y es el número de usuarios únicos para la plataforma correspondiente. El eje X de ambos gráficos es la fecha en la que se usó una aplicación en una plataforma determinada.<br/>|
 6.<br/>|Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **usuarios** , seleccione Outlook, Word, Excel, PowerPoint, OneDrive o Teams para ver solo la información relacionada con cada uno de ellos. Al cambiar esta selección no se cambia la información de la tabla de cuadrícula que hay debajo de ella.|
 |7.<br/>|En la tabla, se muestra un desglose de los datos en el nivel de usuario. Puede agregar o quitar columnas de la tabla. <br/><br/>**Username** es la dirección de correo electrónico del usuario que realizó la actividad en Microsoft apps.<br><br/>**Fecha de última activación (UTC)** es la última fecha en la que el usuario activó su suscripción de Microsoft 365 apps.<br/><br/>**Fecha de última actividad (UTC)** es la última fecha en que el usuario realizó una actividad intencionada. Para ver las actividades realizadas en una fecha específica, seleccione la fecha directamente en el gráfico.<br/><br/>Las columnas siguientes corresponden a cada aplicación que identifica si el usuario estuvo activo en esa aplicación en el período seleccionado:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> Las columnas siguientes corresponden a cada plataforma que identifica si el usuario estuvo activo en esa plataforma para cualquier aplicación (dentro de las aplicaciones de Microsoft 365) en el período seleccionado:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (Web)** <br>**Outlook (móvil)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Web)**<br> **Word (móvil)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (Web)**<br> **Excel (móvil)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Web)**<br> **PowerPoint (móvil)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (Web)**<br>**OneNote (móvil)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (Web)**<br>**Teams (móvil)** |
 |8.<br/>|Seleccione el icono **administrar columnas** para agregar o quitar columnas del informe.|
 |9.<br/>|También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Esto exporta datos para todos los usuarios y le permite realizar una adición, ordenación y filtrado sencillos para un análisis más avanzado. Si tiene menos de 100 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 100 usuarios, con el fin de filtrar y ordenar, tendrá que exportar los datos.|
