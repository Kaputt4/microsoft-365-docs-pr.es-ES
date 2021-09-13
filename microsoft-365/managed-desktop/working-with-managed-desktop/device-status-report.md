---
title: Informe de estado del dispositivo
description: Explica el estado del dispositivo
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3e91a329799528eebf9de53b197c7439644b98fb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215197"
---
# <a name="device-status-report"></a>Informe de estado del dispositivo

Este informe agrega el estado de todos los dispositivos registrados para mostrar el uso del servicio Escritorio administrado de Microsoft usuario. Categorizamos los dispositivos en función de su actividad durante los últimos 28 días y de nuestra capacidad para mantener el dispositivo actualizado. Para ser actualizado por Windows Update tan pronto como sea posible, un dispositivo debe conectarse a Internet y no hibernar o pausarse durante un mínimo de seis horas, dos de las cuales deben ser continuas. Aunque es posible que se actualice un dispositivo que no cumpla estos requisitos, los dispositivos que los cumplan tienen la mayor probabilidad de actualizarse.

:::image type="content" source="../../media/mmd-device-status.png" alt-text="Informe que muestra el gráfico de donut del estado de actividad del dispositivo en la parte superior izquierda, ver filtros en la parte superior derecha con un botón para generar el informe y tabla de detalles a lo largo de la parte inferior":::

Informamos del estado del dispositivo con estas etiquetas: 

- **Listo para el usuario:** dispositivos que se han registrado correctamente con nuestro servicio y están listos para ser entregados a un usuario 
- **Activo:** dispositivos que se están utilizando y han cumplido los criterios de actividad (seis horas, dos continuas) para la versión de actualización de seguridad más reciente y han registrado con Microsoft Intune al menos una vez en los últimos cinco días. 
- **Sincronizado:** dispositivos que se usan y que se han registrado con Intune en los últimos 28 días 
- **Sin sincronización:** dispositivos que se usan pero que no se han registrado con Intune en los últimos 28 días 
- **Other**: La categoría agrega varios estados de error que pueden producirse, normalmente durante el registro del dispositivo. Para obtener más información, consulte [Troubleshooting device registration](../get-started/register-devices-self.md#troubleshooting-device-registration).