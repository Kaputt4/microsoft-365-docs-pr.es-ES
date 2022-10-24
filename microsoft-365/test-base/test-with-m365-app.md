---
title: Prueba de la aplicación con las aplicaciones de Microsoft 365 más recientes
description: Cómo probar la aplicación con las aplicaciones de Microsoft 365 más recientes
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 10/21/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 8fa106208f537ea67202eaa6a60b700c2854614a
ms.sourcegitcommit: 0ca3ab2abe07810e9b2cc2d806e3c6b9f35b146c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68685404"
---
# <a name="test-your-application-with-latest-microsoft-365-apps"></a>Prueba de la aplicación con las aplicaciones de Microsoft 365 más recientes


En esta sección se proporcionan instrucciones sobre cómo probar la aplicación con las aplicaciones de Microsoft 365 más recientes.

> [!IMPORTANT]
> Actualmente solo está disponible la versión preliminar de Office 365 desde el canal de versión preliminar mensual.


### <a name="choose-the-microsoft-365-application"></a>Elección de la aplicación de Microsoft 365 

En el paso **Configurar prueba** al incorporar un nuevo paquete, active el botón de alternancia **Preinstalar aplicaciones de Microsoft** para permitir que el usuario elija la versión preliminar de las aplicaciones de Microsoft 365 con la actualización más reciente que se instalará para las pruebas.

 > [!div class="mx-imgBorder"]  
 > ![Captura de pantalla que muestra la prueba de configuración del paquete](Media/testwithm365app01.png)  
 > [!NOTE] 
 > Como el canal de versión preliminar de Office proporciona actualizaciones de Office de versión preliminar con cadencia mensual, solo se habilita el tipo de **actualización de seguridad** para el paquete una vez que se activa el botón de alternancia. Las versiones del sistema operativo Windows que se podrían seleccionar en la matriz de pruebas también se limitarán a los productos de Windows para los que está disponible el producto de Office elegido. Debido al requisito previo mencionado, si desea activar la característica de prueba de actualizaciones de Office para paquetes existentes, el tipo de actualización no compatible y los productos del sistema operativo Windows se deshabilitarán de forma predeterminada.

&nbsp;  
### <a name="define-the-install-sequence-for-the-chosen-microsoft-365-application"></a>Definición de la secuencia de instalación para la aplicación de Microsoft 365 elegida 

Puede usar **la prueba funcional** para definir la secuencia de instalación para la versión preliminar de Office con la actualización más reciente. Haga clic en el icono **Abrir panel de prueba funcional** como se muestra a continuación después de crear su propio script y agregar a la lista Prueba funcional.

 > [!div class="mx-imgBorder"]  
 > ![Captura de pantalla que muestra paquete de edición de paquetes](Media/testwithm365app02.png)

Podrá reordenar los scripts en el panel de lista funcional arrastrando los elementos hacia arriba y hacia abajo hasta el paso adecuado. Elija qué paso ejecutar la instalación de Office seleccionando el script antes de que se produzca la instalación de Office de versión preliminar.  

En el ejemplo siguiente, windows update se instalará primero, seguido del script pre-office-install y, a continuación, la versión preliminar de Office se instalará antes del script de instalación para la aplicación del usuario después del cual se ejecutará el script de prueba de ejecución.

 > [!div class="mx-imgBorder"]  
 > ![Captura de pantalla que muestra la prueba funcional](Media/testwithm365app03.png)  
 > [!NOTE]
 > Para el tipo de prueba lista para usar, la instalación de Office se ejecutará de forma predeterminada después de la instalación de Windows Update y antes de que se ejecute el script de instalación.

&nbsp;  
### <a name="view-the-test-result-with-microsoft-365-application"></a>Visualización del resultado de la prueba con la aplicación Microsoft 365  

Una ejecución de prueba se ejecutará después de que el paquete pase la validación. Mensualmente, se programará una ejecución automatizada en cada revisión el martes cuando se publique la última actualización de seguridad de Windows. El paquete instalará la versión preliminar más reciente de Office desde el canal de versión preliminar mensual a partir de la fecha de ejecución correspondiente para permitir que la aplicación se pruebe con las actualizaciones más recientes de Windows y Office.

Puede ver los resultados de las ejecuciones de prueba en la página Resumen de la prueba haciendo clic en el vínculo en el nombre del paquete.

 > [!div class="mx-imgBorder"]  
 > ![Captura de pantalla que muestra la actualización de seguridad](Media/testwithm365app04.png)

&nbsp;  
En la página detallada, verá install-Office como un script ejecutado automáticamente que representa el estado de la instalación de Office de versión preliminar.

 > [!div class="mx-imgBorder"]  
 > ![Captura de pantalla que muestra confiabilidad](Media/testwithm365app05.png)  
 > [!NOTE]
 > Para el tipo de prueba preconfigurado, se ejecutará un script de prueba de interoperabilidad de Office predefinido para ayudar a recopilar señales de conflicto para office de versión preliminar que se ejecuta con la aplicación instalada del usuario de forma predeterminada. Puede usar la prueba funcional para definir su propio flujo de prueba y omitir el script de prueba de Office si desea centrarse en probar cómo funciona la aplicación con las últimas actualizaciones de Office.
