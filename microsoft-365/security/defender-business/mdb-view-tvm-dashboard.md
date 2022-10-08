---
title: Vea el panel de Administración de vulnerabilidades de Microsoft Defender en Microsoft Defender para Empresas
description: Use el panel de Administración de vulnerabilidades de Microsoft Defender para ver los elementos importantes a abordar en Defender para empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/02/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.custom: intro-get-started
ms.openlocfilehash: d3bfaa93e390a61d7c70e3763929247398a59481
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68110609"
---
# <a name="use-your-vulnerability-management-dashboard-in-microsoft-defender-for-business"></a>Use el panel de administración de vulnerabilidades en Microsoft Defender para Empresas

Defender for Business incluye un panel de administración de vulnerabilidades diseñado para ahorrar tiempo y esfuerzo al equipo de seguridad. Además de proporcionar una puntuación de exposición, ese panel le permite ver información sobre los dispositivos expuestos y ver las recomendaciones de seguridad pertinentes. Puede usar el panel de Administración de vulnerabilidades de Defender para:

- Vea la puntuación de exposición, que está asociada a los dispositivos de su empresa.
- Vea las principales recomendaciones de seguridad, como solucionar problemas de comunicación con dispositivos, activar la protección del firewall o actualizar las definiciones Microsoft Defender Antivirus.
- Vea las actividades de corrección, como los archivos enviados a cuarentena o las vulnerabilidades encontradas en los dispositivos.

## <a name="vulnerability-management-features-and-capabilities"></a>Características y funcionalidades de administración de vulnerabilidades

Las características y funcionalidades de administración de vulnerabilidades de Microsoft Defender para Empresas incluyen:

- **Panel**: proporciona información sobre vulnerabilidades, exposición y recomendaciones. Puede ver las actividades de corrección recientes, los dispositivos expuestos y las formas de mejorar la seguridad general de su empresa. Cada tarjeta del panel incluye un vínculo a información más detallada o a una página donde puede realizar una acción recomendada.

    :::image type="content" source="media/mdb-mdvm-dashboard.png" alt-text="Captura de pantalla de Administración de vulnerabilidades de Microsoft Defender Panel." lightbox="media/mdb-mdvm-dashboard.png":::

- **Recomendaciones**: enumera las recomendaciones de seguridad actuales y la información de amenazas relacionada que se debe revisar y considerar. Al seleccionar un elemento de la lista, se abre un panel flotante con más detalles sobre las amenazas y las acciones que puede realizar.

- **Corrección**: enumera las acciones de corrección y su estado. Las actividades de corrección pueden incluir el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y el bloqueo de la ejecución de una amenaza detectada. Las actividades de corrección también pueden incluir la actualización de un dispositivo, la ejecución de un examen antivirus y mucho más. 

    :::image type="content" source="media/mdb-mdvm-remediation.png" alt-text="Captura de pantalla de Administración de vulnerabilidades de Microsoft Defender-Remediation." lightbox="media/mdb-mdvm-remediation.png":::

- **Inventarios**: enumera el software y las aplicaciones actualmente en uso en su organización. Verá exploradores, sistemas operativos y otro software en los dispositivos, junto con las debilidades y amenazas identificadas.

- **Puntos débiles**: enumera las vulnerabilidades junto con el número de dispositivos expuestos en su organización. Si ve "0" en la columna Dispositivos expuestos, no es necesario realizar ninguna acción inmediata. Sin embargo, puede obtener más información sobre cada vulnerabilidad que aparece en esta página. Seleccione un elemento para obtener más información sobre él y lo que puede hacer para mitigar la posible amenaza para su empresa.

    :::image type="content" source="media/mdb-mdvm-weakness-details.png" alt-text="Captura de pantalla de Administración de vulnerabilidades de Microsoft Defender-Debilidades." lightbox="media/mdb-mdvm-weakness-details.png":::

- **Escala de tiempo de** eventos: enumera las vulnerabilidades que afectan a la organización en una vista de escala de tiempo.   

[Más información sobre Administración de vulnerabilidades de Microsoft Defender](../defender-vulnerability-management/defender-vulnerability-management.md).

## <a name="next-steps"></a>Pasos siguientes

- [Prueba de tutoriales y simulaciones en Defender para empresas](mdb-tutorials.md)
- [Incorporar dispositivos a Defender para Empresas](mdb-onboard-devices.md)
- [Visualización o edición de directivas en Defender para empresas](mdb-view-edit-create-policies.md)
