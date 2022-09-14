---
title: Configuración y validación de exclusiones para Microsoft Defender para punto de conexión en Mac
description: Proporcione y valide exclusiones para Microsoft Defender para punto de conexión en Mac. Las exclusiones se pueden establecer para archivos, carpetas y procesos.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, exclusiones, exámenes, antivirus
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
search.appverid: met150
ms.openlocfilehash: 3efc1d4b6beea3c2fe63bcea8de86534ec95de02
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67692372"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a>Configuración y validación de exclusiones para Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se proporciona información sobre cómo definir exclusiones que se aplican a los exámenes a petición y la protección y supervisión en tiempo real.

> [!IMPORTANT]
> Las exclusiones descritas en este artículo no se aplican a otras funcionalidades de Defender para punto de conexión en Mac, incluida la detección y respuesta de puntos de conexión (EDR). Los archivos que se excluyen mediante los métodos descritos en este artículo todavía pueden desencadenar alertas de EDR y otras detecciones.

Puede excluir determinados archivos, carpetas, procesos y archivos abiertos por procesos de los exámenes de Defender para punto de conexión en Mac.

Las exclusiones pueden ser útiles para evitar detecciones incorrectas en archivos o software que son únicos o personalizados para su organización. También pueden ser útiles para mitigar los problemas de rendimiento causados por Defender para punto de conexión en Mac.

> [!WARNING]
> La definición de exclusiones reduce la protección que ofrece Defender para punto de conexión en Mac. Siempre debe evaluar los riesgos asociados a la implementación de exclusiones y solo debe excluir los archivos que esté seguro de que no son malintencionados.

## <a name="supported-exclusion-types"></a>Tipos de exclusión admitidos

En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para punto de conexión en Mac.

Exclusión|Definición|Ejemplos
---|---|---
Extensión de archivo|Todos los archivos con la extensión, en cualquier lugar de la máquina|`.test`
Archivo|Un archivo específico identificado por la ruta de acceso completa|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`
Folder|Todos los archivos de la carpeta especificada (de forma recursiva)|`/var/log/` <p> `/var/*/`
Proceso|Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él|`/bin/cat` <p> `cat` <p> `c?t`

Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:

Carácter comodín|Descripción|Ejemplo|Coincidencias|No coincide
---|---|---|---|---
\*|Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este carácter comodín dentro de una ruta de acceso, solo sustituirá una carpeta).|`/var/*/*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|Coincide con cualquier carácter único|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`

> [!NOTE]
> El producto intenta resolver los vínculos firmes al evaluar las exclusiones. La resolución de vínculo firme no funciona cuando la exclusión contiene caracteres comodín o el archivo de destino (en el `Data` volumen) no existe.

## <a name="how-to-configure-the-list-of-exclusions"></a>Configuración de la lista de exclusiones

### <a name="from-the-management-console"></a>Desde la consola de administración

Para obtener más información sobre cómo configurar exclusiones de JAMF, Intune u otra consola de administración, vea [Establecer preferencias para Defender para punto de conexión en Mac](mac-preferences.md).

### <a name="from-the-user-interface"></a>Desde la interfaz de usuario

Abra la aplicación Defender para punto de conexión y vaya a **Administrar la configuración** \> **Agregar o quitar exclusión...**, como se muestra en la captura de pantalla siguiente:

:::image type="content" source="images/mdatp-37-exclusions.png" alt-text="Página Administrar exclusiones" lightbox="images/mdatp-37-exclusions.png":::

Seleccione el tipo de exclusión que desea agregar y siga las indicaciones.

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Validación de listas de exclusiones con el archivo de prueba EICAR

Puede validar que las listas de exclusión funcionan mediante `curl` para descargar un archivo de prueba.

En el siguiente fragmento de código de Bash, reemplace por `test.txt` un archivo que se ajuste a las reglas de exclusión. Por ejemplo, si ha excluido la `.testing` extensión, reemplace por `test.txt` `test.testing`. Si va a probar una ruta de acceso, asegúrese de ejecutar el comando dentro de esa ruta de acceso.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Si Defender para punto de conexión en Mac informa de malware, la regla no funciona. Si no hay ningún informe de malware y el archivo descargado existe, la exclusión funciona. Puede abrir el archivo para confirmar que el contenido es el mismo que el que se describe en el [sitio web del archivo de prueba EICAR](http://2016.eicar.org/86-0-Intended-use.html).

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
