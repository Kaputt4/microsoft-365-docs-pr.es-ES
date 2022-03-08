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
ms.openlocfilehash: be685d39bbda3b96f689c13a3bc3485c011f1ec8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319885"
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
| Activa | Dispositivos que se usan. <ul><li>Han cumplido los criterios de actividad (seis horas, dos continuas) para la versión de actualización de seguridad más reciente.</li> <li>Se han registrado con Microsoft Intune al menos una vez en los últimos cinco días.</li></ul> |
| Sincronizado | Dispositivos que se usan y se han registrado con Intune en los últimos 28 días.
| Sin sincronización | Dispositivos que se usan pero que no se han registrado con Intune en los últimos 28 días. |
| Otro | La etiqueta agrega varios estados de error que pueden producirse, normalmente durante el registro del dispositivo. Para obtener más información, consulte [Troubleshooting device registration](../get-started/manual-registration.md#troubleshooting-device-registration). |
