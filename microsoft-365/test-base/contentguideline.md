---
title: Directrices del paquete de prueba
description: Revisión de las directrices sobre el paquete de prueba
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: eea9d04f2a50ce7a9a858a302eeef2c9feef8868
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315556"
---
# <a name="test-package-guidelines"></a>Directrices del paquete de prueba

## <a name="1-script-referencing"></a>1. Referencia de script

Al cargar un archivo .zip en el portal, descomprimimos todo el contenido de ese archivo en una carpeta raíz. No es necesario escribir ningún código para realizar esta operación de descompresión inicial. También puede hacer referencia a cualquier archivo dentro de la .zip mediante la ruta de acceso relativa al archivo ZIP cargado.

En el ejemplo siguiente, se muestra cómo puede hacer referencia a los archivos binarios o scripts desde el campo de entrada de la pestaña Tareas. El texto en azul debe escribirse en el campo **Ruta de acceso de script** **sin comillas.**

Es importante que conozca el contenido del archivo ZIP antes de cargarlo. A menudo, al comprimir una carpeta, el equipo local creará una carpeta principal debajo del archivo ZIP. En este caso, la referencia será como se muestra en **negrita** a continuación:

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

Otras veces, el archivo ZIP puede tener los archivos o el contenido justo debajo de él (por ejemplo, ninguna carpeta de segundo nivel):

**Zip_file_uploaded.zip**:

```console
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
```

- ScriptX.ps1 - **"ScriptX.ps1"**
- Script.ps1: **"folder1/script.ps1"**

## <a name="2-script-execution"></a>2. Ejecución de scripts

**Pruebas integradas:** El paquete de aplicación debe contener al menos tres scripts de PowerShell. Estos scripts ejecutarán la instalación, el inicio y el cierre desatendidos de la aplicación y sus dependencias. Cada script debe controlar la comprobación de sus propios requisitos previos, validar su propio éxito y limpiar después de sí mismo (si es necesario).

**Pruebas funcionales:** El paquete de aplicación debe contener al menos un script de PowerShell. Cuando se proporciona más de un script, los scripts se ejecutan en la secuencia de carga y un error en un script determinado impedirá la ejecución de scripts posteriores.

### <a name="script-requirements"></a> Requisitos de script

- Versión 5.1+ de PowerShell
- Ejecución desatendida
- Código devuelto por error
- Validación correcta
- Registro para crear scripts de una carpeta de registro específica

Cada script debe ejecutarse desatendida (sin avisos de usuario) para ejecutarse correctamente en la canalización de prueba.

> [!NOTE]
> Los scripts deben devolver "0" al finalizar correctamente y un código de error distinto de cero si se produce algún error durante la ejecución.

Cada script debe validar que se ejecutó correctamente. Por ejemplo, el script de instalación debe comprobar la existencia de determinados archivos binarios o claves del Registro en el sistema después de que el binario del instalador termine de ejecutarse. Esta comprobación ayuda a garantizar con un grado razonable de confianza que la instalación se realizó correctamente.

La validación es necesaria para diagnosticar correctamente dónde se producen errores durante una ejecución de prueba. Por ejemplo, si el script no puede instalar la aplicación correctamente en lugar de no poder iniciarla.

> [!IMPORTANT]
> **Evite lo siguiente:** Los scripts no deben reiniciar la máquina, si es necesario reiniciar, especifique esto durante la carga de los scripts.

## <a name="3-log-collection"></a>3. Recopilación de registros

Cada script debe generar los registros que genera en una carpeta denominada `logs`. Todas las carpetas del directorio denominado `logs` se copiarán y presentarán para su descarga en la `Test Results` página.

Por ejemplo, el script de instalación (que puede encontrarse en el directorio **App/scripts/install** ) puede generar sus registros en: **logs/install.log**, de modo que el registro final esté en: **Apps/scripts/install/logs/install.log**

El sistema recogerá el `install.log` archivo junto con otros archivos dentro de otras `logs` carpetas y lo intercalará para su descarga.

## <a name="4-application-binaries"></a>4. Archivos binarios de la aplicación

Los archivos binarios y las dependencias deben incluirse en el único archivo ZIP.

Estos archivos binarios deben incluir todo lo necesario para la instalación de la aplicación (por ejemplo, el instalador de la aplicación). Si la aplicación tiene una dependencia en cualquier marco, como .NET Core/Standard o .NET Framework, estos marcos deben incluirse en el archivo y hacer referencia a ellos correctamente en los scripts proporcionados.

> [!NOTE]
> El archivo ZIP cargado no puede tener espacios ni caracteres especiales en su nombre

## <a name="5-applicationtest-rules"></a>5. Reglas de aplicación/prueba

Para que las aplicaciones o pruebas se ejecuten correctamente en la infraestructura base de pruebas, deben cumplir las reglas descritas en [Reglas de aplicación/prueba ](rules.md). 

## <a name="next-steps"></a>Siguientes pasos

Pase al siguiente artículo para ver algunas **preguntas más frecuentes (P+F)**
> [!div class="nextstepaction"]
> [Paso siguiente](faq.md)
