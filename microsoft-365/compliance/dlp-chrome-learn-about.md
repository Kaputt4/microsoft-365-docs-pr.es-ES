---
title: Más información sobre la extensión de Microsoft Purview
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: La extensión de Microsoft Purview extiende la supervisión y el control de las actividades de archivo y acciones protectoras al explorador Google Chrome
ms.openlocfilehash: a74cfeb734f41622d491c8aaffe3a5e054479a2a
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65172249"
---
# <a name="learn-about-the-microsoft-purview-extension"></a>Más información sobre la extensión de Microsoft Purview

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La [prevención de pérdida de datos en punto de conexión (DLP en punto de conexión)](endpoint-dlp-learn-about.md) amplía la supervisión de la actividad y las capacidades de protección de la [Prevención de pérdida de datos (DLP) de Microsoft Purview](dlp-learn-about-dlp.md) a elementos confidenciales que estén en dispositivos con Windows 10. Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft Purview, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el [explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).

Una vez instalada la extensión en un dispositivo con Windows 10, las organizaciones podrán detectar si un usuario intenta acceder o cargar un elemento confidencial a un servicio en la nube mediante Google Chrome, y podrán aplicar acciones de protección mediante la DLP.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Actividades que puede supervisar y sobre las que puede tomar medidas

La extensión le permitirá auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.

actividad |description  | acciones compatibles de directiva|
|---------|---------|---------|
|archivo copiado en la nube  | Detecta si un usuario intenta cargar un elemento confidencial en un dominio de servicio restringido con el explorador Chrome. |auditar, bloquear con invalidación, bloquear|
|archivo impreso  |Detecta si un usuario trata de imprimir un elemento confidencial abierto en el explorador Chrome en una impresora local o de la red |auditar, bloquear con invalidación, bloquear|
|archivo copiado en el portapapeles |Se detecta cuando un usuario intenta copiar información de un elemento confidencial que se está viendo en el explorador Chrome y, a continuación, lo pega en otra aplicación, proceso o elemento. |auditar, bloquear con invalidación, bloquear|
|archivo copiado en un almacenamiento extraíble    | Detecta si un usuario intenta copiar un elemento o información confidencial de un elemento confidencial abierto en el explorador Chrome en un medio extraíble o dispositivo USB |auditar, bloquear con invalidación, bloquear|
|archivo copiado en el recurso compartido de red  |Detecta si un usuario intenta copiar un elemento o información confidencial de un elemento confidencial abierto en el explorador Chrome en un recurso compartido de red o unidad de red asignada.|auditar, bloquear con invalidación, bloquear |

## <a name="deployment-process"></a>Proceso de implementación
1. [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
2. [Herramientas y métodos de incorporación para dispositivos Windows 10](device-onboarding-overview.md)
3. [Instalar la extensión en los dispositivos de Windows 10](dlp-chrome-get-started.md)
4. [Cree o edite directivas de DLP](create-test-tune-dlp-policy.md) que limiten la carga a servicios en la nube, o el acceso por parte de acciones de exploradores no permitidos y aplíquelas a sus dispositivos de Windows 10

## <a name="next-steps"></a>Siguientes pasos

Consulte [Introducción a la extensión de Microsoft Purview](dlp-chrome-get-started.md) para ver procedimientos y escenarios completos de implementación.

## <a name="see-also"></a>Consulte también

- [Introducción a la extensión de Microsoft Purview](dlp-chrome-get-started.md)
- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Administración de riesgos internos](insider-risk-management.md)
