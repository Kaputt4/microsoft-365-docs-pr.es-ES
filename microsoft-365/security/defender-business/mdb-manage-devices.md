---
title: Administración de dispositivos en Microsoft Defender para Empresas
description: Aprenda a administrar dispositivos en Microsoft Defender para Empresas
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
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 453cce2c52902116bc3eaa71f5e6c998ab4164a1
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862838"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Administración de dispositivos en Microsoft Defender para Empresas

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

En Microsoft Defender para Empresas, puede administrar los dispositivos de la siguiente manera:

- [Ver una lista de dispositivos incorporados](#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento
- [Realizar acciones en un dispositivo](#take-action-on-a-device-that-has-threat-detections) que tenga detecciones de amenazas
- [Incorporación de un dispositivo a Defender for Business](#onboard-a-device)  
- [Desconectar un dispositivo de Defender para empresas](#offboard-a-device)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="view-the-list-of-onboarded-devices"></a>Ver la lista de dispositivos incorporados

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Captura de pantalla del inventario de dispositivos":::

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Inventario de dispositivos**.

3. Seleccione un dispositivo para abrir su panel flotante, donde puede obtener más información sobre su estado y tomar medidas. 

   Si aún no aparece ningún dispositivo, [incorpore dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Realizar acciones en un dispositivo que tenga detecciones de amenazas

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Captura de pantalla de un dispositivo seleccionado con detalles y acciones disponibles":::

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Inventario de dispositivos**. 

2. Seleccione un dispositivo para abrir su panel flotante y revise la información que se muestra.

3. Seleccione los puntos suspensivos (**...**) para abrir el menú acciones. 

4. Seleccione una acción, como **Ejecutar examen antivirus** o **Iniciar investigación automatizada**. 

## <a name="onboard-a-device"></a>Incorporación de un dispositivo

Consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).

## <a name="offboard-a-device"></a>Fuera de bordo de un dispositivo

Consulte [Offboarding a device (Offboarding a device](mdb-offboard-devices.md)).

## <a name="next-steps"></a>Siguientes pasos

- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Creación o edición de grupos de dispositivos](mdb-create-edit-device-groups.md)