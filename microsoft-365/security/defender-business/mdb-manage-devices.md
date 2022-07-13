---
title: Administración de dispositivos en Microsoft Defender para Empresas
description: Obtenga información sobre cómo agregar, quitar y administrar dispositivos en Defender para empresas, endpoint protection para pequeñas y medianas empresas.
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
ms.openlocfilehash: 735f9e04a9176ce1b6626a050429c0b7323a7c0b
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2022
ms.locfileid: "66772935"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Administración de dispositivos en Microsoft Defender para Empresas

En Defender para empresas, puede administrar los dispositivos de la siguiente manera:

- [Ver una lista de dispositivos incorporados](#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento
- [Realizar acciones en un dispositivo](#take-action-on-a-device-that-has-threat-detections) que tenga detecciones de amenazas
- [Incorporación de un dispositivo a Defender for Business](#onboard-a-device)  
- [Desconectar un dispositivo de Defender para empresas](#offboard-a-device)


## <a name="view-the-list-of-onboarded-devices"></a>Ver la lista de dispositivos incorporados

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Pantalla del inventario de dispositivos":::

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Inventario de dispositivos**.

3. Seleccione un dispositivo para abrir su panel flotante, donde puede obtener más información sobre su estado y tomar medidas. 

   Si aún no aparece ningún dispositivo, [incorpore dispositivos a Defender for Business](mdb-onboard-devices.md).

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Realizar acciones en un dispositivo que tenga detecciones de amenazas

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Captura de pantalla de un dispositivo seleccionado con detalles y acciones disponibles":::

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Inventario de dispositivos**. 

2. Seleccione un dispositivo para abrir su panel flotante y revise la información que se muestra.

3. Seleccione los puntos suspensivos (**...**) para abrir el menú acciones. 

4. Seleccione una acción, como **Ejecutar escaneo antivirus** o **Iniciar Investigación automatizada**. 

## <a name="onboard-a-device"></a>Incorporación de un dispositivo

Consulte [Incorporación de dispositivos a Defender for Business](mdb-onboard-devices.md).

## <a name="offboard-a-device"></a>Retirar un dispositivo

Consulte [Offboarding a device (Offboarding a device](mdb-offboard-devices.md)).

## <a name="next-steps"></a>Pasos siguientes

- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Creación o edición de grupos de dispositivos](mdb-create-edit-device-groups.md)