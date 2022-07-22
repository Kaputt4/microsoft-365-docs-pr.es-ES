---
title: Novedades de Microsoft Defender para punto de conexión en Mac
description: Obtenga información sobre los cambios principales de las versiones anteriores de Microsoft Defender para punto de conexión en Mac.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 3ea2822adabcd0a747d34fbdb8c6d8d2c944afdf
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969548"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Novedades de Microsoft Defender para punto de conexión en Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Para obtener más información sobre Microsoft Defender para punto de conexión en otros sistemas operativos: 
- [Novedades de Microsoft Defender para punto de conexión en Linux](linux-whatsnew.md) 
- [Novedades de Microsoft Defender para punto de conexión en iOS](ios-whatsnew.md)</br>

<details>
  <summary>Jul-2022 (compilación: 101.73.77 | Versión de lanzamiento: 20.122062.17377.0)</summary>

&ensp;Fecha de lanzamiento: **21 de julio de 2022**<br/>
&ensp;Publicado: **21 de julio de 2022**<br/>
&ensp;Compilación: **101.73.77**<br/>
&ensp;Versión de lanzamiento: **20.122062.17377.0**<br/>
&ensp;Versión del motor: **1.1.19200.3**<br/>
&ensp;Versión de firma: **1.367.1011.0**<br/>

**Novedades**

- Se ha corregido un problema por el que la impresión no se pudo completar correctamente debido a la extensión de red.
- Se ha agregado una opción para [configurar el cálculo de hash de archivos](mac-preferences.md#configure-file-hash-computation-feature).
- A partir de esta compilación, el producto tendrá el nuevo motor antimalware de forma predeterminada.
- Mejoras de rendimiento para las operaciones de copia de archivos
- Correcciones de errores

<br/>
</details>

<details>
  <summary>Jul-2022 (compilación: 101.71.18 | Versión: 20.122052.17118.0)</summary>

&ensp;Fecha de lanzamiento: **7 de julio de 2022**<br/>
&ensp;Publicado: **7 de julio de 2022**<br/>
&ensp;Compilación: **101.71.18**<br/>
&ensp;Versión de lanzamiento: **20.122052.17118.0**<br/>

**Novedades**

- `mdatp connectivity test` se extendió con una dirección URL adicional que el producto requiere para funcionar correctamente. La nueva dirección URL es [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- Hasta ahora, el nivel de registro del producto no se conservaba entre los reinicios del producto. A partir de esta versión, hay un nuevo modificador de la herramienta de línea de comandos que conserva el nivel de registro. El nuevo comando es `mdatp log level persist --level <level>`.
- Se ha corregido un error en el paquete de instalación del producto que, en raras ocasiones, podía provocar una pérdida del estado del producto durante las actualizaciones.
- Mejoras de rendimiento para operaciones de copia de archivos y aplicaciones macOS integradas
- Correcciones de errores

<br/>
</details>

<details>
  <summary>Jun-2022 (compilación: 101.70.19 | Versión: 20.122051.17019.0)</summary>

&ensp;Fecha de lanzamiento: **14 de junio de 2022**<br/>
&ensp;Publicado: **14 de junio de 2022**<br/>
&ensp;Compilación: **101.70.19**<br/>
&ensp;Versión de lanzamiento: **20.122051.17019.0**<br/>

**Novedades**

- Se ha corregido un error que provocaba que las notificaciones relacionadas con amenazas no siempre se presentaran al usuario final.
- Mejoras de rendimiento & otras correcciones de errores

<br/>
</details>


<details>
  <summary>Jun-2022 (compilación: 101.70.18 | Versión: 20.122042.17018.0)</summary>

&ensp;Fecha de lanzamiento: **2 de junio de 2022**<br/>
&ensp;Publicado: **2 de junio de 2022**<br/>
&ensp;Compilación: **101.70.18**<br/>
&ensp;Versión de lanzamiento: **20.122042.17018.0**<br/>

**Novedades**

- Se ha corregido un error por el que el paquete de instalación a veces se bloqueaba indefinidamente durante las actualizaciones del producto.
- Se ha corregido un error por el que el producto a veces detectaba archivos incorrectamente dentro de la carpeta de cuarentena.
- Mejoras de rendimiento & otras correcciones de errores

<br/>
</details>

<details>
  <summary>Mayo de 2022 (compilación: 101.66.54 | Versión: 20.122041.16654.0) </summary>

&ensp;Fecha de lanzamiento: **11 de mayo de 2022**<br/>
&ensp;Publicado: **11 de mayo de 2022**<br/>
&ensp;Compilación: **101.66.54**<br/>
&ensp;Versión de lanzamiento: **20.122041.16654.0**<br/>


**Novedades**

- Se ha corregido un problema por `mdatp diagnostic real-time-protection-statistics` el que no se imprimía la ruta de acceso de proceso correcta en algunos casos.
- Correcciones de errores

<br/>
</details>

<details>
  <summary>Abril de 2022 (compilación: 101.64.15 | Versión: 20.122032.16415.0)</summary>

&ensp;Fecha de lanzamiento: **26 de abril de 2022**<br/>
&ensp;Publicado: **26 de abril de 2022**<br/>
&ensp;Compilación: **101.64.15**<br/>
&ensp;Versión de lanzamiento: **20.122032.16415.0**<br/>

**Novedades**

- Se ha corregido una regresión introducida en la versión 101.61.69 en la que el icono del menú de estado a veces mostraba un icono de error, aunque no se requería ninguna acción del usuario final.
- Se ha mejorado el `conflicting_applications` campo en `mdatp health` para mostrar solo los 10 procesos más recientes y también para incluir los nombres de los procesos. Esto facilita la identificación de los procesos que pueden entrar en conflicto con Microsoft Defender para punto de conexión para Mac.
- Se ha corregido un error en el `mdatp device-control removable-media policy list` que el identificador de proveedor y el identificador de producto se mostraban como decimales en lugar de hexadecimales.
- Mejoras de rendimiento & otras correcciones de errores

<br/>
</details>

<details>
  <summary>Mar-2022 (compilación: 101.61.69 | Versión de lanzamiento: 20.122022.16169.0) </summary>

&ensp;Fecha de lanzamiento: **25 de marzo de 2022**<br/>
&ensp;Publicado: **25 de marzo de 2022**<br/>
&ensp;Compilación: **101.61.69**<br/>
&ensp;Versión: **20.122022.16169.0**<br/>

**Novedades**

- Correcciones de errores

<br/>
</details>

<details>
  <summary>Mar-2022 (compilación: 101.60.91 | Versión: 20.122021.16091.0)</summary>

&ensp;Fecha de lanzamiento: **8 de marzo de 2022**<br/>
&ensp;Publicado: **8 de marzo de 2022**<br/>
&ensp;Compilación: **101.60.91**<br/>
&ensp;Versión: **20.122021.16091.0**<br/>

**Novedades**

- Esta versión contiene una actualización de seguridad para [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)

<br/>
</details>

<details>
  <summary>Febrero de 2022 (compilación: 101.59.50 | Versión de lanzamiento: 20.122021.15950.0) </summary>

&ensp;Fecha de publicación: **28 de febrero de 2022**<br/>
&ensp;Publicado: **28 de febrero de 2022**<br/>
&ensp;Compilación: **101.59.50**<br/>
&ensp;Versión: **20.122021.15950.0**<br/>

**Novedades**

- Esta versión agrega compatibilidad con macOS 12.3. A partir de macOS 12.3, [Apple está quitando Python 2.7](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes). No habrá ninguna versión de Python preinstalada en macOS de forma predeterminada. **ACCIÓN NECESARIA**: 
  - Los usuarios deben actualizar Microsoft Defender para punto de conexión para Mac a la versión 101.59.50 (o posterior) antes de actualizar sus dispositivos a macOS Monterey 12.3 (o posterior). Esta versión mínima 101.59.50 es un requisito previo para eliminar los problemas relacionados con Python con Microsoft Defender para punto de conexión para Mac en macOS Monterey.
  - En el caso de las implementaciones remotas, las configuraciones de MDM existentes deben actualizarse a Microsoft Defender para punto de conexión para Mac versión 101.59.50 (o posterior). La inserción a través de MDM de una versión anterior de Microsoft Defender para punto de conexión para Mac en macOS Monterey 12.3 (o posterior) provocará un error de instalación.

<br/>
</details>

<details>
  <summary>Febrero de 2022 (compilación: 101.59.10 | Versión: 20.122012.15910.0)</summary>

&ensp;Fecha de publicación: **22 de febrero de 2022**<br/>
&ensp;Publicado: **22 de febrero de 2022**<br/>
&ensp;Compilación: **101.59.10**<br/>
&ensp;Versión de lanzamiento: **20.122012.15910.0**<br/>

**Novedades**

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación distinta a la en la que se detectó originalmente el archivo. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Control de dispositivo extendido para controlar dispositivos conectados a través de Thunderbolt 3
- Se ha mejorado el control de las directivas de control de dispositivos que contienen identificadores de proveedor e identificadores de producto no válidos. Antes de esta versión, si la directiva contenía uno o varios identificadores no válidos, se omitió toda la directiva. A partir de esta versión, solo se omiten las partes no válidas de la directiva. Los problemas con la directiva se exponen a través de `mdatp device-control removable-media policy list`.
- Correcciones de errores

<br/>
</details>

<details>
  <summary>Febrero de 2022 (compilación: 101.56.62 | Versión de lanzamiento: 20.121122.15662.0)</summary>

&ensp;Fecha de publicación: **7 de febrero de 2022**<br/>
&ensp;Publicado: **7 de febrero de 2022**<br/>
&ensp;Compilación: **101.56.62**<br/>
&ensp;Versión de lanzamiento: **20.121122.15662.0**<br/>

**Novedades**

- Correcciones de errores 

<br/>
</details>

<details>
  <summary> Enero de 2022 (compilación: 101.56.35 | Versión de lanzamiento: 20.121121.15635.0)</summary>

&ensp;Fecha de publicación: **30 de enero de 2022**<br/>
&ensp;Publicado: **30 de enero de 2022**<br/>
&ensp;Compilación: **101.56.35**<br/>
&ensp;Versión de lanzamiento: **20.121121.15635.0**<br/>

**Novedades**

- Se ha cambiado el nombre de la aplicación de "ATP de Microsoft Defender" a "Microsoft Defender". Los usuarios finales observarán los siguientes cambios:
- La ruta de instalación de la aplicación se ha cambiado de `/Application/Microsoft Defender ATP.app` a `/Applications/Microsoft Defender.app`.
- Dentro de la experiencia del usuario, las apariciones de "ATP de Microsoft Defender" se han reemplazado por "Microsoft Defender"
- Se ha resuelto un problema por el que algunas aplicaciones VPN no se podían conectar debido al filtro de contenido de red que se distribuye con Microsoft Defender para punto de conexión para Mac
- Se ha corregido un problema detectado en macOS 12.2 beta 2 en el que no se pudo abrir el paquete de instalación debido a un cambio en el sistema operativo (SO) que impide la instalación de paquetes con ciertas características. Aunque parece que este cambio del sistema operativo no está incluido en la versión final de macOS 12.2, es probable que se vuelva a introducir en una versión futura de macOS. Por lo tanto, animamos a todos los administradores empresariales a actualizar el paquete de Microsoft Defender para punto de conexión en su consola de administración a esta versión del producto (o a una versión más reciente).
- Se ha corregido un problema detectado en algunos dispositivos M1 en los que el producto se bloqueaba con definiciones antimalware no válidas y no se podía actualizar correctamente a un conjunto de definiciones de trabajo.
- `mdatp health`la salida se ha ampliado con un atributo adicional llamado `full_disk_access_enabled` que se puede usar para determinar si se ha concedido el acceso completo al disco a todos los componentes de Microsoft Defender para punto de conexión para Mac.
- Mejoras de rendimiento & correcciones de errores

<br/>
</details>

<details>
  <summary>Enero de 2022 (compilación: 101.54.16 | Versión: 20.121111.15416.0) </summary>

&ensp;Fecha de publicación: **12 de enero de 2022**<br/>
&ensp;Publicado: **12 de enero de 2022**<br/>
&ensp;Compilación: **101.54.16**<br/>
&ensp;Versión: **20.121111.15416.0**<br/>

**Novedades**

- macOS 10.14 (Mojave) ya no se admite
- Una vez que el administrador deja de administrar una configuración de producto a través de MDM, ahora vuelve al valor que tenía antes de que se administrara (el valor configurado localmente por el usuario final o, si no se proporcionó explícitamente dicho valor local, el valor predeterminado usado por el producto). Antes de este cambio, después de que una configuración dejara de administrarse, el producto conservaba su valor administrado y lo seguía usando.
- Mejoras de rendimiento & correcciones de errores
    
<br/>
</details>

<details><summary>Versiones de 2021 </summary><blockquote>
    <details><summary>(Compilación: 101.49.25 | Versión de lanzamiento: 20.121092.14925.0)</summary>

&ensp;Build: **101.49.25**<br/>
&ensp;Versión: **20.121092.14925.0** <br/>

**Novedades**

- Se ha agregado un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de `mdatp config scan-archives --value [enabled/disabled]` . De forma predeterminada, se establece en habilitado. 
- Correcciones de errores  

<br/>
</details>
 
<details><summary>(Compilación: 101.47.27 | Versión de lanzamiento: 20.121082.14727.0)</summary>

&ensp;Build: **101.47.27**<br/>
&ensp;Versión: **20.121082.14727.0** <br/>

**Novedades**
- Corrección de una inmovilización del sistema que se produce al apagar macOS Mojave y macOS Catalina. 

<br/>
</details>

<details><summary>(Compilación: 101.43.84 | Versión: 20.121082.14384.0)</summary>

&ensp;Build: **101.43.84**<br/>
&ensp;Versión: **20.121082.14384.0** <br/>

**Novedades**
- Compilación candidata para macOS 12 (Monterey) 
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.41.10 | Versión: 20.121072.14110.0)</summary>

&ensp;Build: **101.41.10**<br/>
&ensp;Versión: **20.121072.14110.0** <br/>

**Novedades**
- Se han agregado nuevos modificadores a la herramienta de línea de comandos: 
    - Control del grado de paralelismo para los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]` . De forma predeterminada, se usa un grado de paralelismo de 2. 
    - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]` . De forma predeterminada, se establece en habilitado. 
- Cambiar el nivel de registro del producto ahora requiere elevación. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.40.84 | Versión de lanzamiento: 20.121071.14084.0)</summary>

&ensp;Build: **101.40.84**<br/>
&ensp;Versión: **20.121071.14084.0** <br/>

**Novedades**
- Compatibilidad nativa con chip M1 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.37.97 | Versión de lanzamiento: 20.121062.13797.0)</summary>

&ensp;Build: **101.37.97**<br/>
&ensp;Versión: **20.121062.13797.0** <br/>

**Novedades**
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.34.28 | Versión de lanzamiento: 20.121061.13428.0)</summary>

&ensp;Build: **101.34.28**<br/>
&ensp;Versión: **20.121061.13428.0** <br/>

**Novedades**
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.34.27 | Versión de lanzamiento: 20.121052.13427.0)</summary>

&ensp;Build: **101.34.27**<br/>
&ensp;Versión: **20.121052.13427.0** <br/>

**Novedades**
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.34.20 | Versión de lanzamiento: 20.121051.13420.0)</summary>

&ensp;Build: **101.34.20**<br/>
&ensp;Versión: **20.121051.13420.0** <br/>

**Novedades**
- [Control de dispositivo para macOS](mac-device-control-overview.md)  está ahora en disponibilidad general. 
- Se ha corregido un problema por el que no se podía iniciar un examen rápido desde el menú de estado en macOS 11 (Big Sur). 
- Otras correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.32.69 | Versión de lanzamiento: 20.121042.13269.0)</summary>

&ensp;Build: **101.32.69**<br/>
&ensp;Versión: **20.121042.13269.0** <br/>

**Novedades**
- Se ha corregido un problema por el que el acceso simultáneo a la cadena de claves desde Microsoft Defender para punto de conexión y otras aplicaciones puede provocar daños en la cadena de claves.

<br/>
</details>

<details><summary>(Compilación: 101.29.64 | Versión de lanzamiento: 20.121042.12964.0)</summary>

&ensp;Build: **101.29.64**<br/>
&ensp;Versión: **20.121042.12964.0** <br/> 

**Novedades**
- A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario todavía requieren una acción manual. 
- `mdatp diagnostic real-time-protection-statistics` ahora admite dos conmutadores adicionales: 
    - `--sort`: ordena la salida descendente por el número total de archivos examinados. 
    - `--top N`: muestra los N resultados principales (solo funciona si `--sort` también se especifica) 
- Mejoras de rendimiento (específicamente para cuando `YARN` se usa) & correcciones de errores

<br/>
</details>

<details><summary>(Compilación: 101.27.50 | Versión de lanzamiento: 20.121022.12750.0)</summary>

&ensp;Build: **101.27.50**<br/>
&ensp;Versión: **20.121022.12750.0** <br/> 

**Novedades**
- Corrección para adaptarse a la expiración del certificado de Apple para macOS Catalina y versiones anteriores. Esta corrección restaura la funcionalidad de administración de vulnerabilidades & amenazas (TVM).  

<br/>
</details>

<details><summary>(Compilación: 101.25.69 | Versión de lanzamiento: 20.121022.12569.0)</summary>

&ensp;Build: **101.25.69**<br/>
&ensp;Versión: **20.121022.12569.0** <br/> 

**Novedades**
- Microsoft Defender para punto de conexión en macOS ya está disponible en versión preliminar para los clientes del Gobierno de EE. UU. Para obtener más información, vea  [Microsoft Defender para punto de conexión para clientes del Gobierno de EE. UU](gov.md). . 
- Las mejoras de rendimiento (específicamente para la situación en la que se usa la aplicación XCode Simulator) & correcciones de errores. 

<br/>
</details>

<details><summary>(Compilación: 101.23.64 | Versión de lanzamiento: 20.121021.12364.0)</summary>

&ensp;Build: **101.23.64**<br/>
&ensp;Versión: **20.121021.12364.0** <br/> 

**Novedades**
- Se ha agregado una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus` . 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

</details>

<details><summary>Versiones anteriores </summary><blockquote>
<details><summary>(Compilación: 101.22.79 | Versión: 20.121012.12279.0)</summary>

&ensp;Compilación: **101.22.79** <br> &ensp;Versión de lanzamiento: **20.121012.12279.0**<br>

**Novedades**
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.19.88 | Versión de lanzamiento: 20.121011.11988.0)</summary>

&ensp;Build:**101.19.88**<br>
&ensp;Versión de lanzamiento: **20.121011.11988.0**<br>

**Novedades**
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.19.48 | Versión: 20.120121.11948.0)</summary>

&ensp;Compilación: **101.19.48**<br>
&ensp;Versión: **20.120121.11948.0**<br>

**Novedades**
> [!NOTE]
> La antigua sintaxis de la herramienta de línea de comandos ha quedado en desuso con esta versión. Para obtener información sobre la nueva sintaxis, vea [Recursos](mac-resources.md#configuring-from-the-command-line). 
- Se ha agregado un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable`. Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para punto de conexión en Mac. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.19.21 | Versión: 20.120101.11921.0)</summary>

&ensp;Compilación: **101.19.21**<br>
&ensp;Versión: **20.120101.11921.0** <br>

**Novedades**
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.15.26 | Versión: 20.120102.11526.0)</summary>

&ensp;Compilación: **101.15.26**<br>
&ensp;Versión: **20.120102.11526.0**<br>

**Novedades**
- Se ha mejorado la confiabilidad del agente cuando se ejecuta en macOS 11 Big Sur. 
- Se ha agregado un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones de AV durante exámenes personalizados (`mdatp scan custom`). 
- Mejoras de rendimiento & correcciones de errores

<br/> 
</details>

<details><summary>(Compilación: 101.13.75 | Versión: 20.120101.11375.0)</summary>

&ensp;Compilación: **101.13.75**<br>
&ensp;Versión: **20.120101.11375.0**<br>

**Novedades** 
- Se quitaron las condiciones cuando Microsoft Defender para punto de conexión desencadenaba un error de macOS 11 (Big Sur) que se manifiesta en un pánico del kernel. 
- Se ha corregido una pérdida de memoria en la extensión del sistema Endpoint Security al ejecutarse en mac 11 (Big Sur). 
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.10.72)</summary>

&ensp;Compilación: **101.10.72** <br>

**Novedades** 
- Correcciones de errores  

<br/>
</details>

<details><summary>(Compilación: 101.09.61)</summary>

&ensp;Compilación: **101.09.61**<br>

**Novedades** 
- Se ha agregado una nueva preferencia administrada para [deshabilitar la opción para enviar comentarios](mac-preferences.md#show--hide-option-to-send-feedback). 
- El icono del menú Estado ahora muestra un estado correcto cuando se administra la configuración del producto. Anteriormente, el icono del menú de estado mostraba un estado de advertencia o error, aunque el administrador administrase la configuración del producto. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.09.50)</summary>

&ensp;Compilación: **101.09.50**<br>

**Novedades** 
- Esta versión del producto se ha validado en macOS Big Sur 11 beta 9. 
- La nueva sintaxis de la herramienta de línea de comandos mdatp es ahora la predeterminada. Para obtener más información sobre la nueva sintaxis, consulte [Recursos para Microsoft Defender para punto de conexión en macOS](mac-resources.md#configuring-from-the-command-line). 
> [!NOTE]
> La antigua sintaxis de la herramienta de línea de comandos se quitará del producto el **1 de enero de 2021**.
- Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.09.49)</summary>

&ensp;Compilación: **101.09.49**<br>

**Novedades** 
- Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local. 
- Uso mejorado de LA CPU durante los exámenes a petición. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.07.23)</summary>

&ensp;Compilación: **101.07.23**<br>

**Novedades** 
- Se han agregado nuevos campos a la salida de `mdatp --health` para comprobar el estado del modo pasivo y el identificador de grupo EDR. 
> [!NOTE]
> `mdatp --health` se reemplazará por `mdatp health` en una actualización de producto futura. 
- Se ha corregido un error que provocaba que el envío automático de muestras no se marcase como administrado en la interfaz de usuario. 
- Se ha agregado una nueva configuración para controlar la retención de elementos en el historial de exámenes antivirus. Ahora puede [especificar el número de días para conservar elementos en el historial](mac-preferences.md#antivirus-scan-history-retention-in-days) de exámenes y [especificar el número máximo de elementos en el historial de exámenes](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history). 
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.06.63)</summary>

&ensp;Compilación: **101.06.63**<br>

**Novedades** 
- Se ha corregido una regresión de rendimiento introducida en la versión `101.05.17`. La regresión se introdujo con la corrección para eliminar el pánico del kernel que algunos clientes han observado al acceder a recursos compartidos SMB. Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los pánicos del kernel. 

<br/>
</details>

<details><summary>(Compilación: 101.05.17)</summary>

&ensp;Compilación: **101.05.17**<br> 

**Novedades** 
> [!IMPORTANT]
> Estamos trabajando en una sintaxis nueva y mejorada para la herramienta de línea `mdatp` de comandos. La nueva sintaxis es actualmente la predeterminada en los canales de actualización Insider Fast e Insider Slow. Le recomendamos que se famliliarize con esta nueva sintaxis. Seguiremos admitiendo la sintaxis antigua en paralelo con la nueva sintaxis y proporcionaremos más comunicación sobre el plan de desuso de la sintaxis antigua en los próximos meses. 
- Se ha corregido un pánico del kernel que a veces se producía al acceder a recursos compartidos de archivos SMB. 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.05.16)</summary>

&ensp;Compilación: **101.05.16**<br>

**Novedades** 
- Mejoras en la lógica de examen rápido para reducir significativamente el número de archivos escaneados. 
- Se ha agregado compatibilidad  con [la autocompletar](mac-resources.md#how-to-enable-autocompletion)para la herramienta de línea de comandos. 
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.03.12)</summary>

&ensp;Compilación: **101.03.12**<br>

**Novedades** 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.01.54)</summary>

&ensp;Compilación: **101.01.54**<br>

**Novedades** 
- Mejoras en la compatibilidad con Time Machine 
- Mejoras de accesibilidad 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 101.00.31)</summary>

&ensp;Compilación: **101.00.31** <br>

**Novedades** 
- Experiencia mejorada [de incorporación de productos para usuarios Intune](/mem/intune/apps/apps-advanced-threat-protection-macos) 
-  [Las exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)
- Se ha agregado la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS. Ahora puede hacer clic con el botón derecho en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para punto de conexión**. 
- Ahora el instalador no permite explícitamente las degradaciones de productos en contexto. Si necesita cambiar a una versión anterior, desinstale primero la versión existente y vuelva a configurar el dispositivo. 
- Otras mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.90.27)</summary>

&ensp;Compilación: **100.90.27** <br>   

**Novedades** 
- Ahora puede [establecer un canal](mac-updates.md#set-the-channel-name) de actualización para Microsoft Defender para punto de conexión en macOS que sea diferente del canal de actualización de todo el sistema. 
- Icono de nuevo producto 
- Otras mejoras de la experiencia del usuario 
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.86.92)</summary>

&ensp;Compilación: **100.86.92**<br>

**Novedades** 
- Mejoras en la compatibilidad con Time Machine 
- Se ha corregido un problema por el que el producto a veces no limpiaba todos los archivos de `/Library/Application Support/Microsoft/Defender` durante la desinstalación. 
- Se ha reducido el uso de CPU del producto cuando los productos de Microsoft se actualizan a través de Microsoft AutoUpdate. 
- Otras mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.86.91)</summary>

&ensp;Compilación: **100.86.91**<br>

**Novedades**
> [!CAUTION]
> Para garantizar la protección más completa para los dispositivos macOS y en consonancia con apple que detiene la entrega de actualizaciones de seguridad nativas de macOS a versiones del sistema operativo anteriores a [actual - 2], la implementación y las actualizaciones de MDATP para Mac ya no se admitirán en macOS Sierra [10.12]. Las actualizaciones y mejoras de MDATP para Mac se entregarán a los dispositivos que ejecutan las versiones Catalina [10.15], Mojave [10.14], y High Sierra [10.13].
>
> Si ya tiene MDATP para Mac implementado en los dispositivos Sierra [10.12], actualice a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.

-  Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.83.73)</summary>

&ensp;Compilación: **100.83.73**<br>

**Novedades**
- Se han agregado más controles para los administradores de TI en torno [a la administración de exclusiones](mac-preferences.md#exclusion-merge-policy),  [la administración de la configuración del tipo de amenaza](mac-preferences.md#threat-type-settings-merge-policy) y [las acciones de amenazas no permitidas](mac-preferences.md#disallowed-threat-actions). 
- Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado. 
- Mejoras de rendimiento & correcciones de errores
 
<br/>
</details>

<details><summary>(Compilación: 100.82.60)</summary>

&ensp;Compilación: **100.82.60** <br>

**Novedades**
- Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.

<br/> 
</details>

<details><summary>(Compilación: 100.80.42)</summary>

&ensp;Compilación: **100.80.42**<br>

**Novedades**
- Correcciones de errores

<br/> 
</details>

<details><summary>(Compilación: 100.79.42)</summary>

&ensp;Compilación: **100.79.42**<br>

**Novedades**
- Se ha corregido un problema que provocaba que Microsoft Defender para punto de conexión en Mac a veces interfiera con time machine. 
- Se ha agregado un nuevo modificador a la utilidad de línea de comandos para probar la conectividad con el servicio back-end.
 
  ```bash
  mdatp connectivity test
  ```
- Se ha agregado la capacidad de ver el historial completo de amenazas en la interfaz de usuario (se puede acceder a este desde la vista Historial   **de protección**). 
- Mejoras de rendimiento & correcciones de errores

<br/>
</details>

<details><summary>(Compilación: 100.72.15)</summary> 

&ensp;Compilación: **100.72.15**<br>

**Novedades**
- Correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.70.99)</summary> 

&ensp;Compilación: **100.70.99**<br>

**Novedades**
- Se ha corregido un problema que afectaba a la capacidad de algunos usuarios de actualizar a macOS Catalina cuando la protección en tiempo real está habilitada. Este problema esporádico se debe a Microsoft Defender para punto de conexión bloqueo de archivos dentro del paquete de actualización de Catalina al examinarlos en busca de amenazas, lo que produjo errores en la secuencia de actualización.

<br/>
</details> 

<details><summary>(Compilación: 100.68.99)</summary> 

&ensp;Compilación: **100.68.99**<br>

**Novedades**
- Se ha agregado la capacidad de configurar la funcionalidad del antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enforcement-level-for-antivirus-engine). 
- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<details><summary>(Compilación: 100.65.28)</summary> 

&ensp;Compilación: **100.65.28**<br>

**Novedades**
- Se ha agregado compatibilidad con macOS Catalina. 
> [!CAUTION]
> macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como documentos, descargas, escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para punto de conexión no puede proteger completamente el dispositivo.
> 
> El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para punto de conexión:
> 
> - Para las implementaciones manuales, consulte las instrucciones actualizadas en el [tema Implementación manual](mac-install-manually.md#how-to-allow-full-disk-access).
> - Para las implementaciones administradas, consulte las instrucciones actualizadas en los temas de implementación   [basada en JAMF](mac-install-with-jamf.md)y  [Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles) 

- Mejoras de rendimiento & correcciones de errores 

<br/>
</details>

<br/><br/>
</details>