---
title: Administración de dispositivos en Microsoft Defender para Empresas
description: Obtenga información sobre cómo agregar, quitar y administrar dispositivos en Defender para empresas, endpoint protection para pequeñas y medianas empresas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 09/14/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: 36f3b704c4e28e1237c9b518b1dede6962d2b3dc
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096905"
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

2. En el panel de navegación, vaya a **Dispositivos activos** > .

3. Seleccione un dispositivo para abrir su panel flotante, donde puede obtener más información sobre su estado y tomar medidas. 

   Si aún no aparece ningún dispositivo, [incorpore dispositivos a Defender for Business](mdb-onboard-devices.md).

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Realizar acciones en un dispositivo que tenga detecciones de amenazas

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Captura de pantalla de un dispositivo seleccionado con detalles y acciones disponibles":::

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, vaya a **Dispositivos activos** > . 

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