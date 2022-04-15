---
title: Revisar las acciones de corrección en Microsoft Defender para Empresas
description: Ver las correcciones que se han realizado automáticamente o que están en espera de aprobación en el Centro de acciones
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 15a64491f6e97137d1e919aa126d4bf134c47999
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862222"
---
# <a name="review-remediation-actions-in-the-action-center"></a>Revisión de las acciones de corrección en el Centro de acciones

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

A medida que se detectan amenazas, entran en juego las acciones de corrección. En función de la amenaza en particular y de cómo se configure la configuración de seguridad, es posible que las acciones de corrección se realicen automáticamente o solo tras la aprobación. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y la eliminación de una tarea programada. Todas las acciones de corrección se realizan en el Centro de acciones.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones":::

**En este artículo se describe lo siguiente**:

- [Uso del Centro de acciones](#how-to-use-the-action-center)
- [Acciones de corrección](#remediation-actions)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="how-to-use-the-action-center"></a>Uso del Centro de acciones

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta en directo.

4. Seleccione la pestaña **Historial** para ver una lista de acciones completadas. 

## <a name="remediation-actions"></a>Acciones de corrección

Microsoft Defender para Empresas incluye varias acciones de corrección. Estas acciones incluyen acciones de respuesta manual, acciones después de la investigación automatizada y acciones de respuesta en vivo.

En la tabla siguiente se enumeran las acciones de corrección que están disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de respuesta manual](../defender-endpoint/respond-machine-alerts.md)   | - Ejecución del examen antivirus <br/>- Aislar el dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta en directo](../defender-endpoint/live-response.md)   | - Recopilación de datos forenses <br/>- Análisis de un archivo <br/>- Ejecución de un script <br/>- Envío de una entidad sospechosa a Microsoft para su análisis <br/>- Corrección de un archivo <br/>- Búsqueda proactiva de amenazas         |

## <a name="next-steps"></a>Siguientes pasos

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)