---
title: ¿Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender
description: Vea por qué la protección en la nube debe estar activada para Antivirus de Microsoft Defender. Ayuda a que muchas características de seguridad de Microsoft Defender for Endpoint funcionen
keywords: Antivirus de Microsoft Defender, protección en la nube, características de seguridad, envío de ejemplo
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/22/2021
ms.collection: m365-security-compliance
ms.openlocfilehash: 50e9639ed861bee3a661da7ad1374c06b72b071e
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555457"
---
# <a name="why-cloud-protection-should-be-enabled-for-microsoft-defender-antivirus"></a>¿Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- Antivirus de Microsoft Defender

Antivirus de Microsoft Defender protección en la nube ayuda a proteger contra malware en los puntos de conexión y en toda la red. Se recomienda mantener activada la protección en la nube, ya que determinadas funciones y características de seguridad de Microsoft Defender para endpoint solo funcionan cuando la protección en la nube está habilitada. 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="Diagrama que muestra cosas que dependen de la protección en la nube":::](enable-cloud-protection-microsoft-defender-antivirus.md)

En la tabla siguiente se resumen las características y capacidades que dependen de la protección en la nube: <br/><br/>

| Característica/funcionalidad  | Requisitos de suscripción |  Descripción  |
|---------|---------|--------|
| Comprobación de metadatos en la nube  | Plan 1 o Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E3 o E5) | El Antivirus de Microsoft Defender cloud usa modelos de aprendizaje automático como una capa adicional de defensa. Estos modelos de aprendizaje automático incluyen metadatos, por lo que cuando se detecta un archivo sospechoso o malintencionado, se comprueban sus metadatos. <br/><br/>Para obtener más información, vea Blog: Conozca las tecnologías avanzadas en el núcleo de Microsoft Defender para la protección de última [generación de endpoints](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)  |
| Protección en la nube y envío de muestra | Plan 1 o Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E3 o E5) | Los archivos y archivos ejecutables se pueden enviar al servicio Antivirus de Microsoft Defender nube para su detonación y análisis. <br/><br/>Para obtener más información, consulte [Cloud protection and sample submission in Antivirus de Microsoft Defender](cloud-protection-microsoft-antivirus-sample-submission.md).<br/><br/>**NOTA:** El envío automático de ejemplo se basa en la protección en la nube, aunque también se puede configurar como una configuración independiente.         |
| Protección contra alteraciones | Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E5) | La protección contra alteraciones ayuda a proteger contra cambios no deseados en la configuración de seguridad de la organización. Para aplicar la protección contra alteraciones en el portal de Microsoft 365 Defender, la protección en la nube debe estar habilitada. <br/><br/>Para obtener más información, vea [Protect security settings with tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md).        |
| Bloqueo a primera vista | Plan 1 o Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E3 o E5) | Bloquear a primera vista detecta nuevo malware y lo bloquea en segundos. Cuando se detecta un archivo sospechoso o malintencionado, bloquea las capacidades a primera vista consulta el back-end de protección en la nube y aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si es una amenaza.<br/><br/>Para obtener más información, vea [¿Qué es "bloquear a primera vista"?](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)   |
| Actualizaciones de firmas de emergencia | Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E5) | Cuando se detecta contenido malintencionado, se implementan actualizaciones y correcciones de firmas de emergencia. En lugar de esperar la próxima actualización regular, puede recibir estas correcciones y actualizaciones en cuestión de minutos.   |
| Detección y respuesta de Endpoint (EDR) en el modo bloqueo | Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E5) | EDR en modo de bloqueo proporciona protección adicional cuando Antivirus de Microsoft Defender no es el producto antivirus principal de un dispositivo. EDR en modo de bloqueo corrige los artefactos encontrados durante EDR análisis generados por microsoft que la solución antivirus principal que no es de Microsoft podría haber perdido. Cuando se habilita para dispositivos con Antivirus de Microsoft Defender como solución antivirus principal, EDR en modo de bloqueo proporciona la ventaja adicional de corregir automáticamente artefactos identificados durante los EDR generados por el usuario. <br/><br/>Para obtener más información, [vea EDR en modo de bloque](edr-in-block-mode.md).|
| Reglas de reducción de la superficie expuesta a ataques | Plan 1 o Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E3 o E5) | La reducción de superficie de ataque se trata de reducir los lugares y formas en que los puntos de conexión de la organización son vulnerables a un ataque cibernético. Las reglas de reducción de superficie de ataque son reglas inteligentes que puedes configurar para ayudar a detener el malware. Ciertas reglas requieren que la protección en la nube esté activada para funcionar completamente. Estas reglas son: <br/>- Bloquear la ejecución de archivos ejecutables a menos que cumplan criterios de prevalencia, antigüedad o lista de confianza <br/>- Usar protección avanzada contra ransomware <br/>- Impedir que los programas que no son de confianza se ejecuten desde unidades extraíbles <br/><br/>Para obtener más información, consulta [Usar reglas de reducción de superficie de ataque para evitar la infección de malware.](attack-surface-reduction.md)  |
| Indicadores de peligro (IoCs) | Plan 2 de Microsoft Defender para Endpoint (independiente o incluido en un plan como Microsoft 365 E5) | Los IoCs de Defender for Endpoint se pueden configurar para definir la detección, prevención y exclusión de entidades. Por ejemplo, los indicadores "permitir" se pueden usar para definir excepciones para realizar Antivirus de Microsoft Defender análisis y acciones de corrección en Defender para endpoint. Como otro ejemplo, se pueden usar indicadores de "alerta y bloqueo" para evitar que se ejecuten archivos o procesos y para realizar un seguimiento de estas actividades con alertas que se pueden ver en el portal de Microsoft 365 Defender web. <br/><br/>Para obtener más información, vea [Crear indicadores](manage-indicators.md).    |

> [!TIP]
> Para obtener más información sobre los planes de Defender for Endpoint, consulte [Microsoft Defender for Endpoint Plan 1 (versión preliminar) y Plan 2](defender-endpoint-plan-1-2.md).

## <a name="next-steps"></a>Siguientes pasos

Ahora que tiene una introducción a la protección en la nube y su rol en Antivirus de Microsoft Defender, estos son algunos pasos siguientes:

1. **[Habilitar la protección en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)**. Puede habilitar la protección en la nube con Microsoft Endpoint Manager (que ahora incluye Microsoft Endpoint Configuration Manager y Microsoft Intune), directivas de grupo o cmdlets de PowerShell.

2. **[Especifique el nivel de protección de nube](specify-cloud-protection-level-microsoft-defender-antivirus.md)**. Puede especificar el nivel de protección ofrecido por la nube mediante Microsoft Endpoint Manager o directiva de grupo. El nivel de protección afecta a la cantidad de información compartida con la nube y a la forma agresiva en que se bloquean los nuevos archivos.

3. **[Configurar y validar conexiones de red para Antivirus de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md)**. Hay determinadas direcciones URL de Microsoft a las que la red y los puntos de conexión deben poder conectarse para que la protección en la nube funcione de forma eficaz. En este artículo se enumeran las direcciones URL que se deben permitir mediante firewall o reglas de filtrado de red, e instrucciones para confirmar que la red está correctamente inscrita en la protección en la nube.

4. **[Configurar la característica "bloquear a primera vista".](configure-block-at-first-sight-microsoft-defender-antivirus.md)** La característica "bloquear a primera vista" puede bloquear malware nuevo en cuestión de segundos, sin tener que esperar horas para la inteligencia de seguridad tradicional. Puede habilitarla y configurarla mediante Microsoft Endpoint Manager o directiva de grupo.

5. **[Configurar el período de tiempo de espera del bloque de nube.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)** Antivirus de Microsoft Defender bloquear la ejecución de archivos sospechosos mientras consulta nuestro servicio de protección en la nube. Puede configurar la cantidad de tiempo que se impedirá que el archivo se ejecute mediante Microsoft Endpoint Manager o directiva de grupo.
