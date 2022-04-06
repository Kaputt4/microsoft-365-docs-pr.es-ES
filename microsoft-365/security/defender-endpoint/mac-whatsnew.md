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
ms.openlocfilehash: d36d05a4abe36ffe63e53eb8e164e248755de0ec
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665918"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Novedades de Microsoft Defender para punto de conexión en Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="1016169-20122022161690"></a>101.61.69 (20.122022.16169.0)

- Correcciones de errores

## <a name="1016091-20122021160910"></a>101.60.91 (20.122021.16091.0)

- Esta versión contiene una actualización de seguridad para [CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)

## <a name="1015950-20122021159500"></a>101.59.50 (20.122021.15950.0)

- Esta versión agrega compatibilidad con macOS 12.3. A partir de macOS 12.3, [Apple está quitando Python 2.7](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes). No habrá ninguna versión de Python preinstalada en macOS de forma predeterminada. **ACCIÓN NECESARIA**: 
  - Los usuarios deben actualizar Microsoft Defender para punto de conexión para Mac a la versión 101.59.50 (o posterior) antes de actualizar sus dispositivos a macOS Monterey 12.3 (o posterior). Esta versión mínima 101.59.50 es un requisito previo para eliminar los problemas relacionados con Python con Microsoft Defender para punto de conexión para Mac en macOS Monterey.
  - En el caso de las implementaciones remotas, las configuraciones de MDM existentes deben actualizarse a Microsoft Defender para punto de conexión para Mac versión 101.59.50 (o posterior). La inserción a través de MDM de una versión anterior de Microsoft Defender para punto de conexión para Mac en macOS Monterey 12.3 (o posterior) provocará un error de instalación.

## <a name="1015910-20122012159100"></a>101.59.10 (20.122012.15910.0)

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación distinta a la en la que se detectó originalmente el archivo. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Control de dispositivo extendido para controlar dispositivos conectados a través de Thunderbolt 3
- Se ha mejorado el control de las directivas de control de dispositivos que contienen identificadores de proveedor e identificadores de producto no válidos. Antes de esta versión, si la directiva contenía uno o varios identificadores no válidos, se omitió toda la directiva. A partir de esta versión, solo se omiten las partes no válidas de la directiva. Los problemas con la directiva se exponen a través de `mdatp device-control removable-media policy list`.
- Correcciones de errores

## <a name="1015662-20121122156620"></a>101.56.62 (20.121122.15662.0)

- Correcciones de errores

## <a name="1015635-20121121156350"></a>101.56.35 (20.121121.15635.0)

- Se ha cambiado el nombre de la aplicación de "ATP de Microsoft Defender" a "Microsoft Defender". Los usuarios finales observarán los siguientes cambios:
  - La ruta de instalación de la aplicación se ha cambiado de `/Application/Microsoft Defender ATP.app` a `/Applications/Microsoft Defender.app`.
  - Dentro de la experiencia del usuario, las apariciones de "ATP de Microsoft Defender" se han reemplazado por "Microsoft Defender"
- Se ha resuelto un problema por el que algunas aplicaciones VPN no se podían conectar debido al filtro de contenido de red que se distribuye con Microsoft Defender para punto de conexión para Mac
- Se ha corregido un problema detectado en macOS 12.2 beta 2 en el que no se pudo abrir el paquete de instalación debido a un cambio en el sistema operativo (SO) que impide la instalación de paquetes con ciertas características. Aunque parece que este cambio del sistema operativo no está incluido en la versión final de macOS 12.2, es probable que se vuelva a introducir en una versión futura de macOS. Por lo tanto, animamos a todos los administradores empresariales a actualizar el paquete de Microsoft Defender para punto de conexión en su consola de administración a esta versión del producto (o a una versión más reciente).
- Se ha corregido un problema detectado en algunos dispositivos M1 en los que el producto se bloqueaba con definiciones antimalware no válidas y no se podía actualizar correctamente a un conjunto de definiciones de trabajo.
- `mdatp health`la salida se ha ampliado con un atributo adicional llamado `full_disk_access_enabled` que se puede usar para determinar si se ha concedido el acceso completo al disco a todos los componentes de Microsoft Defender para punto de conexión para Mac.
- Mejoras de rendimiento & correcciones de errores

## <a name="1015416-20121111154160"></a>101.54.16 (20.121111.15416.0)

- macOS 10.14 (Mojave) ya no se admite
- Una vez que el administrador deja de administrar una configuración de producto a través de MDM, ahora vuelve al valor que tenía antes de que se administrara (el valor configurado localmente por el usuario final o, si no se proporcionó explícitamente dicho valor local, el valor predeterminado usado por el producto). Antes de este cambio, después de que una configuración dejara de administrarse, el producto conservaba su valor administrado y lo seguía usando.
- Mejoras de rendimiento & correcciones de errores

## <a name="1014925-20121092149250"></a>101.49.25 (20.121092.14925.0)

- Se ha agregado un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de `mdatp config scan-archives --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Correcciones de errores

## <a name="1014727-20121082147270"></a>101.47.27 (20.121082.14727.0)

- Corrección de una inmovilización del sistema que se produce al apagar macOS Mojave y macOS Catalina

## <a name="1014384-20121082143840"></a>101.43.84 (20.121082.14384.0)

- Compilación candidata para macOS 12 (Monterey)
- Correcciones de errores

## <a name="1014110-20121072141100"></a>101.41.10 (20.121072.14110.0)

- Se han agregado nuevos modificadores a la herramienta de línea de comandos:
  - Control del grado de paralelismo para los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`. De forma predeterminada, se usa un grado de paralelismo de `2` .
  - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Cambiar el nivel de registro del producto ahora requiere elevación
- Mejoras de rendimiento & correcciones de errores

## <a name="1014084-20121071140840"></a>101.40.84 (20.121071.14084.0)

- Compatibilidad nativa con chip M1
- Mejoras de rendimiento & correcciones de errores

## <a name="1013797-20121062137970"></a>101.37.97 (20.121062.13797.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1013428-20121061134280"></a>101.34.28 (20.121061.13428.0)

- Correcciones de errores

## <a name="1013427-20121052134270"></a>101.34.27 (20.121052.13427.0)

- Correcciones de errores

## <a name="1013420-20121051134200"></a>101.34.20 (20.121051.13420.0)

- [El control de dispositivo para macOS](mac-device-control-overview.md) está ahora en disponibilidad general
- Se ha corregido un problema por el que no se podía iniciar un examen rápido desde el menú de estado en macOS 11 (Big Sur)
- Otras correcciones de errores

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- Se ha corregido un problema por el que el acceso simultáneo a la cadena de claves desde Microsoft Defender para punto de conexión y otras aplicaciones puede provocar daños en la cadena de claves.

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario todavía requieren una acción manual.
- `mdatp diagnostic real-time-protection-statistics` ahora admite dos conmutadores adicionales:
  - `--sort`: ordena la salida descendente por el número total de archivos examinados.
  - `--top N`: muestra los N resultados principales (solo funciona si `--sort` también se especifica)
- Mejoras de rendimiento (específicamente para cuando se usa YARN) & correcciones de errores

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Corrección para adaptarse a la expiración del certificado de Apple para macOS Catalina y versiones anteriores. Esta corrección restaura la funcionalidad de administración de vulnerabilidades & amenazas (TVM).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender para punto de conexión en macOS ya está disponible en versión preliminar para los clientes del Gobierno de EE. UU. Para obtener más información, consulte [Microsoft Defender para punto de conexión para clientes del gobierno de EE. UU](gov.md).
- Las mejoras de rendimiento (específicamente para la situación en la que se usa la aplicación XCode Simulator) & correcciones de errores.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Se ha agregado una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`
- Mejoras de rendimiento & correcciones de errores

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> La antigua sintaxis de la herramienta de línea de comandos ha quedado en desuso con esta versión. Para obtener información sobre la nueva sintaxis, vea [Recursos](mac-resources.md#configuring-from-the-command-line).

- Se ha agregado un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable`. Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para punto de conexión en Mac
- Mejoras de rendimiento & correcciones de errores

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Correcciones de errores

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Se ha mejorado la confiabilidad del agente cuando se ejecuta en macOS 11 Big Sur
- Se ha agregado un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones de AV durante exámenes personalizados (`mdatp scan custom`)
- Mejoras de rendimiento & correcciones de errores

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Se quitaron las condiciones cuando Microsoft Defender para punto de conexión desencadenaba un error de macOS 11 (Big Sur) que se manifiesta en un pánico del kernel.
- Se ha corregido una pérdida de memoria en la extensión del sistema endpoint Security al ejecutarse en mac 11 (Big Sur)
- Correcciones de errores

## <a name="1011072"></a>101.10.72

- Correcciones de errores

## <a name="1010961"></a>101.09.61

- Se ha agregado una nueva preferencia administrada para [deshabilitar la opción de enviar comentarios](mac-preferences.md#show--hide-option-to-send-feedback).
- El icono del menú Estado ahora muestra un estado correcto cuando se administra la configuración del producto. Anteriormente, el icono del menú de estado mostraba un estado de advertencia o error, aunque el administrador administrase la configuración del producto.
- Mejoras de rendimiento & correcciones de errores

## <a name="1010950"></a>101.09.50

- Esta versión del producto se ha validado en macOS Big Sur 11 beta 9

- La nueva sintaxis de la `mdatp` herramienta de línea de comandos es ahora la predeterminada. Para obtener más información sobre la nueva sintaxis, consulte [Recursos para Microsoft Defender para punto de conexión en macOS](mac-resources.md#configuring-from-the-command-line).

  > [!NOTE]
  > La antigua sintaxis de la herramienta de línea de comandos se quitará del producto el **1 de enero de 2021**.

- Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente
- Mejoras de rendimiento & correcciones de errores

## <a name="1010949"></a>101.09.49

- Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local
- Uso mejorado de LA CPU durante los exámenes a petición
- Mejoras de rendimiento & correcciones de errores

## <a name="1010723"></a>101.07.23

- Se han agregado nuevos campos a la salida de `mdatp --health` para comprobar el estado del modo pasivo y el identificador de grupo EDR

  > [!NOTE]
  > `mdatp --health` se reemplazará por `mdatp health` en una actualización de producto futura.

- Se ha corregido un error que provocaba que el envío automático de muestras no se marcase como administrado en la interfaz de usuario.
- Se ha agregado una nueva configuración para controlar la retención de elementos en el historial de exámenes antivirus. Ahora puede [especificar el número de días para conservar elementos en el historial de exámenes](mac-preferences.md#antivirus-scan-history-retention-in-days) y [especificar el número máximo de elementos en el historial de exámenes](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history).
- Correcciones de errores

## <a name="1010663"></a>101.06.63

- Se ha corregido una regresión de rendimiento introducida en la versión `101.05.17`. La regresión se introdujo con la corrección para eliminar el pánico del kernel que algunos clientes han observado al acceder a recursos compartidos SMB. Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los pánicos del kernel.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Estamos trabajando en una sintaxis nueva y mejorada para la herramienta de línea `mdatp` de comandos. La nueva sintaxis es actualmente la predeterminada en los canales de actualización Insider Fast e Insider Slow. Le recomendamos que se famliliarize con esta nueva sintaxis.
>
> Seguiremos admitiendo la sintaxis antigua en paralelo con la nueva sintaxis y proporcionaremos más comunicación sobre el plan de desuso de la sintaxis antigua en los próximos meses.

- Se ha corregido un pánico del kernel que a veces se producía al acceder a recursos compartidos de archivos SMB
- Mejoras de rendimiento & correcciones de errores

## <a name="1010516"></a>101.05.16

- Mejoras en la lógica de examen rápido para reducir significativamente el número de archivos escaneados
- Se ha agregado [compatibilidad con la autocompletar](mac-resources.md#how-to-enable-autocompletion) para la herramienta de línea de comandos.
- Correcciones de errores

## <a name="1010312"></a>101.03.12

- Mejoras de rendimiento & correcciones de errores

## <a name="1010154"></a>101.01.54

- Mejoras en la compatibilidad con Time Machine
- Mejoras de accesibilidad
- Mejoras de rendimiento & correcciones de errores

## <a name="1010031"></a>101.00.31

- Experiencia [mejorada de incorporación de productos para usuarios Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)
- [Las exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)
- Se ha agregado la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS. Ahora puede hacer clic con el botón derecho en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para punto de conexión**
- Ahora el instalador no permite explícitamente las degradaciones de productos en contexto. Si necesita cambiar a una versión anterior, desinstale primero la versión existente y vuelva a configurar el dispositivo.
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1009027"></a>100.90.27

- Ahora puede [establecer un canal de actualización](mac-updates.md#set-the-channel-name) para Microsoft Defender para punto de conexión en macOS que sea diferente del canal de actualización de todo el sistema.
- Icono de nuevo producto
- Otras mejoras de la experiencia del usuario
- Correcciones de errores

## <a name="1008692"></a>100.86.92

- Mejoras en la compatibilidad con Time Machine
- Se ha corregido un problema por el que el producto a veces no limpiaba todos los archivos en `/Library/Application Support/Microsoft/Defender` durante la desinstalación.
- Se ha reducido el uso de CPU del producto cuando los productos de Microsoft se actualizan a través de Microsoft AutoUpdate
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Para garantizar la protección más completa para los dispositivos macOS y en consonancia con apple que detiene la entrega de actualizaciones de seguridad nativas de macOS a versiones del sistema operativo anteriores a [actual - 2], la implementación y las actualizaciones de MDATP para Mac ya no se admitirán en macOS Sierra [10.12]. Las actualizaciones y mejoras de MDATP para Mac se entregarán a los dispositivos que ejecutan las versiones Catalina [10.15], Mojave [10.14], y High Sierra [10.13].
>
> Si ya tiene MDATP para Mac implementado en los dispositivos Sierra [10.12], actualice a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.

- Mejoras de rendimiento & correcciones de errores

## <a name="1008373"></a>100.83.73

- Se han agregado más controles para los administradores de TI en torno [a la administración de exclusiones](mac-preferences.md#exclusion-merge-policy), [la administración de la configuración del tipo de amenaza](mac-preferences.md#threat-type-settings-merge-policy) y [las acciones de amenaza no permitidas](mac-preferences.md#disallowed-threat-actions).
- Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado.
- Mejoras de rendimiento & correcciones de errores

## <a name="1008260"></a>100.82.60

- Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.

## <a name="1008042"></a>100.80.42

- Correcciones de errores

## <a name="1007942"></a>100.79.42

- Se ha corregido un problema que provocaba que Microsoft Defender para punto de conexión en Mac a veces interfiera con time machine.
- Se ha agregado un nuevo modificador a la utilidad de línea de comandos para probar la conectividad con el servicio back-end.

  ```bash
  mdatp connectivity test
  ```

- Se ha agregado la capacidad de ver el historial completo de amenazas en la interfaz de usuario (se puede acceder a este desde la vista **Historial de protección** )
- Mejoras de rendimiento & correcciones de errores

## <a name="1007215"></a>100.72.15

- Correcciones de errores

## <a name="1007099"></a>100.70.99

- Se ha corregido un problema que afectaba a la capacidad de algunos usuarios de actualizar a macOS Catalina cuando la protección en tiempo real está habilitada. Este problema esporádico se debe a Microsoft Defender para punto de conexión bloqueo de archivos dentro del paquete de actualización de Catalina al examinarlos en busca de amenazas, lo que produjo errores en la secuencia de actualización.

## <a name="1006899"></a>100.68.99

- Se ha agregado la capacidad de configurar la funcionalidad del antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enforcement-level-for-antivirus-engine).
- Mejoras de rendimiento & correcciones de errores

## <a name="1006528"></a>100.65.28

- Se ha agregado compatibilidad con macOS Catalina

  > [!CAUTION]
  > macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como documentos, descargas, escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para punto de conexión no puede proteger completamente el dispositivo.
  >
  > El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para punto de conexión:
  >
  > - Para las implementaciones manuales, consulte las instrucciones actualizadas en el tema [Implementación manual](mac-install-manually.md#how-to-allow-full-disk-access) .
  > - Para las implementaciones administradas, consulte las instrucciones actualizadas en los temas de [implementación basada en JAMF](mac-install-with-jamf.md) y [implementación basada en Microsoft Intune](mac-install-with-intune.md#create-system-configuration-profiles).

- Mejoras de rendimiento & correcciones de errores
