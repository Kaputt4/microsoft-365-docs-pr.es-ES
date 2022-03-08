---
title: Revisar acciones de corrección en Microsoft Defender para empresas
description: Ver las correcciones que se tomaron automáticamente o que están a la espera de su aprobación en el Centro de acciones
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 5a0fed3ebdb3c7b7275425c24288efab293d6a6d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322959"
---
# <a name="review-remediation-actions-in-the-action-center"></a>Revisar acciones de corrección en el Centro de acciones

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

A medida que se detectan las amenazas, las acciones de corrección se reproducen. Según la amenaza en particular y la configuración de la configuración de seguridad, las acciones de corrección pueden realizarse automáticamente o solo después de su aprobación. Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo a la cuarentena, la detención de la ejecución de un proceso y la eliminación de una tarea programada. Todas las acciones de corrección se realiza un seguimiento en el Centro de acciones.

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acciones":::

**En este artículo se describe lo siguiente**:

- [Cómo usar el Centro de acciones](#how-to-use-the-action-center)

- [Acciones de corrección](#remediation-actions)

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="how-to-use-the-action-center"></a>Cómo usar el Centro de acciones

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la **pestaña** Pendiente para ver y aprobar (o rechazar) cualquier acción pendiente. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de respuesta manual o las sesiones de respuesta en directo.

4. Seleccione la **pestaña** Historial para ver una lista de acciones completadas. 

## <a name="remediation-actions"></a>Acciones de corrección

Microsoft Defender para empresas incluye varias acciones de corrección. Estas acciones incluyen acciones de respuesta manual, acciones tras investigación automatizada y acciones de respuesta en directo.

En la tabla siguiente se enumeran las acciones de corrección disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del Registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de respuesta manuales](../defender-endpoint/respond-machine-alerts.md)   | - Ejecutar examen antivirus <br/>- Aislar dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta en directo](../defender-endpoint/live-response.md)   | - Recopilar datos forenses <br/>- Analizar un archivo <br/>- Ejecutar un script <br/>- Enviar una entidad sospechosa a Microsoft para su análisis <br/>- Corregir un archivo <br/>- Búsqueda proactiva de amenazas         |

## <a name="next-steps"></a>Siguientes pasos

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md)