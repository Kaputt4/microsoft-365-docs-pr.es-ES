---
title: Respuesta y mitigación de amenazas en Microsoft Defender para Empresas
description: A medida que se detectan amenazas en Defender para empresas, puede realizar acciones para responder a esas amenazas. Vea cómo usar la vista de inventario de dispositivos.
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
ms.openlocfilehash: b7a911991935407f9d512213c9d76c92106b74c8
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089570"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>Respuesta y mitigación de amenazas en Microsoft Defender para Empresas

El portal de Microsoft 365 Defender permite al equipo de seguridad responder y mitigar las amenazas detectadas. Este artículo le guiará a través de un ejemplo de cómo puede usar Defender para empresas.


## <a name="view-detected-threats"></a>Visualización de las amenazas detectadas

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Observe las tarjetas en la página principal. Las tarjetas le indican de un vistazo cuántas amenazas se detectaron, junto con cuántas cuentas de usuario, puntos de conexión (dispositivos) y otros recursos se vieron afectados. La siguiente imagen es un ejemplo de tarjetas que puede ver:

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="Captura de pantalla de las tarjetas en el portal de Microsoft 365 Defender":::

3. Seleccione un botón o vínculo en la tarjeta para ver más información y tomar medidas. Por ejemplo, nuestra tarjeta **Dispositivos en riesgo** incluye un botón **Ver detalles** . Al seleccionar ese botón, se nos lleva a la página **Inventario** de dispositivos, como se muestra en la siguiente imagen:

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Captura de pantalla del inventario de dispositivos":::

   En la página **Inventario de** dispositivos se enumeran los dispositivos de la empresa, junto con su nivel de riesgo y nivel de exposición.

4. Seleccione un elemento, como un dispositivo. Se abre un panel flotante y muestra más información sobre las alertas y los incidentes generados para ese elemento, como se muestra en la siguiente imagen:  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Captura de pantalla del panel flotante de un dispositivo seleccionado":::

5. En el control flotante, vea la información que se muestra. Seleccione los puntos suspensivos (...) para abrir un menú que enumera las acciones disponibles, como se muestra en la siguiente imagen: 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Captura de pantalla de las acciones disponibles para un dispositivo seleccionado":::

6. Seleccione una acción disponible. Por ejemplo, puede elegir **Ejecutar examen antivirus**, lo que hará que Antivirus de Microsoft Defender inicie un examen rápido en el dispositivo. O bien, podría seleccionar **Iniciar investigación automatizada** para desencadenar una investigación automatizada en el dispositivo.

## <a name="next-steps"></a>Pasos siguientes

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
