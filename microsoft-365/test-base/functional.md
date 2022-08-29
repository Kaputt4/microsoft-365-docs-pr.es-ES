---
title: Pruebas funcionales en la base de pruebas
description: Detalles sobre cómo probar la aplicación con las pruebas funcionales automatizadas existentes
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-Microsoft 365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 566ca739c15920d1d9c1260d7b7e771dd984b9d8
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315508"
---
# <a name="functional-testing"></a>Pruebas de funcionamiento

Como editor de software, ahora puede realizar pruebas funcionales personalizadas mediante el marco de pruebas de su elección, a través del portal base de pruebas de autoservicio para Microsoft 365. 

Al iniciar inicialmente el servicio, se ofrecieron las pruebas integradas, que es un conjunto predefinido de pruebas controladas mediante scripting estandarizado. Sin embargo, esto no pudo lograr una cobertura de prueba completa para muchos proveedores de software independientes (ISV). 

Por lo tanto, en respuesta a sus comentarios, proporcionamos a nuestros ISV la capacidad de cargar pruebas funcionales automatizadas.

Para usar esta característica, siga estos pasos:

1. Cargue los archivos (archivos binarios, dependencias y scripts) como un único paquete .zip.
2. Elija si desea reiniciar el Virtual Machines de prueba (VM) en varios puntos de ejecución.
3. Administre las opciones disponibles para los scripts.
4. Elija cuándo aplicar la actualización de Windows en la máquina virtual durante la ejecución.

A continuación se resaltan descripciones detalladas de los pasos anteriores:

**Carga de un paquete de prueba funcional**

Para empezar, vaya a la página Cargar y seleccione Cargar nueva aplicación en Catálogo de aplicaciones en el menú de navegación de la izquierda del portal Base de pruebas para M365 en Azure. Desde allí:

Pestaña 1: escriba información básica. Proporcione el nombre y la versión de la aplicación. En la opción Tipo de prueba, seleccione ```Functional tests```. 

*La opción Lista para usar (OOB) es necesaria de forma predeterminada.*


![Seleccione la pestaña Pruebas funcionales.](Media/functional_testing_tab1.png)

Pestaña 2: Cargue los componentes del paquete cargando un archivo ZIP con toda la prueba (archivos binarios, dependencias, scripts, etc.). 

Consulte aka.ms/usl-package-outline para obtener más información. (Nota: Tanto los scripts de prueba de fábrica como el contenido de la prueba funcional deben colocarse en el mismo archivo ZIP). Actualmente, el tamaño del archivo está limitado a 2 GB.

Pestaña 3: Configurar las tareas de prueba integradas y funcionales. Aquí, elija las rutas de acceso a los scripts de PowerShell que instalarán, iniciarán, cerrarán y desinstalarán la aplicación (para la versión de fábrica) y las rutas de acceso a todos los scripts personalizados para realizar la prueba funcional. **(Nota: Un script para desinstalar la aplicación es opcional).**

Actualmente, puede cargar de 1 a 8 scripts para las pruebas funcionales. (Por favor, comente esta publicación si necesita más scripts).

![Cargue hasta 8 scripts con pruebas funcionales.](Media/functional_testing_tab3.png)

(Opcional) Puede configurar un reinicio después de la instalación. Algunas aplicaciones requieren un reinicio después de la instalación. 

Seleccione ```Reboot After Execution``` el script específico en la pestaña Tareas si desea que se realice un reinicio después de la ejecución de ese script.

Pestaña 4: elija cuándo se instala la actualización de Windows: la aplicación de la revisión de Windows Update se realiza antes de cualquier script de su elección. Se recomienda instalar una actualización de Windows después de la instalación de la aplicación para imitar estrechamente los escenarios de uso de la aplicación real.

![La actualización de Windows se puede instalar después de un script específico.](Media/functional_testing_tab4.png)

Pestaña 5: Revisar y crear el paquete. Una vez que haya completado los pasos enumerados anteriormente, seleccione ```Create``` para finalizar el proceso de carga.

Una vez creado el paquete, puede comprobar el estado de verificación del paquete.

Ejecutamos una prueba inicial para instalar, iniciar, cerrar y desinstalar la aplicación. Nos permite comprobar que el paquete puede instalarse en nuestro servicio sin errores.

El proceso de verificación puede tardar hasta 24 horas. Una vez completada la comprobación, puede ver el estado en el ```Manage packages``` menú, que sería una de las dos entradas:

1. La comprobación se realiza correctamente: el paquete se probará automáticamente con las actualizaciones de Windows de versión preliminar para las compilaciones del sistema operativo que seleccionó.
o
2. Se produce un error en la comprobación: tendrá que investigar los motivos del error, corregir el problema y volver a cargar el paquete.

También se le notificará de cualquiera de los resultados a través del icono de notificación del Azure Portal.
