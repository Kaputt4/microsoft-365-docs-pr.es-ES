---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879783"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar los análisis programados rápidos o completos del Antivirus de Windows Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Además de la protección siempre activa y en tiempo real y los exámenes [antivirus](run-scan-microsoft-defender-antivirus.md) a petición, puede configurar exámenes antivirus regulares programados. Puede configurar el tipo de examen, cuándo debe producirse el [](manage-protection-updates-microsoft-defender-antivirus.md) examen y si el examen debe producirse después de una actualización de protección o cuando no se está utilizando un extremo. También puede configurar exámenes especiales para completar acciones de corrección si es necesario.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

- [Obtenga información sobre exámenes rápidos, exámenes completos y exámenes personalizados](#quick-scan-full-scan-and-custom-scan)
- [Usar la directiva de grupo para programar exámenes antivirus](schedule-antivirus-scans-group-policy.md)
- [Usar Windows PowerShell para programar exámenes antivirus](schedule-antivirus-scans-powershell.md)
- [Usar Windows management instrumentation para programar exámenes antivirus](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados. Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado. 

- Si un dispositivo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar. Antivirus de Microsoft Defender se ejecutará un examen completo en la próxima hora programada.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Examen rápido, examen completo y examen personalizado

Al configurar exámenes programados, puede especificar si el examen debe ser un examen completo o rápido. En la mayoría de los casos, se recomienda realizar un examen rápido. 

| Examen rápido  | Examen completo  | Examen personalizado |
|---------|---------|---------|
| (Recomendado) Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio. <p>Combinado con la protección siempre activa y en tiempo real, que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra malware que comienza con el malware del sistema y el nivel de kernel. <p>En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para exámenes programados. | Un examen completo comienza ejecutando un examen rápido y, a continuación, continúa con un examen secuencial de archivos de todos los discos fijos montados y unidades extraíbles/de red (si el examen completo está configurado para hacerlo). <p>Un examen completo puede tardar unas horas o días en completarse, según la cantidad y el tipo de datos que se deben examinar.<p>Cuando se completa el examen completo, hay nueva inteligencia de seguridad disponible y, a continuación, se requiere un nuevo examen para asegurarse de que no se detecten otras amenazas con la nueva inteligencia de seguridad. <p>Debido al tiempo y los recursos implicados en un examen completo, en general, Microsoft no recomienda programar exámenes completos.  | Un examen personalizado es un examen rápido que se ejecuta en los archivos y carpetas que especifique. Por ejemplo, puedes optar por examinar una unidad USB o una carpeta específica en la unidad local del dispositivo. <p> | 

> [!NOTE]
> De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>¿Cómo sé qué tipo de examen elegir?

Use la tabla siguiente para elegir un tipo de examen.

| Escenario  | Tipo de examen recomendado  |
|---------|---------|
| Desea configurar exámenes regulares y programados     | Examen rápido <p>Un examen rápido comprueba los procesos, la memoria, los perfiles y determinadas ubicaciones del dispositivo. Combinado con la protección siempre activa en tiempo [real,](configure-real-time-protection-microsoft-defender-antivirus.md)un examen rápido ayuda a proporcionar una cobertura sólida tanto para malware que comienza con el malware del sistema como del nivel de kernel. La protección en tiempo real revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta.         |
| Las amenazas, como el malware, se detectan en un dispositivo individual     | Examen rápido <p>En la mayoría de los casos, un examen rápido detectará y limpiará el malware detectado.   |
| Desea ejecutar un examen a [petición](run-scan-microsoft-defender-antivirus.md)     | Examen rápido       |
| Quieres asegurarte de que un dispositivo portátil, como una unidad USB, no contiene malware | Examen personalizado <p>Un examen personalizado permite seleccionar ubicaciones, carpetas o archivos específicos y ejecuta un examen rápido. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>¿Qué más necesito saber sobre los exámenes rápidos y completos?

- Los archivos malintencionados se pueden almacenar en ubicaciones que no se incluyen en un examen rápido. Sin embargo, la protección siempre activa en tiempo real revisa todos los archivos que se abren y cierran y los archivos que se encuentran en carpetas a las que un usuario tiene acceso. La combinación de protección en tiempo real y un examen rápido ayuda a proporcionar una protección segura contra malware.

- La protección en tiempo de acceso [con](cloud-protection-microsoft-defender-antivirus.md) protección entregada en la nube ayuda a garantizar que todos los archivos a los que se accede en el sistema se examinan con los modelos de inteligencia de seguridad y aprendizaje automático en la nube más recientes.

- Cuando la protección en tiempo real detecta malware y el alcance de los archivos afectados no se determina inicialmente, Antivirus de Microsoft Defender inicia un examen completo como parte del proceso de corrección.

- Un examen completo puede detectar archivos malintencionados que no fueron detectados por otros exámenes, como un examen rápido. Sin embargo, un examen completo puede tardar un tiempo y usar valiosos recursos del sistema para completarse.

- Si un dispositivo está sin conexión durante un período prolongado de tiempo, un examen completo puede tardar más tiempo en completarse. 

