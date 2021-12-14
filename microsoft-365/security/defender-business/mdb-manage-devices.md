---
title: Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre cómo administrar dispositivos en Microsoft Defender para empresas (versión preliminar)
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
ms.openlocfilehash: 5bb36ecb0ca2d382ce64a6746b1c6bfcfceff22b
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421143"
---
# <a name="manage-devices-in-microsoft-defender-for-business-preview"></a>Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

En Microsoft Defender para empresas (versión preliminar), puedes administrar dispositivos de la siguiente manera:

- [Ver una lista de dispositivos incorporados](#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento
- [Realizar acciones en un dispositivo que](#take-action-on-a-device-that-has-threat-detections) tenga detecciones de amenazas
- [Incorporación de un dispositivo a Defender para empresas (versión preliminar)](#onboard-a-device)  
- [Offboard a device from Defender for Business (preview)](#offboard-a-device)

## <a name="view-the-list-of-onboarded-devices"></a>Ver la lista de dispositivos incorporados

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Captura de pantalla del inventario de dispositivos":::

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. En el panel de navegación, elija **Inventario de dispositivos**.

3. Selecciona un dispositivo para abrir su panel desplegable, donde puedes obtener más información sobre su estado y tomar medidas. 

   Si aún no tienes ningún dispositivo en la lista, incorpora dispositivos [a Microsoft Defender para empresas (versión preliminar)](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Realizar acciones en un dispositivo que tenga detecciones de amenazas

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Captura de pantalla de un dispositivo seleccionado con detalles y acciones disponibles":::

1. En el portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ), en el panel de navegación, elija Inventario de **dispositivos**. 

2. Selecciona un dispositivo para abrir el panel desplegable y revisa la información que se muestra.

3. Seleccione los puntos suspensivos (**...**) para abrir el menú de acciones. 

4. Seleccione una acción, como Ejecutar examen **antivirus** o **Iniciar investigación automatizada.** 

## <a name="onboard-a-device"></a>Incorporación de un dispositivo

Consulta [Incorporación de dispositivos a Microsoft Defender para empresas (versión preliminar).](mdb-onboard-devices.md)

## <a name="offboard-a-device"></a>Fuera de un dispositivo

Consulta [Offboard a device](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device).

## <a name="next-steps"></a>Siguientes pasos

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Crear o editar grupos de dispositivos](mdb-create-edit-device-groups.md)
