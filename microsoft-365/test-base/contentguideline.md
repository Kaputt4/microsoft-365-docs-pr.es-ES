---
title: Directrices del paquete de prueba
description: Revisar las directrices sobre el paquete de prueba
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: null
ms.reviewer: mapatel
f1.keywords: NOCSH
---
# <a name="test-package-guidelines"></a>Directrices del paquete de prueba

## <a name="1-script-referencing"></a>1. Referencia a scripts

Al cargar un archivo .zip en el portal, descomprimimos todo el contenido de ese archivo en una carpeta raíz. No es necesario escribir ningún código para realizar esta operación inicial de descomprimir. También puede hacer referencia a cualquier archivo dentro del .zip mediante la ruta de acceso relativa al archivo zip cargado.

En el ejemplo siguiente, se muestra cómo puede hacer referencia a los archivos binarios o scripts desde el campo de entrada en la pestaña Tareas. El texto en azul debe especificarse en el **campo Ruta de acceso** script **sin las comillas.**

Es importante que conozca el contenido del archivo zip antes de cargarlo. A menudo, al comprimir una carpeta, el equipo local creará una carpeta principal debajo del archivo zip. En este caso, la referencia será como se muestra en negrita **a** continuación:

**Contoso_App_Folder.zip**:

```console
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│      ├── file3.exe

│      ├── script.ps1
```

- ScriptX.ps1: **"Contoso_App_Folder/ScriptX.ps1"**
- Script.ps1: **"Contoso_App_Folder/folder1/script.ps1"**

Otras veces, el archivo zip puede tener los archivos o el contenido justo debajo de él (por ejemplo, ninguna carpeta de 2nd-level):

**Zip_file_uploaded.zip**:

```console
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
```

- ScriptX.ps1: **"ScriptX.ps1"**
- Script.ps1: **"folder1/script.ps1"**

## <a name="2-script-execution"></a>2. Ejecución de scripts

**Pruebas de salida:** El paquete de la aplicación debe contener al menos tres scripts de PowerShell. Estos scripts ejecutarán la instalación, el inicio y el cierre desatendidos de la aplicación y sus dependencias. Cada script debe controlar la comprobación de sus propios requisitos previos, validar su propio éxito y limpiar después de sí mismo (si es necesario).

**Pruebas funcionales:** El paquete de aplicación debe contener al menos un script de PowerShell. Cuando se proporciona más de un script, los scripts se ejecutan en secuencia de carga y un error en un script determinado impedirá la ejecución de scripts posteriores.

### <a name="script-requirements"></a> Requisitos de script

- PowerShell versión 5.1+
- Ejecución desatendida
- Código de devolución de errores
- Validar el éxito
- Registro en una carpeta de registro específica del script

Cada script debe ejecutarse desatendidamente (sin avisos de usuario) para ejecutarse correctamente en la canalización de prueba.

> [!NOTE]
> Los scripts deben devolver "0" al finalizar correctamente y un código de error distinto de cero si se produce algún error durante la ejecución.

Cada script debe validar que se ejecutó correctamente. Por ejemplo, el script de instalación debe comprobar la existencia de determinados archivos binarios o claves del Registro en el sistema después de que el binario del instalador termine de ejecutarse. Esta comprobación ayuda a garantizar con un grado razonable de confianza que la instalación se ha realizado correctamente.

La validación es necesaria para diagnosticar correctamente dónde se producen errores durante una ejecución de prueba. Por ejemplo, si el script no puede instalar la aplicación correctamente frente a no poder iniciarla.

> [!IMPORTANT]
> **Evite lo siguiente:** Los scripts no deben reiniciar el equipo, si es necesario reiniciarlo, especifique esto durante la carga de los scripts.

## <a name="3-log-collection"></a>3. Colección de registros

Cada script debe generar los registros que genere en una carpeta denominada `logs`. Todas las carpetas del directorio denominado `logs` se copiarán y se presentarán para su descarga en la `Test Results` página.

Por ejemplo, el script de instalación (que puede encontrarse en el directorio **App/scripts/install** ) puede generar sus registros en: **logs/install.log**, de modo que el registro final estará en: **Apps/scripts/install/logs/install.log**

El sistema recogerá el archivo `install.log` junto con otros archivos dentro de `logs` otras carpetas y lo intercalará para su descarga.

## <a name="4-application-binaries"></a>4. Archivos binarios de aplicación

Los archivos binarios y las dependencias deben incluirse en el archivo zip único.

Estos archivos binarios deben incluir todo lo necesario para la instalación de la aplicación (por ejemplo, el instalador de la aplicación). Si la aplicación tiene una dependencia en algún marco, como .NET Core/Standard o .NET Framework, estos marcos deben incluirse en el archivo y hacer referencia correctamente en los scripts proporcionados.

> [!NOTE]
> El archivo zip cargado no puede tener espacios ni caracteres especiales en su nombre

## <a name="5-applicationtest-rules"></a>5. Reglas de aplicación y prueba

Para que las aplicaciones o pruebas se ejecuten correctamente en la infraestructura base de pruebas, deben cumplir las reglas descritas en [Reglas de aplicación y prueba ](rules.md). 

## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para ver algunas **preguntas más frecuentes (PREGUNTAS FRECUENTES)**
> [!div class="nextstepaction"]
> [Paso siguiente](faq.md)
