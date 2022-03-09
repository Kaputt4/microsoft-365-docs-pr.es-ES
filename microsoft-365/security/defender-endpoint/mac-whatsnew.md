---
title: Novedades de Microsoft Defender para Endpoint en Mac
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, installation, macos, whatsnew
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
ms.openlocfilehash: 80245af54aa6f7a3328515257fe6e6e73f0739b0
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401040"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Novedades de Microsoft Defender para Endpoint en Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="1016091-20122021160910"></a>101.60.91 (20.122021.16091.0)

- Esta versión contiene una actualización de seguridad [para CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/)

## <a name="1015950-20122021159500"></a>101.59.50 (20.122021.15950.0)

- Esta versión agrega compatibilidad con macOS 12.3. A partir de macOS 12.3, [Apple quita Python 2.7](https://developer.apple.com/documentation/macos-release-notes/macos-12_3-release-notes). No habrá ninguna versión de Python preinstalada en macOS de forma predeterminada. **ACCIÓN NECESARIA**: 
  - Los usuarios deben actualizar Microsoft Defender para Endpoint para Mac a la versión 101.59.50 (o posterior) antes de actualizar sus dispositivos a macOS Monterey 12.3 (o posterior). Esta versión mínima 101.59.50 es un requisito previo para eliminar problemas relacionados con Python con Microsoft Defender para Endpoint para Mac en macOS Monterey.
  - Para las implementaciones remotas, las configuraciones de MDM existentes deben actualizarse a Microsoft Defender para Endpoint para Mac versión 101.59.50 (o posterior). Al insertar a través de MDM una versión anterior de Microsoft Defender para Endpoint para Mac a macOS Monterey 12.3 (o posterior) provocará un error de instalación.

## <a name="1015910-20122012159100"></a>101.59.10 (20.122012.15910.0)

- La herramienta de línea de comandos ahora admite la restauración de archivos en cuarentena en una ubicación que no sea la que se detectó originalmente. Esto se puede hacer a través de `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- Control de dispositivo extendido para controlar dispositivos conectados a través de Thunderbolt 3
- Se ha mejorado el control de las directivas de control de dispositivos que contienen los IDs de proveedor y los IDs de producto no válidos. Antes de esta versión, si la directiva contenía uno o más IDs no válidos, se omitió toda la directiva. A partir de esta versión, solo se omiten las partes no válidas de la directiva. Los problemas con la directiva se han presentado a través de `mdatp device-control removable-media policy list`.
- Correcciones de errores

## <a name="1015662-20121122156620"></a>101.56.62 (20.121122.15662.0)

- Correcciones de errores

## <a name="1015635-20121121156350"></a>101.56.35 (20.121121.15635.0)

- Se ha cambiado el nombre de la aplicación de "Atp de Microsoft Defender" a "Microsoft Defender". Los usuarios finales observarán los siguientes cambios:
  - La ruta de instalación de la aplicación se ha cambiado de `/Application/Microsoft Defender ATP.app` a `/Applications/Microsoft Defender.app`.
  - Dentro de la experiencia del usuario, las repeticiones de "ATP de Microsoft Defender" se han reemplazado por "Microsoft Defender"
- Se ha resuelto un problema por el que algunas aplicaciones VPN no se podían conectar debido al filtro de contenido de red que se distribuye con Microsoft Defender para Endpoint para Mac
- Se ha corregido un problema detectado en macOS 12.2 beta 2 en el que el paquete de instalación no se podía abrir debido a un cambio en el sistema operativo (SO) que impide la instalación de paquetes con determinadas características. Aunque parece que este cambio del sistema operativo no se incluye en la versión final de macOS 12.2, es probable que se reintrodujo en una versión futura de macOS. Por lo tanto, animamos a todos los administradores empresariales a actualizar el paquete de Microsoft Defender para Endpoint en su consola de administración a esta versión del producto (o a una versión más reciente).
- Se ha corregido un problema visto en algunos dispositivos M1 en los que el producto estaba atascado con definiciones de antimalware no válidas y no se podía actualizar correctamente a un conjunto de definiciones de trabajo.
- `mdatp health` el resultado se ha extendido con un atributo adicional llamado que se puede usar para determinar si se ha concedido acceso en disco completo a `full_disk_access_enabled` todos los componentes de Microsoft Defender para Endpoint para Mac.
- Mejoras de rendimiento & correcciones de errores

## <a name="1015416-20121111154160"></a>101.54.16 (20.121111.15416.0)

- macOS 10.14 (Mojave) ya no es compatible
- Después de que el administrador deje de administrar una configuración de producto a través de MDM, ahora vuelve al valor que tenía antes de que se administrara (el valor configurado localmente por el usuario final o, si no se proporcionaba explícitamente dicho valor local, el valor predeterminado usado por el producto). Antes de este cambio, después de que una configuración dejara de administrarse, el valor administrado persistía y el producto aún lo usaba.
- Mejoras de rendimiento & correcciones de errores

## <a name="1014925-20121092149250"></a>101.49.25 (20.121092.14925.0)

- Se agregó un nuevo modificador a la herramienta de línea de comandos para controlar si los archivos se examinan durante los exámenes a petición. Esto se puede configurar a través de `mdatp config scan-archives --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Correcciones de errores

## <a name="1014727-20121082147270"></a>101.47.27 (20.121082.14727.0)

- Corrección de un bloqueo del sistema que se produce al apagar macOS Mojave y macOS Catalina

## <a name="1014384-20121082143840"></a>101.43.84 (20.121082.14384.0)

- Compilación candidata para macOS 12 (Monterrey)
- Correcciones de errores

## <a name="1014110-20121072141100"></a>101.41.10 (20.121072.14110.0)

- Se agregaron nuevos modificadores a la herramienta de línea de comandos:
  - Controlar el grado de paralelismo de los exámenes a petición. Esto se puede configurar a través de `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`. De forma predeterminada, se usa un grado de paralelismo `2` de.
  - Controlar si los exámenes después de las actualizaciones de inteligencia de seguridad están habilitados o deshabilitados. Esto se puede configurar a través de `mdatp config scan-after-definition-update --value [enabled/disabled]`. De forma predeterminada, se establece en `enabled`.
- Cambiar el nivel de registro de producto ahora requiere elevación
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

- [El control de dispositivos para macOS](mac-device-control-overview.md) ahora está en disponibilidad general
- Se ha corregido un problema por el que no se podía iniciar un examen rápido desde el menú de estado de macOS 11 (Big Sur)
- Otras correcciones de errores

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- Se ha corregido un problema por el que el acceso simultáneo a la cadena de teclas de Microsoft Defender para Endpoint y otras aplicaciones puede provocar daños en la cadena de teclas.

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente. Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario aún requieren una acción manual.
- `mdatp diagnostic real-time-protection-statistics` ahora admite dos modificadores adicionales:
  - `--sort`: ordena el resultado descendente por número total de archivos analizados
  - `--top N`: muestra los resultados N superiores (solo funciona si `--sort` también se especifica)
- Mejoras de rendimiento (específicamente para cuando se usa YARN) & correcciones de errores

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Corrección para dar cabida a la expiración del certificado de Apple para macOS Catalina y versiones anteriores. Esta corrección restaura la & de administración de vulnerabilidades (TVM).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender para Endpoint en macOS ya está disponible en versión preliminar para los clientes del Gobierno de Estados Unidos. Para obtener más información, vea [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Mejoras de rendimiento (específicamente para la situación en la que se usa la aplicación XCode Simulator) & correcciones de errores.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Se agregó una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición. Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`
- Mejoras de rendimiento & correcciones de errores

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Mejoras de rendimiento & correcciones de errores

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> La sintaxis de la herramienta de línea de comandos antigua ha quedado en desuso con esta versión. Para obtener información sobre la nueva sintaxis, vea [Resources](mac-resources.md#configuring-from-the-command-line).

- Se agregó un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable`. Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para Endpoint en Mac
- Mejoras de rendimiento & correcciones de errores

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Correcciones de errores

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Se mejoró la confiabilidad del agente al ejecutarse en macOS 11 Big Sur
- Se agregó un nuevo modificador de línea de comandos (`--ignore-exclusions`) para omitir las exclusiones av durante los exámenes personalizados (`mdatp scan custom`)
- Mejoras de rendimiento & correcciones de errores

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Se quitaron las condiciones cuando Microsoft Defender para endpoint desencadenaba un error de macOS 11 (Big Sur) que se manifestó en un estado de pánico del kernel
- Se ha corregido una pérdida de memoria en la extensión del sistema Endpoint Security cuando se ejecutaba en mac 11 (Big Sur)
- Correcciones de errores

## <a name="1011072"></a>101.10.72

- Correcciones de errores

## <a name="1010961"></a>101.09.61

- Se agregó una nueva preferencia administrada para [deshabilitar la opción para enviar comentarios](mac-preferences.md#show--hide-option-to-send-feedback)
- El icono del menú Estado ahora muestra un estado correcto cuando se administra la configuración del producto. Anteriormente, el icono del menú de estado mostraba un estado de advertencia o error, aunque la configuración del producto la administraba el administrador.
- Mejoras de rendimiento & correcciones de errores

## <a name="1010950"></a>101.09.50

- Esta versión del producto se validó en macOS Big Sur 11 beta 9

- La nueva sintaxis de la herramienta `mdatp` de línea de comandos es ahora la predeterminada. Para obtener más información sobre la nueva sintaxis, vea [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > La sintaxis de la herramienta de línea de comandos antigua se quitará del producto el 1 de enero **de 2021**.

- Extendido `mdatp diagnostic create` con un nuevo parámetro (`--path [directory]`) que permite guardar los registros de diagnóstico en un directorio diferente
- Mejoras de rendimiento & correcciones de errores

## <a name="1010949"></a>101.09.49

- Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local
- Uso mejorado de la CPU durante exámenes a petición
- Mejoras de rendimiento & correcciones de errores

## <a name="1010723"></a>101.07.23

- Se agregaron nuevos campos al resultado de `mdatp --health` para comprobar el estado del modo pasivo y el EDR de grupo

  > [!NOTE]
  > `mdatp --health` se reemplazará con en `mdatp health` una actualización futura del producto.

- Se ha corregido un error en el que el envío automático de muestra no estaba marcado como administrado en la interfaz de usuario
- Se agregó una nueva configuración para controlar la retención de elementos en el historial de análisis del antivirus. Ahora puede especificar [el número de días para](mac-preferences.md#antivirus-scan-history-retention-in-days) conservar elementos en el historial de análisis y especificar el [número máximo de elementos en el historial de examen](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Correcciones de errores

## <a name="1010663"></a>101.06.63

- Se ha abordado una regresión de rendimiento introducida en la versión `101.05.17`. La regresión se introdujo con la corrección para eliminar los problemas del kernel que algunos clientes han observado al acceder a recursos compartidos SMB. Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los problemas del kernel.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Estamos trabajando en una sintaxis nueva y mejorada para la herramienta `mdatp` de línea de comandos. La nueva sintaxis es actualmente la predeterminada en los canales de actualización rápida e interna lenta de Insider. Le recomendamos que se famliliarize con esta nueva sintaxis.
>
> Seguiremos dando soporte a la sintaxis antigua en paralelo con la nueva sintaxis y proporcionaremos más comunicación en torno al plan de desuso de la sintaxis antigua en los próximos meses.

- Se ha solucionado un problema de kernel que se produjo a veces al acceder a recursos compartidos de archivos SMB
- Mejoras de rendimiento & correcciones de errores

## <a name="1010516"></a>101.05.16

- Mejoras en la lógica de examen rápido para reducir significativamente el número de archivos analizados
- Se [agregó compatibilidad de autocompletion](mac-resources.md#how-to-enable-autocompletion) para la herramienta de línea de comandos
- Correcciones de errores

## <a name="1010312"></a>101.03.12

- Mejoras de rendimiento & correcciones de errores

## <a name="1010154"></a>101.01.54

- Mejoras en la compatibilidad con Time Machine
- Mejoras de accesibilidad
- Mejoras de rendimiento & correcciones de errores

## <a name="1010031"></a>101.00.31

- Experiencia de [incorporación de productos mejorada para usuarios de Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)
- Las [exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)
- Se agregó la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS. Ahora puedes hacer clic con el botón secundario en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para endpoint**
- Las degradaciones de productos locales ahora son explícitamente no permitidos por el instalador. Si necesita degradar, desinstale primero la versión existente y vuelva a configurar el dispositivo
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1009027"></a>100.90.27

- Ahora puede establecer [un canal de](mac-updates.md#set-the-channel-name) actualización para Microsoft Defender para Endpoint en macOS que sea diferente del canal de actualización de todo el sistema
- Icono de nuevo producto
- Otras mejoras en la experiencia del usuario
- Correcciones de errores

## <a name="1008692"></a>100.86.92

- Mejoras en la compatibilidad con Time Machine
- Se ha corregido un problema en el que el producto a veces no limpiaba todos los archivos durante `/Library/Application Support/Microsoft/Defender` la desinstalación
- Se ha reducido el uso de cpu del producto cuando los productos de Microsoft se actualizan a través de Microsoft AutoUpdate
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Para garantizar la protección más completa para los dispositivos macOS y en alineación con apple que detenga la entrega de actualizaciones de seguridad nativas de macOS en versiones del sistema operativo anteriores a [actual - 2], la implementación y las actualizaciones de MDATP para Mac ya no se admiten en macOS Sierra [10.12]. Las actualizaciones y mejoras de MDATP para Mac se entregarán a dispositivos que ejecutan versiones de Catalina [10.15], Mojave [10.14] y High Sierra [10.13].
>
> Si ya tienes MDATP para Mac implementado en tus dispositivos Sierra [10.12], actualiza a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.

- Mejoras de rendimiento & correcciones de errores

## <a name="1008373"></a>100.83.73

- Se agregaron más controles para los administradores de TI en torno a la administración de [exclusiones](mac-preferences.md#exclusion-merge-policy)[, la](mac-preferences.md#threat-type-settings-merge-policy) administración de la configuración del tipo de amenaza y las [acciones de amenazas no permitidos](mac-preferences.md#disallowed-threat-actions)
- Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado
- Mejoras de rendimiento & correcciones de errores

## <a name="1008260"></a>100.82.60

- Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.

## <a name="1008042"></a>100.80.42

- Correcciones de errores

## <a name="1007942"></a>100.79.42

- Se ha corregido un problema por el que Microsoft Defender para Endpoint en Mac a veces interfiría con time machine
- Se agregó un nuevo modificador a la utilidad de línea de comandos para probar la conectividad con el servicio back-end

  ```bash
  mdatp connectivity test
  ```

- Se agregó la capacidad de ver el historial completo de amenazas en la interfaz de usuario (se puede obtener acceso desde la **vista Historial de** protección)
- Mejoras de rendimiento & correcciones de errores

## <a name="1007215"></a>100.72.15

- Correcciones de errores

## <a name="1007099"></a>100.70.99

- Se ha corregido un problema que afectaba a la capacidad de algunos usuarios de actualizar a macOS Catalina cuando la protección en tiempo real está habilitada. Este problema esporádico se debe a que Microsoft Defender para los archivos de bloqueo de extremo dentro del paquete de actualización de Catalina al analizarlos en busca de amenazas, lo que provocó errores en la secuencia de actualización.

## <a name="1006899"></a>100.68.99

- Se agregó la capacidad de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enforcement-level-for-antivirus-engine)
- Mejoras de rendimiento & correcciones de errores

## <a name="1006528"></a>100.65.28

- Se agregó compatibilidad con macOS Catalina

  > [!CAUTION]
  > macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.
  >
  > El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para endpoint:
  >
  > - Para las implementaciones manuales, vea las instrucciones actualizadas en el [tema Implementación](mac-install-manually.md#how-to-allow-full-disk-access) manual.
  > - Para las implementaciones administradas, vea las instrucciones actualizadas en los temas de implementación basada en JAMF [y Microsoft Intune de implementación basada en](mac-install-with-intune.md#create-system-configuration-profiles) [JAMF](mac-install-with-jamf.md).

- Mejoras de rendimiento & correcciones de errores
