---
title: Revisar las acciones de corrección en Microsoft Defender para Empresas
description: Vea las correcciones que se han tomado en las amenazas detectadas con Defender for Business. Puede ver las acciones en el Centro de acciones en el portal de Microsoft 365 Defender.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5c73b840b127770c4581dda4d03b3c95066df515
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089536"
---
# <a name="review-remediation-actions-in-the-action-center"></a>Revisión de las acciones de corrección en el Centro de acciones

A medida que se detectan amenazas, entran en juego las acciones de corrección. En función de la amenaza en particular y de cómo se configure la configuración de seguridad, es posible que las acciones de corrección se realicen automáticamente o solo tras la aprobación. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y la eliminación de una tarea programada. Todas las acciones de corrección se realizan en el Centro de acciones.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones":::

**En este artículo se describe**:

- [Uso del Centro de acción](#how-to-use-the-action-center)
- [Acciones de corrección](#remediation-actions)


## <a name="how-to-use-the-action-center"></a>Uso del Centro de acción

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de contestación manual o las sesiones de respuesta inmediata.

4. Seleccione la pestaña **Historial** para ver una lista de las acciones completadas. 

## <a name="remediation-actions"></a>Acciones de corrección

Microsoft Defender para Empresas incluye varias acciones de corrección. Estas acciones incluyen acciones de contestación manual, acciones después de la investigación automatizada y acciones de respuesta inmediata.

En la tabla siguiente se enumeran las acciones de corrección que están disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de contestación manual](../defender-endpoint/respond-machine-alerts.md)   | - Ejecutar examen de antivirus <br/>- Aislar el dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta inmediata](../defender-endpoint/live-response.md)   | - Recopilación de datos forenses <br/>- Análisis de un archivo <br/>- Ejecutar un script <br/>- Envío de una entidad sospechosa a Microsoft para su análisis <br/>- Corrección de un archivo <br/>- Buscar amenazas de forma proactiva         |

## <a name="next-steps"></a>Pasos siguientes

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)