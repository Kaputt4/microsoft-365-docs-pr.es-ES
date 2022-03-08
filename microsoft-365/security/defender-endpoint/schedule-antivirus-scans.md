---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/22/2022
ms.reviewer: pauhijbr, ksarens, mkaminska
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: 96827430b8d2fe1b45b9839ffe87eb5aa5571b93
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326599"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Configurar los análisis programados rápidos o completos del Antivirus de Windows Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

Además de la protección siempre activa y en tiempo real y los exámenes [antivirus](run-scan-microsoft-defender-antivirus.md) a petición, puede configurar exámenes antivirus regulares programados. Puede configurar el tipo de examen, cuándo debe producirse el examen y si el examen debe producirse después de [](manage-protection-updates-microsoft-defender-antivirus.md) una actualización de protección o cuando no se está utilizando un extremo. También puede configurar exámenes especiales para completar acciones de corrección si es necesario.

## <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

- [Obtenga información sobre exámenes rápidos, exámenes completos y exámenes personalizados](#quick-scan-full-scan-and-custom-scan)
- [Usar la directiva de grupo para programar exámenes antivirus](schedule-antivirus-scans-group-policy.md)
- [Usar Windows PowerShell para programar exámenes antivirus](schedule-antivirus-scans-powershell.md)
- [Usar Windows Management Instrumentation para programar exámenes antivirus](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Tenga en cuenta los siguientes puntos

- De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados. Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado.

- Si un dispositivo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar. Antivirus de Microsoft Defender se ejecutará un examen completo en la próxima hora programada.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Examen rápido, examen completo y examen personalizado

Al configurar exámenes programados, puede especificar si el examen debe ser un examen completo o rápido. En la mayoría de los casos, se recomienda realizar un examen rápido.

<br/><br/>

|Examen rápido|Examen completo|Examen personalizado|
|---|---|---|
|(Recomendado) Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows inicio. <br/><br/>Combinado con la protección siempre activa y en tiempo real, que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra malware que comienza con el malware del sistema y el nivel de kernel.<br/><br/>En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para exámenes programados.|Un examen completo comienza ejecutando un examen rápido y, a continuación, continúa con un examen secuencial de archivos de todos los discos fijos montados y unidades extraíbles/de red (si el examen completo está configurado para hacerlo).<br/><br/>Un examen completo puede tardar unas horas o días en completarse, según la cantidad y el tipo de datos que se deben examinar.<br/><br/>Cuando se completa el examen completo, hay nueva inteligencia de seguridad disponible y, a continuación, se requiere un nuevo examen para asegurarse de que no se detecten otras amenazas con la nueva inteligencia de seguridad.<br/><br/>Debido al tiempo y los recursos implicados en un examen completo, en general, Microsoft no recomienda programar exámenes completos.|Un examen personalizado se ejecuta en los archivos y carpetas que especifique. Por ejemplo, puedes elegir examinar una unidad USB o una carpeta específica en la unidad local del dispositivo.|

> [!NOTE]
> De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>¿Cómo sé qué tipo de examen elegir?

Use la tabla siguiente para elegir un tipo de examen.
<br/><br/>

|Escenario|Tipo de examen recomendado|
|---|---|
|Desea configurar exámenes regulares y programados|Examen rápido <p> Un examen rápido comprueba los procesos, la memoria, los perfiles y determinadas ubicaciones del dispositivo. Combinado con [la protección siempre](configure-real-time-protection-microsoft-defender-antivirus.md) activa en tiempo real, un examen rápido ayuda a proporcionar una cobertura sólida tanto para malware que comienza con el malware del sistema como del nivel de kernel. La protección en tiempo real revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta.|
|Las amenazas, como el malware, se detectan en un dispositivo individual|Examen rápido <p> En la mayoría de los casos, un examen rápido detectará y limpiará el malware detectado.|
|Desea ejecutar un examen a [petición](run-scan-microsoft-defender-antivirus.md)|Examen rápido|
|Quieres asegurarte de que un dispositivo portátil, como una unidad USB, no contiene malware|Examen personalizado <p> Un examen personalizado permite seleccionar ubicaciones, carpetas o archivos específicos y ejecuta un examen rápido.|

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>¿Qué más necesito saber sobre los exámenes rápidos y completos?

- Los archivos malintencionados se pueden almacenar en ubicaciones que no se incluyen en un examen rápido. Sin embargo, la protección siempre activa en tiempo real revisa todos los archivos que se abren y cierran y los archivos que se encuentran en carpetas a las que un usuario tiene acceso. La combinación de protección en tiempo real y un examen rápido ayuda a proporcionar una protección segura contra malware.

- La protección en tiempo de [acceso con protección](cloud-protection-microsoft-defender-antivirus.md) entregada en la nube ayuda a garantizar que todos los archivos a los que se accede en el sistema se examinan con los modelos de inteligencia de seguridad y aprendizaje automático en la nube más recientes.

- Cuando la protección en tiempo real detecta malware y la extensión de los archivos afectados no se determina inicialmente, Antivirus de Microsoft Defender inicia un examen completo como parte del proceso de corrección.

- Un examen completo puede detectar archivos malintencionados que no fueron detectados por otros exámenes, como un examen rápido. Sin embargo, un examen completo puede tardar un tiempo y usar valiosos recursos del sistema para completarse.

- Si un dispositivo está sin conexión durante un período prolongado de tiempo, un examen completo puede tardar más tiempo en completarse.
