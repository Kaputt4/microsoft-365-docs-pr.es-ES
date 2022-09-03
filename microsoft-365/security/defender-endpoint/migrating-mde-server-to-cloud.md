---
title: Migración de servidores de Microsoft Defender para punto de conexión a Microsoft Defender for Cloud
description: Obtenga información sobre cómo migrar servidores de Microsoft Defender para punto de conexión a Microsoft Defender for Cloud.
keywords: migrate server, server, Microsoft Defender para punto de conexión server, Microsoft Defender for Cloud, MDE, azure, azure cloud, CSPM, CWP, cloud workload protection, threat protection, advanced threat protection, Microsoft Azure, multi-cloud connector
author: alekyaj
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: migrationguides
ms.date: 07/19/2022
ms.subservice: mde
ms.openlocfilehash: 2290a736ccb5460fac26db0263b475aadbcbd832
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67577549"
---
# <a name="migrating-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Migración de servidores de Microsoft Defender para punto de conexión a Microsoft Defender for Cloud

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Este artículo le guía en la migración de servidores de Microsoft Defender para punto de conexión (MDE) a Defender for Cloud.

[Microsoft Defender para punto de conexión](https://www.microsoft.com/security/business/endpoint-security/microsoft-defender-endpoint) (MDE) es una plataforma de seguridad de punto de conexión empresarial diseñada para ayudar a las redes empresariales a prevenir, detectar, investigar y responder a amenazas avanzadas.

[Microsoft Defender for Cloud](https://azure.microsoft.com/services/defender-for-cloud/) es una solución para la administración de la posición de seguridad en la nube (CSPM) y la protección de cargas de trabajo en la nube (CWP) que encuentra puntos débiles en la configuración de la nube. También ayuda a reforzar la posición de seguridad general de su entorno y puede proteger las cargas de trabajo en entornos híbridos y en varias nubes frente a amenazas en constante evolución.

Aunque ambos productos ofrecen funcionalidades de protección de servidores, Microsoft Defender for Cloud es nuestra solución principal para proteger los recursos de infraestructura, incluidos los servidores. 

## <a name="how-do-i-migrate-my-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Cómo migrar mis servidores de Microsoft Defender para punto de conexión a Microsoft Defender for Cloud?

Si tiene servidores incorporados a Defender para punto de conexión, el proceso de migración varía según el tipo de máquina, pero hay un conjunto de requisitos previos compartidos. 

Microsoft Defender for Cloud es un servicio basado en suscripciones en microsoft Azure Portal. Por lo tanto, Defender for Cloud y los planes subyacentes, como El plan 2 de Microsoft Defender para servidores, deben estar habilitados en las suscripciones de Azure.

Para habilitar Defender para servidores para máquinas virtuales de Azure y máquinas que no son de Azure conectadas a través de [servidores habilitados para Azure Arc](/azure/azure-arc/servers/overview), siga esta guía:

1. Si aún no usa Azure, planee el entorno siguiendo [azure Well-Architected Framework](/azure/architecture/framework/).

2. Habilite [Microsoft Defender for Cloud](/azure/defender-for-cloud/get-started) en sus suscripciones.

3. Habilite uno de los planes de Microsoft Defender for Server en [sus suscripciones](/azure/defender-for-cloud/enable-enhanced-security). En caso de que use el plan 2 de Defender para servidores, asegúrese de habilitarlo también en el área de trabajo de Log Analytics a la que están conectadas las máquinas; le permitirá usar características opcionales como supervisión de integridad de archivos, controles de aplicación adaptables y mucho más.

4. Asegúrese de que la [integración de MDE](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows) está habilitada en la suscripción. Si tiene suscripciones de Azure preexistedas, es posible que vea uno (o ambos) de los dos botones de participación que se muestran en la imagen siguiente.

     :::image type="content" source="images/mde-integration.png" alt-text="Captura de pantalla que muestra cómo habilitar la integración de MDE." lightbox="images/mde-integration.png":::

   Si tiene cualquiera de estos botones en el entorno, asegúrese de habilitar la integración para ambos. En las nuevas suscripciones, ambas opciones se habilitarán de forma predeterminada. En este caso, no verá estos botones en su entorno.

5. Asegúrese de que se cumplen los requisitos de conectividad de Azure Arc. Microsoft Defender for Cloud requiere que todas las máquinas locales y que no sean de Azure se conecten a través del agente de Azure Arc. Además, Azure Arc no admite todos los sistemas operativos compatibles con MDE. Por lo tanto, aprenda a planear [las implementaciones de Azure Arc aquí](/azure/azure-arc/servers/plan-at-scale-deployment).

6. *Recomienda:* Si desea ver los resultados de vulnerabilidades en Defender for Cloud, asegúrese de habilitar [Administración de vulnerabilidades de Microsoft Defender](/azure/defender-for-cloud/enable-data-collection?tabs=autoprovision-va) para Defender for Cloud.

   :::image type="content" source="images/enable-threat-and-vulnerability-management.png" alt-text="Captura de pantalla que muestra cómo habilitar la administración de vulnerabilidades." lightbox="images/enable-threat-and-vulnerability-management.png"::: 

## <a name="how-do-i-migrate-existing-azure-vms-to-microsoft-defender-for-cloud"></a>Cómo migrar máquinas virtuales de Azure existentes a Microsoft Defender for Cloud?

En el caso de las máquinas virtuales de Azure, no se requieren pasos adicionales, que se incorporan automáticamente a Microsoft Defender for Cloud, gracias a la integración nativa entre la plataforma de Azure y Defender for Cloud.

## <a name="how-do-i-migrate-on-premises-machines-to-microsoft-defender-for-servers"></a>Cómo migrar máquinas locales a Microsoft Defender para servidores?

Una vez cumplidos todos los requisitos previos, [conecte](/azure/defender-for-cloud/quickstart-onboard-machines?pivots=azure-arc) las máquinas locales a través de servidores conectados a Azure Arc.

## <a name="how-do-i-migrate-vms-from-aws-or-gcp-environments"></a>Cómo migrar máquinas virtuales desde entornos de AWS o GCP?

1. Cree un nuevo conector multin cloud en su suscripción. (Para obtener más información sobre el conector, consulte [Cuentas de AWS](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings) o [proyectos de GCP](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings).

2. En el conector de nube múltiple, habilite Defender para servidores en conectores [de AWS](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites) o [GCP](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings#configure-the-servers-plan) .

3. Habilite el aprovisionamiento automático en el conector de nube múltiple para el agente de Azure Arc, la extensión Microsoft Defender para punto de conexión, la evaluación de vulnerabilidades y, opcionalmente, la extensión de Log Analytics.

     :::image type="content" source="images/select-plans-aws-gcp.png" alt-text="Captura de pantalla que muestra cómo habilitar el aprovisionamiento automático para el agente de Azure Arc." lightbox="images/select-plans-aws-gcp.png":::

   Para obtener más información, consulte [Las funcionalidades multinube de Defender for Cloud](https://aka.ms/mdcmc).

## <a name="what-happens-once-all-migration-steps-are-completed"></a>¿Qué ocurre una vez completados todos los pasos de migración?

Una vez completados los pasos de migración pertinentes, Microsoft Defender for Cloud implementará la `MDE.Windows` extensión o `MDE.Linux` en las máquinas virtuales de Azure y las máquinas que no son de Azure conectadas a través de Azure Arc (incluidas las máquinas virtuales en proceso de AWS y GCP).

La extensión actúa como interfaz de administración e implementación, que orquestará y encapsulará los scripts de instalación de MDE dentro del sistema operativo y reflejará su estado de aprovisionamiento en el plano de administración de Azure. El proceso de instalación reconocerá una instalación existente de Defender para punto de conexión y la conectará a Defender for Cloud agregando automáticamente etiquetas de servicio de Defender para punto de conexión.

En caso de que tenga Windows Server 2012 máquinas R2 o 2016 aprovisionadas con la solución Microsoft Defender para punto de conexión heredada basada en Log Analytics, el proceso de implementación de Microsoft Defender for Cloud implementará la [solución unificada](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) de Defender para punto de conexión. Después de una implementación correcta, detendrá y deshabilitará el proceso heredado de Defender para punto de conexión en estas máquinas.
