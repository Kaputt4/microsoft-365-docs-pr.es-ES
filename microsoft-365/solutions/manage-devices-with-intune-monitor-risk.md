---
title: Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-jun2020
keywords: ''
description: ''
ms.openlocfilehash: 8a4b2e8170d98261f0f3c6d1f77dd50e05de5d87
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129269"
---
# <a name="step-6-monitor-device-risk-and-compliance-to-security-baselines"></a>Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad

Después de que su organización haya implementado Microsoft Defender para punto de conexión, puede obtener más información y protección de los dispositivos mediante la integración de Microsoft Intune con Defender para punto de conexión. En el caso de los dispositivos móviles, esto incluye la capacidad de supervisar el riesgo del dispositivo como una condición de acceso. En el caso de los dispositivos Windows, puede supervisar el cumplimiento de estos dispositivos con las líneas base de seguridad. 

![Ilustración de integración de Defender para punto de conexión y Microsoft Intune](../media/devices/devices-defender-for-endpoint-steps.png#lightbox)

En esta ilustración: Microsoft Defender para punto de conexión aumenta considerablemente la sofisticación de la protección contra amenazas para dispositivos. Aunque Microsoft Intune permite establecer directivas de protección de aplicaciones y administrar dispositivos (incluidos los cambios de configuración), Defender para punto de conexión supervisa continuamente los dispositivos en busca de amenazas y puede tomar medidas automatizadas para corregir los ataques. 

En este artículo se incluyen estos pasos:
- Conectar Microsoft Intune a Defender para punto de conexión
- Supervisar el riesgo del dispositivo
- Supervisar el cumplimiento de las líneas base de seguridad

Si Defender para punto de conexión aún no se ha configurado, trabaje con el administrador de protección contra amenazas para [configurar el entorno piloto y de evaluación](../security/defender/eval-defender-endpoint-overview.md). Puede trabajar con el grupo piloto para probar las funcionalidades de este artículo.

## <a name="connect-microsoft-intune-to-defender-for-endpoint"></a>Conectar Microsoft Intune a Defender para punto de conexión

Configurar la integración de Microsoft Intune con Defender para endpoint es sencillo. Use este artículo: [Configurar Microsoft Defender para punto de conexión en Intune](/mem/intune/protect/advanced-threat-protection-configure). 

![Conectar Intune a Microsoft Defender para punto de conexión](../media/devices/connect-intune-to-microsoft-defender.png#lightbox)

## <a name="monitor-device-risk-as-a-condition-for-access"></a>Supervisar el riesgo del dispositivo como condición para el acceso

Con Microsoft Defender para punto de conexión implementado, puede aprovechar las señales de riesgo de amenazas. Esto le permite bloquear el acceso a los dispositivos en función de su puntuación de riesgo. Microsoft recomienda permitir el acceso a dispositivos con una puntuación de riesgo media o inferior.

Para Android e iOS/iPadOS, se pueden usar señales de amenazas dentro de las directivas de protección de aplicaciones (APP). Para obtener información sobre cómo configurar esto, consulte [Crear y asignar directiva de protección de aplicaciones para establecer el nivel de riesgo del dispositivo](/mem/intune/protect/advanced-threat-protection-configure).

Para todas las plataformas, puede establecer el nivel de riesgo en las directivas de cumplimiento de dispositivos existentes. Consulte [Crear y asignar directivas de cumplimiento para establecer el nivel de riesgo del dispositivo](/mem/intune/protect/advanced-threat-protection-configure).

## <a name="deploy-security-baselines-and-monitor-compliance-to-these-settings"></a>Implementar líneas base de seguridad y supervisar el cumplimiento de esta configuración

Se aplica a: Windows 10, Windows 11

El artículo, [Paso 5. Implementar perfiles de configuración,](manage-devices-with-intune-configuration-profiles.md)recomienda empezar a usar los perfiles de configuración mediante las líneas base de seguridad, disponibles para Windows 10 y Windows 11. Microsoft Defender para punto de conexión también incluye líneas base de seguridad que proporcionan opciones de configuración que optimizan todos los controles de seguridad de la pila de Defender para punto de conexión, incluida la configuración para la detección y respuesta de puntos de conexión (EDR). También se implementan mediante Microsoft Intune.

Lo ideal es que los dispositivos incorporados a Defender para punto de conexión se implementen en ambas líneas base: la línea base de seguridad de Windows Intune para proteger inicialmente Windows y, a continuación, la línea base de seguridad de Defender para punto de conexión superpuesta para configurar de forma óptima los controles de seguridad de Defender para punto de conexión.

Para beneficiarse de los datos más recientes sobre riesgos y amenazas y para minimizar los conflictos a medida que evolucionan las líneas base, aplique siempre las versiones más recientes de las líneas base en todos los productos en cuanto se publiquen. 

Con Defender para punto de conexión, puede supervisar el cumplimiento de estas líneas base. 

![La tarjeta para supervisar el cumplimiento de las líneas base de seguridad](../media/devices/secconmgmt-baseline-card.png#lightbox)

Para implementar líneas base de seguridad y supervisar el cumplimiento de esta configuración, siga los pasos de esta tabla.


|Paso  |Descripción  |
|---------|---------|
|1     |Revise los conceptos clave y compare Microsoft Defender para punto de conexión y las líneas base de seguridad de Windows Intune. <br><br>Consulte [Aumentar el cumplimiento de la línea de base de seguridad de Microsoft Defender para punto de conexión](../security/defender-endpoint/configure-machines-security-baseline.md) para obtener recomendaciones.<br><br>Consulte [Usar líneas base de seguridad para configurar dispositivos Windows en Intune ](/mem/intune/protect/security-baselines) revisar la lista de líneas base de seguridad disponibles y cómo evitar conflictos.         |
|2     |  Implemente la configuración de línea de base de seguridad de Windows para Intune. Es posible que ya lo haya hecho si ha seguido las instrucciones del [Paso 5. Implemente perfiles de configuración](manage-devices-with-intune-configuration-profiles.md).        |
|3    |  Implemente la configuración de línea de base de Defender para punto de conexión para Intune. Consulte [Administrar perfiles de línea de base de seguridad en Microsoft Intune](/mem/intune/protect/security-baselines-configure) para crear el perfil y elegir la versión de línea base.<br><br>También puede seguir las instrucciones siguientes: [Revisar y asignar la línea base de seguridad de Microsoft Defender para punto de conexión](../security/defender-endpoint/configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline).     |
|4     | En Defender para punto de conexión, revise la tarjeta de línea base de seguridad de [en la administración de la configuración de dispositivos](../security/defender-endpoint/configure-machines.md).          |
| | |

## <a name="next-steps"></a>Pasos siguientes
Vaya al [Paso 7. Implemente DLP con funcionalidades de protección de la información en puntos de conexión](manage-devices-with-intune-dlp-mip.md).