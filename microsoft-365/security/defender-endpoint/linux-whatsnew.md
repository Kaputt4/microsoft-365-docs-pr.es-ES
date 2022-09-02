---
title: Novedades de Microsoft Defender para punto de conexión en Linux
description: Lista de cambios principales para Microsoft Defender para punto de conexión en Linux.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, linux, whatsnew, release
ms.service: microsoft-365-security
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
ms.subservice: mde
ms.openlocfilehash: 877cf9b7db508798a35cc99f8a163d0de0b91f37
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520849"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Novedades de Microsoft Defender para punto de conexión en Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Este artículo se actualiza con frecuencia para informarle de las novedades de las últimas versiones de Microsoft Defender para punto de conexión en Linux. 

- [Novedades de Defender para punto de conexión en macOS](mac-whatsnew.md)
- [Novedades de Defender para punto de conexión en iOS](ios-whatsnew.md)

<details>
  <summary>Ago-2022 (compilación: 101.75.43 | Versión de lanzamiento: 30.122071.17543.0)</summary>

&ensp;Fecha de lanzamiento: **2 de agosto de 2022**<br/>
&ensp;Publicado: **2 de agosto de 2022**<br/>
&ensp;Compilación: **101.75.43**<br/>
&ensp;Versión de lanzamiento: **30.122071.17543.0**<br/>
&ensp;Versión del motor: **1.1.19300.3**<br/>
&ensp;Versión de firma: **1.369.395.0**<br/>

**Novedades**

- Se ha agregado compatibilidad con Red Hat Enterprise Linux versión 9.0
- Se ha agregado un nuevo campo en la salida de `mdatp health` que se puede usar para consultar el nivel de cumplimiento de la característica de protección de red. Se llama al `network_protection_enforcement_level` nuevo campo y puede tomar uno de los siguientes valores: `audit`, `block`o `disabled`.
- Se ha corregido un error de producto en el que varias detecciones del mismo contenido podían dar lugar a entradas duplicadas en el historial de amenazas.
- Se ha corregido un problema por el que uno de los procesos generados por el producto (`mdatp_audisp_plugin`) a veces no se terminaba correctamente cuando se detuvo el servicio.
- Otras correcciones de errores
</br>

<br/><br/>
</details>

<details>
  <summary>Jul-2022 (compilación: 101.73.77 | Versión: 30.122062.17377.0)</summary>

&ensp;Fecha de lanzamiento: **21 de julio de 2022**<br/>
&ensp;Publicado: **21 de julio de 2022**<br/>
&ensp;Compilación: **101.73.77**<br/>
&ensp;Versión de lanzamiento: **30.122062.17377.0**<br/>
&ensp;Versión del motor: **1.1.19200.3**<br/>
&ensp;Versión de firma: **1.367.1011.0**<br/>


**Novedades**

- Se ha agregado una opción para [configurar el cálculo de hash de archivos](linux-preferences.md#configure-file-hash-computation-feature).
- A partir de esta compilación, el producto tendrá el nuevo motor antimalware de forma predeterminada.
- Mejoras de rendimiento para las operaciones de copia de archivos
- Correcciones de errores
</br>

<br/><br/>
</details>

<details>
  <summary>Jun-2022 (compilación: 101.71.18 | Versión de lanzamiento: 30.122052.17118.0)</summary>

&ensp;Fecha de lanzamiento: **24 de junio de 2022**<br/>
&ensp;Publicado: **24 de junio de 2022**<br/>
&ensp;Compilación: **101.71.18**<br/>
&ensp;Versión de lanzamiento: **30.122052.17118.0**<br/>


**Novedades**

- Corrección para admitir el almacenamiento de definiciones en ubicaciones no estándar (fuera de /var) para las actualizaciones de definiciones v2
- Se ha corregido un problema en el sensor de producto usado en RHEL 6 que podía provocar un bloqueo del sistema operativo.
- `mdatp connectivity test` se extendió con una dirección URL adicional que el producto requiere para funcionar correctamente. La nueva dirección URL es [https://go.microsoft.com/fwlink/?linkid=2144709](https://go.microsoft.com/fwlink/?linkid=2144709).
- Hasta ahora, el nivel de registro del producto no se conservaba entre los reinicios del producto. A partir de esta versión, hay un nuevo modificador de la herramienta de línea de comandos que conserva el nivel de registro. El nuevo comando es `mdatp log level persist --level <level>`.
- Se quitó la dependencia del `python` paquete de instalación del producto.
- Mejoras de rendimiento para las operaciones de copia de archivos y el procesamiento de eventos de red originados en `auditd`
- Correcciones de errores
</br>

<br/><br/>
</details>


<details>
  <summary>Mayo de 2022 (compilación: 101.68.80 | Versión de lanzamiento: 30.122042.16880.0)</summary>

&ensp;Fecha de lanzamiento: **23 de mayo de 2022**<br/>
&ensp;Publicado: **23 de mayo de 2022**<br/>
&ensp;Compilación: **101.68.80**<br/>
&ensp;Versión de lanzamiento: **30.122042.16880.0**<br/>

**Novedades** 

- Se ha agregado compatibilidad con la versión `2.6.32-754.47.1.el6.x86_64` del kernel cuando se ejecuta en RHEL 6.
- En RHEL 6, el producto ahora se puede instalar en dispositivos que ejecutan Unbreakable Enterprise Kernel (UEK)
- Se ha corregido un problema por el que el nombre del proceso a veces se mostraba incorrectamente como `unknown` cuando se ejecutaba `mdatp diagnostic real-time-protection-statistics`
- Se ha corregido un error por el que el producto a veces detectaba archivos incorrectamente dentro de la carpeta de cuarentena.
- Se ha corregido un problema por el que la `mdatp` herramienta de línea de comandos no funcionaba cuando `/opt` se montaba como un vínculo temporal.
- Mejoras de rendimiento & correcciones de errores
</br>

<br/><br/>
</details>

<details>
<summary>Mayo de 2022 (compilación: 101.65.77 | Versión: 30.122032.16577.0)</summary>

&ensp;Fecha de lanzamiento: **2 de mayo de 2022**<br/>
&ensp;Publicado: **2 de mayo de 2022**<br/>
&ensp;Compilación: **101.65.77**<br/>
&ensp;Versión de lanzamiento: **30.122032.16577.0**<br/>


**Novedades**

- Se ha mejorado el `conflicting_applications` campo en `mdatp health` para mostrar solo los 10 procesos más recientes y también para incluir los nombres de los procesos. Esto facilita la identificación de los procesos que pueden entrar en conflicto con Microsoft Defender para punto de conexión para Linux.
- Correcciones de errores


<br/><br/>
</details><details>
<summary>Mar-2022 (compilación: 101.62.74 | Versión: 30.122022.16274.0)</summary>

&ensp;Fecha de lanzamiento: **24 de marzo de 2022**<br/>
&ensp;Publicado: **24 de marzo de 2022**<br/>
&ensp;Compilación: **101.62.74**<br/>
&ensp;Versión de lanzamiento: **30.122022.16274.0**<br/>


**Novedades**

- Se ha corregido un problema por el que el producto bloqueaba incorrectamente el acceso a archivos de más de 2 GB al ejecutarse en versiones anteriores del kernel.
- Correcciones de errores


<br/><br/>
</details><details>
<summary>Mar-2022 (compilación: 101.60.93 | Versión: 30.122012.16093.0)</summary>

&ensp;Fecha de lanzamiento: **9 de marzo de 2022**<br/>
&ensp;Publicado: **9 de marzo de 2022**<br/>
&ensp;Compilación: **101.60.93**<br/>
&ensp;Versión de lanzamiento: **30.122012.16093.0**<br/>

**Novedades**

- Esta versión contiene una actualización de seguridad para [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)


<br/><br/>
</details><details>
<summary>Mar-2022 (compilación: 101.60.05 | Versión: 30.122012.16005.0)</summary>

&ensp;Fecha de lanzamiento: **3 de marzo de 2022**<br/>
&ensp;Publicado: **3 de marzo de 2022**<br/>
&ensp;Compilación: **101.60.05**<br/>
&ensp;Versión: **30.122012.16005.0**<br/>

**Novedades**

- Se ha agregado compatibilidad con la versión 2.6.32-754.43.1.el6.x86_64 del kernel para RHEL 6.10
- Correcciones de errores


<br/><br/>
</details><details>
<summary>Febrero de 2022 (compilación: 101.58.80 | Versión: 30.122012.15880.0)</summary>

&ensp;Fecha de publicación: **20 de febrero de 2022**<br/>
&ensp;Publicado: **20 de febrero de 2022**<br/>
&ensp;Compilación: **101.58.80**<br/>
&ensp;Versión: **30.122012.15880.0**<br/>

**Novedades**

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación distinta a la en la que se detectó originalmente el archivo. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- A partir de esta versión, la protección de red para Linux se puede evaluar a petición
- Correcciones de errores



<br/><br/>
</details><details>
<summary>Enero de 2022 (compilación: 101.56.62 | Versión de lanzamiento: 30.121122.15662.0)</summary>

&ensp;Fecha de publicación: **26 de enero de 2022**<br/>
&ensp;Publicado: **26 de enero de 2022**<br/>
&ensp;Compilación: **101.56.62**<br/>
&ensp;Versión de lanzamiento: **30.121122.15662.0**<br/>

**Novedades**

- Se ha corregido un bloqueo de producto introducido en la versión 101.53.02 y que ha afectado a varios clientes.


<br/><br/>
</details><details>
<summary>Enero de 2022 (compilación: 101.53.02 | Versión de lanzamiento: (30.121112.15302.0)</summary>

&ensp;Fecha de publicación: **8 de enero de 2022**<br/>
&ensp;Publicado: **8 de enero de 2022**<br/>
&ensp;Compilación: **101.53.02**<br/>
&ensp;Versión de lanzamiento: **30.121112.15302.0**<br/>

**Novedades**

- Mejoras de rendimiento & correcciones de errores



</details>

<details><summary> Versiones de 2021</summary><blockquote>
  <details><summary>(Compilación: 101.52.57 | Versión de lanzamiento: 30.121092.15257.0)</summary>
   
  <p><b> Compilación: 101.52.57 <br>
Versión de lanzamiento: 30.121092.15257.0</b></p>
   
  <p><b> Novedades </b></p>

   - Se ha agregado una funcionalidad para detectar los archivos JAR de log4j vulnerables que usan las aplicaciones Java. La máquina se inspecciona periódicamente para ejecutar procesos de Java con jars log4j cargados. La información se notifica al back-end Microsoft Defender para punto de conexión y se expone en el área Administración de vulnerabilidades del portal.
   
   </details>

  <details><summary>(Compilación: 101.47.76 | Versión de lanzamiento: 30.121092.14776.0)</summary>
   
  <p><b> Compilación: 101.47.76 <br>
Versión de lanzamiento: 30.121092.14776.0</b></p>
   
  <p><b>Novedades</b></p>

   - Se ha agregado un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de mdatp config scan-archives --value [enabled/disabled]. De forma predeterminada, se establece en habilitado.

   - Correcciones de errores

   </details>

   <details><summary>(Compilación: 101.45.13 | Versión de lanzamiento: 30.121082.14513.0)</summary>
   
  <p> 
  Compilación: <b>101.45.13 </b>  <br>
Versión de lanzamiento:<b> 30.121082.14513.0 </b></p>
   
  <p><b>Novedades</b></p>

  - A partir de esta versión, se ofrece compatibilidad con Microsoft Defender para punto de conexión a las siguientes distribuciones:

    - Versiones de RHEL6.7-6.10 y CentOS6.7-6.10.
    - Amazon Linux 2
    - Fedora 33 o superior

  - Correcciones de errores

   </details>


   <details><summary>(Compilación: 101.45.00 | Versión: 30.121072.14500.0)</summary>
   
   <p> 
   Compilación:<b> 101.45.00</b> <br>
Versión de lanzamiento: <b>30.121072.14500.0</b></p>
   
   <p><b>Novedades</b></p>
      

  - Se han agregado nuevos modificadores a la herramienta de línea de comandos:
    - Control del grado de paralelismo para los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`. De forma predeterminada, se usa un grado de paralelismo de `2` .
    - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
  - Cambiar el nivel de registro del producto ahora requiere elevación
  - Correcciones de errores

   </details>

   <details><summary>(Compilación: 101.39.98 | Versión: 30.121062.13998.0)</summary>
   
   <p> 
   Compilación: <b>101.39.98 </b><br>
Versión de lanzamiento: <b>30.121062.13998.0</b></p>
   
   <p><b>Novedades</b></p>

  - Mejoras de rendimiento & correcciones de errores
  
   </details>

   <details><summary>(Compilación: 101.34.27 | Versión de lanzamiento: 30.121052.13427.0)</summary>
   
   <p> 
   Compilación:<b> 101.34.27</b> <br>
Versión de lanzamiento: <b>30.121052.13427.0</b></p>
   
   <p><b>Novedades</b></p>

   - Mejoras de rendimiento & correcciones de errores
  
   </details>

   <details><summary>(Compilación: 101.29.64 | Versión: 30.121042.12964.0)</summary>
   
   <p> 
   Compilación:<b> 101.29.64 </b><br>
Versión de lanzamiento:<b> 30.121042.12964.0</b></p>
   
   <p><b>Novedades</b></p>

   - A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario todavía requieren una acción manual.
   - `mdatp diagnostic real-time-protection-statistics` ahora admite dos conmutadores adicionales:
     - `--sort`: ordena la salida descendente por el número total de archivos examinados.
     - `--top N`: muestra los N resultados principales (solo funciona si `--sort` también se especifica)
   - Mejoras de rendimiento & correcciones de errores
  
   </details>

   <details><summary>(Compilación: 101.25.72 | Versión de lanzamiento: 30.121022.12563.0)</summary>
   
   <p> 
   Compilación:<b> 101.25.72</b> <br>
Versión de lanzamiento: <b>30.121022.12563.0</b></p>
   
   <p><b>Novedades</b></p>

   - Microsoft Defender para punto de conexión en Linux ya está disponible en versión preliminar para los clientes del Gobierno de EE. UU. Para obtener más información, consulte [Microsoft Defender para punto de conexión para clientes del gobierno de EE. UU](gov.md).
   - Se ha corregido un problema por el que el uso de Microsoft Defender para punto de conexión en Linux en sistemas con sistemas de archivos FUSE provocaba que el sistema operativo se bloquease.
   - Mejoras de rendimiento & otras correcciones de errores
  
   </details>

   
   <details><summary>(Compilación: 101.25.63 | Versión de lanzamiento: 30.121022.12563.0)</summary>
   
   <p> 
   Compilación:<b> 101.25.63</b> <br>
Versión de lanzamiento: <b>30.121022.12563.0</b></p>
   
   <p><b>Novedades</b></p>

   - Mejoras de rendimiento & correcciones de errores
  
   </details>

   <details><summary>(Compilación: 101.23.64 | Versión: 30.121021.12364.0)</summary>
   
   <p>
Compilación:<b> 101.23.64 </b><br>
Versión: 30.121021.12364.0</b></p>
   
   <p><b>Novedades</b></p>

   - Mejora del rendimiento de la situación en la que se agrega un punto de montaje completo a la lista de exclusión del antivirus. Antes de esta versión, el producto seguía procesando la actividad de archivo que se originaba desde el punto de montaje. A partir de esta versión, se suprime la actividad de archivo de los puntos de montaje excluidos, lo que conduce a un mejor rendimiento del producto.
   - Se ha agregado una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`
   - Otras mejoras de rendimiento & correcciones de errores
  
   </details>

   <details><summary>(Compilación: 101.18.53)</summary>
   
    <p> 
    Compilación:<b> 101.18.53 </b><br>
        
    <p>Novedades</b></p>

   - EDR para Linux ya está [disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
   - Se ha agregado un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones de AV durante exámenes personalizados (`mdatp scan custom`)
   - Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente
    - Mejoras de rendimiento & correcciones de errores
    
   </details>





</blockquote></details>

