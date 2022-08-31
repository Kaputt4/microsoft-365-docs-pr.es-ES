---
title: Revisión de los requisitos de arquitectura de Microsoft Defender para punto de conexión y los conceptos clave
description: El diagrama técnico de Microsoft Defender para punto de conexión en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de compilar el laboratorio de prueba o el entorno piloto.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 5a446047168394fd8506f2aaed911ce3af284f10
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67467973"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Revisión de los requisitos de arquitectura de Microsoft Defender para punto de conexión y los conceptos clave

**Se aplica a:** Microsoft 365 Defender

Este artículo le guiará en el proceso de configuración de la evaluación para Microsoft Defender para punto de conexión entorno.

Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-endpoint-overview.md).

Antes de habilitar Microsoft Defender para punto de conexión, asegúrese de comprender la arquitectura y de que puede cumplir los requisitos.

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

En el diagrama siguiente se muestra Microsoft Defender para punto de conexión arquitectura e integraciones. 

:::image type="content" source="../../media/defender/m365-defender-endpoint-architecture.png" alt-text="Los pasos para agregar Microsoft Defender para Office al entorno de evaluación de Defender" lightbox="../../media/defender/m365-defender-endpoint-architecture.png":::

En la tabla siguiente se describe la ilustración.

Llamada | Descripción
:---|:---|
1 | Los dispositivos se abordan a través de una de las herramientas de administración admitidas. 
2 | Los dispositivos integrados proporcionan y responden a Microsoft Defender para punto de conexión datos de señal.
3 | Los dispositivos administrados se unen o se inscriben en Azure Active Directory.
4 | Los dispositivos Windows unidos a un dominio se sincronizan con Azure Active Directory mediante Azure Active Directory Connect.
5 | Microsoft Defender para punto de conexión alertas, investigaciones y respuestas se administran en Microsoft 365 Defender.

## <a name="understand-key-concepts"></a>Descripción de los conceptos clave

En la tabla siguiente se identificaron conceptos clave que son importantes comprender al evaluar, configurar e implementar Microsoft Defender para punto de conexión: 

Concepto | Descripción | Más información
:---|:---|:---|
Portal de administración | Microsoft 365 Defender portal para supervisar y ayudar a responder a alertas de posibles infracciones de datos o actividad de amenazas persistentes avanzadas. | [Introducción al portal de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/portal-overview)
Reducción de la superficie expuesta a ataques | Ayude a reducir las superficies expuestas a ataques minimizando los lugares donde su organización es vulnerable a ciberataques y ataques. | [Introducción a la reducción de la superficie expuesta a ataques](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)
Detección y respuesta de puntos de conexión | Las funcionalidades de detección y respuesta de puntos de conexión proporcionan detecciones avanzadas de ataques casi en tiempo real y accionables. | [Introducción a las funcionalidades de detección y respuesta de puntos de conexión](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)
Bloqueo y contención del comportamiento | Las funcionalidades de bloqueo y contención del comportamiento pueden ayudar a identificar y detener amenazas, en función de sus comportamientos y de los árboles de proceso, incluso cuando la amenaza ha comenzado a ejecutarse. | [Bloqueo y contención de comportamientos](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)
Investigación y respuesta automatizadas | La investigación automatizada usa varios algoritmos de inspección basados en procesos que usan los analistas de seguridad y están diseñados para examinar alertas y tomar medidas inmediatas para resolver infracciones. | [Uso de investigaciones automatizadas para investigar y corregir amenazas](/microsoft-365/security/defender-endpoint/automated-investigations)
Búsqueda avanzada | La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas que le permite explorar hasta 30 días de datos sin procesar para poder inspeccionar de forma proactiva eventos en la red para localizar indicadores de amenazas y entidades. | [Introducción a la búsqueda avanzada](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)
Análisis de amenazas | Análisis de amenazas es un conjunto de informes de expertos investigadores de seguridad de Microsoft que cubren las amenazas más relevantes. | [Seguir las amenazas emergentes y responder a ellas](/microsoft-365/security/defender-endpoint/threat-analytics)


Para obtener información más detallada sobre las funcionalidades incluidas con Microsoft Defender para punto de conexión, consulte [¿Qué es Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)?

## <a name="siem-integration"></a>Integración de SIEM

Puede integrar Microsoft Defender para punto de conexión con Microsoft Sentinel para analizar de forma más completa los eventos de seguridad en toda la organización y crear cuadernos de estrategias para una respuesta eficaz e inmediata. 

Microsoft Defender para punto de conexión también se pueden integrar en otras soluciones de administración de eventos e información de seguridad (SIEM). Para obtener más información, consulte [Habilitación de la integración siem en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/enable-siem-integration).


## <a name="next-steps"></a>Pasos siguientes
[Habilitar la evaluación](eval-defender-endpoint-enable-eval.md)

Vuelva a la introducción para [Evaluar Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
