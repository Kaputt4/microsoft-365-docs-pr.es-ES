---
title: Revisar acciones de corrección en Microsoft Defender para empresas (versión preliminar)
description: Ver las correcciones que se tomaron automáticamente o que están a la espera de su aprobación en el Centro de acciones
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 314bb913a161e21ef61c09568cd87aad61ccd10e
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421875"
---
# <a name="review-remediation-actions-in-the-action-center"></a>Revisar acciones de corrección en el Centro de acciones

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

A medida que se detectan las amenazas, las acciones de corrección se reproducen. Según la amenaza en particular y la configuración de la configuración de seguridad, las acciones de corrección pueden realizarse automáticamente o solo después de su aprobación. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y la eliminación de una tarea programada. Todas las acciones de corrección se realiza un seguimiento en el Centro de acciones.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones":::

**En este artículo se describe**:

- [Cómo usar el Centro de acciones](#how-to-use-the-action-center)
- [Acciones de corrección](#remediation-actions)

## <a name="how-to-use-the-action-center"></a>Cómo usar el Centro de acciones

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la **pestaña** Pendiente para ver y aprobar (o rechazar) cualquier acción pendiente. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta en directo.

4. Seleccione la **pestaña** Historial para ver una lista de acciones completadas. 

## <a name="remediation-actions"></a>Acciones de corrección

Microsoft Defender para empresas (versión preliminar) incluye varias acciones de corrección. Estas acciones incluyen acciones de respuesta manual, acciones tras investigación automatizada y acciones de respuesta en directo.

En la tabla siguiente se enumeran las acciones de corrección disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de respuesta manuales](../defender-endpoint/respond-machine-alerts.md)   | - Ejecutar examen antivirus <br/>- Aislar dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta en directo](../defender-endpoint/live-response.md)   | - Recopilar datos forenses <br/>- Analizar un archivo <br/>- Ejecutar un script <br/>- Enviar una entidad sospechosa a Microsoft para su análisis <br/>- Corregir un archivo <br/>- Búsqueda proactiva de amenazas         |

## <a name="next-steps"></a>Siguientes pasos

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-manage-devices.md)