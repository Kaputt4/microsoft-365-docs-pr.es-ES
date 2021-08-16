---
title: Conectar para Microsoft 365 Government Community Cloud datos (GCC) con Análisis de uso
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
description: Obtenga información sobre cómo conectarse a los datos del espacio empresarial Microsoft 365 Government Community Cloud (GCC) mediante la aplicación de plantilla Microsoft 365 análisis de uso en Power BI.
ms.openlocfilehash: f11a174f83dcdc9b2afadd71133cce19a5e6f677
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58253974"
---
# <a name="connect-to-microsoft-365-government-community-cloud-gcc-data-with-usage-analytics"></a>Conectar para Microsoft 365 Government Community Cloud datos (GCC) con Análisis de uso

Use los siguientes procedimientos para conectarse a los datos con el informe Microsoft 365 Análisis de uso en un inquilino Microsoft 365 Government Community Cloud (GCC). 

> [!NOTE]
> Estas instrucciones son específicamente para Microsoft 365 GCC inquilinos. 

## <a name="before-you-begin"></a>Antes de empezar

Para configurar inicialmente Microsoft 365 análisis de uso: 

- Debe ser un administrador Microsoft 365 global para habilitar la recopilación de datos. 
- Necesita la aplicación [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) para usar el archivo de plantilla. 
- Necesita una licencia [Power BI Pro o](https://go.microsoft.com/fwlink/p/?linkid=845347) una Premium para publicar y ver el informe. 

## <a name="step-1-make-you-organizations-data-available-for-the-microsoft-365-usage-analytics-report"></a>Paso 1: Hacer que los datos de la organización estén disponibles para el Microsoft 365 análisis de uso

1. En el Centro de administración de Microsoft 365, expanda el menú de navegación, seleccione **Informes** y, a continuación, seleccione **Uso**. 
2. En la **página Informes de** uso, en la Microsoft 365 Análisis de uso, seleccione **Introducción**. 
3. En **Habilitar Power BI para análisis** de uso, seleccione Hacer que los datos de uso de la organización estén disponibles para el análisis de uso de Microsoft para **Power BI** y, a continuación, seleccione **Guardar**.

    ![Hacer que los datos del espacio empresarial estén disponibles](../../media/usage-analytics/make-data-available.png) 



    Esto iniciará un proceso para que los datos de las organizaciones estén accesibles para este informe y verá un mensaje que indica que estamos preparando los datos para el análisis de uso Microsoft 365 **de datos.** Tenga en cuenta que este proceso puede tardar 24 horas en completarse. 

4. Cuando los datos de la organización estén listos, la actualización de la página mostrará un mensaje que indica que los datos ya están disponibles y también proporcionará su número **de identificador de** inquilino. Deberá usar el identificador de inquilino en un paso posterior cuando intente conectarse a los datos del espacio empresarial. 
 
    ![Identificación del inquilino](../../media/usage-analytics/tenant-id-gcc.png) 
 
    > [!IMPORTANT]
    > Cuando los datos estén disponibles, no seleccione **Ir a Power BI**, lo que le llevará al Power BI Marketplace.  La aplicación de plantilla para este informe requerida por GCC inquilinos no está disponible en el Power BI Marketplace.  


## <a name="step-2-download-the-power-bi-template-connect-to-your-data-and-publish-the-report"></a>Paso 2: Descargar la Power BI, conectarse a los datos y publicar el informe

Microsoft 365 GCC los usuarios pueden descargar y usar el archivo de plantilla de informe Microsoft 365 análisis de uso para conectarse a sus datos. Necesitarás Power BI Desktop abrir y usar el archivo de plantilla. 

 > [!NOTE]
 > Actualmente, una aplicación de plantilla para el informe Microsoft 365 análisis de uso no está disponible para GCC inquilinos en Power BI Marketplace.  

1. Después de descargar la [Power BI ,](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)ábrala con Power BI Desktop. 
2. Cuando se le pida un **TenantID,** escriba el identificador de inquilino que recibió al preparar los datos de la organización para este informe en el paso 1. A continuación, **seleccione Cargar**. Los datos tardarán varios minutos en cargarse. 

    ![Escriba el identificador de inquilino](../../media/usage-analytics/add-tenant-id.png) 



3. Cuando se complete la carga, se mostrará el informe y verá un resumen ejecutivo de los datos. 

    ![Resumen ejecutivo](../../media/usage-analytics/exec-summary.png) 
 

4. Guarde los cambios en el informe. 
5. Seleccione **Publicar** en el menú Power BI Desktop para publicar el informe en el servicio Power BI online donde se puede ver. Esto requiere una licencia Power BI Pro o Power BI Premium capacidad. Como parte del proceso [de](/power-bi/create-reports/desktop-upload-desktop-files#to-publish-a-power-bi-desktop-dataset-and-reports)publicación, deberá seleccionar un destino para publicarlo en un área de trabajo disponible en el servicio Power BI online.

## <a name="related-content"></a>Contenido relacionado

[Sobre análisis de uso](usage-analytics.md) </br>
[Obtener la última versión de los análisis de uso](get-the-latest-version-of-usage-analytics.md) </br>
[Navegar y usar los informes en Análisis de uso de Microsoft 365](navigate-and-utilize-reports.md) </br>