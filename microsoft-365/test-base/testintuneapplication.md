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
ms.openlocfilehash: 2fbe3a21762f6bf048d5f35485a359389df93ce2
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315994"
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


**Paso 4: Matriz de prueba**
1. Compruebe las selecciones predeterminadas presentes en la lista del sistema operativo para ver los tipos de prueba correspondientes.
    - La base de pruebas admite la selección de varias actualizaciones acumulativas **de Windows de Windows 10 1909 excepto Windows 10 2004**, pero Intune aplicación Win se asignaría con una versión de versiones iguales o superiores a **Windows 10 1607**.
    - La lista del sistema operativo incluirá de forma predeterminada todos los sistemas operativos compatibles con test base, que es mayor que el sistema operativo mínimo especificado para la aplicación Intune Win.
2. Los usuarios pueden modificar la selección del sistema operativo según sea necesario.


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




