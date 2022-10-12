---
title: Prueba de la aplicación de Intune en Test Base
description: Prueba de la aplicación de Intune
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 04/11/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 4ebfff151c96752af0bca757c43f3df49a3d2ede
ms.sourcegitcommit: 893add1e40c3e26e5624663eaf272d12a72d0141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68540035"
---
# <a name="test-your-intune-application-on-test-base"></a>Prueba de la aplicación de Intune en Test Base 
  > [!Note] 
  > Esta guía le guiará para cargar el paquete de formato intunewin en Test Base. Para obtener instrucciones generales sobre la carga de paquetes de Test Base, consulte este [documento](https://microsoft.sharepoint.com/:w:/t/AzureSUVPCoreTeam/EeHQIT3qA0FKqBDWI5TzmzgBiH2Syz39o5VbY2kdugMn4A?e=Rk1KD9).

## <a name="intunewin-upload-flow"></a>Flujo de carga de Intunewin
Como un esfuerzo para habilitar aún más el uso comercial, Test Base comenzó a admitir el formato intunewin para los profesionales de TI que administran aplicaciones para sus aplicaciones dentro de Intune como el formato de paquete de incorporación estándar. El flujo de carga de intunewin proporciona la experiencia para que los profesionales de TI reutilicen sus paquetes de formato intunewin, que contienen las aplicaciones que implementaron en sus dispositivos finales a través de MEM/Intune para incorporar sus aplicaciones y probar configuraciones rápidamente en Test Base. 

**Requisitos previos**
  - Actualmente, la compatibilidad con Test Base se sincroniza a través de la misma suscripción entre Intune cuenta y la cuenta base de prueba (no es necesario tener una cuenta de Intune para cargar el paquete intunewin, pero si desea sincronizar la configuración de Intune para las aplicaciones correspondientes del archivo intunewin desde Intune, deberá asegurarse de que la Intune  se crea en la misma suscripción que la cuenta base de prueba).
  - Paquetes intunewin que se van a cargar. 

**Flujo de carga de archivos de Intunwin (sincronizado con Intune cuenta)** <br/>
Como cliente Intune que tiene un paquete de Intune, que ya se ha incorporado a Intune portal. El cliente puede incorporar el paquete intunewin (que contiene una aplicación con o sin dependencias de aplicaciones preinstaladas administradas en Intune) al servicio Base de prueba. (a través de Intune cuenta, que tiene el permiso adecuado para sincronizar la información de Intune aplicación).

**Paso de preparación**
1. Inicie sesión con su cuenta de Test Base.
2. Prepare el paquete intunewin.
3. Para empezar a cargar, haga clic en el vínculo "Crear paquete con Intune aplicación" como se muestra a continuación.
    
    > [!div class="mx-imgBorder"] 
    > ![Empezar a compilar un paquete con Intune aplicación](Media/testintuneapplication01.png) 


**Paso 1: Definir contenido**
1. Cargue el paquete intunewin que elija.
2. Conceda el token haciendo clic en el vínculo siguiente "Conceder token y seleccionar aplicación".
3. Después de la sincronización automática con la cuenta de Intune, aparecerá con la aplicación las aplicaciones en la cuenta de Intune. Elija la aplicación correspondiente al paquete intunewin cargado y haga clic en "Seleccionar".
    
    > [!div class="mx-imgBorder"] 
    > ![Carga del paquete de Intune](Media/testintuneapplication02.png) 


5. En la página Paso 1, verá las dependencias enumeradas en la sección Dependencia, puede optar por cargar el archivo de instalación de la dependencia o quitarlo de este paso (si tiene previsto administrar la dependencia en el paso 3, proporcione automáticamente los archivos binarios relacionados). Las dependencias seleccionadas de esta sección se instalarán previamente de la misma manera que se instalarán a través de Intune.
    
    > [!div class="mx-imgBorder"] 
    > ![Carga del paquete de dependencias](Media/testintuneapplication03.png) 


**Paso 2: Configurar prueba**
1. Seleccione PowerShell.
2. Seleccione Lista para usar.


**Paso 3: Editar paquete**
1. Compruebe que los scripts generados automáticamente se etiquetan correctamente.
2. Si sincronizó la configuración de Intune correctamente, debería poder ver que los comandos de instalación o desinstalación de la aplicación de prueba se han agregado en los scripts de instalación o desinstalación, los comandos de la dependencia **que se ha cargado** también se deben insertar en el árbol del explorador de paquetes para su revisión.
3. Compruebe que los archivos binarios de la aplicación de prueba se mueven en **la carpeta bin** .
4. Compruebe los archivos binarios de dependencia **que se han cargado** colocado en la carpeta **guid** .
5. Puede editar los scripts según sea necesario y guardarlos.
    > [!Note] 
    > Si no se ha cargado el paquete de dependencias, Test Base no generará comandos de instalación o desinstalación para él.  


**Paso 4. Establecer matriz de prueba**

La pestaña Matriz de pruebas le permite indicar el programa de actualización de Windows específico o el producto de Windows en el que puede que desee que se ejecute la prueba.

   > [!div class="mx-imgBorder"]
   > ![Establecimiento del nuevo paquete de matriz de pruebas](Media/settestmatrix01-newpackage.png)

1. Elegir **tipo de actualización del sistema operativo**
   - Test Base proporciona pruebas programadas para asegurarse de que el rendimiento de las aplicaciones no se verá interrumpido por las últimas actualizaciones de Windows. 

   > [!div class="mx-imgBorder"]
   > ![Establecer matriz de prueba elegir osupdate](Media/settestmatrix02-chooseosupdate.png)

   - Hay 2 opciones disponibles:
   
     - Las **actualizaciones de seguridad** permiten probar el paquete con renovaciones incrementales de actualizaciones de seguridad mensuales de Windows.
     - Las **actualizaciones de características** permiten probar el paquete con las nuevas características de las compilaciones de Windows Insider Preview más recientes del programa Windows Insider.

2. Configurar **actualización de seguridad** Para configurar las actualizaciones de seguridad, debe especificar los productos de Windows con los que desea realizar la prueba en la lista desplegable de "Versiones del sistema operativo que se van a probar".

   > [!div class="mx-imgBorder"]
   > ![Establecimiento de la matriz de prueba para configurar securityupdate](Media/settestmatrix03-configuresecurityupdate.png)

   - La selección registrará la aplicación para las ejecuciones de pruebas automáticas en la versión B de las actualizaciones de calidad mensuales de Windows de los productos seleccionados.
     - Para los clientes que tienen clientes de acceso predeterminado en Test Base, sus aplicaciones se validan con respecto a la versión final de las actualizaciones de seguridad de la versión B, a partir del martes de revisión.
     - Para los clientes que tienen clientes de acceso completo en La base de pruebas, sus aplicaciones se validan con respecto a las versiones preliminares de las actualizaciones de seguridad de la versión B, a partir de 3 semanas antes del martes de revisión. Esto permite que los clientes de acceso completo tengan tiempo para tomar medidas proactivas para resolver los problemas detectados durante las pruebas antes de la versión final del martes de revisión.  
       (¿Cómo convertirse en un cliente de acceso completo? Consulte [Solicitud para cambiar el nivel de acceso | Microsoft Docs](accesslevel.md))

3. Configuración **de la actualización de características**
   - Para configurar las actualizaciones de características, debe especificar el producto de destino y su canal en versión preliminar de la lista desplegable "Canal insider".

   > [!div class="mx-imgBorder"]
   > ![Establecer la configuración de la matriz de prueba featureupdate](Media/settestmatrix04-configurefeatureupdate.png)

   - La selección registrará la aplicación para que se ejecuten pruebas automáticas con las últimas actualizaciones de características del canal de producto seleccionado y todas las actualizaciones nuevas futuras en las últimas Windows Insider Preview compilaciones de la selección.

   - También puede establecer el sistema operativo actual en "Línea de base del sistema operativo para Insight". Le proporcionaremos más información de prueba mediante el análisis de regresión del entorno del sistema operativo tal cual y el sistema operativo de destino más reciente.

   > [!div class="mx-imgBorder"]
   > ![Establecimiento de sistemas operativos de conjunto de matrices de prueba](Media/settestmatrix05-setos.png)  


**Paso 5: Revisar y publicar** <br/>
Revise la configuración después de la cual se podría publicar el paquete.<br/><br/>


**Flujo de carga de archivos de Intunwin (no se puede sincronizar con Intune cuenta)** <br/>
Como cliente de Test Base que tiene un paquete intunewin independiente. El cliente puede incorporar el paquete intunewin (que contiene una aplicación con o sin dependencias de aplicaciones preinstaladas administradas en Intune) sin necesidad de obtener permiso concedido en Intune cuenta para finalizar el proceso de incorporación.

**Paso de preparación**
1. Inicie sesión con su cuenta de Test Base.
2. Prepare el paquete intunewin.
3. Para empezar a cargar, haga clic en el vínculo "Crear paquete con Intune aplicación" como se muestra a continuación.
    
    > [!div class="mx-imgBorder"] 
    > ![Creación de un paquete con Intune App](Media/testintuneapplication04.png) 


**Paso 1: Definir contenido**
1. Cargue el paquete intunewin.
2. Especifique toda la información según sus preferencias.


**Paso 2: Configurar prueba**
1. Seleccione PowerShell.
2. Seleccione Lista para usar.


**Paso 3: Editar paquete**
1. Compruebe que los scripts están etiquetados correctamente.
2. Dado que no se sincroniza ningún comando de instalación o desinstalación desde la cuenta de Intune correspondiente, deberá proporcionar todos los scripts (instalar, desinstalar, iniciar o cerrar) por sí mismo.
3. Compruebe que los archivos binarios de la aplicación de prueba se mueven en la carpeta bin.
4. Puede editar los scripts según sea necesario y guardarlos.


**Paso 4: Matriz de prueba**
1. No se seleccionará previamente ninguna versión predeterminada del sistema operativo.
2. Los usuarios pueden realizar su propia selección en los sistemas operativos que se van a programar.


**Paso 5: Revisar y publicar** <br/>
Revise la configuración después de la cual se podría publicar el paquete.




