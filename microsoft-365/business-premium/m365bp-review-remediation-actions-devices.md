---
title: Revisar las acciones de corrección en Microsoft 365 Empresa Premium
description: Consulte cómo ver las correcciones que se realizaron automáticamente o que están a la espera de aprobación en el Centro de actividades.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 2c86ff14326315596318e5fce11c7c26c5c22f85
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630861"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>Revisar las acciones de corrección en Microsoft 365 Empresa Premium

Bien, ha descubierto una vulneración de seguridad, pero ¿qué hacer? Depende de la naturaleza de ella.

Entre los ejemplos de acciones de corrección se incluyen el envío de un archivo en cuarentena, la detención de la ejecución de un proceso o la eliminación completa de una tarea programada. Se realiza un seguimiento de todas las acciones de corrección en el Centro de acción que se encuentra en [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center).

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="Captura de pantalla del Centro de acción en M365.":::

**En este artículo se describe**:

- [Cómo utilizar el Centro de actividades](#how-to-use-your-action-center).
- [ Tipos de acciones correctivas](#types-of-remediation-actions).


## <a name="how-to-use-your-action-center"></a>Cómo usar el Centro de acción

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Centro de actividades**.

3. Seleccione la pestaña **Pendiente** para ver y aprobar (o rechazar) las acciones pendientes. Estas acciones pueden surgir de la protección antivirus/antimalware, las investigaciones automatizadas, las actividades de contestación manual o las sesiones de respuesta inmediata.

4. Seleccione la pestaña **Historial** para ver una lista de las acciones completadas.

## <a name="types-of-remediation-actions"></a>Tipos de acciones de corrección

La suscripción incluye varios tipos diferentes de acciones de corrección para las amenazas detectadas. Estas acciones incluyen acciones de contestación manual, acciones después de la investigación automatizada y acciones de respuesta inmediata.

En la tabla siguiente se enumeran las acciones de corrección que están disponibles:

| Origen  | Acciones  |
|---------|---------|
| [Investigaciones automatizadas](../security/defender-endpoint/automated-investigations.md)      | - Poner en cuarentena un archivo <br/>- Quitar una clave del registro <br/>- Eliminación de un proceso <br/>- Detener un servicio <br/>- Deshabilitar un controlador <br/>- Quitar una tarea programada        |
| [Acciones de contestación manual](../security/defender-endpoint/respond-machine-alerts.md)   | - Ejecutar examen de antivirus <br/>- Aislar el dispositivo <br/>- Detener y poner en cuarentena <br/>- Agregar un indicador para bloquear o permitir un archivo       |
| [Respuesta inmediata](../security/defender-endpoint/live-response.md)   | - Recopilación de datos forenses <br/>- Análisis de un archivo <br/>- Ejecutar un script <br/>- Envío de una entidad sospechosa a Microsoft para su análisis <br/>- Corrección de un archivo <br/>- Buscar amenazas de forma proactiva         |
