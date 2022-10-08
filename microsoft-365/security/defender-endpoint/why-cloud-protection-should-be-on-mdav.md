---
title: Por qué se debe habilitar la protección en la nube para Microsoft Defender Antivirus
description: Vea por qué se debe activar la protección en la nube para Microsoft Defender Antivirus. Ayuda a muchas características de seguridad en Microsoft Defender para punto de conexión trabajo
keywords: Microsoft Defender Antivirus, protección en la nube, características de seguridad, envío de ejemplo
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: article
ms.date: 10/22/2021
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 856bb2ac16e3b0e96a76c596e6ef1234ef0e3fd7
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68233428"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>Por qué se debe habilitar la protección en la nube para Microsoft Defender Antivirus

**Se aplica a:**

- Antivirus de Microsoft Defender
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**Plataformas**
- Windows

Microsoft Defender Antivirus cloud protection ayuda a protegerse contra el malware en los puntos de conexión y en toda la red. Se recomienda mantener activada la protección en la nube, ya que ciertas características y funcionalidades de seguridad en Microsoft Defender para punto de conexión solo funcionan cuando la protección en la nube está habilitada. 

[![alt-text="Diagrama que muestra cosas que dependen de la protección en la nube](images/mde-cloud-protection.png#lightbox)](enable-cloud-protection-microsoft-defender-antivirus.md)

En la tabla siguiente se resumen las características y funcionalidades que dependen de la protección en la nube: <br/><br/>

| Característica o funcionalidad  | Requisitos de suscripción |  Descripción  |
|---------|---------|--------|
| Comprobación de metadatos en la nube  | Microsoft Defender para punto de conexión Plan 1 o Plan 2 (independiente o incluido en un plan como Microsoft 365 E3 o E5) | El servicio en la nube Microsoft Defender Antivirus usa modelos de aprendizaje automático como una capa adicional de defensa. Estos modelos de aprendizaje automático incluyen metadatos, por lo que cuando se detecta un archivo sospechoso o malintencionado, se comprueban sus metadatos. <br/><br/>Para más información, consulte [Blog: Conocer las tecnologías avanzadas en el núcleo de Microsoft Defender para punto de conexión protección de próxima generación](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).  |
| Protección en la nube y envío de muestra | Microsoft Defender para punto de conexión Plan 1 o Plan 2 (independiente o incluido en un plan como Microsoft 365 E3 o E5) | Los archivos y ejecutables se pueden enviar al servicio en la nube Microsoft Defender Antivirus para su detonación y análisis. <br/><br/>Para más información, consulte [Protección en la nube y envío de ejemplo en Microsoft Defender Antivirus](cloud-protection-microsoft-antivirus-sample-submission.md).<br/><br/>**NOTA**: El envío automático de ejemplos se basa en la protección en la nube, aunque también se puede configurar como una configuración independiente.         |
| Protección contra alteraciones | Microsoft Defender para punto de conexión plan 2 (independiente o incluido en un plan como Microsoft 365 E5) | La protección contra alteraciones ayuda a protegerse frente a cambios no deseados en la configuración de seguridad de la organización. Para aplicar la protección contra alteraciones en Microsoft 365 Defender portal, se debe habilitar la protección en la nube. <br/><br/>Para más información, consulte [Protección de la configuración de seguridad con protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md).        |
| Bloqueo a primera vista | Microsoft Defender para punto de conexión Plan 1 o Plan 2 (independiente o incluido en un plan como Microsoft 365 E3 o E5) | Bloquear a primera vista detecta malware nuevo y lo bloquea en cuestión de segundos. Cuando se detecta un archivo sospechoso o malintencionado, las funcionalidades de bloqueo a primera vista consultan el back-end de protección en la nube y aplican heurística, aprendizaje automático y análisis automatizado del archivo para determinar si se trata de una amenaza.<br/><br/>Para obtener más información, consulte [¿Qué es "bloquear a primera vista"?](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| Actualizaciones de firmas de emergencia | Microsoft Defender para punto de conexión plan 2 (independiente o incluido en un plan como Microsoft 365 E5) | Cuando se detecta contenido malintencionado, se implementan actualizaciones y correcciones de firmas de emergencia. En lugar de esperar a la siguiente actualización regular, puede recibir estas correcciones y actualizaciones en cuestión de minutos.   |
| Detección y respuesta de Endpoint (EDR) en el modo bloqueo | Microsoft Defender para punto de conexión plan 2 (independiente o incluido en un plan como Microsoft 365 E5) | EDR en modo de bloque proporciona protección adicional cuando Microsoft Defender Antivirus no es el producto antivirus principal en un dispositivo. EDR en modo de bloque corrige los artefactos encontrados durante los exámenes generados por EDR que la solución antivirus principal que no es de Microsoft podría haber perdido. Cuando se habilita para dispositivos con Microsoft Defender Antivirus como solución antivirus principal, EDR en modo de bloque proporciona la ventaja adicional de corregir automáticamente los artefactos identificados durante los exámenes generados por EDR. <br/><br/>Para más información, consulte [EDR en modo de bloque](edr-in-block-mode.md).|
| Reglas de reducción de la superficie expuesta a ataques | Microsoft Defender para punto de conexión Plan 1 o Plan 2 (independiente o incluido en un plan como Microsoft 365 E3 o E5) | La reducción de la superficie expuesta a ataques consiste en reducir los lugares y las formas en que los puntos de conexión de su organización son vulnerables a un ciberataque. Las reglas de reducción de superficie expuesta a ataques son reglas inteligentes que puede configurar para ayudar a detener el malware. Algunas reglas requieren que la protección en la nube esté activada para funcionar completamente. Estas reglas son: <br/>- Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza <br/>- Uso de la protección avanzada contra ransomware <br/>- Impedir que los programas que no son de confianza se ejecuten desde unidades extraíbles <br/><br/>Para obtener más información, consulta [Usar reglas de reducción de superficie expuesta a ataques para evitar la infección por malware](attack-surface-reduction.md).  |
| Indicadores de riesgo (IoC) | Microsoft Defender para punto de conexión plan 2 (independiente o incluido en un plan como Microsoft 365 E5) | Los ioCs de Defender para punto de conexión se pueden configurar para definir la detección, prevención y exclusión de entidades. Por ejemplo, los indicadores "allow" se pueden usar para definir excepciones para Microsoft Defender análisis del Antivirus y acciones de corrección en Defender para punto de conexión. Como otro ejemplo, se pueden usar indicadores de "alerta y bloqueo" para evitar que se ejecuten archivos o procesos, y para realizar un seguimiento de estas actividades con alertas que se pueden ver en el portal de Microsoft 365 Defender. <br/><br/>Para obtener más información, consulte [Creación de indicadores](manage-indicators.md).    |

> [!TIP]
> Para más información sobre los planes de Defender para punto de conexión, consulte [Microsoft Defender para punto de conexión Plan 1 y Plan 2](defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Pasos siguientes

Ahora que tiene información general sobre la protección en la nube y su rol en Microsoft Defender Antivirus, estos son algunos pasos siguientes:

1. **[Habilite la protección en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)**. Puede habilitar la protección en la nube con Microsoft Endpoint Manager (que ahora incluye Configuration Manager de punto de conexión de Microsoft y Microsoft Intune), directiva de grupo o cmdlets de PowerShell.

2. **[Especifique el nivel de protección en la nube](specify-cloud-protection-level-microsoft-defender-antivirus.md)**. Puede especificar el nivel de protección que ofrece la nube mediante Microsoft Endpoint Manager o directiva de grupo. El nivel de protección afecta a la cantidad de información compartida con la nube y a la forma agresiva en que se bloquean los archivos nuevos.

3. **[Configure y valide las conexiones de red para Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md)**. Hay determinadas direcciones URL de Microsoft a las que la red y los puntos de conexión deben poder conectarse para que la protección en la nube funcione de forma eficaz. En este artículo se enumeran las direcciones URL que se deben permitir a través de reglas de filtrado de red o firewall e instrucciones para confirmar que la red está correctamente inscrita en la protección en la nube.

4. **[Configure la característica "bloquear a primera vista"](configure-block-at-first-sight-microsoft-defender-antivirus.md)**. La característica "bloquear a primera vista" puede bloquear el nuevo malware en cuestión de segundos, sin tener que esperar horas para la inteligencia de seguridad tradicional. Puede habilitarlo y configurarlo mediante Microsoft Endpoint Manager o directiva de grupo.

5. **[Configure el período de tiempo de espera del bloque de nube](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)**. Microsoft Defender Antivirus puede impedir que se ejecuten archivos sospechosos mientras consulta nuestro servicio de protección en la nube. Puede configurar la cantidad de tiempo que se impedirá que el archivo se ejecute mediante Microsoft Endpoint Manager o directiva de grupo.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)