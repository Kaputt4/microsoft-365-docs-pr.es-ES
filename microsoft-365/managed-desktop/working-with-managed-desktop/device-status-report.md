---
title: Informe de estado del dispositivo
description: Explica el estado del dispositivo
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 14c83d007d2506e0e85c156f4d738f78f91fad75
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321032"
---
# <a name="device-status-report"></a>Informe de estado del dispositivo

Este informe agrega el estado de todos los dispositivos registrados para mostrar el uso del servicio de Escritorio administrado de Microsoft.

Categorizamos los dispositivos en función de su actividad durante los últimos 28 días y de nuestra capacidad para mantener el dispositivo actualizado.

Para ser actualizado por Windows tan pronto como sea posible, un dispositivo debe:

- Conectarse a Internet.
- No hibernar.
- No se ha pausado durante un mínimo de seis horas, dos de las cuales deben ser continuas.

Aunque es posible que se actualice un dispositivo que no cumpla estos requisitos. Los dispositivos que los cumplen tienen la mayor probabilidad de actualizarse.

:::image type="content" source="../../media/mmd-device-status.png" alt-text="Informe que muestra el gráfico de donut del estado de actividad del dispositivo en la parte superior izquierda, ver filtros en la parte superior derecha con un botón para generar el informe y tabla de detalles a lo largo de la parte inferior":::

## <a name="device-status-labels"></a>Etiquetas de estado del dispositivo

Informamos del estado del dispositivo con las siguientes etiquetas:

| Etiqueta de estado del dispositivo | Descripción |
| ------ | ------ |
| Listo para el usuario | Dispositivos que se han registrado correctamente con nuestro servicio y listos para ser entregados a un usuario.|
| Activo | Dispositivos que se usan. <ul><li>Han cumplido los criterios de actividad (seis horas, dos continuas) para la versión de actualización de seguridad más reciente.</li> <li>Se han registrado con Microsoft Intune al menos una vez en los últimos cinco días.</li></ul> |
| Sincronizado | Dispositivos que se usan y se han registrado con Intune en los últimos 28 días.
| Sin sincronización | Dispositivos que se usan pero que no se han registrado con Intune en los últimos 28 días. |
| Otro | La etiqueta agrega varios estados de error que pueden producirse, normalmente durante el registro del dispositivo. Para obtener más información, consulte [Troubleshooting device registration](../get-started/register-devices-self.md#troubleshooting-device-registration). |
