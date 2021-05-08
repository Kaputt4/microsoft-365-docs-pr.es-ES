---
title: Protección proporcionada en la nube y Antivirus de Windows Defender
description: Obtenga información sobre la protección y la protección entregadas en la nube Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, av de última generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección entregada en la nube
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: d95f8dec433f29dea0fd5f7f718f34f571b790d4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274813"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>Usar tecnologías de última generación en Antivirus de Microsoft Defender a través de la protección entregada en la nube

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- Antivirus de Microsoft Defender

Las tecnologías de última generación de Microsoft Antivirus de Microsoft Defender protección automatizada casi instantánea contra amenazas nuevas y emergentes. Para identificar las nuevas amenazas de forma dinámica, estas tecnologías funcionan con grandes conjuntos de datos interconectados en Microsoft Intelligent Security Graph y potentes sistemas de inteligencia artificial (AI) controlados por modelos avanzados de aprendizaje automático.  

Antivirus de Microsoft Defender varias tecnologías de detección y prevención para ofrecer una protección precisa, en tiempo real e inteligente. [Conozca las tecnologías avanzadas en el núcleo de La](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)protección de última generación de Microsoft Defender para endpoint.
![Lista de motores antivirus de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Para aprovechar la potencia y la velocidad de estas tecnologías de próxima generación, Antivirus de Microsoft Defender funciona sin problemas con los servicios en la nube de Microsoft. Estos servicios de protección en la nube, también denominados Servicio de protección avanzada de Microsoft (MAPS), mejoran la protección estándar en tiempo real, proporcionando posiblemente la mejor defensa antivirus. 

>[!NOTE]
>El Antivirus de Microsoft Defender en la nube es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión. Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube, sino que usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a un ritmo mucho más rápido que las actualizaciones de inteligencia de seguridad tradicionales.

Con la protección entregada en la nube, las tecnologías de última generación proporcionan una identificación rápida de las nuevas amenazas, a veces incluso antes de que una sola máquina se infecte. Vea el siguiente vídeo sobre microsoft AI y Antivirus de Microsoft Defender en acción: 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Para comprender cómo las tecnologías de última generación acortan el tiempo de entrega de protección a través de la nube, vea el siguiente vídeo: 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Lea las siguientes entradas de blog para obtener información detallada sobre la protección en la nube y microsoft AI: 

- [Por Antivirus de Microsoft Defender es el más implementado en la empresa](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [La supervisión del comportamiento combinada con el aprendizaje automático estropea una campaña masiva de minería de monedas Dofoil](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Cómo la inteligencia artificial detuvo un brote de Emotet](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonar un conejito malo: defensas Antivirus de Microsoft Defender aprendizaje automático en capas](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Antivirus de Microsoft Defender de protección en la nube: defensa avanzada en tiempo real contra malware nunca visto](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>Obtener protección de entrega en la nube 

La protección entregada en la nube está habilitada de forma predeterminada. Sin embargo, es posible que deba volver a habilitarlo si se ha deshabilitado como parte de directivas organizativas anteriores.

Las organizaciones que Windows 10 E5 también pueden aprovechar las actualizaciones de inteligencia dinámica de emergencia, que proporcionan protección casi en tiempo real frente a amenazas emergentes. Al activar la protección entregada en la nube, las correcciones para problemas de malware se pueden entregar a través de la nube en cuestión de minutos, en lugar de esperar a la siguiente actualización.

>[!TIP]
>También puedes visitar el sitio web Windows Defender Testground en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

En la tabla siguiente se describen las diferencias en la protección entregada en la nube entre las versiones recientes de Windows y Configuration Manager.

|Versión del sistema operativo o aplicación de servicio |Etiqueta de servicio de protección en la nube  |Nivel de informes (nivel de pertenencia a MAPS)  |Período de tiempo de espera de bloqueo de nube  |
|---------|---------|---------|---------|
|Windows 8.1 (directiva de grupo)     |Servicio de protección avanzada de Microsoft   |Básico, Avanzado   |No         |
|Windows 10, versión 1607 (directiva de grupo)  |Servicio de protección avanzada de Microsoft      |Opciones avanzadas         |No         |
|Windows 10, versión 1703 o posterior (directiva de grupo)      |Protección basada en la nube      |Opciones avanzadas         |Configurable         |
|System Center 2012 Configuration Manager  |      N/A         |Depende de Windows versión         |No configurable |
|Microsoft Endpoint Manager (rama actual)         |Servicio de protección en la nube         |Depende de Windows versión          |Configurable         |
|Microsoft Intune     |Servicio de protección avanzada de Microsoft         |Depende de Windows versión         |Configurable         |

También puede configurar los Antivirus de Microsoft Defender recibir automáticamente nuevas actualizaciones de protección basadas [en informes de nuestro servicio en la nube.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)


## <a name="tasks"></a>Tasks

- [Habilitar la protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md). Puede habilitar la protección entregada en la nube con Microsoft Endpoint Configuration Manager, directiva de grupo, Microsoft Intune y cmdlets de PowerShell.

- [Especifique el nivel de protección entregado en la nube.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Puede especificar el nivel de protección ofrecido por la nube con la directiva de grupo y Microsoft Endpoint Configuration Manager. El nivel de protección afectará a la cantidad de información compartida con la nube y a la forma agresiva en que se bloquean los nuevos archivos.

- [Configurar y validar conexiones de red para Antivirus de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md). Hay determinadas direcciones URL de Microsoft a las que la red y los puntos de conexión deben poder conectarse para que la protección entregada en la nube funcione de forma eficaz. En este artículo se enumeran las direcciones URL que se deben permitir mediante firewall o reglas de filtrado de red, e instrucciones para confirmar que la red está correctamente inscrita en la protección entregada en la nube.

- [Configurar la característica de bloque a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md). La característica "bloquear a primera vista" puede bloquear malware nuevo en cuestión de segundos, sin tener que esperar horas para la inteligencia de seguridad tradicional. Puede habilitarla y configurarla con Microsoft Endpoint Manager y directiva de grupo.

- [Configurar el período de tiempo de espera del bloque de nube.](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) Antivirus de Microsoft Defender bloquear la ejecución de archivos sospechosos mientras consulta nuestro servicio de protección entregado en la nube. Puede configurar la cantidad de tiempo que se impedirá que el archivo se ejecute con Microsoft Endpoint Manager directiva de grupo.