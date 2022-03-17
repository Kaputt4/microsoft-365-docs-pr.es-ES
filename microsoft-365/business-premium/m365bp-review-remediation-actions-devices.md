---
title: Revisar acciones de corrección en Microsoft 365 Empresa Premium
description: Vea cómo ver las correcciones que se tomaron automáticamente o que están a la espera de su aprobación en el Centro de acciones
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 160cef2ec7691fbc9debad809b20461a0d3efe23
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526641"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>Revisar acciones de corrección en Microsoft 365 Empresa Premium

A medida que se detectan las amenazas, las acciones de corrección se reproducen. Según la amenaza en particular y la configuración de la configuración de seguridad, las acciones de corrección pueden realizarse automáticamente o solo después de su aprobación. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y la eliminación de una tarea programada. Todas las acciones de corrección se realiza un seguimiento en el Centro de acciones, que se encuentra en [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center).

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones en M365.":::

**En este artículo se describe lo siguiente**:

- [Cómo usar el Centro de acciones](#how-to-use-your-action-center)

- [Tipos de acciones de corrección](#types-of-remediation-actions)


## <a name="how-to-use-your-action-center"></a>Cómo usar el Centro de acciones

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la **pestaña** Pendiente para ver y aprobar (o rechazar) cualquier acción pendiente. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta en directo.

4. Seleccione la **pestaña** Historial para ver una lista de acciones completadas. 

## <a name="types-of-remediation-actions"></a>Tipos de acciones de corrección

La suscripción incluye varios tipos diferentes de acciones de corrección para las amenazas detectadas. Estas acciones incluyen acciones de respuesta manual, acciones tras investigación automatizada y acciones de respuesta en directo.

En la tabla siguiente se enumeran las acciones de corrección disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../security/defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de respuesta manuales](../security/defender-endpoint/respond-machine-alerts.md)   | - Ejecutar examen antivirus <br/>- Aislar dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta en directo](../security/defender-endpoint/live-response.md)   | - Recopilar datos forenses <br/>- Analizar un archivo <br/>- Ejecutar un script <br/>- Enviar una entidad sospechosa a Microsoft para su análisis <br/>- Corregir un archivo <br/>- Búsqueda proactiva de amenazas         |
