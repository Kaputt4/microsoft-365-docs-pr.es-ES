---
title: Programar exámenes rápidos y completos normales con Microsoft Defender Antivirus
description: Configurar exámenes periódicos (programados), incluidos cuándo se deben ejecutar y si se ejecutan como exámenes completos o rápidos
keywords: examen rápido, examen completo, rápido frente a completo, examen programado, diario, semanal, tiempo, programado, periódico, regular
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 08/09/2022
ms.reviewer: pauhijbr, ksarens, mkaminska
manager: dansimp
ms.subservice: mde
ms.topic: how-to
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: 8e3603887a7b4c1713c72bfe4640c63d71f44c1b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68219110"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar los análisis programados rápidos o completos del Antivirus de Windows Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Además de la protección siempre activa en tiempo real y los exámenes [antivirus a petición](run-scan-microsoft-defender-antivirus.md) , puede configurar exámenes antivirus regulares y programados. Puede configurar el tipo de examen, cuándo debe producirse el examen y si el examen debe producirse después de una [actualización de protección](manage-protection-updates-microsoft-defender-antivirus.md) o cuando no se usa un punto de conexión. También puede configurar exámenes especiales para completar las acciones de corrección si es necesario.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

- [Más información sobre los exámenes rápidos, los exámenes completos y los exámenes personalizados](#quick-scan-full-scan-and-custom-scan)
- [Uso de directiva de grupo para programar exámenes antivirus](schedule-antivirus-scans-group-policy.md)
- [Uso de Windows PowerShell para programar exámenes antivirus](schedule-antivirus-scans-powershell.md)
- [Uso de Instrumental de administración de Windows para programar exámenes antivirus](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- De forma predeterminada, Microsoft Defender Antivirus comprueba si hay una actualización 15 minutos antes de la hora de los exámenes programados. Puede [administrar la programación de cuándo se deben descargar y aplicar las actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md) para invalidar este valor predeterminado.

- Si un dispositivo está desconectado y funcionando con batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de la finalización. Microsoft Defender Antivirus ejecutará un examen completo en la próxima hora programada.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Examen rápido, examen completo y examen personalizado

Al configurar exámenes programados, puede especificar si el examen debe ser completo o rápido. En la mayoría de los casos, se recomienda un examen rápido; sin embargo, también se recomienda ejecutar al menos un examen completo después de instalar o habilitar antivirus de Defender. Este examen proporciona una oportunidad para encontrar amenazas existentes y ayuda a rellenar la memoria caché para exámenes futuros.

|Examen rápido|Examen completo|Examen personalizado|
|---|---|---|
|(Recomendado) Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows. <br/><br/>Combinado con la protección siempre activa en tiempo real, que revisa los archivos cuando se abren y cierran, y cada vez que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra el malware que comienza con el sistema y el malware de nivel de kernel.<br/><br/>En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para los exámenes programados.|Un examen completo comienza ejecutando un examen rápido y, a continuación, continúa con un examen secuencial de archivos de todos los discos fijos montados y las unidades extraíbles o de red (si el examen completo está configurado para hacerlo).<br/><br/>Un examen completo puede tardar unas horas o días en completarse, en función de la cantidad y el tipo de datos que se deba examinar.<br/><br/>Una vez completado el examen completo, está disponible una nueva inteligencia de seguridad y, a continuación, se requiere un nuevo examen para asegurarse de que no se detecta ninguna otra amenaza con la nueva inteligencia de seguridad.<br/><br/>Debido al tiempo y los recursos implicados en un examen completo, en general, Microsoft no recomienda programar exámenes completos.|Un examen personalizado se ejecuta en archivos y carpetas que especifique. Por ejemplo, puede elegir examinar una unidad USB o una carpeta específica en la unidad local del dispositivo.|

> [!NOTE]
> De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Cómo saber qué tipo de examen elegir?

Use la tabla siguiente para elegir un tipo de examen.
<br/><br/>

|Escenario|Tipo de examen recomendado|
|---|---|
|Desea configurar exámenes regulares y programados|Examen rápido <p> Un examen rápido comprueba los procesos, la memoria, los perfiles y determinadas ubicaciones del dispositivo. Combinado con la [protección en tiempo real siempre activa](configure-real-time-protection-microsoft-defender-antivirus.md), un examen rápido ayuda a proporcionar una cobertura sólida tanto para el malware que comienza con el sistema como para el malware de nivel de kernel. La protección en tiempo real revisa los archivos cuando se abren y cierran, y cada vez que un usuario navega a una carpeta.|
|Las amenazas, como el malware, se detectan en un dispositivo individual|Examen rápido <p> En la mayoría de los casos, un examen rápido detectará y limpiará el malware detectado.|
|Desea ejecutar un examen a [petición](run-scan-microsoft-defender-antivirus.md)|Examen rápido|
|Quiere asegurarse de que un dispositivo portátil, como una unidad USB, no contenga malware.|Examen personalizado <p> Un examen personalizado le permite seleccionar ubicaciones, carpetas o archivos específicos y ejecuta un examen rápido.|
| Acaba de instalar o volver a habilitar Microsoft Defender Antivirus | Examen completo <p>La ejecución de un examen completo después de haber habilitado o instalado Microsoft Defender Antivirus ayuda a rellenar la memoria caché para exámenes futuros. El examen completo también puede ayudar a detectar amenazas existentes en el dispositivo. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>¿Qué más necesito saber sobre los exámenes rápidos y completos?

- Los archivos malintencionados se pueden almacenar en ubicaciones que no se incluyen en un examen rápido. Sin embargo, la protección siempre activa en tiempo real revisa todos los archivos abiertos y cerrados, así como los archivos que se encuentran en carpetas a las que accede un usuario. La combinación de protección en tiempo real y un examen rápido ayuda a proporcionar una protección fuerte contra el malware.

- La protección de acceso con [protección proporcionada](cloud-protection-microsoft-defender-antivirus.md) en la nube ayuda a garantizar que todos los archivos a los que se accede en el sistema se examinan con los modelos más recientes de inteligencia de seguridad y aprendizaje automático en la nube.

- Cuando la protección en tiempo real detecta malware y la extensión de los archivos afectados no se determina inicialmente, Microsoft Defender Antivirus inicia un examen completo como parte del proceso de corrección.

- Un examen completo puede detectar archivos malintencionados que otros exámenes no detectaron, como un examen rápido. Sin embargo, un examen completo puede tardar un tiempo y usar recursos valiosos del sistema para completarse.

- Si un dispositivo está sin conexión durante un período de tiempo prolongado, un examen completo puede tardar más tiempo en completarse.

## <a name="scheduled-quick-scan-performance-optimization"></a>Optimización programada del rendimiento del examen rápido 

Como optimización del rendimiento, Microsoft Defender Antivirus omitirá la ejecución de exámenes rápidos programados en algunas situaciones. Esta optimización solo se aplica a un examen rápido cuando se inicia mediante una programación; no afecta a un examen rápido iniciado por un examen [antivirus a petición](run-scan-microsoft-defender-antivirus.md) . Esta optimización reduce la degradación del rendimiento evitando ejecutar un examen rápido cuando no es necesario y no afectará a la protección.

De forma predeterminada, si se ejecutó un examen rápido calificado en los últimos siete días, no se iniciará un nuevo examen rápido. Un examen rápido se considera calificado si se produce después de instalar la última [actualización de Inteligencia de seguridad](manage-updates-baselines-microsoft-defender-antivirus.md) , Real-Time Protección no se deshabilitó durante ese período y si la máquina se ha reiniciado.  

Esta optimización no se aplica a las condiciones siguientes: 

- Si Microsoft Defender para punto de conexión está [administrado](configuration-management-reference-microsoft-defender-antivirus.md)  

- Si Microsoft Defender [detección y respuesta de puntos de conexión (EDR)](overview-endpoint-detection-response.md) está instalado 

- Si el equipo se ha reiniciado desde el último examen rápido

- Si Microsoft Defender para punto de conexión Real-Time Protección se ha deshabilitado desde que se produjo el último examen rápido, incluido si está deshabilitado actualmente 

- Si no se completó el último examen rápido iniciado

Esta optimización se aplica a las máquinas que ejecutan Windows 10 actualización de aniversario (versión 1607) y todas las versiones posteriores de Windows, así como a Windows Server 2016 (versión 1607) y versiones posteriores de Windows Server, pero no se aplica a las instalaciones de Core Server.  

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
