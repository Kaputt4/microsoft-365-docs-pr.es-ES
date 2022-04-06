---
title: Requisitos previos de implementación de reglas de ASR
description: Proporciona información general y instrucciones de requisitos previos sobre la implementación de reglas de reducción de superficie de ataque (ASR).
keywords: Implementación de reglas de reducción de superficie de ataque, implementación de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades, anti exploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 50b22bc5d1cf81754cc690808d67b6026991e296
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468851"
---
# <a name="asr-rules-deployment-prerequisites"></a>Requisitos previos de implementación de reglas de ASR

## <a name="before-you-begin"></a>Antes de empezar

Las superficies de ataque son todos los lugares donde su organización es vulnerable a ciberamenazas y ataques. Las superficies de ataque de la organización incluyen todos los lugares donde un atacante podría poner en peligro los dispositivos o redes de la organización. Reducir la superficie de ataque significa proteger los dispositivos y la red de la organización, lo que deja a los atacantes con menos formas de atacar. La configuración de reglas de reducción de superficie de ataque (ASR), una de las muchas características de seguridad que se encuentran en Microsoft Defender para endpoint, puede ser útil.

Las reglas ASR se aplican a determinados comportamientos de software, como:

- Iniciar archivos ejecutables y scripts que intenten descargar o ejecutar archivos
- Ejecución de scripts ofuscados o sospechosos
- Comportamientos que las aplicaciones normalmente no se producen durante el trabajo diario normal

Al reducir las distintas superficies de ataque, puedes ayudar a evitar que los ataques se sucedan en primer lugar.

Durante la preparación inicial, es fundamental que comprenda las capacidades de los sistemas que va a poner en marcha. Comprender las capacidades le ayudará a determinar qué reglas de ASR son más importantes para proteger su organización. Además, hay varios requisitos previos a los que debe atender para preparar la implementación de ASR.

>[!IMPORTANT]
>En esta guía se proporcionan imágenes y ejemplos que le ayudarán a decidir cómo configurar reglas ASR; es posible que estas imágenes y ejemplos no reflejen las mejores opciones de configuración para el entorno.

Antes de empezar, revisa [Información](overview-attack-surface-reduction.md) general sobre la reducción de superficie de ataque y [Desmitificando](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) las reglas de reducción de superficie de ataque: parte 1 para obtener información básica. Para comprender las áreas de cobertura y posible impacto, familiarícese con el conjunto actual de reglas ASR; consulta [Referencia de reglas de reducción de superficie de ataque](attack-surface-reduction-rules-reference.md).

Las reglas ASR son solo una funcionalidad de las capacidades de reducción de superficie de ataque dentro de Microsoft Defender para endpoint. En este documento se detallarán más detalles sobre cómo implementar las reglas ASR de forma eficaz para detener amenazas avanzadas como ransomware operado por humanos y otras amenazas.  

### <a name="rules-by-category"></a>Reglas por categoría

Como se describe en [Usar](attack-surface-reduction.md) reglas de reducción de superficie de ataque para evitar infecciones de malware, hay varias reglas de reducción de superficie de ataque dentro de MDE que puedes habilitar para proteger tu organización. A continuación se descompuestos las reglas por categoría:

<br/>

| Amenazas polimórficas | Movimiento lateral & robo de credenciales | Reglas de aplicaciones de productividad |  Reglas de correo electrónico | Reglas de script | Reglas misc |
|:---|:---|:---|:---|:---|:---|
| Bloquear la ejecución de archivos ejecutables a menos que cumplan con una prevalencia (1000 máquinas), la antigüedad (24 horas) o los criterios de lista de confianza | Bloquear creaciones de proceso que se originen en comandos PSExec y WMI | Bloquear Office aplicaciones de creación de contenido ejecutable | Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | Bloquear código de JS/VBS/PS/macro ofuscado | Bloquear el uso indebido de controladores firmados vulnerables explotados <sup>[[1](#fn1)]<sup></sup>  |
| Bloquear procesos que no son de confianza y sin firma que se ejecutan desde USB | Bloquear el robo de credenciales del subsistema Windows autoridad de seguridad local (lsass.exe)<sup>[[2](#fn1)]<sup></sup>   | Bloquear Office aplicaciones para crear procesos secundarios |  Bloquear solo Office aplicaciones de comunicación para crear procesos secundarios | Bloquear JS/VBS para que no inicie contenido ejecutable descargado | |
| Usar protección avanzada contra ransomware | Bloquear la persistencia a través de la suscripción de eventos WMI | Bloquear Office aplicaciones para que no inyecten código en otros procesos | Bloquear Office aplicaciones de comunicación para que no creen procesos secundarios | | |
| | | Impedir que Adobe Reader cree procesos secundarios | | | |

(<a id="fn1">1</a>) El uso indebido de bloqueo de controladores firmados _vulnerables_ explotados no está disponible actualmente en la seguridad de extremo de MEM. Puede configurar esta regla con [MEM OMA-URI](enable-attack-surface-reduction.md#mem).

(<a id="fn1">2</a>) Algunas reglas ASR generan un ruido considerable, pero no bloquean la funcionalidad. Por ejemplo, si estás actualizando Chrome; Chrome accederá a lsass.exe; las contraseñas se almacenan en lsass en el dispositivo. Sin embargo, Chrome no debe tener acceso a los dispositivos lsass.exe. Si habilita la regla para bloquear el acceso a lsass, generará una gran cantidad de eventos. Estos eventos son buenos eventos porque el proceso de actualización de software no debe tener acceso a lsass.exe. Habilitar esta regla impedirá que las actualizaciones de Chrome tengan acceso a lsass, pero no impedirá que Chrome se actualice; esto también ocurre con otras aplicaciones que hacen llamadas innecesarias a lsass.exe. La _regla bloquear el acceso a lsass_ bloqueará las llamadas innecesarias a lsass, pero no bloqueará la ejecución de la aplicación.

### <a name="infrastructure-requirements"></a>Requisitos de infraestructura

Aunque son posibles varios métodos de implementación de reglas ASR, esta guía se basa en una infraestructura que consta de:

- Azure Active Directory
- Microsoft Endpoint Management (MEM)
- Windows 10 y Windows 11 dispositivos
- Microsoft Defender para endpoint E5 o Windows licencias E5

Para aprovechar al máximo las reglas de ASR y los informes, se recomienda usar una Microsoft 365 Defender E5 o Windows de E5 y A5. Más información: [Requisitos mínimos para Microsoft Defender para endpoint](minimum-requirements.md).

>[!Note]
>Existen varios métodos para configurar reglas ASR. Las reglas ASR se pueden configurar mediante: Microsoft Endpoint Manager (MEM), PowerShell, directiva de grupo, Microsoft System Center Configuration Manager (SCCM), MEM OMA-URI.
>Si usas una configuración de infraestructura diferente a la que se muestra para los requisitos de _infraestructura (arriba_ ), puedes obtener más información sobre cómo implementar reglas de reducción de superficie de ataque con otras configuraciones aquí: Habilitar reglas de reducción de superficie de [ataque](enable-attack-surface-reduction.md).  

### <a name="asr-rules-dependencies"></a>Dependencias de reglas ASR

Antivirus de Microsoft Defender debe estar habilitado y configurado como solución antivirus principal y debe estar en el siguiente modo:

- Solución antivirus/antimalware principal  
- Estado: modo activo

Antivirus de Microsoft Defender no debe estar en ninguno de los siguientes modos:

- Pasivo
- Modo pasivo con detección y respuesta de extremo (EDR) en modo de bloqueo
- Examen periódico limitado (LPS)
- Desactivado

Vea: [Protección de entrega en la nube y Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).

### <a name="cloud-protection-maps-must-be-enabled"></a>La protección en la nube (MAPS) debe estar habilitada

Antivirus de Microsoft Defender funciona sin problemas con los servicios en la nube de Microsoft. Estos servicios de protección en la nube, también denominados Servicio de protección avanzada de Microsoft (MAPS), mejoran la protección estándar en tiempo real, lo que podría proporcionar la mejor defensa antivirus. La protección en la nube es fundamental para evitar infracciones de malware y un componente crítico de las reglas ASR.
[Active la protección entregada en la nube en Antivirus de Microsoft Defender](enable-cloud-protection-microsoft-defender-antivirus.md).

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Antivirus de Microsoft Defender componentes deben ser versiones actuales

Las siguientes Antivirus de Microsoft Defender de componentes no deben tener más de dos versiones anteriores a la versión más disponible actualmente:

- **Antivirus de Microsoft Defender versión de actualización de** la plataforma: Antivirus de Microsoft Defender se actualiza mensualmente.
- **Antivirus de Microsoft Defender versión del motor**: Antivirus de Microsoft Defender motor se actualiza mensualmente.
- **Antivirus de Microsoft Defender inteligencia de** seguridad: Microsoft actualiza continuamente la inteligencia de seguridad de Microsoft Defender (también conocida como, definición y firma) para abordar las amenazas más recientes y para refinar la lógica de detección.

Mantener Antivirus de Microsoft Defender versiones actuales ayuda a reducir las reglas ASR falsos resultados positivos y mejora las Antivirus de Microsoft Defender de detección. Para obtener más información sobre las versiones actuales y cómo actualizar los distintos componentes de Antivirus de Microsoft Defender, [visite Antivirus de Microsoft Defender soporte técnico de la plataforma](manage-updates-baselines-microsoft-defender-antivirus.md).

### <a name="caveat"></a>Advertencia

Algunas reglas no funcionan bien si la aplicación y los scripts no firmados y desarrollados internamente tienen un uso alto. Es más difícil implementar reglas ASR si no se aplica la firma de código.

## <a name="asr-rules-deployment-steps"></a>Pasos de implementación de reglas ASR

Al igual que con cualquier implementación nueva a gran escala que podría afectar potencialmente a las operaciones de línea de negocio, es importante ser metódico en la planeación y la implementación. Debido a las potentes capacidades de las reglas ASR para evitar malware, es necesario planear e implementar cuidadosamente estas reglas para garantizar que funcionen mejor para los flujos de trabajo de clientes únicos. Para trabajar en su entorno, debe planear, probar, implementar y poner en funcionamiento cuidadosamente las reglas ASR.  

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-deployment-phases.png" alt-text="Fases de implementación de reglas de ASR" lightbox="images/asr-rules-deployment-phases.png":::

>[!Note]
>Para los clientes que usan un HIPS que no es de Microsoft y están haciendo la transición a Microsoft Defender para las reglas de reducción de superficie de ataque de extremo: Microsoft aconseja a los clientes que ejecuten su solución DE HIPS en paralelo con la implementación de reglas ASR hasta el momento en que cambies del modo Auditoría al modo de bloqueo. Ten en cuenta que debes contactar con el proveedor de antivirus de terceros para obtener recomendaciones de exclusión.  

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Fase 1: Planificar](attack-surface-reduction-rules-deployment-plan.md)

[Fase 2: Probar](attack-surface-reduction-rules-deployment-test.md)

[Fase 3: Implementar](attack-surface-reduction-rules-deployment-implement.md)

[Fase 4: Operar](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="reference"></a>Referencia

### <a name="blogs"></a>Blogs

[Reglas de reducción de superficie de ataque desmitificantes: parte 1](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[Desmitificando reglas de reducción de superficie de ataque- Parte 2](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[Desmitificando reglas de reducción de superficie de ataque- Parte 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[Desmitificando reglas de reducción de superficie de ataque- Parte 4](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>Colección ASR

[Introducción a la reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)

[Usar reglas de reducción de la superficie expuesta a ataques para evitar la infección de malware](attack-surface-reduction.md)

[Habilitar las reglas de la reducción de superficie expuesta a ataques](enable-attack-surface-reduction.md)

[Referencia de reglas de reducción de superficie de ataque](attack-surface-reduction-rules-reference.md)

[Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)

[Protección proporcionada en la nube y Antivirus de Windows Defender](cloud-protection-microsoft-defender-antivirus.md)

[Activar la protección entregada en la nube en Antivirus de Microsoft Defender](enable-cloud-protection-microsoft-defender-antivirus.md)

[Configurar y validar exclusiones en función de la extensión, el nombre o la ubicación](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Antivirus de Microsoft Defender de plataforma](manage-updates-baselines-microsoft-defender-antivirus.md)

[Información general sobre el inventario en el centro Aplicaciones Microsoft 365 administración](/deployoffice/admincenter/inventory)

[Crear un plan de implementación para Windows](/windows/deployment/update/create-deployment-plan)

[Usar el control de acceso basado en roles (RBAC) y las etiquetas de ámbito para la TI distribuida en Intune](/mem/intune/fundamentals/scope-tags)

[Asignación de perfiles para dispositivos en Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>Sitios de administración

[Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)

[Reducción de la superficie expuesta a ataques](https://security.microsoft.com/asr?viewid=detections)

[Reglas de ASR Configuraciones](https://security.microsoft.com/asr?viewid=configuration)

[Exclusiones de reglas ASR](https://security.microsoft.com/asr?viewid=exclusions)
