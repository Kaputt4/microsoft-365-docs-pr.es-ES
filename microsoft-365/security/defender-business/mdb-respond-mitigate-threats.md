---
title: Respuesta y mitigación de amenazas en Microsoft Defender para Empresas
description: A medida que se detectan amenazas, puede realizar acciones para responder a esas amenazas y mitigarlas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/14/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: b6d85d5032b9eb5837482649d4164e68b7c08275
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098788"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>Respuesta y mitigación de amenazas en Microsoft Defender para Empresas

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

El portal de Microsoft 365 Defender permite al equipo de seguridad responder y mitigar las amenazas detectadas. Este artículo le guiará a través de un ejemplo de cómo puede usar Defender para empresas.

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

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

## <a name="next-steps"></a>Siguientes pasos

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
