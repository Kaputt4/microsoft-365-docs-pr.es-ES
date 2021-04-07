---
title: Novedades de Microsoft Defender para Endpoint para Mac
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para Endpoint para Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cd1f64d006b5462634dd47df9083e1a89db0e8c
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615224"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a>Novedades de Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> En macOS 11 (Big Sur), Microsoft Defender para Endpoint requiere perfiles de configuración adicionales. Si es un cliente existente que actualiza desde versiones anteriores de macOS, asegúrese de implementar los perfiles de configuración adicionales enumerados en [esta página](mac-sysext-policies.md).

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender para Endpoint para Mac ya está disponible en versión preliminar para los clientes de US Government. Para obtener más información, vea [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Mejoras de rendimiento (específicamente para la situación en la que se usa la aplicación XCode Simulator) & correcciones de errores

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

- Se agregó un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable` . Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para Endpoint para Mac
- Mejoras de rendimiento & correcciones de errores

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Correcciones de errores

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Se mejoró la confiabilidad del agente al ejecutarse en macOS 11 Big Sur
- Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )
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

- La nueva sintaxis de la `mdatp` herramienta de línea de comandos es ahora la predeterminada. Para obtener más información sobre la nueva sintaxis, vea [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > La sintaxis de la herramienta de línea de comandos antigua se quitará del producto el 1 de enero **de 2021**.

- Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente
- Mejoras de rendimiento & correcciones de errores

## <a name="1010949"></a>101.09.49

- Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local
- Uso mejorado de la CPU durante exámenes a petición
- Mejoras de rendimiento & correcciones de errores

## <a name="1010723"></a>101.07.23

- Se agregaron nuevos campos a la salida de para comprobar el estado del modo pasivo y el id. `mdatp --health` de grupo de EDR

  > [!NOTE]
  > `mdatp --health` se reemplazará con `mdatp health` en una actualización futura del producto.

- Se ha corregido un error en el que el envío automático de muestra no estaba marcado como administrado en la interfaz de usuario
- Se agregó una nueva configuración para controlar la retención de elementos en el historial de análisis del antivirus. Ahora puede especificar [el número de días para](mac-preferences.md#antivirus-scan-history-retention-in-days) conservar elementos en el historial de análisis y especificar el número máximo de elementos en el historial de [examen](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Correcciones de errores

## <a name="1010663"></a>101.06.63

- Se ha abordado una regresión de rendimiento introducida en la versión `101.05.17` . La regresión se introdujo con la corrección para eliminar los problemas del kernel que algunos clientes han observado al acceder a recursos compartidos SMB. Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los problemas del kernel.

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

- Experiencia de [incorporación de productos mejorada para usuarios de Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)
- Las [exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)
- Se agregó la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS. Ahora puedes hacer clic con el botón secundario en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para endpoint**
- Las degradaciones de productos locales ahora son explícitamente no permitidos por el instalador. Si necesita degradar, desinstale primero la versión existente y vuelva a configurar el dispositivo
- Otras mejoras de rendimiento & correcciones de errores

## <a name="1009027"></a>100.90.27

- Ahora puedes establecer [un canal](mac-updates.md#set-the-channel-name) de actualización para Microsoft Defender para Endpoint para Mac que sea diferente del canal de actualización de todo el sistema
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
> Para garantizar la protección más completa para los dispositivos macOS y en línea con que Apple detenga la entrega de actualizaciones de seguridad nativas de macOS en versiones del sistema operativo anteriores a [actual – 2], la implementación y las actualizaciones de MDATP para Mac ya no se admiten en macOS Sierra [10.12]. Las actualizaciones y mejoras de MDATP para Mac se entregarán a dispositivos que ejecutan versiones de Catalina [10.15], Mojave [10.14] y High Sierra [10.13]. 
>
> Si ya tienes MDATP para Mac implementado en tus dispositivos Sierra [10.12], actualiza a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.

- Mejoras de rendimiento & correcciones de errores

## <a name="1008373"></a>100.83.73

- Se agregaron más controles para los administradores de TI en torno a la administración de [exclusiones,](mac-preferences.md#exclusion-merge-policy)la [administración](mac-preferences.md#threat-type-settings-merge-policy)de la configuración del tipo de amenaza y las [acciones de amenazas no permitidos](mac-preferences.md#disallowed-threat-actions)
- Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado
- Mejoras de rendimiento & correcciones de errores

## <a name="1008260"></a>100.82.60

- Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.

## <a name="1008042"></a>100.80.42

- Correcciones de errores

## <a name="1007942"></a>100.79.42

- Se ha corregido un problema por el que Microsoft Defender para Endpoint para Mac a veces interfiría con time machine
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

- Se agregó la capacidad de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enable--disable-passive-mode)
- Mejoras de rendimiento & correcciones de errores

## <a name="1006528"></a>100.65.28

- Se agregó compatibilidad con macOS Catalina

  > [!CAUTION]
  > macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad. A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito. En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.
  >
  > El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para endpoint:
  >
  > - Para las implementaciones manuales, vea las instrucciones actualizadas en el [tema Implementación](mac-install-manually.md#how-to-allow-full-disk-access) manual.
  > - Para las implementaciones administradas, vea las instrucciones actualizadas en los temas de implementación basada en [JAMF](mac-install-with-jamf.md) y [microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)

- Mejoras de rendimiento & correcciones de errores
