---
title: Conexión a los datos de Microsoft 365 Government Community Cloud (GCC) con Usage Analytics
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtenga información sobre cómo conectarse a los datos de su inquilino de Microsoft 365 Government Community Cloud (GCC) mediante la aplicación de plantilla Análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: c82dd3d358621e874281b89a22976e583cc0df95
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193485"
---
# <a name="connect-to-microsoft-365-government-community-cloud-gcc-data-with-usage-analytics"></a>Conexión a los datos de Microsoft 365 Government Community Cloud (GCC) con Usage Analytics

Use los procedimientos siguientes para conectarse a los datos con el informe Análisis de uso de Microsoft 365 en un inquilino de Microsoft 365 Government Community Cloud (GCC). 

> [!NOTE]
> Estas instrucciones son específicamente para inquilinos de GCC de Microsoft 365. 

## <a name="before-you-begin"></a>Antes de empezar

Para configurar inicialmente Microsoft 365 Usage Analytics: 

- Debe ser administrador global de Microsoft 365 para habilitar la recopilación de datos. 
- Necesita la aplicación [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) para usar el archivo de plantilla. 
- Necesita una [licencia de Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347) o una capacidad Premium para publicar y ver el informe. 

## <a name="step-1-make-you-organizations-data-available-for-the-microsoft-365-usage-analytics-report"></a>Paso 1: Hacer que los datos de la organización estén disponibles para el informe análisis de uso de Microsoft 365

1. En el Centro de administración de Microsoft 365, expanda el menú de navegación, seleccione **Informes** y, a continuación, seleccione **Uso**. 
2. En la página **Informes de uso** , en la sección Análisis de uso de Microsoft 365, seleccione **Introducción**. 
3. En **Habilitar Power BI para el análisis de uso**, seleccione **Hacer que los datos de uso de la organización estén disponibles para El análisis de uso de Microsoft para Power BI** y, a continuación, seleccione **Guardar**.

    ![Haga que los datos del inquilino estén disponibles.](../../media/usage-analytics/make-data-available.png) 



    Esto iniciará un proceso para que los datos de las organizaciones sean accesibles para este informe y verá un mensaje que indica que **estamos preparando los datos para el análisis de uso de Microsoft 365**. Tenga en cuenta que este proceso puede tardar 24 horas en completarse. 

4. Cuando los datos de las organizaciones estén listos, al actualizar la página se mostrará un mensaje que indica que los datos ya están disponibles y también se proporcionará el número de **identificador de inquilino** . Tendrá que usar el identificador de inquilino en un paso posterior al intentar conectarse a los datos del inquilino. 
 
    ![Identificador del inquilino.](../../media/usage-analytics/tenant-id-gcc.png) 
 
    > [!IMPORTANT]
    > Cuando los datos estén disponibles, no seleccione **Ir a Power BI**, que le llevará a Marketplace de Power BI.  La aplicación de plantilla para este informe requerida por los inquilinos de GCC no está disponible en Power BI Marketplace.  


## <a name="step-2-download-the-power-bi-template-connect-to-your-data-and-publish-the-report"></a>Paso 2: Descargar la plantilla de Power BI, conectarse a los datos y publicar el informe

Los usuarios de Microsoft 365 GCC pueden descargar y usar el archivo de plantilla de informe de Análisis de uso de Microsoft 365 para conectarse a sus datos. Necesitará Power BI Desktop para abrir y usar el archivo de plantilla. 

 > [!NOTE]
 > Actualmente, una aplicación de plantilla para el informe análisis de uso de Microsoft 365 no está disponible para los inquilinos de GCC en Power BI Marketplace.  

1. Después de descargar la [plantilla de Power BI](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit), ábrala mediante Power BI Desktop. 
2. Cuando se le solicite un **TenantID**, escriba el identificador de inquilino que recibió al preparar los datos de su organización para este informe en el paso 1. A continuación, seleccione **Cargar**. Los datos tardarán varios minutos en cargarse. 

    ![Escriba el identificador de inquilino.](../../media/usage-analytics/add-tenant-id.png) 



3. Cuando se complete la carga, se mostrará el informe y verá un resumen ejecutivo de los datos. 

    ![Resumen ejecutivo.](../../media/usage-analytics/exec-summary.png) 
 

4. Guarde los cambios en el informe. 
5. Seleccione **Publicar** en el menú Power BI Desktop para publicar el informe en el servicio Power BI Online donde se puede ver. Esto requiere una licencia de Power BI Pro o una capacidad de Power BI Premium. Como parte del [proceso de publicación](/power-bi/create-reports/desktop-upload-desktop-files#to-publish-a-power-bi-desktop-dataset-and-reports), deberá seleccionar un destino para publicar en un área de trabajo disponible en el servicio Power BI Online.

## <a name="related-content"></a>Contenido relacionado

[Sobre análisis de uso](usage-analytics.md) </br>
[Obtener la última versión de los análisis de uso](get-the-latest-version-of-usage-analytics.md) </br>
[Navegar y usar los informes en Análisis de uso de Microsoft 365](navigate-and-utilize-reports.md) </br>