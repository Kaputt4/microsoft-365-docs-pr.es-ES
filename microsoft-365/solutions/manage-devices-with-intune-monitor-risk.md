---
title: Step 6. Monitor device risk and compliance to security baselines
ms.author: bcarter
author: brendacarter
f1.keywords:
- connect Intune to Defender
- monitor device risk
- monitor device compliance
- deploy security baselines
manager: dougeby
audience: ITPro
description: Obtenga información sobre cómo conectar Microsoft Intune a Defender para punto de conexión y supervisar el riesgo del dispositivo como una condición de acceso.
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- deploy security baselines
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: a532477d25d0eb3de07af08033f13c7a8112454c
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986562"
---
# <a name="step-6-monitor-device-risk-and-compliance-to-security-baselines"></a>Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad

Después de que su organización haya implementado Microsoft Defender para punto de conexión, puede obtener más información y protección de los dispositivos mediante la integración de Microsoft Intune con Defender para punto de conexión. En el caso de los dispositivos móviles, esto incluye la capacidad de supervisar el riesgo del dispositivo como una condición de acceso. En el caso de los dispositivos Windows, puede supervisar el cumplimiento de estos dispositivos con las líneas base de seguridad. 

La implementación de Microsoft Defender para punto de conexión incluye puntos de conexión de incorporación. Si usó Intune para incorporar puntos de conexión (recomendados), ya ha conectado Microsoft Intune a Defender para punto de conexión. Si usó un método diferente para incorporar puntos de conexión a Defender para punto de conexión, consulte [Configuración de Microsoft Defender para punto de conexión en Intune](/mem/intune/protect/advanced-threat-protection-configure) para asegurarse de que ha configurado la conexión de servicio a servicio entre Intune y Microsoft Defender para punto de conexión. 


![Ilustración de integración de Defender para punto de conexión y Microsoft Intune](../media/devices/devices-defender-for-endpoint-steps.png#lightbox)

En esta ilustración:
- Microsoft Defender para punto de conexión aumenta en gran medida la sofisticación de la protección contra amenazas para dispositivos. 
- Aunque Microsoft Intune permite establecer directivas de Protección de aplicaciones y administrar dispositivos (incluidos los cambios de configuración), Defender para punto de conexión supervisa continuamente los dispositivos en busca de amenazas y puede realizar acciones automatizadas para corregir ataques. 
- Puede usar Intune para incorporar dispositivos a Defender para punto de conexión. Al hacerlo, también está habilitando estos dispositivos para que funcionen con la prevención de pérdida de datos del punto de conexión de Microsoft Purview (DLP de punto de conexión).

En este artículo se incluyen estos pasos:
- Supervisar el riesgo del dispositivo
- Supervisar el cumplimiento de las líneas base de seguridad

Si Defender para punto de conexión aún no se ha configurado, trabaje con el administrador de protección contra amenazas para [configurar el entorno piloto y de evaluación](../security/defender/eval-defender-endpoint-overview.md). Puede trabajar con el grupo piloto para probar las funcionalidades de este artículo.

## <a name="monitor-device-risk-as-a-condition-for-access"></a>Supervisar el riesgo del dispositivo como condición para el acceso

Con Microsoft Defender para punto de conexión implementado, puede aprovechar las señales de riesgo de amenazas. Esto le permite bloquear el acceso a los dispositivos en función de su puntuación de riesgo. Microsoft recomienda permitir el acceso a dispositivos con una puntuación de riesgo media o inferior.

Para Android e iOS/iPadOS, se pueden usar señales de amenazas dentro de las directivas de protección de aplicaciones (APP). Para obtener información sobre cómo configurar esto, consulte [Crear y asignar directiva de protección de aplicaciones para establecer el nivel de riesgo del dispositivo](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level).

Para todas las plataformas, puede establecer el nivel de riesgo en las directivas de cumplimiento de dispositivos existentes. Consulte [Creación de una directiva de acceso condicional](/mem/intune/protect/advanced-threat-protection-configure#create-a-conditional-access-policy).

## <a name="deploy-security-baselines-and-monitor-compliance-to-these-settings"></a>Implementar líneas base de seguridad y supervisar el cumplimiento de esta configuración

Se aplica a: Windows 10, Windows 11

El artículo, [Paso 5. Implementar perfiles de configuración,](manage-devices-with-intune-configuration-profiles.md)recomienda empezar a usar los perfiles de configuración mediante las líneas base de seguridad, disponibles para Windows 10 y Windows 11. Microsoft Defender para punto de conexión también incluye líneas base de seguridad que proporcionan opciones de configuración que optimizan todos los controles de seguridad de la pila de Defender para punto de conexión, incluida la configuración para la detección y respuesta de puntos de conexión (EDR). También se implementan mediante Microsoft Intune.

Lo ideal es que los dispositivos incorporados a Defender para punto de conexión se implementen en ambas líneas base: la línea base de seguridad de Windows Intune para proteger inicialmente Windows y, a continuación, la línea base de seguridad de Defender para punto de conexión superpuesta para configurar de forma óptima los controles de seguridad de Defender para punto de conexión.

Para beneficiarse de los datos más recientes sobre riesgos y amenazas y minimizar los conflictos a medida que evolucionan las líneas base, aplique siempre las versiones más recientes de las líneas base en todos los productos en cuanto se publiquen. 

Con Defender para punto de conexión, puede supervisar el cumplimiento de estas líneas base. 

![La tarjeta para supervisar el cumplimiento de las líneas base de seguridad](../media/devices/secconmgmt-baseline-card.png#lightbox)

Para implementar líneas base de seguridad y supervisar el cumplimiento de esta configuración, siga los pasos de esta tabla.


|Paso  |Descripción  |
|---------|---------|
|1     |Revise los conceptos clave y compare Microsoft Defender para punto de conexión y las líneas base de seguridad de Windows Intune. <br><br>Consulte [Aumentar el cumplimiento de la línea de base de seguridad de Microsoft Defender para punto de conexión](../security/defender-endpoint/configure-machines-security-baseline.md) para obtener recomendaciones.<br><br>Consulte [Usar líneas base de seguridad para configurar dispositivos Windows en Intune ](/mem/intune/protect/security-baselines) revisar la lista de líneas base de seguridad disponibles y cómo evitar conflictos.         |
|2     |  Deploy Windows security baseline settings for Intune. You might have already accomplished this if you followed the guidance in [Step 5. Deploy configuration profiles](manage-devices-with-intune-configuration-profiles.md).        |
|3    |  Implemente la configuración de línea de base de Defender para punto de conexión para Intune. Consulte [Administrar perfiles de línea de base de seguridad en Microsoft Intune](/mem/intune/protect/security-baselines-configure) para crear el perfil y elegir la versión de línea base.<br><br>También puede seguir las instrucciones siguientes: [Revisar y asignar la línea base de seguridad de Microsoft Defender para punto de conexión](../security/defender-endpoint/configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline).     |
|4     | En Defender para punto de conexión, revise la tarjeta de línea base de seguridad de [en la administración de la configuración de dispositivos](../security/defender-endpoint/configure-machines.md).          |


## <a name="next-steps"></a>Pasos siguientes
Vaya al [Paso 7. Implemente DLP con funcionalidades de protección de la información en puntos de conexión](manage-devices-with-intune-dlp-mip.md).