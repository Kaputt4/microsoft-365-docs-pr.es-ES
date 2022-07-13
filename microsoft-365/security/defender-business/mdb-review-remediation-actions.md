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
ms.openlocfilehash: 63bbeb218693174402264bb59a6c014e63e14bef
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66770985"
---
# <a name="review-remediation-actions-in-the-action-center"></a>Revisión de las acciones de corrección en el Centro de acciones

A medida que se detectan amenazas, entran en juego las acciones de corrección. En función de la amenaza en particular y de cómo se configure la configuración de seguridad, es posible que las acciones de corrección se realicen automáticamente o solo tras la aprobación. Entre los ejemplos de acciones de corrección se incluyen: 
- Envío de un archivo a la cuarentena
- Detener la ejecución de un proceso
- Eliminación de una tarea programada

Se realiza un seguimiento de todas las acciones de corrección en el centro de actividades.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones":::

**En este artículo se describe**:

- [Uso del Centro de acción](#how-to-use-the-action-center)
- [Acciones de corrección](#remediation-actions)


## <a name="how-to-use-the-action-center"></a>Uso del Centro de acciones

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Las acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta en directo.

4. Seleccione la pestaña **Historial** para ver una lista de las acciones completadas.

## <a name="remediation-actions"></a>Acciones de corrección

Defender for Business incluye varias acciones de corrección. Estas acciones incluyen acciones de contestación manual, acciones después de la investigación automatizada y acciones de respuesta inmediata.

En la tabla siguiente se enumeran las acciones de corrección que están disponibles.

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../defender-endpoint/automated-investigations.md)      |<ul><li>Poner en cuarentena un archivo</li><li>Eliminación de una clave del Registro</li><li>Eliminación de un proceso</li><li>Detener un servicio</li><li>Deshabilitar un controlador</li><li>Eliminación de una tarea programada </li></ul> |
| [Acciones de contestación manual](../defender-endpoint/respond-machine-alerts.md)   |<ul><li>Ejecutar examen de antivirus</li><li>Aislar un dispositivo</li><li>Detener y poner en cuarentena un archivo</li><li>Adición de un indicador para bloquear o permitir un archivo</li></ul> |
| [Respuesta inmediata](../defender-endpoint/live-response.md)   |<ul><li>Recopilación de datos forenses</li><li>Análisis de un archivo</li><li>Ejecutar un script</li><li>Envío de una entidad sospechosa a Microsoft para su análisis</li><li>Corrección de un archivo </li><li>Búsqueda proactiva de amenazas</li></ul>|

## <a name="next-steps"></a>Pasos siguientes

- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md)
