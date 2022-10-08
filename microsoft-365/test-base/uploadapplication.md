---
title: Carga de un paquete zip precompilado
description: Cómo editar, cargar y probar un archivo .zip precompilado en Test Base
search.appverid: MET150
author: mansipatel-usl
ms.author: rshastri
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 7cec39a88c5b589959a8cd5b9fd3103f465ca60c
ms.sourcegitcommit: fa570d90b00ed1bb40e1ca27b11c66a84c4204e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68481837"
---
# <a name="uploading-a-pre-built-zip-package"></a>Carga de un paquete zip precompilado

En esta sección se proporcionan todos los pasos necesarios para editar, cargar y probar en Test Base cuando ya tiene un archivo .zip compilado previamente.

**Solicitudes previas**

   - Cuenta base de prueba: si no tiene una cuenta **base de prueba** , deberá crear una antes de continuar, como se describe en [Creación de una cuenta base de prueba](createAccount.md).
   - Archivo de .zip precompilado: un archivo .zip creado sin conexión que contiene los scripts binarios y de prueba de la aplicación. Consulte [Compilación de un paquete | Microsoft Docs](buildpackage.md) preparar el paquete de .zip base de pruebas desde el escritorio.

## <a name="upload-an-offline-built-package"></a>Carga de un paquete integrado sin conexión

En el [Azure Portal](https://portal.azure.com/), vaya a la cuenta base de **prueba** para la que va a crear y cargar el paquete y realice los pasos siguientes.

En el menú de la izquierda, en **Catálogo de paquetes**, seleccione nuevo **paquete**. A continuación, seleccione la tercera tarjeta **"Cargar paquete precompilado"**.

> [!div class="mx-imgBorder"]
> [![Menú](Media/uploadingzip01-new-package.png) izquierdo ](Media/uploadingzip01-new-package.png#lightbox)

### <a name="step-1-define-content"></a>Paso 1. Definir contenido

1. En la sección **Origen del paquete** , seleccione Paquete precompilado (.zip) en Tipo de origen del paquete.

   > [!div class="mx-imgBorder"]
   > [![Nuevo paquete](Media/uploadingzip02-define-content.png) ](Media/uploadingzip02-define-content.png#lightbox)

2. Cargue el archivo de paquete precompilado (zip) seleccionando el botón "Seleccionar archivo".

3. Escriba el nombre y la versión del paquete en la sección **Información básica** .

   > [!NOTE]
   > La combinación del nombre y la versión del paquete debe ser única dentro de la cuenta base de prueba.

   > [!div class="mx-imgBorder"]
   > ![Información básica](Media/uploadingzip03-basic-information.png)

4. Después de especificar toda la información solicitada, seleccione el botón **Siguiente: Prueba de configuración** .

   > [!div class="mx-imgBorder"]
   > ![Siguiente: Prueba de configuración](Media/uploadingzip04-next.png)

### <a name="step-2-configure-test"></a>Paso 2. Configuración de la prueba

1. Seleccione el **tipo de prueba** según el paquete precompilado. Se admiten dos tipos de prueba:

   - Una **prueba lista para usar (OOB)** realiza una instalación, inicio, cierre y desinstalación del paquete. Después de la instalación, la rutina de inicio y cierre se repite 30 veces antes de que se ejecute una sola desinstalación. La prueba de OOB proporciona telemetría estandarizada en el paquete para compararlo entre compilaciones de Windows.
   - Una **prueba funcional** ejecuta los scripts de prueba cargados en el paquete. Los scripts se ejecutan en la secuencia especificada y un error en un script determinado impedirá la ejecución de scripts posteriores.

   > [!NOTE]
   > Ahora, la prueba lista para usar es opcional.

   > [!div class="mx-imgBorder"]
   > [![Opción de prueba lista para usar](Media/uploadingzip05-configure-test.png) ](Media/uploadingzip05-configure-test.png#lightbox)

2. Una vez rellenada toda la información necesaria, seleccione el botón Siguiente.

### <a name="step-3-edit-package"></a>Paso 3. Editar paquete

1. En la pestaña Editar paquete, puede hacer lo siguiente:
   - compruebe la carpeta del paquete y la estructura de archivos en **la versión preliminar del paquete**.
   - edite los scripts en línea con el **editor de código de PowerShell**.

   > [!NOTE]
   > El paquete precompilado se extrae para editarlo. Las etiquetas de script se agregan según el nombre del script, revise estas etiquetas de script y ajuste si es necesario. Las etiquetas de script indican las rutas de acceso de script correctas que se usarán cuando se inicien las pruebas.

   > [!div class="mx-imgBorder"]
   > [![Editor](Media/uploadingzip06-edit-package.png) de código de PowerShell ](Media/uploadingzip06-edit-package.png#lightbox)

2. En la **versión preliminar del paquete**, según sus necesidades, puede hacer lo siguiente:

   - crear una nueva carpeta.
   - crear un script nuevo.
   - cargar un nuevo archivo.

3. En **la carpeta scripts**, se han creado scripts de ejemplo y etiquetas de script automáticamente. Todas las etiquetas de script son editables. Puede reasignarlos para hacer referencia a las rutas de acceso del script.

   - Si la **prueba lista** para usar está seleccionada en el paso 2, puede ver la carpeta **outofbox** en la carpeta scripts. También puede elegir agregar la etiqueta **"Reiniciar después de la instalación"** para el script de instalación.

   > [!div class="mx-imgBorder"]
   > [![Scripts de ejemplo y etiquetas](Media/uploadingzip07-edit-script.png) de script ](Media/uploadingzip07-edit-script.png#lightbox)

   > [!NOTE]
   > Las etiquetas de script Install, Launch y Close son obligatorias para el tipo de prueba OOB. La reasignación de etiquetas garantiza que se usará la ruta de acceso de script correcta cuando se inicien las pruebas.

   > [!div class="mx-imgBorder"]
   > [![Falta notificación](Media/uploadingzip08-required-prompt.png) de scripts ](Media/uploadingzip08-required-prompt.png#lightbox)

   - Si la **prueba funcional** está seleccionada en el paso 2, puede ver la carpeta **funcional** en la carpeta scripts. Se pueden agregar scripts de prueba más funcionales mediante el botón **"Agregar a la lista de pruebas funcionales"** . Necesita un script mínimo de (1) y puede agregar hasta ocho (8) scripts de prueba funcionales.

   > [!div class="mx-imgBorder"]
   > [![Agregar a la lista](Media/uploadingzip09-add-to-list.png) de pruebas funcionales ](Media/uploadingzip09-add-to-list.png#lightbox)

   > [!NOTE]
   > Al menos 1 etiqueta de script funcional es obligatoria para el tipo de prueba funcional.

   Seleccione **Agregar a la lista de pruebas funcionales** para agregar más scripts funcionales desde el panel de acciones. Estas son las opciones:

   - Reordene las rutas de acceso del script arrastrando con los botones de puntos suspensivos izquierdos. Los scripts funcionales se ejecutan en la secuencia en la que aparecen. Un error en un script determinado impide que se ejecuten scripts posteriores.
   - Establezca "Reiniciar después de la ejecución" para varios scripts.
   - Aplique la actualización antes en una ruta de acceso de script específica. Esta actualización está destinada a los usuarios que desean realizar pruebas funcionales para indicar cuándo se debe aplicar la revisión de Windows Update en la secuencia de ejecución de sus scripts de prueba funcionales.

   > [!div class="mx-imgBorder"]
   > [![Prueba](Media/uploadingzip10-functional-test.png) funcional ](Media/uploadingzip10-functional-test.png#lightbox)

4. Una vez rellenada toda la información necesaria, puede continuar con el paso 4 seleccionando el botón Siguiente en la parte inferior.

### <a name="step-4-test-matrix"></a>Paso 4. Matriz de prueba

1. En la pestaña Matriz de pruebas, seleccione el **tipo de actualización del sistema operativo**. Se admiten dos tipos de actualización del sistema operativo.

   - Las **actualizaciones de seguridad** permiten probar el paquete con renovaciones incrementales de actualizaciones de seguridad mensuales de versión preliminar de Windows.
   - Las **actualizaciones de características** permiten probar el paquete con las compilaciones de actualizaciones de características bianuales de versión preliminar de Windows del Programa Windows Insider.

2. Seleccione las versiones del sistema operativo para las pruebas de actualización de seguridad.

   Si **se selecciona Actualizaciones de seguridad** en tipo de actualización del sistema operativo, deberá seleccionar las versiones del sistema operativo en las que se probará el paquete.

   > [!NOTE]
   > Si selecciona probar el paquete con los sistemas operativos servidor y cliente, asegúrese de que el paquete es compatible y se puede ejecutar en ambos sistemas operativos.

3. Seleccione las opciones de Pruebas de actualización de características.

   - Si se selecciona **Actualizaciones de características** en tipo de actualización del sistema operativo, debe finalizar las siguientes opciones.
   - En **Canal insider**, seleccione el canal del programa Windows Insider como la compilación en la que se deben probar los paquetes. Actualmente usamos compilaciones piloto en el **canal beta de Insider**.
   - En **Línea base del sistema operativo para Insight**, seleccione la versión del sistema operativo Windows que se usará como línea base para comparar los resultados de la prueba.

   > [!div class="mx-imgBorder"]
   > [![](Media/uploadingzip11-test-matrix.png) Matriz de prueba ](Media/uploadingzip11-test-matrix.png#lightbox)

4. Una vez rellenada toda la información necesaria, puede continuar con el paso 5 (último paso) seleccionando el botón Siguiente en la parte inferior.

### <a name="step-5-review--publish"></a>Paso 5. Revisar y publicar

1. Revise toda la información para ver si el paquete es correcto y preciso. Para realizar correcciones, puede volver a los pasos iniciales en los que especificó la configuración según sea necesario.

   > [!div class="mx-imgBorder"]
   > [![Revisión y publicación](Media/uploadingzip12-review.png) ](Media/uploadingzip12-review.png#lightbox)

2. También puede activar la casilla de notificación para recibir la notificación por correo electrónico del paquete para el aviso de finalización de la ejecución de validación.

   > [!div class="mx-imgBorder"]
   > ![Notificación](Media/uploadingzip13-notification.png)

3. Cuando haya terminado de finalizar la configuración de datos de entrada, seleccione **Publicar** para cargar el paquete en Test Base. La notificación siguiente se muestra cuando el paquete se publica correctamente y ha entrado en el proceso de verificación.

   > [!NOTE]
   > El paquete debe comprobarse antes de que se acepte para futuras pruebas. La comprobación puede tardar hasta 24 horas, ya que incluye la ejecución del paquete en un entorno de prueba real.

   > [!div class="mx-imgBorder"]
   > ![Publicación correcta de la notificación](Media/uploadingzip14-success.png)

4. Se le redirigirá a la página **Administrar paquetes** para comprobar el progreso del paquete recién cargado.

   > [!div class="mx-imgBorder"]
   > [![Administrar paquetes](Media/uploadingzip15-package-list.png) ](Media/uploadingzip15-package-list.png#lightbox)

   > [!NOTE]
   > Cuando se complete el proceso de verificación, el estado de verificación cambiará a Aceptado. En este momento, no se requieren más acciones. El paquete se adquirirá automáticamente para su ejecución cada vez que los sistemas operativos configurados tengan nuevas actualizaciones disponibles. Si se produce un error en el proceso de verificación, el paquete no está listo para las pruebas. Compruebe los registros y evalúe si se han producido errores. También es posible que tenga que comprobar los valores de configuración del paquete para detectar posibles problemas.


## <a name="continue-package-creation"></a>Continuar con la creación de paquetes

Si tiene algún paquete de borrador anterior, puede ver la lista de los paquetes de borrador guardados en la página **Nuevo paquete** . Puede continuar la edición directamente en el paso que detuvo la última vez seleccionando el icono de lápiz "editar".

> [!div class="mx-imgBorder"]
> [![Nueva página](Media/uploadingzip16-draft-packages.png) de paquete ](Media/uploadingzip16-draft-packages.png#lightbox)

> [!NOTE]
> El panel solo muestra el paquete de trabajo en curso. Para el paquete publicado, puede comprobar la página Administrar paquetes.
