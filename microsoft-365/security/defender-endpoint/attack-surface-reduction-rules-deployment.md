---
title: Introducción a la implementación de reglas de reducción de superficie expuesta a ataques (ASR) de Microsoft Defender para punto de conexión (MDE)
description: Proporciona información general y instrucciones de requisitos previos sobre la implementación de reglas de reducción de superficie expuesta a ataques (ASR) de Microsoft Defender para punto de conexión (MDE). Vínculos a temas que muestran cómo planear y implementar ASR, probar reglas de ASR, configurar reglas de ASR y habilitar reglas de ASR.
keywords: Microsoft Defender para punto de conexión (MDE) reglas de reducción de superficie expuesta a ataques, reglas de ASR intune, reglas de ASR de defender, reglas de ASR de Windows 10, reglas de defender asr, informe de reglas de ASR, implementación de reglas de reducción de superficie de ataque de microsoft, visor de eventos de reglas de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades de seguridad, anti-exploit, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas de ASR
search.product: eADQiWindows 10XVcnh
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.topic: conceptual
ms.collection:
- m365-security
- m365solution-asr-rules
- highpri
- tier1
ms.date: 09/18/2022
search.appverid: met150
ms.openlocfilehash: 4506ef953ba543ed5f45046cffc1fcfad49077e4
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68630652"
---
# <a name="attack-surface-reduction-asr-rules-deployment-overview"></a>Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)

Las superficies expuestas a ataques son todos los lugares donde su organización es vulnerable a ciberamenazas y ataques. Reducir la superficie expuesta a ataques significa proteger los dispositivos y la red de su organización, lo que deja a los atacantes con menos formas de atacar. La configuración de reglas de reducción de superficie expuesta a ataques (ASR) de Microsoft Defender para punto de conexión (MDE) puede ayudar.

Las reglas de ASR tienen como destino determinados comportamientos de software, como:

- Inicio de archivos ejecutables y scripts que intentan descargar o ejecutar archivos
- Ejecución de scripts ofuscados o sospechosos
- Comportamientos que las aplicaciones no suelen producirse durante el trabajo diario normal

Al reducir las distintas superficies de ataque, puedes ayudar a evitar que se produzcan ataques en primer lugar.

Esta colección de implementación proporciona información sobre los siguientes aspectos de las reglas de ASR de MDE:

- Requisitos de reglas de ASR
- plan para la implementación de reglas de ASR
- probar reglas de ASR
- configurar y habilitar reglas de asr
- Procedimientos recomendados de las reglas de reducción de superficie expuesta a ataques
- Búsqueda avanzada de reglas de ASR
- Visor de eventos de reglas de ASR

## <a name="asr-rules-deployment-steps"></a>Pasos de implementación de reglas de ASR

Al igual que con cualquier nueva implementación a gran escala que pueda afectar potencialmente a las operaciones de línea de negocio, es importante ser metódico en su planeamiento e implementación. Debido a las eficaces funcionalidades de las reglas de ASR para evitar el malware, es necesario planear e implementar cuidadosamente estas reglas para asegurarse de que funcionan mejor para los flujos de trabajo de clientes únicos. Para trabajar en su entorno, debe planear, probar, implementar y poner en funcionamiento las reglas de ASR cuidadosamente.  

> :::image type="content" source="images/asr-rules-deployment-phases.png" alt-text="Planee las reglas de reducción de superficie expuesta a ataques (ASR) de Microsoft Defender para punto de conexión (MDE), pruebe las reglas de ASR de MDE, habilite las reglas de ASR de MDE y mantenga las reglas de ASR." lightbox="images/asr-rules-deployment-phases.png":::

## <a name="important-pre-deployment-caveat"></a>Advertencia importante previa a la implementación

Mientras pasa por el proceso de planeamiento, auditoría y habilitación de reglas asr, se recomienda habilitar las tres _reglas de protección estándar_ siguientes. Consulta [Reglas de reducción de superficie expuesta a ataques por tipo](attack-surface-reduction-rules-reference.md#attack-surface-reduction-rules-by-type) para obtener detalles importantes sobre los dos tipos de reglas de ASR.

- [Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](attack-surface-reduction-rules-reference.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)
- [Bloquear el abuso de controladores firmados vulnerables explotados](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers)
- [Bloquear la persistencia a través de la suscripción de eventos de Instrumental de administración de Windows (WMI)](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)

Normalmente, puede habilitar las reglas de protección estándar con un impacto mínimo a no perceptible para el usuario final. Para obtener un método sencillo para habilitar las reglas de protección estándar, consulte: [Opción de protección estándar simplificada](attack-surface-reduction-rules-report.md#simplified-standard-protection-option).

> [!NOTE]
> Para los clientes que usan hips que no son de Microsoft y están realizando la transición a Microsoft Defender para punto de conexión reglas de reducción de superficie expuesta a ataques: Microsoft aconseja a los clientes que ejecuten su solución HIPS en paralelo con su implementación de reglas de ASR hasta el momento en que cambie del modo Auditoría a Modo de bloque. Tenga en cuenta que debe ponerse en contacto con el proveedor de antivirus de terceros para obtener recomendaciones de exclusión.  

## <a name="before-you-begin-testing-or-enabling-asr-rules"></a>Antes de empezar a probar o habilitar reglas de ASR

Durante la preparación inicial, es fundamental que comprenda las capacidades de los sistemas que va a poner en marcha. Comprender las funcionalidades le ayudará a determinar qué reglas de ASR son más importantes para proteger su organización. Además, hay varios requisitos previos a los que debe atender para preparar la implementación de ASR.

> [!IMPORTANT]
> En esta guía se proporcionan imágenes y ejemplos que le ayudarán a decidir cómo configurar reglas de ASR; Es posible que estas imágenes y ejemplos no reflejen las mejores opciones de configuración para su entorno.

Antes de empezar, revise [Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md) y [Desmitificar las reglas de reducción de la superficie expuesta a ataques: Parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) para obtener información fundamental. Para comprender las áreas de cobertura y el impacto potencial, familiarícese con el conjunto actual de reglas de ASR; consulte [Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md).  Mientras se familiariza con el conjunto de reglas de ASR, tome nota de las asignaciones de GUID por regla; vea: [regla ASR a matriz GUID](attack-surface-reduction-rules-reference.md#asr-rule-to-guid-matrix).

Las reglas de ASR son solo una funcionalidad de las capacidades de reducción de superficie expuesta a ataques dentro de Microsoft Defender para punto de conexión. Este documento profundizará más en la implementación de reglas de ASR de forma eficaz para detener amenazas avanzadas, como ransomware operados por personas y otras amenazas.  

### <a name="asr-rules-list-by-category"></a>Lista de reglas de ASR por categoría

Como se describe en [Usar reglas de reducción de superficie expuesta a ataques para evitar la infección por malware](attack-surface-reduction.md), hay varias reglas de reducción de superficie expuesta a ataques dentro de MDE que puede habilitar para proteger su organización. A continuación se muestran las reglas desglosadas por categoría:

<br/>

| Amenazas polimórficas | Movimiento lateral & robo de credenciales | Reglas de aplicaciones de productividad |  reglas de Email | Reglas de script | Reglas incorrectas |
|:---|:---|:---|:---|:---|:---|
| Impedir que los archivos ejecutables se ejecuten a menos que cumplan una prevalencia (1000 máquinas), edad (24 horas) o criterios de lista de confianza | Bloquear las creaciones de procesos que se originen a partir de comandos PSExec y WMI | Impedir que las aplicaciones de Office creen contenido ejecutable | Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | Bloquear código JS/VBS/PS/macro ofuscado | Bloquear el abuso de controladores <sup>firmados vulnerables explotados [[1](#fn1)]<sup></sup>  |
| Bloquear procesos que no son de confianza y no firmados que se ejecutan desde USB | Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)<sup>[[2](#fn1)]<sup></sup>   | Impedir que las aplicaciones de Office creen procesos secundarios |  Impedir que solo las aplicaciones de comunicación de Office creen procesos secundarios | Impedir que JS/VBS inicie el contenido ejecutable descargado | |
| Uso de protección avanzada contra ransomware | Bloquear la persistencia a través de la suscripción de eventos WMI | Impedir que las aplicaciones de Office inserten código en otros procesos | Impedir que las aplicaciones de comunicación de Office creen procesos secundarios | | |
| | | Impedir que Adobe Reader cree procesos secundarios | | | |

(<a id="fn1">1</a>) _El abuso de bloqueo de controladores firmados vulnerables explotados_ no está disponible actualmente en la seguridad de los puntos de conexión de MEM. Puede configurar esta regla mediante [MEM OMA-URI](enable-attack-surface-reduction.md#mem).

(<a id="fn1">2</a>) Algunas reglas de ASR generan ruido considerable, pero no bloquean la funcionalidad. Por ejemplo, si va a actualizar Chrome; Chrome accederá a lsass.exe; las contraseñas se almacenan en lsass en el dispositivo. Sin embargo, Chrome no debe tener acceso a lsass.exe de dispositivo local. Si habilita la regla para bloquear el acceso a lsass, generará una gran cantidad de eventos. Estos eventos son buenos eventos porque el proceso de actualización de software no debe tener acceso a lsass.exe. La habilitación de esta regla impedirá que las actualizaciones de Chrome accedan a lsass, pero no impedirá que Chrome se actualice; esto también sucede con otras aplicaciones que realizan llamadas innecesarias a lsass.exe. El _acceso en bloque a la regla lsass_ bloqueará las llamadas innecesarias a lsass, pero no bloqueará la ejecución de la aplicación.

### <a name="asr-infrastructure-requirements"></a>Requisitos de infraestructura de ASR

Aunque son posibles varios métodos de implementación de reglas ASR, esta guía se basa en una infraestructura que consta de:

- Azure Active Directory
- Microsoft Endpoint Management (MEM)
- dispositivos Windows 10 y Windows 11
- licencias de Microsoft Defender para punto de conexión E5 o Windows E5

Para aprovechar al máximo las reglas de ASR y los informes, se recomienda usar una licencia Microsoft 365 Defender E5 o Windows E5 y A5. Más información: [Requisitos mínimos para Microsoft Defender para punto de conexión](minimum-requirements.md).

>[!Note]
>Hay varios métodos para configurar reglas de ASR. Las reglas de ASR se pueden configurar mediante: Microsoft Endpoint Manager (MEM), PowerShell, समूह नीति, Microsoft System Center Configuration Manager (SCCM), MEM OMA-URI.
>Si usa una configuración de infraestructura diferente a la que aparece para _requisitos de infraestructura_ (anterior), puede obtener más información sobre la implementación de reglas de reducción de superficie expuesta a ataques mediante otras configuraciones aquí: [Habilitar reglas de reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md).  

### <a name="asr-rules-dependencies"></a>Dependencias de reglas de ASR

Microsoft Defender Antivirus debe estar habilitado y configurado como solución antivirus principal y debe estar en el modo siguiente:

- Solución antivirus/antimalware principal  
- Estado: modo activo

Microsoft Defender Antivirus no debe estar en ninguno de los modos siguientes:

- Pasiva
- Modo pasivo con detección y respuesta de puntos de conexión (EDR) en modo de bloque
- Examen periódico limitado (LPS)
- Desactivado

Consulte: [Protección entregada en la nube y antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).

### <a name="cloud-protection-maps-must-be-enabled-to-enable-asr-rules"></a>Cloud Protection (MAPS) debe estar habilitado para habilitar las reglas de ASR.

Microsoft Defender Antivirus funciona sin problemas con los servicios en la nube de Microsoft. Estos servicios de protección en la nube, también conocidos como Microsoft Advanced Protection Service (MAPS), mejoran la protección estándar en tiempo real, posiblemente proporcionando la mejor defensa antivirus. La protección en la nube es fundamental para evitar infracciones de malware y un componente crítico de las reglas de ASR.
[Active la protección proporcionada en la nube en Microsoft Defender Antivirus](enable-cloud-protection-microsoft-defender-antivirus.md).

### <a name="microsoft-defender-antivirus-components-must-be-current-versions-for-asr-rules"></a>Microsoft Defender los componentes de Antivirus deben ser versiones actuales de las reglas de ASR

Las siguientes versiones Microsoft Defender componentes antivirus no deben tener más de dos versiones anteriores a la versión más disponible actualmente:

- **Microsoft Defender versión de actualización de la plataforma antivirus**: Microsoft Defender plataforma antivirus se actualiza mensualmente.
- **Microsoft Defender versión del motor antivirus**: Microsoft Defender motor antivirus se actualiza mensualmente.
- **Microsoft Defender Inteligencia de seguridad antivirus**: Microsoft actualiza continuamente Microsoft Defender inteligencia de seguridad (también conocida como, definición y firma) para abordar las amenazas más recientes y para refinar la lógica de detección.

Mantener Microsoft Defender versiones de Antivirus actualizadas ayuda a reducir los resultados falsos positivos de las reglas de ASR y mejora Microsoft Defender capacidades de detección de antivirus. Para obtener más información sobre las versiones actuales y cómo actualizar los diferentes componentes de antivirus de Microsoft Defender, visite [Microsoft Defender compatibilidad con la plataforma antivirus](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="caveat"></a>Advertencia

Algunas reglas no funcionan bien si la aplicación y los scripts no firmados y desarrollados internamente tienen un uso elevado. Es más difícil implementar reglas ASR si no se aplica la firma de código.

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Probar las reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-test.md)

[Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-implement.md)

[Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-operationalize.md)

[Referencia de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-reference.md)

## <a name="reference"></a>Referencia

### <a name="blogs"></a>Blogs

[Reglas de reducción de superficie expuesta a ataques desmitificantes: Parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[Reglas de reducción de superficie expuesta a ataques desmitificantes: Parte 2](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[Reglas de reducción de superficie expuesta a ataques desmitificantes: Parte 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[Reglas de reducción de superficie expuesta a ataques desmitificantes: Parte 4](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-rules-collection"></a>Colección de reglas de ASR

[Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)

[Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware](attack-surface-reduction.md)

[Habilitación de reglas de reducción de superficie expuesta a ataques: configuraciones alternativas](enable-attack-surface-reduction.md)

[Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md)

[Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)

[Protección proporcionada en la nube y Antivirus de Windows Defender](cloud-protection-microsoft-defender-antivirus.md)

[Activar la protección proporcionada en la nube en Microsoft Defender Antivirus](enable-cloud-protection-microsoft-defender-antivirus.md)

[Configuración y validación de exclusiones basadas en la extensión, el nombre o la ubicación](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Compatibilidad con la plataforma Antivirus de Microsoft Defender](manage-updates-baselines-microsoft-defender-antivirus.md)

[Introducción al inventario en el centro de administración de Aplicaciones Microsoft 365](/deployoffice/admincenter/inventory)

[Creación de un plan de implementación para Windows](/windows/deployment/update/create-deployment-plan)

[Use el control de acceso basado en rol (RBAC) y las etiquetas de ámbito para ti distribuida en Intune](/mem/intune/fundamentals/scope-tags)

[Asignación de perfiles para dispositivos en Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>Sitios de administración

[Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)

[Reducción de la superficie expuesta a ataques](https://security.microsoft.com/asr?viewid=detections)

[Configuraciones de reglas de ASR](https://security.microsoft.com/asr?viewid=configuration)

[Exclusiones de reglas de ASR](https://security.microsoft.com/asr?viewid=exclusions)
