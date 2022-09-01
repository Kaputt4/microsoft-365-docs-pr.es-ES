---
title: Configuración y validación de exclusiones para Microsoft Defender para punto de conexión en Linux
description: Proporcione y valide exclusiones para Microsoft Defender para punto de conexión en Linux. Las exclusiones se pueden establecer para archivos, carpetas y procesos.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, exclusiones, exámenes, antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 127f287fe9de0644df4373a62ee78e8ac95c9c2e
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67519828"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Configuración y validación de exclusiones para Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se proporciona información sobre cómo definir exclusiones que se aplican a los exámenes a petición y la protección y supervisión en tiempo real.

> [!IMPORTANT]
> Las exclusiones descritas en este artículo no se aplican a otras funcionalidades de Defender para punto de conexión en Linux, incluida la detección y respuesta de puntos de conexión (EDR). Los archivos que se excluyen mediante los métodos descritos en este artículo todavía pueden desencadenar alertas de EDR y otras detecciones.

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes de Defender para punto de conexión en Linux.

Las exclusiones pueden ser útiles para evitar detecciones incorrectas en archivos o software que son únicos o personalizados para su organización. También pueden ser útiles para mitigar los problemas de rendimiento causados por Defender para punto de conexión en Linux.

> [!WARNING]
> La definición de exclusiones reduce la protección que ofrece Defender para punto de conexión en Linux. Siempre debe evaluar los riesgos asociados a la implementación de exclusiones y solo debe excluir los archivos que esté seguro de que no son malintencionados.

## <a name="supported-exclusion-types"></a>Tipos de exclusión admitidos

En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para punto de conexión en Linux.

Exclusión|Definición|Ejemplos
---|---|---
Extensión de archivo|Todos los archivos con la extensión, en cualquier lugar del dispositivo|`.test`
Archivo|Un archivo específico identificado por la ruta de acceso completa|`/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Folder|Todos los archivos de la carpeta especificada (de forma recursiva)|`/var/log/`<br/>`/var/*/`
Proceso|Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él|`/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> Las rutas de acceso anteriores deben ser vínculos duros, no vínculos simbólicos, para que se excluyan correctamente. Puede comprobar si una ruta de acceso es un vínculo simbólico mediante la ejecución de `file <path-name>`.

Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:

Carácter comodín|Descripción|Ejemplo|Coincidencias|No coincide
---|---|---|---|---
\*|Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este carácter comodín dentro de una ruta de acceso, solo sustituirá una carpeta).|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|Coincide con cualquier carácter único|`file?.log`|`file1.log`<br/>`file2.log`|`file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>Configuración de la lista de exclusiones

### <a name="from-the-management-console"></a>Desde la consola de administración

Para obtener más información sobre cómo configurar exclusiones de Puppet, Ansible u otra consola de administración, consulte [Establecer preferencias para Defender para punto de conexión en Linux](linux-preferences.md).

### <a name="from-the-command-line"></a>Desde la línea de comandos

Ejecute el siguiente comando para ver los modificadores disponibles para administrar exclusiones:

```bash
mdatp exclusion
```

> [!TIP]
> Al configurar exclusiones con caracteres comodín, incluya el parámetro entre comillas dobles para evitar el uso de globbing.

Ejemplos:

- Agregue una exclusión para una extensión de archivo:

    ```bash
    mdatp exclusion extension add --name .txt
    ```

    ```Output
    Extension exclusion configured successfully
    ```

- Agregue una exclusión para un archivo:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```

    ```Output
    File exclusion configured successfully
    ```

- Agregue una exclusión para una carpeta:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- Agregue una exclusión para una segunda carpeta:

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- Agregue una exclusión para una carpeta con un carácter comodín en ella:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Esto solo excluirá las rutas de acceso de un nivel por debajo de */var/*, pero no las carpetas que están más profundamente anidadas; por ejemplo, */var/this-subcarpeta/but-not-this-subcarpeta*.

    ```bash
    mdatp exclusion folder add --path "/var/"
    ```

    > [!NOTE]
    > Esto excluirá todas las rutas de acceso cuyo elemento primario sea */var/*; por ejemplo, */var/this-subcarpeta/and-this-subcarpeta-as-así*.

    ```Output
    Folder exclusion configured successfully
    ```

- Agregue una exclusión para un proceso:

    ```bash
    mdatp exclusion process add --name cat
    ```

    ```Output
    Process exclusion configured successfully
    ```

- Agregue una exclusión para un segundo proceso:

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```

    ```Output
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Validación de listas de exclusiones con el archivo de prueba EICAR

Puede validar que las listas de exclusión funcionan mediante `curl` para descargar un archivo de prueba.

En el siguiente fragmento de código de Bash, reemplace por `test.txt` un archivo que se ajuste a las reglas de exclusión. Por ejemplo, si ha excluido la `.testing` extensión, reemplace por `test.txt` `test.testing`. Si va a probar una ruta de acceso, asegúrese de ejecutar el comando dentro de esa ruta de acceso.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Si Defender para punto de conexión en Linux informa de malware, la regla no funciona. Si no hay ningún informe de malware y el archivo descargado existe, la exclusión funciona. Puede abrir el archivo para confirmar que el contenido es el mismo que el que se describe en el [sitio web del archivo de prueba EICAR](http://2016.eicar.org/86-0-Intended-use.html).

Si no tiene acceso a Internet, puede crear su propio archivo de prueba EICAR. Escriba la cadena EICAR en un nuevo archivo de texto con el siguiente comando de Bash:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

También puede copiar la cadena en un archivo de texto en blanco e intentar guardarlo con el nombre de archivo o en la carpeta que intenta excluir.

## <a name="allow-threats"></a>Permitir amenazas

Además de excluir cierto contenido del examen, también puede configurar el producto para que no detecte algunas clases de amenazas (identificadas por el nombre de la amenaza). Debe tener cuidado al usar esta funcionalidad, ya que puede dejar el dispositivo desprotegido.

Para agregar un nombre de amenaza a la lista permitida, ejecute el siguiente comando:

```bash
mdatp threat allowed add --name [threat-name]
```

El nombre de amenaza asociado a una detección en el dispositivo se puede obtener mediante el siguiente comando:

```bash
mdatp threat list
```

Por ejemplo, para agregar `EICAR-Test-File (not a virus)` (el nombre de amenaza asociado a la detección de EICAR) a la lista de permitidos, ejecute el siguiente comando:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
