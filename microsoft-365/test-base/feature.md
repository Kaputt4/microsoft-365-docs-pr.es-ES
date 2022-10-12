---
title: Validación de actualización de características
description: Detalles sobre cómo cargar la aplicación para la validación de actualizaciones de características
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: bd681f6dceec9182d3fbe80e6bb3beeae510c65a
ms.sourcegitcommit: 893add1e40c3e26e5624663eaf272d12a72d0141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68540013"
---
# <a name="windows-feature-update-validation"></a>Validación de actualización de características de Windows

¿Necesita información sobre cómo funcionarán las aplicaciones con las características más recientes de Windows, antes de que esté disponible en el mercado y sin mantener un entorno? 

¿Desea ejecutar las pruebas de validación en compilaciones del Programa Windows Insider en nuestro entorno de Azure? 

La validación de **actualizaciones de características** en Test Base para Microsoft 365 puede ayudarle a lograr todo esto y mucho más. 

Consulte el esquema paso a paso siguiente para obtener información sobre cómo acceder a esta nueva funcionalidad en test base para el servicio Microsoft 365. 

Para empezar a trabajar con la validación de actualizaciones de características en Test Base para Microsoft 365, cargue las aplicaciones (y los archivos relacionados) a través del portal de incorporación de autoservicio. 

A continuación, se resaltan los pasos que se van a seguir al rellenar la **matriz de pruebas**: 

Para configurar las actualizaciones de características, debe especificar el producto de destino y su canal de vista previa en la lista desplegable "Canal insider". 

![Tipo de sistema operativo de validación de actualización de características.](Media/windowsfeatureupdatevalidation01-featureupdate.png)

La selección registrará la aplicación para que se ejecuten pruebas automáticas con las últimas actualizaciones de características del canal de producto seleccionado y todas las actualizaciones nuevas futuras en las últimas Windows Insider Preview compilaciones de la selección. 

También puede establecer el sistema operativo actual en "Línea de base del sistema operativo para Insight". Le proporcionaremos más información de prueba mediante el análisis de regresión del entorno del sistema operativo tal cual y el sistema operativo de destino más reciente. 

![Validación de actualización de características. Elegir el canal beta de Insider.](Media/windowsfeatureupdatevalidation02-osbaseline.png) 

Para ver más detalles sobre las compilaciones de Windows Insider Preview, consulte [Flight Hub - Windows Insider Program | Microsoft Docs](/../../../../MicrosoftDocs/windows-insider/tree/public/wip/flight-hub/index.md).


## <a name="next-steps"></a>Pasos siguientes

Pase al siguiente artículo para empezar a comprender el análisis de regresión de memoria.
> [!div class="nextstepaction"]
> [Paso siguiente](memory.md)

<!---
Add button for next page
-->
