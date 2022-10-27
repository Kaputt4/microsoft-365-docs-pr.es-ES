---
title: Administración de riesgos internos
description: Aprenda a configurar la administración de riesgos internos. La administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo.
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
- highpri
ms.openlocfilehash: c3d4e6662806cbf2a821e0ef4228e5efa87a012e
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733601"
---
# <a name="insider-risk-management"></a>Administración de riesgos internos

> [!IMPORTANT]
> Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Los empleados ahora tienen más acceso para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, a la vez que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados. Estos riesgos incluyen el posible robo de datos al dejar a los empleados y el riesgo de fugas de datos de información fuera de su organización por uso compartido accidental o intenciones malintencionadas.

Administración de riesgos internos de Microsoft Purview usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar y actuar rápidamente en actividades potencialmente de riesgo. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo. Después de identificar los riesgos, puede tomar medidas para mitigar estos riesgos y, si es necesario, abrir casos de investigación y tomar las medidas legales adecuadas.

Vea los vídeos siguientes para obtener información sobre cómo la administración de riesgos internos puede ayudar a su organización a prevenir, detectar y contener riesgos:


**Solución de administración de riesgos internos & desarrollo**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]
<br>

**Flujo de trabajo de administración de riesgos internos**:
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OUXB]

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="configure-insider-risk-management"></a>Configuración de la administración de riesgos internos

Siga estos pasos para configurar la administración de riesgos internos para su organización:

![Pasos de administración de riesgos internos de soluciones de riesgo internos](../media/ir-solution-ir-steps.png)

1. Más información sobre la [administración de riesgos internos](insider-risk-management.md)
2. Planeamiento de [la administración de riesgos internos y comprobación de licencias](insider-risk-management-plan.md)
3. Configuración de [la administración de riesgos internos](insider-risk-management-settings.md)
4. Configuración de [permisos](insider-risk-management-configure.md#step-1-required-enable-permissions-for-insider-risk-management) y [requisitos previos de directiva & conectores](insider-risk-management-configure.md#step-4-recommended-configure-prerequisites-for-policies)
5. Creación y configuración de [directivas de administración de riesgos internos](insider-risk-management-configure.md#step-6-required-create-an-insider-risk-management-policy)

## <a name="more-information-about-insider-risk-management"></a>Más información sobre la administración de riesgos internos

- [Administración de directivas de riesgo internos](insider-risk-management-policies.md)
- [Investigar alertas de riesgo interno](insider-risk-management-activities.md)
- [Actuar sobre casos de riesgo interno](insider-risk-management-cases.md)
