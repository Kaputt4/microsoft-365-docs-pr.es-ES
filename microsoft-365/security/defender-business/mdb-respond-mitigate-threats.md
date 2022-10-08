---
title: Respuesta y mitigación de amenazas en Microsoft Defender para Empresas
description: A medida que se detectan amenazas en Defender para empresas, puede realizar acciones para responder a esas amenazas. Vea cómo usar la vista de inventario de dispositivos.
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
ms.openlocfilehash: 1ba8e1897e82feed3c3b7e7d585ad60534e2be31
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097388"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>Respuesta y mitigación de amenazas en Microsoft Defender para Empresas

El portal de Microsoft 365 Defender permite al equipo de seguridad responder y mitigar las amenazas detectadas. Este artículo le guiará a través de un ejemplo de cómo puede usar Defender para empresas.


## <a name="view-detected-threats"></a>Visualización de las amenazas detectadas

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Observe las tarjetas en la página principal. Las tarjetas le indican de un vistazo cuántas amenazas se detectaron, junto con cuántas cuentas de usuario, puntos de conexión (dispositivos) y otros recursos se vieron afectados. La siguiente imagen es un ejemplo de tarjetas que puede ver:

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="Captura de pantalla de las tarjetas en el portal de Microsoft 365 Defender":::

3. Seleccione un botón o vínculo en la tarjeta para ver más información y tomar medidas. Por ejemplo, nuestra tarjeta **Dispositivos en riesgo** incluye un botón **Ver detalles** . Al seleccionar ese botón, se nos lleva a la lista **Dispositivos** , como se muestra en la siguiente imagen:

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Pantalla del inventario de dispositivos":::

   En la página **Dispositivos** se enumeran los dispositivos de la empresa, junto con su nivel de riesgo y nivel de exposición.

4. Seleccione un elemento, como un dispositivo. Se abre un panel flotante y muestra más información sobre las alertas e incidentes generados para ese elemento, como se muestra en la siguiente imagen:  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Pantalla del panel flotante de un dispositivo seleccionado":::

5. En el control flotante, vea la información que se muestra. Seleccione los puntos suspensivos (...) para abrir un menú que muestra las acciones disponibles, como se muestra en la siguiente imagen: 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Pantalla de acciones disponibles para un dispositivo seleccionado":::

6. Seleccione una acción disponible. Por ejemplo, puede elegir **Ejecutar examen antivirus**, lo que hará que Antivirus de Microsoft Defender inicie un examen rápido en el dispositivo. O bien, puede seleccionar **Iniciar investigación automatizada** para desencadenar una investigación automatizada en el dispositivo.

## <a name="next-steps"></a>Pasos siguientes

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Administración de dispositivos en Defender para empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
